---
title: 配置媒体旁路全局Skype for Business Server以使用站点和地区信息
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 将媒体旁路配置为仅用于 Skype for Business Server 企业语音 中的某些站点和Skype for Business Server 企业语音。
ms.openlocfilehash: 38fa42374b4b5dd8c8f304de04c9beeb59f2635d955b2e9ee5afb1fb16de7789
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322334"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>配置媒体旁路全局Skype for Business Server以使用站点和地区信息
 
将媒体旁路配置为仅用于 Skype for Business Server 企业语音 中的某些站点和Skype for Business Server 企业语音。 
  
 如果使用本主题中的步骤配置媒体旁路的全局设置，则假定前提是所有 Skype for Business 终结点与在中继连接上配置了媒体旁路的任何对等方之间的连接都不正确。
  
> [!NOTE]
> 启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。 
  
若要使媒体旁路正常工作，必须在拓扑生成器中定义的站点与配置网络区域和网络站点时定义的站点保持一致。 例如，如果您有一个在拓扑生成器中定义为仅部署了 PSTN 网关的分支站点，则必须使用允许分支站点用户通过分支站点的 PSTN 网关路由其 PSTN 呼叫的 企业语音 策略配置该分支站点。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>为媒体旁路配置站点和区域信息

1. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
2. 在左侧导航栏中，单击“网络配置”。
    
3. 双击表中的“全局”配置。
    
4. 在“编辑全局设置”页上，选中“启用媒体旁路”复选框。
    
5. 单击“使用站点和区域配置”。
    
6. 如有必要，请选中“为非映射站点启用旁路”复选框。
    
    > [!NOTE]
    > 仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。 
  
7. 单击“提交”。
    
接下来，将子网添加到网络站点，如将 [子网与网络站点关联中所述](deploy-network.md#BKMK_AssociateSubnets)。 将所有子网与网络站点关联后，媒体旁路部署即完成。
> [!IMPORTANT]
> 如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。 有关详细信息，请参阅在部署[中部署网络区域、站点和Skype for Business。](deploy-network.md) 
  
## <a name="see-also"></a>另请参阅

[将子网与网络站点关联](deploy-network.md#BKMK_AssociateSubnets)

