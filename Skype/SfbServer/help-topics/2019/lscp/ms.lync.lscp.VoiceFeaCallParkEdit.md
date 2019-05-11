---
title: 呼叫寄存创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: 呼叫寄存号码范围定义临时号码直到有人取回他们或其超时寄存的呼叫保存。
ms.openlocfilehash: 7573b64f93f10d1592d1beba2edf33fef626232b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33890849"
---
# <a name="call-park-create-new-or-edit-existing"></a>呼叫寄存：创建新的或编辑现有的

呼叫寄存号码范围定义临时号码直到有人取回他们或其超时寄存的呼叫保存。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称**键入标识号码范围的描述性名称。 保存的号码范围后，无法更改此名称。

- **号码范围**在第一个字段中，键入号码范围的开始号码。 在第二个字段中，键入号码范围的结束号码。

  - 该范围的起始号码必须小于或等于该范围的结束号码。

  - 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。

  - 号码范围必须是唯一的。该范围不能与其他任何范围重叠。

  - 如果号码范围以字符开头\*或 #，该范围必须大于 100。

  - 有效值： 必须匹配的正则表达式的字符串 ([\\* | #] ? [1-9] \d{0,7}) |([1-9] \d{0,8})。 这意味着的值必须是字符开头的字符串\*或 # 或数字 1 至 9 （的第一个字符不能为零）。 如果第一个字符是\*或 #，以下字符必须是数字 1 至 9 （不能为零）。 后续字符可以是任何数字 0 到 9 最多七个其他字符 (例如，"#6000"、"\*92000"，"\*95551212" 和"915551212")。 如果第一个字符不是\*或 #、 第一个字符必须是数字 1 至 9 （不能为零），最多八个字符后, 跟每个数字 0 到 9 (例如： 915551212; 41212; 300)。

  - 每个池不应包含 50,000 个以上的号码。每个号码范围包含的号码数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。

- **目标服务器的 FQDN**选择相应的完全限定的域名 (FQDN) 或服务 ID 承载呼叫寄存应用程序的应用程序服务。 所有呼叫都寄存的起始号指定的范围内的号码，并会向此服务器或池路由中的号码范围的结束号码。

有关呼叫寄存特性和功能的详细信息，请参阅[Plan for Business 的 Skype 中的呼叫寄存](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)。 有关使用呼叫寄存号码范围的详细信息，请参阅[寄存呼叫配置电话号码的扩展](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。


