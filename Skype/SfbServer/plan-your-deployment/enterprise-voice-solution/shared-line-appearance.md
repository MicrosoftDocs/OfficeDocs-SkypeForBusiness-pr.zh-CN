---
title: 规划 Skype for Business Server 2015 中的共享线路外观
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 阅读本主题，了解如何在 Skype for Business Server 2015 2015 年 11 月累积更新中规划共享线路外观 (SLA) 。
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813342"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>规划 Skype for Business Server 2015 中的共享线路外观
 
阅读本主题，了解如何在 Skype for Business Server 2015 2015 年 11 月累积更新中规划共享线路外观 (SLA) 。 
  
共享线路外观是 Skype for Business 中的一项功能，用于处理对称为共享号码的特定号码的多个呼叫。 SLA 可以将任何启用企业语音的 Skype for Business 用户配置为具有多行线路的共享号码，以响应多个呼叫。 实际上不会在共享号码上收到呼叫，而是将呼叫转发给充当共享号码代理的用户。 任何一个代理都可以接听呼叫，而其余的代理人会通过电话收到有关接听呼叫的人以及哪条线路因此变得繁忙的通知。 在 SLA 中，线路数和代理都适用于共享号码。 此外，还可以为共享号码配置高级选项，例如 BusyOption (当所有线路都繁忙) 和 MissedCallOption (当没有代理接电话) 时会发生什么情况。
  
SLA 仅在以下电话设备上受支持 (在计算机、移动电话或其他设备上不支持 Skype for Business) ： 
  
- 具有固件更新 5.4.1 的 Polycom VVX300
    
- 具有固件更新 5.4.1 的 Polycom VVX400
    
- 具有固件更新 5.4.1 的 Polycom VVX500
    
- 具有固件更新 5.4.1 的 Polycom VVX600
    
SLA 是 Skype for Business Server 中的一项新功能，2015 年 11 月累积更新。 
  
有关部署 SLA 的信息，请参阅 [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)。
  
## <a name="feature-list"></a>功能列表

通过设置 SLA 组，可以执行以下操作：
  
- 组内的所有代理人都可以应答对同一共享号码的入站呼叫。 呼叫可以基于 PSTN 或基于 SIP。
    
- 代理人可以保留和接听呼叫。
    
- 代理人可以将呼叫转接到 SLA 组外部的号码。
    
- 代理人可以查看共享号码中当前有多少个呼叫，并查看每个呼叫的状态。
    
- 您可以为共享号码配置最大并发呼叫数。 还可以设置在达到此最大值后处理其他呼叫的方式。 多余呼叫可以通过忙音信号拒绝、转发到备用号码或转发到语音邮件。
    
- 可以配置如何处理未接 (未接来电，) 时间后未接听。 如果为组标识启用语音邮件，则未接来电将自动转到语音邮件。 如果没有为组标识启用语音邮件 (共享号码) ，可以选择通过忙音信号拒绝未接来电、转发到备用号码或断开连接。
    

