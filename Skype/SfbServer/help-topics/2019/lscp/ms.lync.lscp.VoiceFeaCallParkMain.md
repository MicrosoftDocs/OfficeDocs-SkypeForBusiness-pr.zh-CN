---
title: 呼叫寄存
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 当呼叫被转接到临时号码时，呼叫将一直等待，直到有人取回或该呼叫退出。您需要配置一个表，该表包含要保留用于已呼叫的分机号码范围。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 运行呼叫库应用程序的每个池可以具有一个或多个扩展范围。 这些范围在部署中必须是全局唯一的。
ms.openlocfilehash: 679e13cdeb6ef6cf614f5703f5711e86fa1c8c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812162"
---
# <a name="call-park"></a>呼叫寄存

当呼叫被转接到临时号码时，呼叫将一直等待，直到有人取回或该呼叫退出。您需要配置一个表，该表包含要保留用于已呼叫的分机号码范围。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 运行呼叫库应用程序的每个池可以具有一个或多个扩展范围。 这些范围在部署中必须是全局唯一的。

" **呼叫等待** "页显示为组织定义的所有呼叫等待号码范围的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“呼叫寄存”页上执行以下任务：

- 创建新的号码范围

- 更改现有号码范围

- 删除号码范围

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新建** 启动一个新的呼叫呼叫管理号码范围。

- **编辑** 打开所选号码范围进行编辑，选择列表中的所有号码范围，或删除所选号码范围。

- **刷新** 刷新号码范围列表。

下表介绍了该页上的各个字段。

- **名称** 标识号码范围的唯一名称。

- **开始范围** 范围的开始编号。

- **结束范围** 范围的结束号码。

- **目标** FQDN 的 (FQDN) 或承载号码范围的呼叫托管应用程序的应用程序服务的服务 ID。

有关呼叫等待特性和功能的详细信息，请参阅 Plan [for Call Park in Skype for Business。](../../../plan-your-deployment/enterprise-voice-solution/call-park.md) 有关使用呼叫等待号码范围的详细信息，请参阅配置用于"呼叫等待" [的电话号码分机号](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。


