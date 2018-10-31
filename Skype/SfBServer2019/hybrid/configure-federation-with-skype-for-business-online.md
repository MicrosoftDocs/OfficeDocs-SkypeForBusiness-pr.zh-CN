---
title: Skype 混合配置的业务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 摘要： 了解如何为业务 Online 配置内部部署和 Skype 之间的互操作性。
ms.openlocfilehash: db03636d412caa72a3b7a38d0c1d691c83d96a5b
ms.sourcegitcommit: a54864c3fcd1b8d240d0f7f2ccf68f8cba566e47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2018
ms.locfileid: "25849346"
---
# <a name="configure-skype-for-business-hybrid"></a>Skype 混合配置的业务

若要配置业务混合 Skype，您需要：

- [配置内部部署环境与 Office 365 联盟。](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [配置为信任 Office 365 的本地环境并启用共享的 SIP 地址空间，与 Office 365。](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [启用 Office 365 租户中的共享的 SIP 地址空间。](#configure-server-to-server-authentication-if-required)

> [!NOTE]
> 如果您有 Exchange 内部部署，您可能希望为业务 Online 环境 Exchange 内部部署和 Skype 之间配置 OAuth。 有关详细信息，请参阅[Skype 业务服务器中的管理服务器到服务器身份验证](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)和[计划集成业务和 Exchange Skype](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)。 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>配置内部部署边缘服务与 Office 365 联盟

联合身份验证允许在本地部署与 Office 365 组织中的用户进行通信中的用户。 若要配置联合身份验证，请为业务 Server 命令行管理程序 Skype 中运行以下 cmdlet:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>配置内部部署环境以便与 Office 365 的共享的 SIP 地址空间

您还必须配置为信任 Office 365 的本地环境，并启用共享的 SIP 地址空间，与 Office 365。 这意味着 Office 365 可能会承载作为您的本地环境，一组相同的 SIP 域的用户帐户和消息可以是承载在本地用户之间的路由和联机。  通过使用 ProxyFqdn=sipfed.online.lync.com 如下所述配置宿主提供程序执行此操作。

首先，检查您是否已具有 ProxyFqdn=sipfed.online.lync.com 的宿主提供程序。 如果存在，然后将其删除通过使用以下命令：

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

然后创建一个新的宿主提供程序，使用 New-cshostingprovider cmdlet，如下所示： 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>启用 Office 365 租户中的共享的 SIP 地址空间
  
除了在本地部署中所做的更改，您将需要对已启用共享的 SIP 地址空间的本地部署 Office 365 租户中进行相应的更改。  

若要启用 Office 365 租户中的共享的 SIP 地址空间，业务 online 建立与 Skype 的远程 PowerShell 会话，然后运行以下 cmdlet:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性需要保持为“True”，直到完成迁移到联机，且本地已没有用户。 
  
要建立与团队或 Skype 的远程 PowerShell 会话业务 online，首先需要安装用于 Windows PowerShell，可以获取业务 Online 连接器模块的 Skype[此处](https://go.microsoft.com/fwlink/p/?LinkId=391911)。
  
安装该模块后，您可以使用下列 cmdlet 建立远程会话：
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

有关如何建立与 Skype 的远程 PowerShell 会话的业务联机状态，以及如何使用业务 Online Connector 模块 Skype 的详细信息，请参阅[Windows PowerShell 将计算机设置](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  


## <a name="see-also"></a>另请参阅

[新 CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

