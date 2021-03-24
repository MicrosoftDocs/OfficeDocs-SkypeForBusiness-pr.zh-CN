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
description: 当呼叫被取回时，该呼叫将转接到临时号码，呼叫将一直持续到有人取回或它退出。您需要配置一个表，该表包含要为已呼叫预留的分机号码范围。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 每个运行呼叫库应用程序的池都可以有一个或多个扩展范围。 这些范围在部署中必须是全局唯一的。
ms.openlocfilehash: b7926c10424fd5902fdc43e6c0fccadb45e61f79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097068"
---
# <a name="call-park"></a>呼叫寄存

当呼叫被取回时，该呼叫将转接到临时号码，呼叫将一直持续到有人取回或它退出。您需要配置一个表，该表包含要为已呼叫预留的分机号码范围。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 每个运行呼叫库应用程序的池都可以有一个或多个扩展范围。 这些范围在部署中必须是全局唯一的。

The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“呼叫寄存”页上执行以下任务：

- 创建新的号码范围

- 更改现有号码范围

- 删除号码范围

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新建** 启动一个新的呼叫管理号码范围。

- **编辑** 打开选定的号码范围进行编辑，选择列表中的所有号码范围，或删除选定的号码范围。

- **刷新** 刷新号码范围列表。

下表介绍了该页上的各个字段。

- **名称** 标识号码范围的唯一名称。

- **起始范围** 范围的开始编号。

- **结束范围** 范围的结束号码。

- **目标** FQDN 的 (FQDN) 或托管号码范围的呼叫托管应用程序的应用程序服务的服务 ID。

有关呼叫等待特性和功能的详细信息，请参阅 Plan [for Call Park in Skype for Business。](../../../plan-your-deployment/enterprise-voice-solution/call-park.md) 有关使用呼叫等待号码范围的详细信息，请参阅 Configure [Phone Number Extensions for Parking Calls。](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)