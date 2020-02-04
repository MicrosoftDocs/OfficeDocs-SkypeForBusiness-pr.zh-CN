---
title: 会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: 会议策略定义用户在会议（也称为会议）期间可用的功能和功能。
ms.openlocfilehash: 6649471efd9d8d592de1e9395fd6eba8eadb9e23
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700417"
---
# <a name="conferencing-policy"></a>会议策略

会议策略定义用户在会议（也称为会议）期间可用的功能和功能。

会议策略包括全局策略和一个或多个网站和用户策略（可选）：

- **全球政策：** 默认情况下会创建全局策略。 可以编辑全局策略，但无法将其删除。 如果您尝试删除全局策略，则所有设置将重置为默认值。

- **网站策略（可选）：** 你可以创建一个或多个网站会议策略，每个策略都适用于特定网站。 站点策略会覆盖全局策略。

- **用户策略（可选）：** 你可以创建一个或多个用户会议策略，每个策略都适用于特定用户或用户组。 用户策略会覆盖全局策略和站点策略。

"**会议策略**" 页面显示为你的组织定义的所有会议策略的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**位置策略**”页上执行以下任务：

- 创建新的网站会议策略或用户会议策略

- 更改全局策略或现有站点策略或用户策略

- 删除站点策略或用户策略

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新**启动新的 "网站会议策略" 或 "用户会议策略"。

- **编辑**打开所选的会议策略以对其进行编辑，选择列表中的所有会议策略，或删除所选网站策略或用户策略。

    > [!NOTE]
    > 对于全局策略，“**删除**”会将设置重置为默认值。

- **刷新**刷新会议策略列表。

下表介绍了该页上的各个字段。

- **名称**标识会议策略。

- **范围**标识会议策略的范围：全局、网站或用户。

- **数据协作**已检查会议策略是否指定允许在会议中使用数据协作。

- **应用程序共享**已检查会议策略是否指定允许在会议中使用应用程序共享。

- **音频**已检查会议策略是否指定允许在会议中使用音频。

- **视频**已检查会议策略是否指定会议中允许视频。

- **PSTN**已检查会议策略是否指定允许 PSTN 电话拨入式会议。

- **录制**已检查会议策略是否指定允许在会议中录制。

有关会议特性和功能的详细信息，请参阅规划文档中的[Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)。有关使用会议策略的详细信息，请参阅操作文档中的[Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)。


