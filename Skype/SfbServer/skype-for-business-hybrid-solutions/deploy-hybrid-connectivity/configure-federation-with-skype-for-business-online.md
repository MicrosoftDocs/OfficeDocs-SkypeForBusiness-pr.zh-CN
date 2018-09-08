---
title: 配置与 Skype for Business Online 联盟
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 摘要： 了解如何为业务 Online 配置内部部署和 Skype 之间的互操作性。
ms.openlocfilehash: 7367a1fa7bf7eb305a8b72582e488cfd6ba6fa1c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884118"
---
# <a name="configure-federation-with-skype-for-business-online"></a>配置与 Skype for Business Online 联盟
 
**摘要：** 了解如何为业务 Online 配置内部部署和 Skype 之间的互操作性。
  
按照本节业务 online 配置内部部署和 Skype 之间的互操作性中的步骤。
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>为业务 Online 与 Skype 配置联合身份验证您的本地边缘服务

联合身份验证允许在本地部署与 Office 365 组织中的用户进行通信中的用户。 若要配置联合身份验证，请为业务 Server 命令行管理程序 Skype 中运行以下 cmdlet:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>配置业务 Online 租户中为共享的 SIP 地址空间您 Skype

会话初始协议 (SIP) 地址是网络上每个用户的唯一标识符，类似于电话号码或电子邮件地址。 您尝试移动用户从内部部署到 Skype 业务 online 之前，您需要配置 Office 365 租户共享您的本地部署的共享会话初始协议 (SIP) 地址空间。 如果未进行此配置，您可能会看到以下错误消息：
  
Move-csuser: HostedMigration 容错： Error=(510)，说明 = （此用户的租户不启用了共享的 sip 地址空间。）
  
若要配置共享的 SIP 地址空间，业务 online 建立与 Skype 的远程 PowerShell 会话，然后运行以下 cmdlet:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 属性需要保持为“True”，直到完成迁移到联机，且本地已没有用户。 
  
要建立与 Skype 的远程 PowerShell 会话业务 online，首先需要安装用于 Windows PowerShell，您可以在此处获取业务 Online 连接器模块的 Skype: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。
  
安装该模块后，您可以使用下列 cmdlet 建立远程会话：
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

有关使用 PowerShell 和 Skype 业务 online 的详细信息，请参阅[Windows PowerShell 将计算机设置](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。

  
## <a name="see-also"></a>另请参阅

[新 CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)