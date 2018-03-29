---
title: 调用公园新建或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 调用公园数字范围定义人检索它们也下班时间之前排队的调用保存的临时数字。
ms.openlocfilehash: 840caf654e1264d7355f117303e8ded9efbca7d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="call-park-create-new-or-edit-existing"></a>呼叫寄存：创建新的或编辑现有的
 
调用公园数字范围定义人检索它们也下班时间之前排队的调用保存的临时数字。
  
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。
  
- **名称**键入一个描述性的名称，用于标识的范围。 保存的范围之后，无法更改此名称。
    
- **编号范围**在第一个字段中，键入起始数的范围。 在第二个字段中，键入结束的范围数。
    
  - 该范围的起始号码必须小于或等于该范围的结束号码。
    
  - 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。
    
  - 号码范围必须是唯一的。该范围不能与其他任何范围重叠。
    
  - 如果字符开头的数字范围\*或 #，范围必须是大于 100。
    
  - 有效值： 必须匹配的正则表达式字符串 ([\\* | #] ?[1-9]\d{0,7}) |([1-9] \d {0,8})。 这意味着该值必须是一个任意的字符开头的字符串\*# 或数字 1 到 9 （第一个字符不能为零）。 如果第一个字符是\*或 #，下面的字符必须是一个数字 1 到 9 （不能为零）。 后面的字符可以是任意数字 0 到 9，最多七个其他字符 (例如，"#6000"、"\*92000"、"\*95551212"，和"915551212")。 如果第一个字符不是\*#，第一个字符必须为最多八个字符后, 跟一个数字 1 到 9 （不能为零），或每个数字 0 到 9 (例如： 915551212; 41212; 300)。
    
  - 每个池不应包含 50,000 个以上的号码。每个号码范围包含的号码数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。
    
- **目标服务器的 FQDN**选择完全合格的域名称 (FQDN) 或服务呼叫公园应用程序宿主的应用程序服务的 ID。 所有电话都停到指定起始数的范围之内的数字和数字范围内的最终数字将路由到此服务器或池。
    
有关调用公园的特性和功能的详细信息，请参阅[规划中业务 2015年的 Skype 通话公园](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。 有关使用调用公园数字范围的详细信息，请参阅[配置电话号码停车调用扩展](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。
  

