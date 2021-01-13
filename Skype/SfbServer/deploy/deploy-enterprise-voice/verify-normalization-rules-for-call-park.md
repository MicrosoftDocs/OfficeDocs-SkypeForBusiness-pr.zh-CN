---
title: 验证 Skype for Business 中呼叫等待的规范化规则
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
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 了解 Skype for Business Server 企业语音 中的呼叫企业语音。
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830572"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>验证 Skype for Business 中呼叫等待的规范化规则
 
了解 Skype for Business Server 企业语音 中的呼叫企业语音。
  
不得对呼叫停叫通道进行规范化。 请检查拨号计划以确保通道号码未规范化。 如果必须创建其他规范化规则以防止对通道进行规范化，请按照 Skype [for Business Server](dial-plans.md)中的"创建或修改拨号计划"中的过程定义新的规范化规则，以便匹配的模式标识通道范围，转换模式为 **$1。**  例如，如果你的呼叫等待通道范围是 7000 - 7999，要 **匹配的** 模式是 **^ (7\d {3}) $** 和转换模式是 **$1。** 
  
> [!IMPORTANT]
> 请确保拨号计划中的默认规范化规则不包含 **^ (\d \*) 。** 否则，您的呼叫停止规范化规则将永远不会运行。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中创建或修改拨号计划](dial-plans.md)

