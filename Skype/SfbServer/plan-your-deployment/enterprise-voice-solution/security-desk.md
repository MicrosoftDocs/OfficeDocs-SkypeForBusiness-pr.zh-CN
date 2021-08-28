---
title: 将安全服务台包括在Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: 规划如何将组织的安全服务台包括在 E9-1-1 部署中，Skype for Business Server 企业语音。
ms.openlocfilehash: c99bdcbfaaaa74a5050c833dca3fd9a046ca41e5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615598"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>将安全服务台包括在Skype for Business Server
 
规划如何将组织的安全服务台包括在 E9-1-1 部署中，Skype for Business Server 企业语音。
  
公司可能要求安全服务台参与紧急呼叫。为帮助确定如何将安全服务台集成到 E9-1-1 部署，应回答以下问题。
  
**发出紧急呼叫时，是否希望通知安全服务台？**
  
您可以配置位置策略，以便Skype for Business Server向一个或多个安全人员的 Skype for Business SIP 地址发送即时消息 (IM) 警报。 这些警报包含拨打紧急呼叫的人员的姓名、号码和位置，并可在紧急情况下实现安全性。
    
**是否要在发出每个紧急呼叫时通知安全服务台？**
  
如果紧急服务服务提供商支持，可以将位置策略配置为在每个紧急呼叫中包含回拨号码。提供商随后使用此号码通知组织的安全人员参加有关紧急呼叫的会议。可在位置策略中将此会议配置为单向（仅侦听）或双向（双向）。
    
> [!NOTE]
> 如果需要，可针对每个位置策略配置不同的紧急服务人员。这允许您为公司内的不同区域自定义响应，或为来自与网络外部相对的网络内部的紧急呼叫创建不同的行为。您可使用通讯组指定要通知的人员。 
  

