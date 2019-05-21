---
title: 在 Skype for Business 服务器中配置 "绕过媒体" 服务器以始终绕过中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 在 Skype for Business Server Enterprise Voice 中启用 "绕过媒体" 以始终绕过中介服务器。
ms.openlocfilehash: 0e45f8ede38411974f9433c17ccd0a0946b427ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275876"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>在 Skype for Business 服务器中配置 "绕过媒体" 服务器以始终绕过中介服务器
 
在 Skype for Business Server Enterprise Voice 中启用 "绕过媒体" 以始终绕过中介服务器。 
  
 如果你使用本主题中的步骤来配置媒体绕过的全局设置, 则假设你在 Skype for Business 终结点和任何对等客户之间具有良好的连接, 你可以在中继连接上配置了媒体旁路。
  
如果您在 Skype for Business 终结点和所有对等的外部服务器之间没有良好的连接, 并且其各自的干线连接已启用媒体旁路, 则必须将全局媒体绕过设置配置为使用网站和区域信息采用媒体旁路时。 这允许在确定媒体绕过中介服务器时提供更多控制。 若要执行此操作, 请使用 "在[Skype For Business 服务器中配置媒体绕过全局设置" 中的步骤使用网站和区域信息](use-site-and-region-information.md), 而[将子网与网络网站相关联](deploy-network.md#BKMK_AssociateSubnets)。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>在全局范围启用媒体旁路以始终绕过中介服务器

1. 打开 "Skype for Business 服务器" 控制面板。
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 双击列表中的“全局”**** 配置。
    
4. 在“编辑全局设置”**** 页上，选中“启用媒体旁路”**** 复选框。
    
5. 单击“始终绕过”****。
    
6. 单击“**提交**”。
    
## <a name="see-also"></a>另请参阅

[在 Skype for Business 中规划媒体旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[在 Skype for Business 服务器中部署媒体旁路](deploy-media-bypass.md)

