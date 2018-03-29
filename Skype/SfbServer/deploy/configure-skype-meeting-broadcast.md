---
title: 配置 Skype 会议直播本地部署
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 摘要： 了解您需要执行配置 Skype 会议广播业务服务器混合部署您的内部部署 Skype 的步骤。
ms.openlocfilehash: e788a263223ea3fa0f4ce9ed844fb5b4eb0ae898
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>配置 Skype 会议直播本地部署
 
**摘要：**了解您需要执行配置 Skype 会议广播业务服务器混合部署您的内部部署 Skype 的步骤。
  
Skype 会议广播是属于 Office 365 的联机服务。 如果正在运行的业务服务器部署 Skype 并且想要在您的环境中使用 Skype 会议广播，您需要按照本主题中的配置步骤。 在开始之前，您的环境需要配置，以混合的 Skype 的在线业务。 有关详细信息，请参阅[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)和[部署混合来临 Skype 业务服务器和 Skype 的在线业务](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>为 Skype 会议广播配置混合环境

您需要执行以下操作来准备您的环境以便使用 Skype 会议广播：
  
- 配置联合身份验证与 Skype 业务联机资源
    
- 配置 SIP 联盟域
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>配置联合身份验证与 Skype 业务联机资源

要启用联盟与 Skype 业务联机资源，您需要 SIP 联合提供程序配置的外部访问。 为此通过 Skype 业务服务器控件面板执行以下步骤：
  
1. 启动 Skype 业务服务器的控制面板，选择左侧的**外部访问**。
    
2. 选择“SIP 联盟提供程序”****，再单击“新建”****。
    
3. 使用以下设置配置新的提供程序：
    
|||
|:-----|:-----|
|**启用与此提供程序进行通信：** <br/> |选中  <br/> |
|**提供程序名称:** <br/> |LyncOnlineResources  <br/> |
|**访问边缘服务(FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**默认验证级别:** <br/> |允许用户与使用此提供程序的每个人通信。  <br/> |
   
您还可以通过 Skype 在运行以下 cmdlet 业务服务器管理外壳程序启用联盟与 Skype 业务联机资源：
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>配置 SIP 联盟域

接下来，您需要将 SIP 的联盟域添加到允许的域列表。 对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。 这些域包含对于区域数据中心中使用的 Skype 的在线业务。
  
1. 启动 Skype 业务服务器的控制面板，选择左侧的**外部访问**。
    
2. 选择“SIP 联盟域”****，再单击“新建”****。
    
3. 对于“域名(或 FQDN):”****，输入域，为以下每个域重复此过程：
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
您还可以通过 Skype 在运行以下 cmdlet 业务服务器管理外壳配置联合的 SIP 域的外部访问权限：
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "emeameetings.lync.com"
```

```
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
```

```
New-CsAllowedDomain -Identity "resources.lync.com"
```

当您完成这些配置步骤可以开始在部署时使用 Skype 会议广播。 关于 Skype 会议广播的详细信息，请参阅[是 Skype 会议广播什么？](https://go.microsoft.com/fwlink/?LinkId=617071)和[Skype 会议广播管理员指南 》](https://go.microsoft.com/fwlink/?LinkId=617075)。
  

