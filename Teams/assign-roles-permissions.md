---
title: 在 Microsoft Teams 中分配角色和权限
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中分配团队所有者和成员角色，包括创建团队的权限。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98ec3b95395a3d972af245f6653ea0294cfa670d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856312"
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a>在 Microsoft Teams 中分配角色和权限
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

在 Microsoft Teams 中有两种角色：**所有者**和**成员**。 默认情况下，会为创建新团队的用户授予所有者状态。 如果团队是从现有 Office 365 组创建的，则将继承权限。

下表显示了所有者与成员之间的权限差异：

|  |团队所有者  |团队成员  |
|---------|---------|---------|
|**创建团队**     |是        |否         |
|**离开团队**     |是         |是         |
|**编辑团队名称/说明**      |是         |否         |
|**删除团队**      |是         |否         |
|**添加频道**      |是         |是*         |
|**编辑频道名称/说明**      |是         |是*         |
|**删除频道**      |是         |是*         |
|**添加成员**      |是**         |否         |
|**添加选项卡**      |是         |是*         |
|**添加连接器**      |是         |是*         |
|**添加聊天机器人**      |是         |是*         |
\* 所有者可以在团队级别关闭这些项，这样成员将无权访问相应项。

\*\*向团队添加成员后，所有者也可以将成员提升到所有者状态。 此外，所有者也可以将自己的状态降级为成员。



> [!NOTE]
> 所有者可以在“查看团队”选项中将其他成员设为所有者。 一个团队最多可以有 100 个所有者。 建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。 有关孤立群组的详细信息，请参阅[向孤立群组分配新所有者](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。


<a name="permissions-to-create-teams"></a>创建团队的权限
---------------------------

默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Office 365 组，进而有权在 Microsoft Teams 中创建团队。 你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Office 365 组的创建。 有关说明，请参阅[的管理可以创建 Office 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。


||||
|---------|---------|---------|
| ![决策点图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |决策点         |是否所有 Microsoft Teams 用户都将能够创建团队（建议）？         |
| ![后续步骤图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |后续步骤         |如果你需要限制可以创建团队的人员，请修改可以创建 Office 365 组的人员的默认权限         |
