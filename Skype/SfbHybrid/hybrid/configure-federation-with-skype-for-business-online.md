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
description: 摘要：了解如何在本地部署和 Skype for business Online 之间配置互操作性。
ms.openlocfilehash: ccf140b62cdbad11605c99fe1cb0cc66aa1ee4dd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780101"
---
# <a name="configure-skype-for-business-hybrid"></a>配置 Skype for Business 混合

若要配置 Skype for Business 混合，需要执行以下操作：

- [将本地边缘服务配置为与 Office 365 或其他组织联合](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization)。
- [将本地环境配置为信任 office 365 并启用 office 365 的共享 SIP 地址空间](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365)。
- [在 Office 365 组织中启用共享 SIP 地址空间](#enable-shared-sip-address-space-in-your-office-365-organization)。

请注意，如果您有本地 Exchange，则可能需要在 Exchange 内部部署和 Skype for business Online 环境之间配置 OAuth。 有关详细信息，请参阅[在 skype For Business server 中管理服务器到服务器身份验证](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)和[计划集成 Skype For business 和 Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)。 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a>将本地边缘服务配置为与 Office 365 或其他组织联合

联合身份验证允许本地部署中的用户与组织中的 Microsoft 365 或 Office 365 用户进行通信。 若要配置联合，请在 Skype for Business Server 命令行管理程序中运行以下 cmdlet：
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

如果 "-EnablePartnerDiscovery" 值设置为 $True，则 Skype for Business Server 将使用 DNS 记录尝试并发现未在 AllowedDomains 列表中列出的合作伙伴域。 如果将此值设置为 $False，Skype for Business Server 将仅与在 AllowedDomains 列表中找到的域联盟。 如果使用 DNS 服务路由，则需要此参数。

> [!NOTE]
> 有关在本地 Skype for Business 部署的用户和 Skype for business Online 组织的用户之间启用联盟的详细信息，请参阅[在 skype for Business Server 中为 skype for Business online 客户配置联合支持](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)。


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>将本地环境配置为启用与 Office 365 的共享 SIP 地址空间

还必须配置本地环境，以信任 Office 365，并为 Office 365 启用共享 SIP 地址空间。 这意味着 Office 365 可能会将与您的本地环境相同的一组 SIP 域的用户帐户托管在一起，并且可以在本地托管的用户和联机的用户之间路由邮件。  为此，请配置具有 ProxyFqdn = sipfed.online.lync.com> 的托管提供程序，如下所述。

首先，检查是否已有具有 ProxyFqdn = sipfed.online.lync.com> 的托管提供程序。 如果有，则使用以下命令将其删除：

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

然后，创建新的承载提供程序，使用 CsHostingProvider cmdlet，如下所示： 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-organization"></a>在 Office 365 组织中启用共享 SIP 地址空间
  
除了您在本地部署中所做的更改之外，您还需要在 Office 365 组织中进行相应的更改，以便在本地部署中启用共享 SIP 地址空间。  

若要在 Office 365 组织中启用共享 SIP 地址空间，请建立与 Skype for Business Online 的远程 PowerShell 会话，然后运行以下 cmdlet：
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性必须保持为 "True"，直到将联机状态移动到联机状态，并且没有用户保留在本地。 
  
若要与团队或 Skype for business Online 建立远程 PowerShell 会话，首先需要安装可在[此处](https://go.microsoft.com/fwlink/p/?LinkId=391911)获取的适用于 Windows PowerShell 的 Skype For business Online 连接器模块。
  
安装该模块后，可以使用以下 cmdlet 建立远程会话：
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

有关如何建立与 Skype for business Online 的远程 PowerShell 会话以及如何使用 Skype for Business Online 连接器模块的详细信息，请参阅[设置 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  


## <a name="see-also"></a>另请参阅

[新 CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
