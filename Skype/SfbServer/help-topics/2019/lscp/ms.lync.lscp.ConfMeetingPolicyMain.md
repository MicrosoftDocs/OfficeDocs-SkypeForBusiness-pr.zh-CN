---
title: 会议策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
ROBOTS: NOINDEX, NOFOLLOW
description: 会议策略定义会议期间用户可以使用的各种功能。
ms.openlocfilehash: 23377ce4974be1139cf5ff3e7d090cb83d8f2504
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824862"
---
# <a name="conferencing-policy"></a>会议策略

会议策略定义会议期间用户可以使用的各种功能。

会议策略包括全局策略以及可选的一个或多个站点和用户策略：

- **全局策略：** 默认情况下，将创建全局策略。 可以编辑全局策略，但无法将其删除。 如果您尝试删除全局策略，则所有设置将重置为默认值。

- **网站策略 (可选) ：** 可以创建一个或多个站点会议策略，每个策略都适用于特定站点。 站点策略会覆盖全局策略。

- **用户策略 (可选) ：** 可以创建一个或多个用户会议策略，每个策略都适用于特定用户或用户组。 用户策略会覆盖全局策略和站点策略。

“会议策略”页将显示一个为组织定义的所有会议策略的列表。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“位置策略”页上执行以下任务：

- 创建新的站点会议策略或用户会议策略

- 更改全局策略或现有站点策略或用户策略

- 删除站点策略或用户策略

## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。

- **新建** 启动新的站点会议策略或用户会议策略。

- **编辑** 打开所选会议策略进行编辑，选择列表中的所有会议策略，或删除所选的站点策略或用户策略。

    > [!NOTE]
    > 对于全局策略，“删除”会将设置重置为默认值。

- **刷新** 刷新会议策略列表。

下表介绍了该页上的各个字段。

- **名称** 标识会议策略。

- **范围** 标识会议策略的范围：全局、站点或用户。

- **数据协作** 如果会议策略指定允许在会议中进行数据协作，则选中。

- **应用程序共享** 如果会议策略指定允许在会议中共享应用程序，则选中。

- **音频** 如果会议策略指定会议允许音频，则选中。

- **视频** 如果会议策略指定会议允许视频，则选中。

- **PSTN** 如果会议策略指定允许 PSTN 电话拨入式会议，则选中。

- **录制** 如果会议策略指定允许在会议中录制，则选中。

有关会议特性和功能的详细信息，请参阅规划文档中的[Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)。 有关使用会议策略的详细信息，请参阅操作文档中的[Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)。


