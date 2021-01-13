---
title: 未分配电话号码
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
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: 4b736aef028421bca6c4945095f9d293d18f3550
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826882"
---
# <a name="unassigned-phone-number"></a>未分配电话号码

未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。

配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码定制所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码并将其分配给提供新号码的通知。

> [!IMPORTANT]
> 在配置未分配号码表之前，必须已定义一个或多个通知，或已设置 Exchange UM 自动助理。

“未分配号码”页将显示一个为组织定义的未分配号码范围的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“未分配号码”页上执行以下任务：

- 创建新的未分配号码范围

- 更改现有未分配号码范围

- 删除未分配号码范围

- 更改未分配号码范围的顺序，以便确定对匹配未分配号码的传入呼叫首先应采取的操作。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新建** 启动新的未分配号码范围。

- **编辑** 打开选定的未分配号码范围进行编辑，选择列表中所有未分配号码范围，或删除所选的未分配号码范围。

- **上移** 将所选未分配号码范围向上移动，以便 Skype for Business Server 能够更早地找到该号码范围，并应用指定操作，然后再应用为列表中其他范围指定的操作。

    > [!NOTE]
    > Skype for Business Server 从上到下搜索未分配号码表，并使用与未分配号码匹配的第一个范围。 例如，如果有一个范围指定了最后一种操作，请确保将该范围置于列表底部。

- **下移** 在列表中将选定的未分配号码范围向下移动。

- **全部提交** 保存对未分配号码范围进行的所有更改。

    > [!IMPORTANT]
    > 该命令可保存您在“新建未分配号码”页和“编辑未分配号码”页上所做的全部更改。

- **刷新** 刷新未分配号码范围的列表。

下表介绍了该页上的各个字段。

- **名称** 标识未分配号码范围的唯一名称。

- **状态** 显示哪些号码范围已保存到数据库，哪些未保存到数据库中。

- **开始范围** 未分配号码范围的开始号码。

- **结束范围** 未分配号码范围的结束号码。

- **目标** 承载通知应用程序的应用程序服务的服务 ID，它将处理对此未分配号码范围的传入呼叫。

- **公告** 将为此未分配号码范围播放的公告。

有关通知特性和功能的详细信息，请参阅规划文档中[的 Plan for the Announcement application in Skype for Business 2015。](../../plan-your-deployment/enterprise-voice-solution/announcement.md) 有关使用未分配号码范围的详细信息，请参阅操作文档中的[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)。


