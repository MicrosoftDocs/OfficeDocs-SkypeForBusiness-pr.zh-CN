---
title: 在 Skype for Business 服务器中配置媒体绕过全局设置以使用网站和区域信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 将 "绕过媒体" 配置为仅用于 Skype for Business Server Enterprise Voice 中的特定网站和区域。
ms.openlocfilehash: 7a424e6737c1165eb037ca1130e3b87c4d0436e0
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766935"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>在 Skype for Business 服务器中配置媒体绕过全局设置以使用网站和区域信息
 
将 "绕过媒体" 配置为仅用于 Skype for Business Server Enterprise Voice 中的特定网站和区域。 
  
 如果你使用本主题中的步骤来配置媒体绕过的全局设置，则假设你的所有 Skype for Business 终结点和任何对等的用户在中继连接上配置了媒体旁路的任何对等设备之间没有完好的连接。
  
> [!NOTE]
> 启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。 
  
若要使媒体旁路正常工作，在拓扑生成器中定义的网站与在配置网络区域和网络网站时定义的网站之间必须保持一致。 例如，如果您在拓扑生成器中定义了一个已部署 PSTN 网关的分支站点，则必须使用企业语音策略配置分支网站，以便分支站点用户通过 PSTN 路由其 PSTN 呼叫分支站点上的网关。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>为媒体旁路配置站点和区域信息

1. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 双击表中的“全局”**** 配置。
    
4. 在“编辑全局设置”**** 页上，选中“启用媒体旁路”**** 复选框。
    
5. 单击“使用站点和区域配置”****。
    
6. 如有必要，请选中“为非映射站点启用旁路”**** 复选框。
    
    > [!NOTE]
    > 仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。 
  
7. 单击“**提交**”。
    
接着，将子网添加到网络站点中，如[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)中所述。将所有子网与网络站点相关联后，媒体旁路即部署完成。
> [!IMPORTANT]
> 如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。 有关详细信息，请参阅[在 Skype For business 中部署网络区域、网站和子网](deploy-network.md)。 
  
## <a name="see-also"></a>另请参阅

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

