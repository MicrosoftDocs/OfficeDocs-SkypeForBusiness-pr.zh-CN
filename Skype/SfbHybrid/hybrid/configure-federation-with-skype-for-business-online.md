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
description: 摘要：了解如何配置本地部署和本地部署之间的Teams。
ms.openlocfilehash: a0e33c781e307785456698b20738dec2db02b8b4
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510553"
---
# <a name="configure-skype-for-business-hybrid"></a>配置 Skype for Business 混合环境

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

若要配置 Skype for Business 混合，需要执行以下操作：

- [将本地边缘服务配置为与](#configure-your-on-premises-edge-service-to-federate-with-teams)Teams 联合。
- [将本地环境配置为信任Teams并启用共享 SIP 地址空间](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)。
- [在组织中启用共享 SIP 地址Teams空间](#enable-shared-sip-address-space-in-your-organization)。

如果你有本地Exchange，你可能想要在本地和联机环境Exchange OAuth Skype for Business OAuth。 有关详细信息，请参阅在 Skype for Business Server 中管理服务器到服务器身份验证[Skype for Business Exchange。](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) [](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>配置内部部署边缘服务以与 Teams

联合身份验证允许本地部署中的用户与Teams Skype for Business Online 用户进行通信。 若要配置联盟，请运行命令行管理程序Skype for Business Server cmdlet：
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

如果"-EnablePartnerDiscovery"值设置为 $True，Skype for Business Server 将使用 DNS 记录尝试和发现 AllowedDomains 列表中未列出的合作伙伴域。 如果该值设置为 $False ，Skype for Business Server将仅与 AllowedDomains 列表中的域联盟。 如果使用 DNS 服务路由，则需要此参数。

> [!NOTE]
> 有关在内部部署 Skype for Business 部署的用户和 Microsoft 365 组织的用户之间启用联盟的更多详细信息，请参阅在 Skype for Business Server 中为 Microsoft 365 客户配置[联合Skype for Business Server。](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>配置本地环境以启用与用户共享的 SIP 地址Teams

还必须将本地环境配置为信任Teams并启用共享 SIP 地址空间。 此配置Teams可以托管与本地环境相同的 SIP 域集的用户帐户，并且可以在本地和联机托管的用户之间路由消息。 使用 ProxyFqdn=sipfed.online.lync.com 配置宿主提供商，如下所述。

首先，检查您是否已有具有 ProxyFqdn=sipfed.online.lync.com 的宿主提供商。 如果存在，则使用命令行管理程序中的以下命令将其删除Skype for Business Server命令行管理程序：

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

然后，使用 cmdlet 创建新的托管New-CsHostingProvider，如下所示： 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>在组织中启用共享 SIP 地址空间
  
除了在内部部署中做出更改之外，还需要在 Teams 组织中进行相应的更改，以启用本地部署的共享 SIP 地址空间。  

若要在组织中启用共享 SIP 地址空间，请与 Teams 建立远程 PowerShell 会话，然后运行以下 cmdlet：
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性需要保持"True"，直到最终移动到联机，并且没有用户保持本地。 
  
若要与 Teams (或 Skype for Business Online) 建立远程 PowerShell 会话，首先需要安装 Teams [PowerShell 模块](/microsoftteams/teams-powershell-install)。 The Teams PowerShell module replaces the Skype for Busines Online Connector module， which has been retired.
  
安装模块后，可以使用以下 cmdlet 建立远程会话：
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

若要详细了解如何使用 Teams 建立远程 PowerShell 会话，以及如何使用 Teams PowerShell 模块，请参阅为 Windows PowerShell 设置[计算机](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  


## <a name="see-also"></a>另请参阅

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
