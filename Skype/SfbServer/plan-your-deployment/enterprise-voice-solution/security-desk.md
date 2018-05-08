---
title: 在 Skype for Business Server 2015 中包含安全服务台
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: 规划如何将贵组织的安全服务台包含业务 Server 企业语音的 Skype E9-1-1 部署中。
ms.openlocfilehash: adaa1096651c5e3f86d15af1b2409a8de03e6c9c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="include-the-security-desk-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中包含安全服务台
 
规划如何将贵组织的安全服务台包含业务 Server 企业语音的 Skype E9-1-1 部署中。
  
公司可能要求安全服务台参与紧急呼叫。为帮助确定如何将安全服务台集成到 E9-1-1 部署，应回答以下问题。
  
**发出紧急呼叫时，是否希望通知安全服务台？**
  
您可以配置位置策略，以便 Skype 业务服务器向一个或多个安全人员业务 SIP 地址 Skype 发送即时消息 (IM) 通知。 这些警报包含拨打紧急呼叫的人员的姓名、号码和位置，并可在紧急情况下实现安全性。
    
**是否要在发出每个紧急呼叫时通知安全服务台？**
  
如果紧急服务服务提供商支持，可以将位置策略配置为在每个紧急呼叫中包含回拨号码。提供商随后使用此号码通知组织的安全人员参加有关紧急呼叫的会议。可在位置策略中将此会议配置为单向（仅侦听）或双向（双向）。
    
> [!NOTE]
> 如果需要，可针对每个位置策略配置不同的紧急服务人员。这允许您为公司内的不同区域自定义响应，或为来自与网络外部相对的网络内部的紧急呼叫创建不同的行为。您可使用通讯组指定要通知的人员。 
  

