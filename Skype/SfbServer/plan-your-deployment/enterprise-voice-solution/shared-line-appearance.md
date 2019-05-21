---
title: 在 Skype for Business Server 2015 中规划共享线路外观
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 阅读本主题, 了解如何规划 Skype for Business Server 2015 中的共享行外观 (SLA), 2015 累积更新。
ms.openlocfilehash: 966c9f32a27ba936e880bdb51690bcefed4ffbe4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276445"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划共享线路外观
 
阅读本主题, 了解如何规划 Skype for Business Server 2015 中的共享行外观 (SLA), 2015 累积更新。 
  
共享线路的外观是 Skype for Business 中的一项功能, 用于处理特定号码 (称为共享号码) 的多个呼叫。 SLA 可以将任何企业语音启用的 Skype for business 用户配置为具有多个线路的共享号码, 以响应多个呼叫。 这些呼叫实际上并不是通过共享号码接收的，而是转接给担任共享号码的代理人的用户。 其中任何一个代理人都可以接听呼叫，而其余代理人的电话上将收到一个通知，说明已接听呼叫的代理人和哪条线路非常忙碌。 共享号码的线路数和代理人可以在 SLA 中配置。 此外，也可以为共享号码配置高级选项，例如 BusyOption（所有线路都忙碌时发生的情况）和 MissedCallOption（没有人接听呼叫）。
  
仅在以下电话设备上支持 SLA (计算机、移动电话或其他设备上的 Skype for business 客户端不支持): 
  
- 具有固件更新 5.4.1 的 Polycom VVX300
    
- 具有固件更新 5.4.1 的 Polycom VVX400
    
- 具有固件更新 5.4.1 的 Polycom VVX500
    
- 具有固件更新 5.4.1 的 Polycom VVX600
    
SLA 是 Skype for Business 服务器中的新功能, 2015 年11月累积更新。 
  
有关部署 SLA 的信息，请参阅[Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)。
  
## <a name="feature-list"></a>功能列表

设置 SLA 组可以实现以下功能：
  
- 组中的所有代理人都可以应答拨打同一共享号码的入站呼叫。呼叫可以是基于 PSTN 的也可以是基于 SIP 的。
    
- 代理人可以保持和接听呼叫。
    
- 代理人可以将呼叫转接到 SLA 组外部的号码。
    
- 代理人可以查看共享号码上当前存在的呼叫数，并查看每个呼叫的状态。
    
- 您可以为共享号码配置最大并发呼叫数。还可以设置在达到此最大数之后如何处理其他呼叫。额外呼叫可能会被忙音信号拒绝、转接到备用号码或者转接到语音邮件。
    
- 可以配置如何处理未接来电（在特定时间后未接听的呼叫）。如果为组标识启用语音邮件，未接来电将自动转到语音邮件。如果没有为组标识（共享号码）启用语音邮件，则可以选择通过忙音信号拒绝未接来电、将未接来电转接到备用号码或者断开连接。
    

