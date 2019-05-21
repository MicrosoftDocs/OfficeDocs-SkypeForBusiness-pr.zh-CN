---
title: 呼叫寄存 "新建" 或 "编辑现有"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 呼叫寄存号码范围定义了停用通话的临时号码, 直到有人检索它们或超时。
ms.openlocfilehash: 8e6748f0e106195148453094de3b95e9dc48254c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300102"
---
# <a name="call-park-create-new-or-edit-existing"></a>呼叫寄存：创建新的或编辑现有的

呼叫寄存号码范围定义了停用通话的临时号码, 直到有人检索它们或超时。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。

- **名称**键入标识数字范围的描述性名称。 保存号码范围后, 此名称不能更改。

- **数字范围**在第一个字段中, 键入数字范围的起始编号。 在第二个字段中, 键入数字范围的结束编号。

  - 该范围的起始号码必须小于或等于该范围的结束号码。

  - 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。

  - 号码范围必须是唯一的。该范围不能与其他任何范围重叠。

  - 如果数字范围以字符\*或 # 开头, 则范围必须大于100。

  - 有效值: 必须匹配正则表达式字符串 ([\\* | #] ? [1-9] \d{0,7}) |([1-9] \d{0,8})。 这意味着该值必须是以字符\*或 # 或数字1到9开头的字符串 (第一个字符不能为零)。 如果第一个字符是\*或 #, 则以下字符必须是1到9的数字 (不能为零)。 后续字符可以是0到9的任何数字, 最多可有7个附加字符 (例如, "\*#6000"、"\*92000"、"95551212" 和 "915551212")。 如果第一个字符不\*是或 #, 则第一个字符必须是数字1到 9 (不能为零), 后跟八个字符 (数字0到 9) (例如: 915551212; 41212; 300)。

  - 每个池不应包含 50,000 个以上的号码。每个号码范围包含的号码数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。

- **目标服务器的 FQDN**选择托管呼叫寄存应用程序的应用程序服务的完全限定的域名 (FQDN) 或服务 ID。 所有拨出的范围内的号码都将路由到此服务器或池, 并且数字范围内由起始号码和结束号码指定的范围内的电话。

有关呼叫寄存功能和功能的详细信息, 请参阅[在 Skype For business 2015 中计划呼叫寄存](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。 有关使用呼叫寄存号码范围的详细信息, 请参阅[配置停车通话的电话号码扩展](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。


