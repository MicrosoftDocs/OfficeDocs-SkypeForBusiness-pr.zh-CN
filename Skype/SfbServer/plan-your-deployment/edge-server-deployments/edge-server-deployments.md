---
title: 在 Skype for Business 服务器中规划边缘服务器部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '摘要: 规划 Skype for business Server Edge 环境。 本主题向你介绍边缘概念, 让你可以使用更深入的主题进行组织。'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277158"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>在 Skype for Business 服务器中规划边缘服务器部署
 
**摘要:** 规划 Skype for business Server Edge 环境。 本主题向你介绍边缘概念, 让你可以使用更深入的主题进行组织。
  
如果您的 Skype for Business Server 环境在内部工作良好, 则下一步可能是向环境引入边缘服务器或边缘池。 如果你希望 Skype for Business 服务器提供的服务由内部网络外部的用户使用, 此角色将非常重要。 这些人可能包括：
  
- 远程用户：临时或一直不在现场的员工。
    
- 联盟用户: 您的合作伙伴组织的员工。
    
- 移动用户。
    
- 你想邀请其加入会议和演示会的潜在客户、合作伙伴，甚至是匿名用户。
    
外部用户访问, 这是服务器提供的边缘, 允许所有这些操作发生。 你的内部用户将能够享受 Skype for Business Server 部署托管的以下服务:
  
- IM 和通信状态：获得授权的外部用户可加入 IM 对话和会议。 他们可获得其他用户的状态信息（这些用户也获得他们的状态）。 如果您使用的是公共 IM 提供商, 则不能执行多方会议, 这是完全对等通信。 但是支持 SIP 和 XMPP 两种协议。
    
- 音频/视频 (A/V) 会议: 授权外部用户可以参与 Skype for Business 服务器音频和视频会议。
    
- 网络会议: 您授权的外部用户可以参与您的 Skype for Business 会议。 如果您愿意, 也可以为远程用户、联盟用户和匿名用户启用参与。 公共 IM 用户不能参与会议。 此外还有让这些用户参与应用程序和桌面共享，甚至担任会议组织者或演示者的选项。
    
由于企业语音, 支持移动设备访问。 可以将外部用户邀请到你希望他们参加的那些会议，甚至是匿名用户（如果希望将权限授予他们）。
  
如果这听上去符合你组织的需求，那么规划边缘环境对于部署该环境会有很大帮助。如需阅读更多资料，下面列出了有关主题。

> [!NOTE]
> XMPP 网关和代理在 Skype for business Server 2015 中可用, 但 Skype for business Server 2019 不再支持。 有关详细信息, 请参阅[迁移 XMPP 联合身份验证](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 
  
## <a name="planning-topics"></a>规划主题：

规划文章有：
  
- [Skype for Business Server 2015 的边缘服务器系统要求](system-requirements.md)
    
- [Skype for Business Server 2015 的边缘服务器环境要求](edge-environmental-requirements.md)
    
- [Skype for Business Server 2015 中的边缘服务器方案](scenarios.md)
    

