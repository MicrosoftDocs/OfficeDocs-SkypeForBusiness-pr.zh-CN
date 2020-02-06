---
title: 选择转换规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: 对于执行反向数字查找（RNL），企业语音要求将所有拨号字符串正常化为 E-164 格式。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
ms.openlocfilehash: c16c5676eec0659d4cfe47bb878ca4955576a3fc
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798109"
---
# <a name="select-translation-rules"></a>选择转换规则
 
 对于执行反向数字查找（RNL），企业语音要求将所有拨号字符串正常化为 E-164 格式。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
  
> [!IMPORTANT]
> 将一个或多个翻译规则与企业语音中继配置相关联的功能旨在用作在中继对等上配置翻译规则的替代方法。 如果你已在中继对等上配置了转换规则，请不要将翻译规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。 
  
要使用现有的转换规则，请单击列表中的某个规则，然后单击“**确定**”。
  
 
  

