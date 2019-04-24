---
title: 会议配置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: 会议配置设置中定义的会议 (还 calledmeetings) 用户可以创建和控制如何 （或是否） 匿名用户和电话拨入式会议用户可以参加这些会议的类型。 这些设置仅适用于安排的会议。 它们不适用于通过单击客户端中的立即开会选项创建的临时会议。
ms.openlocfilehash: 32bbb6861271623e0a4126d98e36c28542ddfc8d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220317"
---
# <a name="meeting-configuration"></a>会议配置

会议配置设置定义用户可创建的会议类型，以及控制匿名用户和电话拨入式会议用户如何（或是否）可以加入这些会议。这些设置只适用于预定的会议，不适用于通过单击客户端中的“现在开会”选项创建的临时会议。

在全局级、站点级或池级上应用会议配置：

- **全局会议配置：** 默认情况下创建全局会议配置。 可以编辑全局会议配置，但无法将其删除。 如果您尝试删除全局会议配置，则所有设置将重置为默认值。

- **站点会议配置 （可选）：** 您可以创建一个或多个站点会议配置，其中每个适用于特定站点。 站点配置会覆盖全局配置。

- **池会议配置 （可选）：** 您可以创建一个或多个池会议配置，其中每个应用于一个特定的池。 池配置会覆盖全局配置和站点配置。

“**会议配置**”页显示一个为组织定义的所有会议配置的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**会议配置**”页上执行以下任务：

- 创建新的站点会议配置或池会议配置

- 更改全局配置或者现有站点配置或池配置

- 删除站点配置或池配置

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新**开始一个新的站点会议配置或池会议配置。

- **编辑**打开所选的会议配置以进行编辑，在列表中，选择所有会议配置或删除所选的站点配置或池配置。

    > [!NOTE]
    > 对于全局会议配置，“**删除**”会将设置重置为默认值。

- **刷新**刷新会议配置的列表。

下表介绍了该页上的各个字段。

- **名称**标识会议配置。

- **范围**标识会议配置的范围： 全局、 站点或池。

有关使用会议配置的详细信息，请参阅操作文档中的[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)。


