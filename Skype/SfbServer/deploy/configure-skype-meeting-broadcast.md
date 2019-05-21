---
title: 配置 Skype 会议直播本地部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '摘要: 了解为本地 Skype for business Server 混合部署配置 Skype 会议直播时需要执行的步骤。'
ms.openlocfilehash: b744ae55fe9c866b2f65c816e471ed077312df13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291663"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**摘要:** 了解为本地 Skype for business 服务器混合部署配置 Skype 会议直播时需要执行的步骤。
  
Skype 会议直播是 Office 365 中的一种在线服务。 如果您运行的是本地 Skype for business 服务器, 并且想要在您的环境中使用 Skype 会议直播, 则需要按照本主题中的配置步骤操作。 开始之前, 需要为与 Skype for Business Online 的混合配置你的环境。 有关详细信息，请参阅[Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)和[Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>为 Skype 会议直播配置混合环境

您需要执行以下操作来为您的 Skype 会议直播准备环境:
  
- 配置与 Skype for Business Online 资源的联盟
    
- 配置 SIP 联盟域
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>配置与 Skype for Business Online 资源的联盟

若要启用与 Skype for Business Online 资源的联盟, 你需要为 SIP 联合提供商配置外部访问权限。 要使用 Skype for Business 服务器控制面板执行此操作, 请按照下列步骤操作:
  
1. 启动 Skype for Business 服务器控制面板, 然后在左侧选择 "**外部访问**"。
    
2. 选择“SIP 联盟提供程序”****，再单击“新建”****。
    
3. 使用以下设置配置新的提供程序：
    
|||
|:-----|:-----|
|**启用与此提供商的通信:** <br/> |选中  <br/> |
|**提供程序名称:** <br/> |LyncOnlineResources  <br/> |
|**访问边缘服务(FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**默认验证级别:** <br/> |允许用户与使用此提供程序的每个人通信。  <br/> |
   
您也可以通过在 Skype for business Server Management Shell 中运行以下 cmdlet 来启用与 Skype for Business Online 资源的联盟:
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>配置 SIP 联盟域

接下来, 你需要将 SIP 联盟域添加到 "允许的域" 列表。 对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。 这些域包括用于 Skype for Business Online 中的区域数据中心。
  
1. 启动 Skype for Business 服务器控制面板, 然后在左侧选择 "**外部访问**"。
    
2. 选择“SIP 联盟域”****，再单击“新建”****。
    
3. 对于“域名(或 FQDN):”****，输入域，为以下每个域重复此过程：
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
你还可以通过在 Skype for Business Server Management Shell 中运行以下 cmdlet 来配置 SIP 联盟域的外部访问:
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

完成这些配置步骤后, 您可以开始在部署中使用 Skype 会议直播。 有关 Skype 会议直播的详细信息, 请参阅[什么是 Skype 会议直播？](https://go.microsoft.com/fwlink/?LinkId=617071) [Skype 会议直播管理员指南](https://go.microsoft.com/fwlink/?LinkId=617075)。
  

