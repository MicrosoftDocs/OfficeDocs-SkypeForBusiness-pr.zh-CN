---
title: 配置业务服务器的内部部署 Skype 和 Outlook Web App 之间的集成
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
description: 摘要： 将 Skype 集成的企业服务器和 Outlook Web App。
ms.openlocfilehash: 5ad1f6bc898a29c2a5e0f326d3a5edc4d782bab2
ms.sourcegitcommit: 25066ab000f7615aff31f77d9d39c266c65e2aa5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22914094"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>配置业务服务器的内部部署 Skype 和 Outlook Web App 之间的集成
 
**摘要：** 将 Skype 集成的企业服务器和 Outlook Web App。
  
使用本地 Skype 业务服务器部署的客户可在混合部署模式下可以配置与 Microsoft Exchange Online 中的 Microsoft Outlook Web App 互操作性。 互操作性功能包括单一登录和即时消息 (IM) 以及与 Outlook Web App 接口的状态集成。 若要启用此集成，您必须通过完成以下任务在您的本地 Skype 业务服务器部署中配置边缘服务器： 
  
- 配置共享的 SIP 地址空间
    
- 边缘服务器上配置宿主提供商
    
- 验证复制更新后的中央管理存储
    
## <a name="configure-a-shared-sip-address-space"></a>配置共享的 SIP 地址空间

若要将内部部署 Skype 集成业务 server 与 Exchange Online，必须配置共享的 SIP 地址空间。 Skype 业务 server 和 Exchange Online 服务支持相同的 SIP 域地址空间。
  
使用 Skype 业务 Server 命令行管理程序，通过运行**Set-csaccessedgeconfiguration** cmdlet，使用下面的示例中显示的参数配置边缘服务器联盟：
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers**参数指定是否允许内部用户与联盟域中的用户进行通信。 此属性还决定内部用户可以与 Skype 的共享 SIP 地址空间情况用户 Business Server 和 Exchange Online 的通信。
    
有关为业务 Server 命令行管理程序中使用 Skype 的详细信息，请参阅[Business Server Management Shell 的 Skype](../../manage/management-shell.md)。
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a>在边缘服务器上配置宿主提供程序

使用 Skype 业务 Server 命令行管理程序，以边缘服务器上配置宿主提供商，通过运行**New-cshostingprovider** cmdlet，使用下面的示例中的参数：
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 如果您在中国使用 21Vianet 运营的 Office 365，请将此示例中 ProxyFqdn 参数的值（“exap.um.outlook.com”）替换为 21Vianet 运营的服务的 FQDN：“exap.um.partner.outlook.cn”。 如果您使用 Office 365 GCC 高，值替换 ProxyFqdn 参数在本示例中 ("exap.um.outlook.com") 的 FQDN 为 GCC 高:"exap.um.office365.us"。
  
- **标识**要创建 （例如，"Exchange Online"） 的宿主提供商指定唯一的字符串值标识符。 包含空格的值必须用双引号括起来。
    
- **Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。 必须将其设置为 True。
    
- **EnabledSharedAddressSpace**指示是否将共享 SIP 地址空间方案中使用的宿主提供商。 必须将其设置为 True。
    
- **HostsOCSUsers**指示承载服务提供商是否用于承载 Office Communications Server 或 Skype 业务服务器。 必须将其设置为 False。
    
- **ProxyFQDN**指定的宿主提供商使用的代理服务器的完全限定的域名 (FQDN)。 对于 Exchange Online，FQDN 为 exap.um.outlook.com。
    
- **IsLocal**指示承载服务提供商使用的代理服务器是否包含您 Skype 企业服务器拓扑中。 必须将其设置为 False。
    
- **VerificationLevel**指示允许与宿主提供程序发送的邮件的验证级别。 指定**UseSourceVerification**，它依赖于从托管服务提供商发送的消息中包括的验证级别。 如果未指定此级别，则邮件将被拒绝为无法验证。
    
## <a name="verify-replication-of-the-updated-central-management-store"></a>确保复制更新后的中央管理存储

使用 cmdlet 上述各节中所做的更改会自动应用到边缘服务器，并通常执行小于分钟时间才能复制。 您可以验证复制状态，并确认已应用更改到边缘服务器使用以下 cmdlet。
  
若要验证复制更新，在您 Skype 业务服务器部署中的内部服务器上运行以下 cmdlet:
  
```
Get-CsManagementStoreReplicationStatus
```

若要确认已应用所做的更改，在边缘服务器上，运行以下 cmdlet:
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a>另请参阅

[为业务服务器提供 Skype 用户语音邮件上承载的 Exchange UM](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[托管的 Exchange 统一消息集成在 Skype 业务服务器](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)