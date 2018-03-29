---
title: 配置 Outlook Web App 业务服务器 2015年的内部部署 Skype 之间的集成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 摘要： 集成业务服务器和 Outlook Web App Skype。
ms.openlocfilehash: 4ac4d6a71f8006e813d09631f8ccf28742940ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-2015-and-outlook-web-app"></a>配置 Outlook Web App 业务服务器 2015年的内部部署 Skype 之间的集成
 
**摘要：**集成业务服务器和 Outlook Web App，Skype。
  
使用内部部署 Skype 业务服务器 2015年部署的客户可以与 Microsoft Outlook Web App 在 Microsoft Exchange Online 配置互操作性，混合部署模式。 互操作性功能包括单一登录和即时消息 (IM) 以及与 Outlook Web App 接口的状态集成。 若要启用此集成，必须配置边缘服务器在您的内部部署 Skype 业务服务器部署通过完成以下任务： 
  
- 配置共享的 SIP 地址空间
    
- 在边缘服务器上配置宿主提供程序
    
- 验证已更新的中央管理存储的复制
    
## <a name="configure-a-shared-sip-address-space"></a>配置共享的 SIP 地址空间

对于使用 Exchange Online 的业务服务器 2015年集成内部 Skype，您必须配置一个共享的 SIP 地址空间。 通过 Skype 业务服务器和 Exchange 联机服务支持 SIP 域的同一个地址空间。
  
使用 Skype 业务服务器管理外壳，通过运行**一组 CSAccessEdgeConfiguration** cmdlet，使用下面的示例中显示的参数来配置联盟边缘服务器：
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers**参数指定是否允许内部用户与来自联盟域的用户进行通信。 此属性还可确定内部用户可以与用户在共享 SIP 地址空间方案与 Skype 业务服务器和 Exchange 联机通信。
    
有关使用 Skype 业务服务器管理程序的详细信息，请参阅[业务服务器 2015年管理外壳的 Skype](../../manage/management-shell.md)。
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a>在边缘服务器上配置宿主提供程序

使用 Skype 业务服务器管理外壳，配置宿主提供商边缘服务器上运行**新建 CsHostingProvider** cmdlet，在下面的示例中使用的参数：
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 如果您在中国使用 21Vianet 运营的 Office 365，请将此示例中 **ProxyFqdn** 参数的值（“exap.um.outlook.com”）替换为 21Vianet 运营的服务的 FQDN：“exap.um.partner.outlook.cn”。
  
- **标识**指定承载提供程序 （例如"Exchange Online"） 所创建的唯一字符串值的标识符。 包含空格的值必须用双引号括起来。
    
- **Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。 必须将其设置为 True。
    
- **EnabledSharedAddressSpace**表示承载提供程序是否将使用共享的 SIP 地址空间方案中。 必须将其设置为 True。
    
- **HostsOCSUsers**表示是否用于承载机构通讯服务器或 Skype 业务服务器承载提供程序。 必须将其设置为 False。
    
- **ProxyFQDN**指定宿主提供程序使用的代理服务器的完全合格的域名称 (FQDN)。 对于 Exchange Online，FQDN 为 exap.um.outlook.com。
    
- **IsLocal**指示宿主提供程序使用的代理服务器包含在您 Skype 业务服务器拓扑。 必须将其设置为 False。
    
- **VerificationLevel**指示与宿主提供程序发送的邮件所允许的验证级别。 指定**UseSourceVerification**，它依赖于宿主提供程序发送的消息中包含的验证级别。 如果不指定此级别，则消息将被拒绝作为不可验证。
    
## <a name="verify-replication-of-the-updated-central-management-store"></a>确保复制更新后的中央管理存储

通过前面章节中使用 cmdlet 所做的更改将自动应用于边缘服务器，并通常花费不到一分钟即可复制。 您可以验证复制状态并确认到边缘服务器应用了更改，通过使用以下 cmdlet。
  
要验证复制的更新，您的业务服务器部署中，Skype 在内部服务器上运行以下 cmdlet:
  
```
Get-CsManagementStoreReplicationStatus
```

若要确认已应用所做的更改，在边缘服务器上，运行以下 cmdlet:
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a>另请参阅

#### 

[提供业务服务器 2015 Skype 用户语音上 UM 承载 Exchange 邮件](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[承载的 Exchange 统一消息集成在 Skype 业务服务器 2015](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)

