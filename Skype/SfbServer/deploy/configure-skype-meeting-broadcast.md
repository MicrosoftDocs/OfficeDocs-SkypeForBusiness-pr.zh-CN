---
title: 配置 Skype 会议直播本地部署
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
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
description: 摘要： 了解您需要为您的本地 Skype Business Server 混合部署配置 Skype 会议广播执行的步骤。
ms.openlocfilehash: 10f09fc31f32e2784bb377ba5fe393e5f13a5618
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229451"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**摘要：** 了解您需要为您的本地 Skype Business Server 混合部署配置 Skype 会议广播执行的步骤。
  
Skype 会议广播是为 Office 365 的一部分的联机服务。 如果您的业务 Server 内部部署运行 Skype，并想要在您的环境中使用 Skype 会议广播，您需要按照本主题中的配置步骤。 在开始之前，您的环境需要用来配置混合 Skype 业务 online。 有关详细信息，请参阅[Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)和[Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>为会议广播 Skype 配置混合环境

您需要执行以下操作来为 Skype 会议广播准备环境：
  
- 配置联合身份验证与 Skype 的业务联机资源
    
- 配置 SIP 联盟域
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>配置联合身份验证与 Skype 的业务联机资源

若要启用的业务联机资源与 Skype 联合身份验证，您需要配置外部访问的 SIP 联盟提供程序。 若要执行此使用适用于业务 Server Control Panel Skype 执行以下步骤：
  
1. 为业务 Server Control Panel 启动 Skype 并选择左侧的**外部访问**。
    
2. 选择“SIP 联盟提供程序”****，再单击“新建”****。
    
3. 使用以下设置配置新的提供程序：
    
|||
|:-----|:-----|
|**启用与此提供程序通信：** <br/> |选中  <br/> |
|**提供程序名称:** <br/> |LyncOnlineResources  <br/> |
|**访问边缘服务(FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**默认验证级别:** <br/> |允许用户与使用此提供程序的每个人通信。  <br/> |
   
您还可以通过运行以下 cmdlet 中 Skype 业务 Server 命令行管理程序启用业务联机资源与 Skype 联合身份的验证：
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>配置 SIP 联盟域

接下来，您需要将 SIP 联盟域添加到允许的域列表。 对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。 包含这些域是的区域数据中心中使用的 Skype 业务联机。
  
1. 为业务 Server Control Panel 启动 Skype 并选择左侧的**外部访问**。
    
2. 选择“SIP 联盟域”****，再单击“新建”****。
    
3. 对于“域名(或 FQDN):”****，输入域，为以下每个域重复此过程：
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
您还可以通过运行以下 cmdlet 中的 Skype 业务 Server 命令行管理程序配置 SIP 联盟域的外部访问：
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

已完成这些配置步骤之后，您可以开始部署中使用 Skype 会议广播。 有关 Skype 会议广播的详细信息，请参阅[Skype 会议广播是什么？](https://go.microsoft.com/fwlink/?LinkId=617071)和[Skype 会议广播管理指南](https://go.microsoft.com/fwlink/?LinkId=617075)。
  

