---
title: 验证 Skype for Business 中的呼叫寄存的规范化规则
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 了解有关在 Skype 的呼叫寄存的规范化规则的业务 Server 企业语音。
ms.openlocfilehash: 794d64efcefbc4b36fac84e6356df46df76dc5a2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877274"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>验证 Skype for Business 中的呼叫寄存的规范化规则
 
了解有关在 Skype 的呼叫寄存的规范化规则的业务 Server 企业语音。
  
呼叫寄存轨道必须未标准化。 检查拨号计划以确保未对通道号码进行规范化。 如果您必须创建要进行规范化阻止您轨道其他规范化规则，请按照中的过程[创建或修改拨号计划中 Skype Business Server](dial-plans.md)因此定义新的规范化规则，该**模式与之匹配**标识的通道范围和**转换模式**是 **$1**。 例如，如果您呼叫寄存通道范围为 7000 7999**模式与之匹配**将 **^(7\d{3})$** **转换模式**， **$1**。
  
> [!IMPORTANT]
> 确保拨号计划中的默认规范化规则不包含 **^(\d\*)**。 否则，您呼叫寄存的规范化规则不会运行。
  
## <a name="see-also"></a>另请参阅

[创建或修改拨号计划中 Skype 业务服务器](dial-plans.md)

