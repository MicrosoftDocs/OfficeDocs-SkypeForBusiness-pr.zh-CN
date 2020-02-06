---
title: 呼叫寄存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 当呼叫停止时，它将被转移到一个临时号码中，该号码一直保持通话，直到有人将其检索或超时。您需要使用您为寄存的呼叫保留的分机号码范围配置表。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 运行呼叫驻留应用程序的每个池可以有一个或多个扩展区域。 这些范围在部署中必须是全局唯一的。
ms.openlocfilehash: 7f4a660c3fdd1dbba5080b93bec0aac116d453ea
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797809"
---
# <a name="call-park"></a>呼叫寄存

当呼叫停止时，它将被转移到一个临时号码中，该号码一直保持通话，直到有人将其检索或超时。您需要使用您为寄存的呼叫保留的分机号码范围配置表。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 运行呼叫驻留应用程序的每个池可以有一个或多个扩展区域。 这些范围在部署中必须是全局唯一的。

"**呼叫驻留**" 页面显示为您的组织定义的所有呼叫寄存号码范围的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**呼叫寄存**”页上执行以下任务：

- 创建新的号码范围

- 更改现有号码范围

- 删除号码范围

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新**开始新的通话寄存号码范围。

- **编辑**打开所选的数字范围进行编辑，选择列表中的所有数字范围，或删除选定的数字范围。

- **刷新**刷新数字范围列表。

下表介绍了该页上的各个字段。

- **名称**标识数字范围的唯一名称。

- **开始范围**区域的起始编号。

- **结束范围**范围的结束编号。

- **目标**为数字范围托管呼叫寄存应用程序的应用程序服务的完全限定的域名（FQDN）或服务 ID。

有关呼叫寄存功能和功能的详细信息，请参阅[在 Skype For business 中计划通话寄存](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)。 有关使用呼叫寄存号码范围的详细信息，请参阅[配置停车通话的电话号码扩展](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。


