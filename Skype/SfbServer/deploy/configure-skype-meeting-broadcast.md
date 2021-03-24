---
title: 为 Skype 会议直播配置本地部署
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 摘要：了解为本地 Skype for Business Server 混合部署配置 Skype 会议直播需要执行的步骤。
ms.openlocfilehash: b70272ee90146bdac87264acf0c7673b8def05c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103688"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>为 Skype 会议直播配置本地部署
 
**摘要：** 了解为本地 Skype for Business Server 混合部署配置 Skype 会议直播需要执行的步骤。
  
Skype 会议广播是一项在线服务，属于 Office 365。 如果你正在本地运行 Skype for Business Server，并且想要在你的环境中使用 Skype 会议直播，则需要遵循本主题中的配置步骤。 开始之前，需要将环境配置为与 Skype for Business Online 进行混合。 有关详细信息，请参阅 Plan [hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 和 Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>为 Skype 会议直播配置混合环境

你需要执行以下操作来为 Skype 会议直播准备你的环境：
  
- 配置与 Skype for Business Online 资源的联盟
    
- 配置 SIP 联盟域
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>配置与 Skype for Business Online 资源的联盟

要启用与 Skype for Business Online 资源的联盟，需要为 SIP 联盟提供程序配置外部访问。 若要使用 Skype for Business Server 控制面板完成此操作，请按照以下步骤操作：
  
1. 启动 Skype for Business Server 控制面板，然后选择 **左侧的"外部** 访问"。
    
2. 选择 **"SIP 联盟提供程序"，** 然后单击"新建 **"。**
    
3. 使用下列设置配置新提供程序：
    
|||
|:-----|:-----|
|**启用与此提供商的通信：** <br/> |已选定  <br/> |
|**提供程序名称：** <br/> |LyncOnlineResources  <br/> |
|**访问边缘服务 (FQDN) ：** <br/> |sipfed.resources.lync.com  <br/> |
|**默认验证级别：** <br/> |允许用户使用此提供程序与所有人通信。  <br/> |
   
还可以在 Skype for Business Server 命令行管理程序 中运行以下 cmdlet，以启用与 Skype for Business Online 资源的联盟：
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>配置 SIP 联盟域

接下来，您需要将 SIP 联盟域添加到允许的域列表中。 对列出的每个域重复这些步骤，创建 4 个新的 SIP 联盟域。 这些域包括用于 Skype for Business Online 中使用的区域数据中心。
  
1. 启动 Skype for Business Server 控制面板，然后选择 **左侧的"外部** 访问"。
    
2. 选择 **"SIP 联盟域"，** 然后单击"新建 **"。**
    
3. 对于 **"域名 (FQDN) ：**"，输入域，对以下每个域重复此过程：
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
您还可以在 Skype for Business Server 命令行管理程序 中运行以下 cmdlet，为 SIP 联盟域配置外部访问：
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

完成这些配置步骤后，就可以开始在部署中使用 Skype 会议直播。 有关 Skype 会议直播详细信息，请参阅 [什么是 Skype 会议直播？](https://go.microsoft.com/fwlink/?LinkId=617071) 和 [Skype 会议直播管理指南](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)。
