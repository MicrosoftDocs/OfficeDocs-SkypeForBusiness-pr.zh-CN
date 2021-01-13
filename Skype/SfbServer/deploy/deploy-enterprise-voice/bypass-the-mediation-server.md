---
title: 在 Skype for Business Server 中配置媒体旁路以始终绕过中介服务器
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 启用媒体旁路功能，以始终绕过 Skype for Business Server 企业语音。
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804212"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>在 Skype for Business Server 中配置媒体旁路以始终绕过中介服务器
 
启用媒体旁路功能，以始终绕过 Skype for Business Server 企业语音。 
  
 如果使用本主题中的步骤为媒体旁路配置全局设置，则假定前提是 Skype for Business 终结点与在中继连接上配置了媒体旁路的任何对等方之间的连接良好。
  
如果 Skype for Business 终结点与中介服务器的所有对等方之间没有良好的连接，且中介服务器各自的中继连接已启用媒体旁路，则必须配置全局媒体旁路设置，以在使用媒体旁路时使用站点和地区信息。 这可以在媒体绕过中介服务器时，提供更为细化的控制。 为此，请使用 Skype for [Business Server](use-site-and-region-information.md) 中的"配置媒体旁路全局设置"中的步骤使用站点和地区信息，并改为将子网与 [网络站点](deploy-network.md#BKMK_AssociateSubnets) 关联。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>在全局范围启用媒体旁路以始终绕过中介服务器

1. 打开 Skype for Business Server 控制面板。
    
2. 在左侧导航栏中，单击“网络配置”。
    
3. 双击列表中的“全局”配置。
    
4. 在“编辑全局设置”页上，选中“启用媒体旁路”复选框。
    
5. 单击“始终绕过”。
    
6. 单击“提交”。
    
## <a name="see-also"></a>另请参阅

[在 Skype for Business 中规划媒体旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[在 Skype for Business Server 中部署媒体旁路](deploy-media-bypass.md)

