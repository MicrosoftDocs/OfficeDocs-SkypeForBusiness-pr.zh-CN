---
title: 为本地广播配置Skype 会议部署
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 摘要：了解为本地部署和混合部署Skype 会议广播Skype for Business Server的步骤。
ms.openlocfilehash: 9d1ccadfc6a8bed52a7f6d4aa72bd72c2a5e94c8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771694"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>为本地广播配置Skype 会议部署
 
**摘要：** 了解为本地部署和混合部署Skype 会议广播Skype for Business Server的步骤。
  
Skype 会议广播是一种联机服务，它是Office 365。 如果要在本地Skype for Business Server广播，并且想要Skype 会议广播，则需要遵循本主题中的配置步骤。 开始之前，需要将环境配置为与 Skype for Business Online 混合。 有关详细信息，请参阅 Plan [hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)和 Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online。](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>为混合广播配置Skype 会议环境

你需要执行以下操作来为广播环境Skype 会议环境：
  
- 配置与 Skype for Business Online 资源的联盟
    
- 配置 SIP 联盟域
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>配置与 Skype for Business Online 资源的联盟

若要启用与 Skype for Business Online 资源的联盟，您需要为 SIP 联盟提供程序配置外部访问。 为此，请Skype for Business Server控制面板执行以下步骤：
  
1. 启动"Skype for Business Server控制面板"，然后选择 **左侧的"外部** 访问"。
    
2. 选择 **"SIP 联盟提供程序"，** 然后单击"新建 **"。**
    
3. 使用下列设置配置新提供程序：
    
   - **启用与此提供商的通信：** 已选择
   - **提供程序名称：** LyncOnlineResources
   - **访问边缘服务 (FQDN) ：sipfed.resources.lync.com**
   - **默认验证级别：** 允许用户使用此提供程序与所有人通信。 
   
您还可以通过运行命令行管理Skype for Business中的以下 cmdlet 来启用与 Skype for Business Server Online 资源的联盟：
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>配置 SIP 联盟域

接下来，您需要将 SIP 联盟域添加到允许的域列表中。 对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。 这些域包括用于 Skype for Business Online 中使用的区域数据中心。
  
1. 启动"Skype for Business Server控制面板"，然后选择 **左侧的"外部** 访问"。
    
2. 选择 **"SIP 联盟域"，** 然后单击"新建 **"。**
    
3. 对于 **"域名 (FQDN) ：，** 输入域，对以下每个域重复此过程：
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
您还可以在命令行管理程序中运行以下 cmdlet，为 SIP 联盟域Skype for Business Server访问：
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

完成这些配置步骤后，可以在部署中开始使用Skype 会议广播。 有关广播Skype 会议，请参阅什么是Skype 会议[广播？](https://go.microsoft.com/fwlink/?LinkId=617071)和Skype 会议[广播管理指南](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)。
