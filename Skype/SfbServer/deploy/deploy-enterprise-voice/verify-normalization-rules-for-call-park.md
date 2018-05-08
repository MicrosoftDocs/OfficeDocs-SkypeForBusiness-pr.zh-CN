---
title: 在 Skype for Business 2015 中验证呼叫寄存的规范化规则
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 了解有关在 Skype 的呼叫寄存的规范化规则的业务 Server 企业语音。
ms.openlocfilehash: c637240d4c193bbec05228d167d77f7bd18c0d04
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a>在 Skype for Business 2015 中验证呼叫寄存的规范化规则
 
了解有关在 Skype 的呼叫寄存的规范化规则的业务 Server 企业语音。
  
呼叫寄存轨道必须未标准化。 检查拨号计划以确保未对通道号码进行规范化。 如果您必须创建要进行规范化阻止您轨道其他规范化规则，请按照中的过程[创建或修改拨号计划中 Skype 业务服务器 2015年](dial-plans.md)因此定义新的规范化规则，该**模式与之匹配**标识的通道范围和**转换模式**是 **$1**。 例如，如果您呼叫寄存通道范围为 7000 7999**模式与之匹配**将 **^(7\d{3})$** **转换模式**， **$1**。
  
> [!IMPORTANT]
> 确保拨号计划中的默认规范化规则不包含 **^(\d\*)**。 否则，您呼叫寄存的规范化规则不会运行。
  
## <a name="see-also"></a>另请参阅

#### 

[创建或修改拨号计划中 Skype 业务服务器 2015](dial-plans.md)

