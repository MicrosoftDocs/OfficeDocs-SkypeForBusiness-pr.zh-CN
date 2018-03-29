---
title: 在 Skype for Business Server 2015 中规划共享线路外观
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 阅读本主题可了解如何规划用于共享行外观 (SLA) 在 Skype 业务服务器 2015，11 月 2015年累积更新。
ms.openlocfilehash: bed7eaf520cb8fd9bfc9c7a9a27093d55647b510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中规划共享线路外观
 
阅读本主题可了解如何规划用于共享行外观 (SLA) 在 Skype 业务服务器 2015，11 月 2015年累积更新。 
  
共享的行外观用于处理多个调用特定数量称为共享的号是 Skype 的业务功能。 SLA 可以配置任何企业语音启用 Skype 业务用户为具有多行共享数字来响应的多个调用。 这些呼叫实际上并不是通过共享号码接收的，而是转接给担任共享号码的代理人的用户。 其中任何一个代理人都可以接听呼叫，而其余代理人的电话上将收到一个通知，说明已接听呼叫的代理人和哪条线路非常忙碌。 共享号码的线路数和代理人可以在 SLA 中配置。 此外，也可以为共享号码配置高级选项，例如 BusyOption（所有线路都忙碌时发生的情况）和 MissedCallOption（没有人接听呼叫）。
  
SLA 是仅支持以下电话设备 （它不支持 Skype 业务上为客户端计算机、 移动电话或其他设备）： 
  
- 具有固件更新 5.4.1 的 Polycom VVX300
    
- 具有固件更新 5.4.1 的 Polycom VVX400
    
- 具有固件更新 5.4.1 的 Polycom VVX500
    
- 具有固件更新 5.4.1 的 Polycom VVX600
    
SLA 是 Skype 业务服务器中的新功能 11 月 2015年累积更新。 
  
有关部署 SLA 的信息，请参阅[部署共享行中的外观业务服务器 2015年的 Skype](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)。
  
## <a name="feature-list"></a>功能列表

设置 SLA 组可以实现以下功能：
  
- 组中的所有代理人都可以应答拨打同一共享号码的入站呼叫。呼叫可以是基于 PSTN 的也可以是基于 SIP 的。
    
- 代理人可以保持和接听呼叫。
    
- 代理人可以将呼叫转接到 SLA 组外部的号码。
    
- 代理人可以查看共享号码上当前存在的呼叫数，并查看每个呼叫的状态。
    
- 您可以为共享号码配置最大并发呼叫数。还可以设置在达到此最大数之后如何处理其他呼叫。额外呼叫可能会被忙音信号拒绝、转接到备用号码或者转接到语音邮件。
    
- 可以配置如何处理未接来电（在特定时间后未接听的呼叫）。如果为组标识启用语音邮件，未接来电将自动转到语音邮件。如果没有为组标识（共享号码）启用语音邮件，则可以选择通过忙音信号拒绝未接来电、将未接来电转接到备用号码或者断开连接。
    

