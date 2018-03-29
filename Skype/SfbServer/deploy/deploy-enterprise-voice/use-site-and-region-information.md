---
title: 在 Skype 的业务服务器 2015 使用网站和区域信息配置媒体绕过全局设置
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 配置媒体旁路用于某些站点和区域在 Skype 业务服务器企业语音。
ms.openlocfilehash: cebfa9d416fe3e68cd5615ae11616707ba1f60a8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-2015-to-use-site-and-region-information"></a>在 Skype 的业务服务器 2015 使用网站和区域信息配置媒体绕过全局设置
 
配置媒体旁路用于某些站点和区域在 Skype 业务服务器企业语音。 
  
 如果您使用绕过配置全局设置媒体本主题中的步骤操作，假设是不具有很好互连性业务终结点的所有 Skype 和任何您配置媒体回避干线连接的对等。
  
> [!NOTE]
> 启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。 
  
对于媒体忽略工作正确一致性之间必须站点拓扑生成器中定义和按定义配置区域网络和网络站点时。 例如，如果您的拓扑生成器中定义为具有一个分支网站的 PSTN 网关部署，然后使分支网站用户，让其通过 PSTN 路由的 PSTN 电话企业语音策略必须配置该分支站点在分部地点的网关。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>为媒体旁路配置站点和区域信息

1. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。  
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 双击表中的“全局”****配置。
    
4. 在“编辑全局设置”****页上，选中“启用媒体旁路”****复选框。
    
5. 单击“使用站点和区域配置”****。
    
6. 如有必要，请选中“为非映射站点启用旁路”****复选框。
    
    > [!NOTE]
    > 仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。 
  
7. 单击“**提交**”。
    
接着，将子网添加到网络站点中，如[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)中所述。将所有子网与网络站点相关联后，媒体旁路即部署完成。
> [!IMPORTANT]
> 如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。 有关详细信息，请参阅[部署网络区域、 站点和子网中为业务 2015 Skype](deploy-network.md)。 
  
## <a name="see-also"></a>另请参阅

#### 

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

