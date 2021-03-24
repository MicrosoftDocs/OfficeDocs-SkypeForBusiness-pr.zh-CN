---
title: 会议配置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: 会议配置设置定义会议类型 (也称为会议) 用户可以创建的会议类型，并控制 (或) 匿名用户和电话拨入式会议用户是否可以加入这些会议。 这些设置仅适用于安排的会议。 它们不适用于通过单击客户端中的"现在开会"选项创建临时会议。
ms.openlocfilehash: 053378ef694a66413f11760be5f449cd21e6b764
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095966"
---
# <a name="meeting-configuration"></a>会议配置

会议配置设置定义会议类型 (也称为"会议") 用户可以创建的会议类型，并控制 (或) 匿名用户和电话拨入式会议用户是否可以加入这些会议。 这些设置仅适用于安排的会议。 它们不适用于通过单击客户端中的"现在开会"选项创建临时会议。

在全局级、站点级或池级上应用会议配置：

- **全局会议配置：** 默认情况下，将创建全局会议配置。 可以编辑全局会议配置，但无法将其删除。 如果您尝试删除全局会议配置，则所有设置将重置为默认值。

- **站点会议配置 (可选) ：** 可以创建一个或多个站点会议配置，其中每个配置都适用于特定站点。 站点配置会覆盖全局配置。

- **池会议配置 (可选) ：** 可以创建一个或多个池会议配置，每个配置都适用于特定池。 池配置会覆盖全局配置和站点配置。

“会议配置”页显示一个为组织定义的所有会议配置的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“会议配置”页上执行以下任务：

- 创建新的站点会议配置或池会议配置

- 更改全局配置或者现有站点配置或池配置

- 删除站点配置或池配置

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新建** 启动新的站点会议配置或池会议配置。

- **编辑** 打开所选会议配置以对其进行编辑，选择列表中的所有会议配置，或删除所选的站点配置或池配置。

    > [!NOTE]
    > 对于全局会议配置，“删除”会将设置重置为默认值。

- **刷新** 刷新会议配置列表。

下表介绍了该页上的各个字段。

- **名称** 标识会议配置。

- **范围** 标识会议配置的范围：全局、站点或池。

有关使用会议配置的详细信息，请参阅操作文档中的[Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings)。