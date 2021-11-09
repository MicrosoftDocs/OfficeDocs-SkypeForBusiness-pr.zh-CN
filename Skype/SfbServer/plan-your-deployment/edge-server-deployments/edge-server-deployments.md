---
title: 在部署中规划边缘服务器Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 摘要：规划边缘Skype for Business Server环境。 本主题向你介绍 Edge 概念，并让你可以使用我们更深入的主题进行组织。
ms.openlocfilehash: ae6dd672e3da6568d41898a4bc2ae022b23ad3f3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834110"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>在部署中规划边缘服务器Skype for Business Server
 
**摘要：** 规划边缘Skype for Business Server。 本主题向你介绍 Edge 概念，并让你可以使用我们更深入的主题进行组织。
  
当具有Skype for Business Server运行良好的外部环境时，下一步是向该环境引入边缘服务器或边缘池。 如果希望外部人员使用由 Skype for Business Server 提供的服务，此角色将非常重要。 这些可能包括：
  
- 远程用户：临时或持续离开的员工。
    
- 联盟用户：合作伙伴组织的员工。
    
- 移动用户。
    
- 希望受邀参加会议和演示的潜在客户、合作伙伴甚至匿名用户。
    
外部用户访问（边缘服务器提供）允许执行所有这些操作。 内部用户将能够享受由您的内部部署托管的Skype for Business Server服务：
  
- 用于通信的 IM 和状态：授权的外部用户可以加入 IM 对话和会议。 他们可以获取其他用户状态信息 (获取其状态信息的用户) 。 如果使用公共 IM 提供程序，则不能进行多方会议，这严格来说就是对等通信。 但支持 SIP 和 XMPP 协议。
    
- A/V 会议 (/视频) ：授权外部用户可以参加Skype for Business Server音频和视频会议。
    
- Web 会议：授权的外部用户可以参加Skype for Business会议。 如果需要，您还可以允许远程用户、联盟用户和匿名用户参与。 公共 IM 用户不能参加会议。 还有一些选项允许这些用户参与应用程序和桌面共享，甚至充当会议组织者或演示者。
    
支持移动设备访问，就像支持企业语音。 如果要向外部用户授予权限，可以邀请外部用户参加你希望他们参加的会议，甚至是匿名用户。
  
如果这听起来组织需要一些内容，那么规划边缘环境对于部署边缘环境将大有帮助。 为了进一步阅读，我们在下面列出了主题。

> [!NOTE]
> XMPP 网关和代理在 Skype for Business Server 2015 中可用，但在 2019 年 2 月不再Skype for Business Server支持。 有关详细信息 [，请参阅迁移 XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 联盟。 
  
## <a name="planning-topics"></a>规划主题：

规划文章包括：
  
- [Skype for Business Server 2015 中的边缘服务器系统要求](system-requirements.md)
    
- [2015 年 Skype for Business Server 中的边缘服务器环境要求](edge-environmental-requirements.md)
    
- [Skype for Business Server 2015 中的边缘服务器方案](scenarios.md)
    

