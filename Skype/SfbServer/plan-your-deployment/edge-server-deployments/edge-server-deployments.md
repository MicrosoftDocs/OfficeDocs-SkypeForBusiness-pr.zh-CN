---
title: 规划在 Skype 业务服务器的边缘服务器部署
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 摘要： 规划业务服务器边缘环境您 Skype。 本主题介绍了边缘概念，并允许您获取组织与我们更深入的主题。
ms.openlocfilehash: e2154abd7e263b92011ca198ddaa1b90f8bd38c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881651"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>规划在 Skype 业务服务器的边缘服务器部署
 
**摘要：** Plan for Business 服务器边缘环境您 Skype。 本主题介绍了边缘概念，并允许您获取组织与我们更深入的主题。
  
Skype 也内部使用的业务服务器环境后下, 一步您可能引入到环境的边缘服务器或边缘池。 此角色将为重要，如果您希望 Skype 业务服务器要使用您的内部网络之外的人员提供的服务。 这些人可能包括：
  
- 远程用户：临时或一直不在现场的员工。
    
- 联盟用户： 合作伙伴组织的员工。
    
- 移动用户。
    
- 你想邀请其加入会议和演示会的潜在客户、合作伙伴，甚至是匿名用户。
    
外部用户访问，这是边缘服务器的提供，允许所有这种情况。 您的内部用户将能够享受您 Skype 业务服务器部署由以下服务：
  
- IM 和通信状态：获得授权的外部用户可加入 IM 对话和会议。 他们可获得其他用户的状态信息（这些用户也获得他们的状态）。 您不能进行多方会议，如果您使用的公共 IM 提供商，即严格对等通信。 但是支持 SIP 和 XMPP 两种协议。
    
- 音频/视频 (A / V) 会议： 授权的外部用户可以参加您 Skype Business Server 音频和视频会议。
    
- Web 会议： 授权的外部用户可以参加您 Skype 业务会议。 如果您愿意，您还可以启用远程用户、 联盟的用户和匿名用户参与。 公共 IM 用户不能参加会议。 此外还有让这些用户参与应用程序和桌面共享，甚至担任会议组织者或演示者的选项。
    
支持移动设备访问，如为企业语音。 可以将外部用户邀请到你希望他们参加的那些会议，甚至是匿名用户（如果希望将权限授予他们）。
  
如果这听上去符合你组织的需求，那么规划边缘环境对于部署该环境会有很大帮助。如需阅读更多资料，下面列出了有关主题。

> [!NOTE]
> XMPP 网关和代理中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。 有关详细信息，请参阅[迁移 XMPP 联盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 
  
## <a name="planning-topics"></a>规划主题：

规划文章有：
  
- [Skype for Business Server 2015 的边缘服务器系统要求](system-requirements.md)
    
- [Skype for Business Server 2015 的边缘服务器环境要求](edge-environmental-requirements.md)
    
- [Skype for Business Server 2015 中的边缘服务器方案](scenarios.md)
    

