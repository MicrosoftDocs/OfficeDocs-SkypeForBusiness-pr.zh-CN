---
title: 未分配电话号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: 910b83f18350bc2a26da281f2e0660e8aa8913b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690387"
---
# <a name="unassigned-phone-number"></a>未分配电话号码

> [!NOTE]
> 将 Skype for business 2019 与 Exchange 2013 或 Exchange 2016 集成时，exchange UM 将在 Skype for business Server 2019 中保持可用。 由于 Exchange 2019 中的支持的更改，Exchange UM 集成已被取消重点，取而代之的是云语音邮件和云自动助理功能。

未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。

配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码定制所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码并将其分配给提供新号码的通知。

> [!IMPORTANT]
> 在配置未分配号码表之前，必须已定义一个或多个通知，或已设置 Exchange UM 自动助理。

“**未分配号码**”页将显示一个为组织定义的未分配号码范围的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**未分配号码**”页上执行以下任务：

- 创建新的未分配号码范围

- 更改现有未分配号码范围

- 删除未分配号码范围

- 更改未分配号码范围的顺序，以便确定对匹配未分配号码的传入呼叫首先应采取的操作。

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新**启动新的未分配的号码范围。

- **编辑**打开所选的未分配的号码范围进行编辑，选择列表中的所有未分配号码范围，或删除所选的未分配号码范围。

- **上移**将所选的未分配的号码范围在列表中上移，以便 Skype for Business 服务器更快地发现它，并在应用为列表中的其他范围指定的操作之前应用指定的操作。

    > [!NOTE]
    > Skype for Business 服务器从上到下搜索 "未分配的号码" 表，并使用与未分配号码匹配的第一个区域。 例如，如果有一个范围指定了最后一种操作，请确保将该范围置于列表底部。

- **下移**将选定的未分配的号码范围向下移动到列表中。

- **全部提交**保存对未分配的号码范围所做的所有更改。

    > [!IMPORTANT]
    > 该命令可保存您在“**新建未分配号码**”页和“**编辑未分配号码**”页上所做的全部更改。

- **刷新**刷新未分配的号码范围列表。

下表介绍了该页上的各个字段。

- **名称**标识未分配的号码范围的唯一名称。

- **状态**显示已将哪些数字范围保存到数据库中，哪些尚未保存。

- **开始范围**未分配的号码范围的起始编号。

- **结束范围**未分配的号码范围的结束编号。

- **目标**托管公告应用程序的应用程序服务的服务 ID 将处理传入呼叫到此范围的未分配号码。

- **公告**将为此未分配号码范围播放的公告。

有关公告功能和功能的详细信息，请参阅规划文档中的[Skype For business 中的公告应用程序计划](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)。 有关使用未分配号码范围的详细信息，请参阅操作文档中的[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)。


