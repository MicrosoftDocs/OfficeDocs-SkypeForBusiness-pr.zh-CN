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
description: 摘要：了解如何在本地部署和 Skype for Business Online 之间配置互操作性。
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569214"
---
# <a name="configure-skype-for-business-hybrid"></a>配置 Skype for Business 混合环境

若要配置 Skype for Business 混合，需要执行以下操作：

- [将本地边缘服务配置为与 Microsoft 365 或 Office 365 联盟](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)。
- [将本地环境配置为信任 Microsoft 365 或 Office 365，并启用共享 SIP 地址空间](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)。
- [在 Microsoft 365 或 Office 365 组织中启用共享 SIP 地址空间](#enable-shared-sip-address-space-in-your-organization)。

请注意，如果你有 Exchange 本地部署，你可能想要在本地 Exchange 和 Skype for Business Online 环境之间配置 OAuth。 有关详细信息，请参阅在[Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)中管理服务器到服务器身份验证，并[计划集成 Skype for Business 和 Exchange。](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>将本地边缘服务配置为与 Microsoft 365 或 Office 365 联盟

联盟允许本地部署中的用户与组织中 Microsoft 365 或 Office 365 用户进行通信。 若要配置联盟，请运行 Skype for Business Server 命令行管理程序 中的以下 cmdlet：
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

如果"-EnablePartnerDiscovery"值设置为 $True，Skype for Business Server 将使用 DNS 记录来尝试和发现 AllowedDomains 列表中未列出的合作伙伴域。 如果将该值设置为 $False，Skype for Business Server 将仅与 AllowedDomains 列表中的域联盟。 如果使用 DNS 服务路由，则需要此参数。

> [!NOTE]
> 有关在本地 Skype for Business 部署的用户与 Skype for Business Online 组织的用户之间启用联盟的更多详细信息，请参阅在 Skype for Business Server 中为 [Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)客户配置联盟支持。


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>配置本地环境以使用 Microsoft 365 或 Office 365 启用共享 SIP 地址空间

还必须将本地环境配置为信任 Microsoft 365 或 Office 365，并启用共享 SIP 地址空间。 这意味着 Microsoft 365 或 Office 365 可能会托管与本地环境相同的 SIP 域集的用户帐户，并且可以在本地和联机托管的用户之间路由消息。  为此，可以使用 ProxyFqdn=sipfed.online.lync.com 配置宿主提供商，如下所述。

首先，检查您是否已有具有 ProxyFqdn=sipfed.online.lync.com 的宿主提供商。 如果存在，则使用以下命令将其删除：

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

然后，创建新的宿主提供商，New-CsHostingProvider cmdlet，如下所示： 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>在组织中启用共享 SIP 地址空间
  
除了在本地部署中做出更改之外，还需要在 Microsoft 365 或 Office 365 组织中进行相应的更改，以在本地部署中启用共享 SIP 地址空间。  

若要在组织中启用共享 SIP 地址空间，请与 Skype for Business Online 建立远程 PowerShell 会话，然后运行以下 cmdlet：
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性需要保持"True"，直到移动到联机是最终的，并且没有用户保留本地。 
  
若要与 Teams 或 Skype for Business Online 建立远程 PowerShell 会话，首先需要安装 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
  
安装模块后，可以使用以下 cmdlet 建立远程会话：
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

若要详细了解如何与 Skype for Business Online 建立远程 PowerShell 会话，以及如何使用 Skype for Business Online 连接器模块，请参阅"为计算机设置[Windows PowerShell。](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
  


## <a name="see-also"></a>另请参阅

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
