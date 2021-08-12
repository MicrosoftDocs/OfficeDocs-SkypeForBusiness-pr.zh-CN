---
title: 配置媒体旁路Skype for Business Server以始终绕过中介服务器
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
description: 启用媒体旁路功能可始终绕过中介服务器Skype for Business Server 企业语音。
ms.openlocfilehash: c80b3479546e9154480af8f71417b5ebce43b261510eec19332ecf1cf9287bc4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310027"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>配置媒体旁路Skype for Business Server以始终绕过中介服务器
 
启用媒体旁路功能可始终绕过中介服务器Skype for Business Server 企业语音。 
  
 如果使用本主题中的步骤配置媒体旁路的全局设置，则假定前提是 Skype for Business 终结点与在中继连接上配置了媒体旁路的任何对等方之间的连接良好。
  
如果在 Skype for Business 终结点与中介服务器的所有对等方（其各自的中继连接已启用媒体旁路）之间没有良好的连接，则必须配置全局媒体旁路设置，以在使用媒体旁路时使用站点和地区信息。 这可以在媒体绕过中介服务器时，提供更为细化的控制。 为此，请使用配置媒体旁路全局设置中的步骤Skype for Business Server[站点和](use-site-and-region-information.md)地区信息以及改为将子网[与网络站点](deploy-network.md#BKMK_AssociateSubnets)关联。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>在全局范围启用媒体旁路以始终绕过中介服务器

1. 打开Skype for Business Server控制面板"。
    
2. 在左侧导航栏中，单击“网络配置”。
    
3. 双击列表中的“全局”配置。
    
4. 在“编辑全局设置”页上，选中“启用媒体旁路”复选框。
    
5. 单击“始终绕过”。
    
6. 单击“提交”。
    
## <a name="see-also"></a>另请参阅

[规划媒体旁路Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[部署媒体旁路Skype for Business Server](deploy-media-bypass.md)

