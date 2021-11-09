---
title: 呼叫寄存
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: 当呼叫被取回时，该呼叫将转接到临时号码，呼叫将一直持续到有人取回或它退出。您需要配置一个表，该表包含要为已呼叫预留的分机号码范围。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 每个运行呼叫库应用程序的池都可以有一个或多个扩展范围。 这些范围在部署中必须是全局唯一的。
ms.openlocfilehash: 14c5ddbf3bd7f2d862cfd3f3e89310932964b8b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841564"
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

- **目标** FQDN 的完全限定 (FQDN) 或承载号码范围的呼叫托管应用程序的应用程序服务的服务 ID。

有关呼叫等待特性和功能的详细信息，请参阅 Plan [for Call Park in Skype for Business 2015。](../../plan-your-deployment/enterprise-voice-solution/call-park.md) 有关使用呼叫等待号码范围的详细信息，请参阅 Configure[电话 Number Extensions for Parking Calls。](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)