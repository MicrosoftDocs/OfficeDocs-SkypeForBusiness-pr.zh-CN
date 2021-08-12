---
title: 在呼叫管理中验证呼叫Skype for Business
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
description: 了解呼叫管理中心中呼叫Skype for Business Server 企业语音。
ms.openlocfilehash: 5c357a9ff9b2174ae414e1e4511cb7ebf267e19787091e19ce27f75f90b8a51e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298612"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>在呼叫管理中验证呼叫Skype for Business
 
了解呼叫管理中心中呼叫Skype for Business Server 企业语音。
  
不能对呼叫存储通道进行规范化。 请检查拨号计划，确保通道号码未规范化。 如果必须创建其他规范化规则以防止对通道进行规范化，请按照在 Skype for Business Server 创建或修改拨号计划中的过程来定义新的规范化规则，以便要匹配的 **模式** 标识通道范围，转换模式为 **$1。** [](dial-plans.md) 例如，如果呼叫等待通道范围为 7000 - 7999，则要匹配的模式为 **^ (7\d {3}) $，** 转换模式为 **$1。** 
  
> [!IMPORTANT]
> 请确保拨号计划中的默认规范化规则不包含 **^ (\d \*)**。 否则，您的呼叫停止规范化规则将永远不会运行。
  
## <a name="see-also"></a>另请参阅

[在拨号计划中创建或修改Skype for Business Server](dial-plans.md)

