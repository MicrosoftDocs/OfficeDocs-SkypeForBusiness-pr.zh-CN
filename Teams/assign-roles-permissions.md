---
title: 在 Microsoft Teams 中分配团队所有者和成员
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
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
ms.openlocfilehash: 0c7343f294f18d5aaacf01059459524cdd2700a2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195022"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>在 Microsoft Teams 中分配团队所有者和成员
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft 团队中有两个用户角色：**所有者**和**成员**。 默认情况下，创建新的工作组的用户被授予所有者状态。 如果团队是从现有 Office 365 组创建的，则将继承权限。

下表显示在权限所有者和某个成员之间的差异。


|                                   | 团队所有者 | 团队成员 |
|-----------------------------------|------------|-------------|
|          **创建团队**          |    是<sup>1</sup>     |     否      |
|          **离开团队**           |    是     |     是     |
|  **编辑团队名称/说明**   |    是     |     否      |
|          **删除团队**          |    是     |     否      |
|          **添加频道**          |    是     |    是<sup>2</sup>|
| **编辑频道名称/说明** |    是     |    是<sup>2</sup>|
|        **删除频道**         |    是     |    是<sup>2</sup>|
|          **添加成员**          |  是<sup>3</sup>   |     没有<sup>4</sup>    |
|          **请求添加成员**          |  不适用   |     是<sup>5</sup>     |
|           **添加选项卡**            |    是     |    是<sup>2</sup>|
|        **添加连接器**         |    是     |    是<sup>2</sup>|
|           **添加聊天机器人**            |    是     |    是<sup>2</sup>|

<sup>1</sup>除非他们已被禁止这样做，团队所有者可创建团队。 请参阅下面的"创建工作组的权限"。
>
<sup>2</sup>这些项可以关闭所有者在团队级别中，在这种情况下成员不会对它们的访问。

<sup>3</sup>后添加到团队的成员，所有者可以升级到所有者状态成员。 还有可能的所有者降级成员自己状态。

<sup>4</sup>工作组成员可以将其他成员添加到公共团队。

<sup>5</sup>时团队成员无法直接将成员添加到专用团队，它们可以请求某人添加到组中已经存在的成员。 当成员请求某人添加到组中时，团队所有者将收到通知他们具有挂起的申请，他们可以接受或拒绝。



> [!NOTE]
> 所有者可以在“查看团队”选项中将其他成员设为所有者。 一个团队最多可以有 100 个所有者。 建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。 有关孤立群组的详细信息，请参阅[向孤立群组分配新所有者](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。


<a name="permissions-to-create-teams"></a>创建团队的权限
---------------------------

默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Office 365 组，进而有权在 Microsoft Teams 中创建团队。 你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Office 365 组的创建。 有关说明，请参阅[的管理可以创建 Office 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。


||||
|---------|---------|---------|
| ![决策点图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |决策点         |是否所有 Microsoft Teams 用户都将能够创建团队（建议）？         |
| ![后续步骤图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |后续步骤         |如果你需要限制可以创建团队的人员，请修改可以创建 Office 365 组的人员的默认权限         |
