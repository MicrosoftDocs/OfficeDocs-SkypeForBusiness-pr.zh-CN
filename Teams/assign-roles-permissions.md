---
title: 在 Microsoft Teams 中分配团队所有者和成员
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中分配团队所有者和成员角色，包括创建团队的权限。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a8993882bb281dc7c9bd6b8bde95387a183b637
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562761"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams"></a>在 Microsoft Teams 中分配团队所有者和成员

在 Microsoft Teams 中有两种用户角色：**所有者** 和 **成员**。 默认情况下，会为创建新团队的用户授予所有者状态。 此外，团队所有者和成员可以拥有频道的审核员功能（前提是设置了审核）。 如果团队是从现有 Microsoft 365 组创建的，则会继承权限。

下表显示了所有者与成员之间的权限差异。


|    任务                               | 团队所有者 | 工作组成员 |
|-----------------------------------|------------|-------------|
|          **创建团队**          |    是<sup>1</sup>     |     否      |
|          **离开团队**           |    是     |     是     |
|  **编辑团队名称/说明**   |    是     |     否      |
|          **删除团队**          |    是     |     否      |
|          **添加标准频道**          |    是     |    是<sup>2</sup>|
| **编辑标准频道名称/说明** |    是     |    是<sup>2</sup>|
|        **删除标准频道**         |    是     |    是<sup>2</sup>|
|          ***添加私人频道**          |    是     |    是<sup>2</sup>|
| ***编辑私人频道名称/说明** |    否     |    不适用|
|        ***删除专用通道**         |    是     |    否|
|          **添加共享通道**          |    是     |    否|
| **编辑共享频道名称/说明** |    弱     |    No<sup>6</sup>|
|        **删除共享频道**         |    是     |    No<sup>6</sup>|
|          **添加成员**          |  是<sup>3</sup>   |     否<sup>4</sup>    |
|          **请求添加成员**          |  不适用   |     是<sup>5</sup>     |
|           **添加应用**            |    是     |    是<sup>2</sup>|

<sup>1</sup> 团队所有者可创建团队，除非他们受到限制。 如下[创建团队的权限](#permissions-to-create-teams)。<br>
<sup>2</sup> 所有者可以在团队级别关闭这些项目，在这种情况下，成员将不能访问它们。<br>
<sup>3</sup> 向团队添加成员后，所有者也可以将成员提升到所有者状态。 此外，所有者也可以将自己的状态降级为成员。<br>
<sup>4</sup> 团队成员可以向公共团队中添加其他成员。<br>
<sup>5</sup> 尽管团队成员无法直接将成员添加到私人团队，但可以请求将某人添加到他们所属的团队。 当成员请求将某人添加到团队时，团队所有者将收到通知，告知他们有一个可接受或拒绝的待定请求。<br>
<sup>6</sup> 如果团队成员是共享频道所有者，他们可以执行此操作。

了解更多关于私人频道访问权限的信息，请参阅[Teams 中的私人频道](private-channels.md)。

> [!NOTE]
> 所有者可以在“查看团队”选项中将其他成员设为所有者。 一个团队可以拥有最多 100 个所有者。 建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。 有关孤立组的详细信息，请参阅[将新的所有者分配到孤立组](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。

## <a name="moderator-capabilities"></a>审核员功能

除了其他功能之外，团队所有者和成员还可以拥有频道的审核员功能（前提是针对团队启用了审核）。 审核员可以在频道中发布新帖子，并控制团队成员能否回复现有频道消息。 审查器还可以控制具有机器人和连接器功能的应用是否可以提交频道消息。

审核员功能在频道级别分配。 默认情况下，团队所有者拥有审核员功能。 默认情况下，团队成员已关闭审核员功能，但是团队所有者可向团队成员提供频道审核员功能。 频道内的审核员可在该渠道中添加或删除其他审核员。

有关审核员功能详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。

## <a name="assign-a-user-role"></a>分配用户角色

若要分配用户角色，请在 Teams 中选择团队名称，然后 (**...**) >**管理团队** 选择 **更多选项**。 在“成员”选项卡上，可以添加成员并选择所有者和审核员（如果你有足够的权限）。 有关详细信息，请参阅 [Teams 中的更改团队设置](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)。

> [!NOTE]
> 对于固定频道，不会显示“ **管理团队** ”选项。 在下方的 *“团队*”下选择团队名称，然后选择 (**...**) 名称右侧的 **“更多”选项**。

## <a name="permissions-to-create-teams"></a>创建团队的权限

默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Microsoft 365 组，进而有权在 Microsoft Teams 中创建团队。 你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Microsoft 365 组的创建。 有关说明，请参阅[管理哪些人可以创建 Microsoft 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。
