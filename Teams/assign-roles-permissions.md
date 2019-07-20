---
title: 在 Microsoft Teams 中分配团队所有者和成员
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中分配团队所有者和成员角色，包括创建团队的权限。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eca4f5350e4e06d3f598191e020b8708b6f47563
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2019
ms.locfileid: "35804766"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>在 Microsoft Teams 中分配团队所有者和成员
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft 团队内部有两个用户角色:**所有者**和**成员**。 默认情况下, 会向创建新团队的用户授予所有者状态。 此外, 所有者和成员可以拥有频道的审阅者功能 (前提是已设置了 "裁决")。 如果团队是从现有 Office 365 组创建的，则将继承权限。

下表显示了所有者和成员之间的权限差异。


|                                   | 团队所有者 | 团队成员 |
|-----------------------------------|------------|-------------|
|          **创建团队**          |    是<sup>1</sup>     |     否      |
|          **离开团队**           |    是     |     是     |
|  **编辑团队名称/说明**   |    是     |     否      |
|          **删除团队**          |    是     |     否      |
|          **添加频道**          |    是     |    是<sup>2</sup>|
| **编辑频道名称/说明** |    是     |    是<sup>2</sup>|
|        **删除频道**         |    是     |    是<sup>2</sup>|
|          **添加成员**          |  是<sup>3</sup>   |     无<sup>4</sup>    |
|          **请求添加成员**          |  不适用   |     是<sup>5</sup>     |
|           **添加选项卡**            |    是     |    是<sup>2</sup>|
|        **添加连接器**         |    是     |    是<sup>2</sup>|
|           **添加聊天机器人**            |    是     |    是<sup>2</sup>|

<sup>1</sup>团队所有者可以创建团队, 除非他们受到限制。 [创建团队的权限](#permissions-to-create-teams)。<br>
><sup>2</sup>所有者可以在团队级别关闭这些项目, 在这种情况下, 成员将无权访问它们。<br>
<sup>3</sup>将成员添加到团队后, 所有者还可以将成员提升为所有者状态。 所有者也可以将自己的状态降级为成员。<br>
<sup>4 个</sup>团队成员可以将其他成员添加到公共团队。<br>
<sup>5</sup>当团队成员无法直接将成员添加到专用团队时, 他们可以请求将某人添加到他们已成为其成员的团队。 当成员请求将某人添加到团队时, 团队所有者会收到通知, 通知他们具有他们可以接受或拒绝的待定请求。

> [!NOTE]
> 所有者可以在 "**查看团队**" 选项中使其他成员成为所有者。 一个团队最多可以有 100 个所有者。 我们建议您至少拥有少数几名所有者来帮助管理团队;如果一个所有者离开你的组织, 这还将阻止孤立组。 有关孤立群组的详细信息，请参阅[向孤立群组分配新所有者](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。

## <a name="moderator-capabilities"></a>版主功能

除了其他功能, 团队所有者和成员还可以拥有频道的审阅者功能 (前提是为团队启用了裁决)。 审阅人可以在频道中启动新的文章, 并控制团队成员是否可以答复现有频道消息。 他们还可以控制机器人和连接器是否可以提交频道消息。

版主功能在频道级别分配。 团队所有者默认具有 "审阅者" 功能。 默认情况下, 团队成员已关闭 "审阅者" 功能, 但团队所有者可以向团队成员提供频道的审阅者功能。 频道内的审阅人可以在该频道中添加和删除其他监督人。

有关审阅者功能的详细信息, 请参阅[在 Microsoft 团队中设置和管理频道裁决](manage-channel-moderation-in-teams.md)。

## <a name="assign-a-user-role"></a>分配用户角色

若要分配用户角色, 请在 "团队" 中选择团队名称, 然后单击 "**更多选项** > **管理团队**"。 在 "**成员**" 选项卡上, 您可以添加成员并选择 "所有者" 和 "审阅者" (如果您有足够的权限)。 有关详细信息, 请参阅[更改团队中的团队设置](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)。

## <a name="permissions-to-create-teams"></a>创建团队的权限

默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Office 365 组，进而有权在 Microsoft Teams 中创建团队。 你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Office 365 组的创建。 有关说明, 请参阅[管理可创建 Office 365 组的人员](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。


||||
|---------|---------|---------|
| ![表示决策点的图标](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |决策点         |是否所有 Microsoft Teams 用户都将能够创建团队（建议）？         |
| ![表示后续步骤的图标](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |后续步骤         |如果你需要限制可以创建团队的人员，请修改可以创建 Office 365 组的人员的默认权限         |
