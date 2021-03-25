---
title: 配置 Skype for Business 混合
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：了解如何配置本地部署和 Skype for Business Online 之间的互操作性。
ms.openlocfilehash: e2af514ef1a10d652abae7bdd39a923dc52e1c4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118941"
---
# <a name="configure-skype-for-business-hybrid"></a>配置 Skype for Business 混合环境

若要配置 Skype for Business 混合，需要执行以下操作：

- [将本地边缘服务配置为与 Microsoft 365 或 Office 365 联合](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)。
- [将本地环境配置为信任 Microsoft 365 或 Office 365 并启用共享 SIP 地址空间](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)。
- [在 Microsoft 365 或 Office 365 组织中启用共享 SIP](#enable-shared-sip-address-space-in-your-organization)地址空间。

请注意，如果你有本地 Exchange，你可能想要在本地 Exchange 和 Skype for Business Online 环境之间配置 OAuth。 有关详细信息，请参阅在[Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)中管理服务器到服务器身份验证和[计划集成 Skype for Business 和 Exchange。](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>配置本地边缘服务以与 Microsoft 365 或 Office 365 联盟

联合身份验证允许本地部署中的用户与贵组织的 Microsoft 365 或 Office 365 用户进行通信。 若要配置联盟，请运行 Skype for Business Server 命令行管理程序中的以下 cmdlet：
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

如果"-EnablePartnerDiscovery"值设置为 $True，Skype for Business Server 将使用 DNS 记录来尝试和发现未列在 AllowedDomains 列表中的合作伙伴域。 如果该值设置为 $False ，Skype for Business Server 将仅与 AllowedDomains 列表中的域联盟。 如果使用 DNS 服务路由，则需要此参数。

> [!NOTE]
> 有关在本地 Skype for Business 部署的用户和 Skype for Business Online 组织的用户之间启用联盟的更多详细信息，请参阅在 Skype for Business Server 中为 [Skype for Business Online](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)客户配置联盟支持。


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>配置本地环境以启用 Microsoft 365 或 Office 365 的共享 SIP 地址空间

还必须将本地环境配置为信任 Microsoft 365 或 Office 365 并启用共享 SIP 地址空间。 这意味着 Microsoft 365 或 Office 365 可能会托管与本地环境相同的 SIP 域集的用户帐户，并且可以在本地和联机托管的用户之间路由消息。  为此，您可以使用 ProxyFqdn=sipfed.online.lync.com 配置宿主提供商，如下所述。

首先，检查您是否已有具有 ProxyFqdn=sipfed.online.lync.com 的宿主提供商。 如果存在，则使用下列命令将其删除：

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

然后，创建新的宿主提供商，New-CsHostingProvider cmdlet，如下所示： 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>在组织中启用共享 SIP 地址空间
  
除了在本地部署中做出更改之外，还需要在 Microsoft 365 或 Office 365 组织中进行相应的更改，以启用本地部署的共享 SIP 地址空间。  

若要在组织中启用共享 SIP 地址空间，请与 Skype for Business Online 建立远程 PowerShell 会话，然后运行以下 cmdlet：
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性需要保持"True"，直到最终移动到联机，并且没有用户保持本地。 
  
若要与 Teams 或 Skype for Business Online 建立远程 PowerShell 会话，首先需要安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
  
安装模块后，可以使用以下 cmdlet 建立远程会话：
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

若要详细了解如何与 Skype for Business Online 建立远程 PowerShell 会话，以及如何使用 Skype for Business Online 连接器模块，请参阅为计算机设置[Windows PowerShell。](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  


## <a name="see-also"></a>另请参阅

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)