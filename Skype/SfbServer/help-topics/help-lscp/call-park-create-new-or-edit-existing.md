---
title: 呼叫管理创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 呼叫等待号码范围定义临时号码，在有人取回或呼叫时间过长之前，将一直呼叫该临时号码。
ms.openlocfilehash: 1a85bacf1ebb13afd7302f8e1cf50c112c3139e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095676"
---
# <a name="call-park-create-new-or-edit-existing"></a>呼叫寄存：创建新的或编辑现有的

呼叫等待号码范围定义临时号码，在有人取回或呼叫时间过长之前，将一直呼叫该临时号码。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称** 键入标识号码范围的描述性名称。 保存号码范围后，此名称将无法更改。

- **号码范围** 第一个字段中，键入号码范围的开始编号。 第二个字段中，键入号码范围的结束号码。

  - 该范围的起始号码必须小于或等于该范围的结束号码。

  - 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。

  - 号码范围必须是唯一的。该范围不能与其他任何范围重叠。

  - 如果号码范围以字符或 #开头，则范围 \* 必须大于 100。

  - 有效值：必须与正则表达式字符串匹配 ([ \\ *|#]？[1-9]\d {0,7}) | ([1-9]\d {0,8}) 。 这意味着该值必须是以字符或 # 或数字 1 到 9 开头的字符串 (第一个字符不能为 \* 零) 。 如果第一个字符是 或 #，则下一个字符必须是 1 到 \* 9 (不能是零) 。 后续字符可以是 0 到 9 之间的任意数字 (例如 \* ，"#6000"、"92000"、"95551212"和 \* "915551212") 。 如果第一个字符不是 或 #，则第一个字符必须是数字 1 到 9 (不能为零) ，后跟最多八个字符，每个字符从 0 到 \* 9 (例如：915551212;41212;300) 。

  - 每个池不应包含 50,000 个以上的号码。每个号码范围包含的号码数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。

- **目标服务器的 FQDN** 选择托管呼叫 (的应用程序) FQDN 的完全限定域名或服务 ID。 该号码范围中由起始号码和结束号码指定的范围内的号码的所有呼叫都将路由到此服务器或池。

有关呼叫等待特性和功能的详细信息，请参阅 Plan [for Call Park in Skype for Business 2015。](../../plan-your-deployment/enterprise-voice-solution/call-park.md) 有关使用呼叫等待号码范围的详细信息，请参阅 Configure [Phone Number Extensions for Parking Calls。](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)