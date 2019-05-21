---
title: 在 Skype for Business 中验证呼叫寄存的规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 了解 Skype for business Server Enterprise Voice 中的呼叫寄存的规范化规则。
ms.openlocfilehash: 36e9a91ff1269caffb8eab5be9a2c681d3244b31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300935"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>在 Skype for Business 中验证呼叫寄存的规范化规则
 
了解 Skype for business Server Enterprise Voice 中的呼叫寄存的规范化规则。
  
调用寄存轨道式不得正常化。 检查拨号计划以确保未对通道号码进行规范化。 如果必须创建另一个规范化规则来防止你的轨道式被正常化, 请按照在[Skype For Business 服务器中创建或修改拨号计划中](dial-plans.md)的过程定义新的规范化规则, 以便**匹配模式**标识 "轨道" 区域和**翻译模式**为 **$1**。 例如, 如果您的呼叫公园的 "轨道" 范围为 7000-7999, 则**要匹配的模式**为 **^{3}(7 \ d) $** 和**转换模式**为 **$1**。
  
> [!IMPORTANT]
> 请确保你的拨号计划中的默认规范化规则不包含 **^ (\d\*)**。 否则, 您的通话寄存规范化规则将永远不会运行。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中创建或修改拨号计划](dial-plans.md)

