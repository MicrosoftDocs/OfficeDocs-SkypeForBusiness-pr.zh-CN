---
title: 在 Microsoft Teams 管理中心分配团队所有者和成员
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
ms.openlocfilehash: e0f259a7a24552988d4eca503deeb9151dde144d
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019408"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心分配团队所有者和成员

**所有者** 和 **成员** 是 Microsoft Teams 中的两个用户角色。 默认情况下，创建新团队的用户被授予所有者状态。 所有者和成员在与团队及其频道交互时具有不同类型的权限和功能。 有关 [Teams 中的角色的详细信息，请参阅 Microsoft Teams 中的团队和频道概述](teams-channels-overview.md) 。

> [!NOTE]
> 如果团队是从现有 Microsoft 365 组创建的，则会继承权限。

## <a name="assign-a-user-role-in-teams-admin-center"></a>在 Teams 管理中心分配用户角色

1. 在 Teams 管理中心中，展开 **“Teams** ”，然后选择“ **管理团队**”。
2. 在“显示名称”列下选择团队名称。
3. 在“成员”选项卡中，可以添加或删除成员，并向成员分配所有者和审查者角色。

## <a name="restrict-permission-to-create-teams"></a>限制创建团队的权限

Exchange Online中具有邮箱的所有用户都有权在 Microsoft Teams 中创建 Microsoft 365 组和团队。 通过将组创建和管理权限委托给一组用户来限制用户创建新团队和 Microsoft 365 组。 如果此限制处于活动状态，则团队所有者或成员都不能创建新团队。 有关详细信息，请参阅[管理哪些人可以创建 Microsoft 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。

## <a name="user-permissions-based-on-assigned-roles"></a>基于分配的角色的用户权限

下表显示了所有者与成员之间的权限差异。

### <a name="teams"></a>Teams

|Teams 任务| 团队所有者 | 工作组成员 |
|---------|---------|---------|
|创建/删除团队  |    是     |     否    |
|编辑团队名称/说明   |     是    |     否     |
|将成员添加到专用团队    |     是    |  否 |
|将成员添加到公共团队    |     是    |     是   |
|请求添加新成员   |     不适用    |    是   |
|提升/降级用户状态 | 是 | 否 |
|离开团队  |    是     |     是    |
|添加/删除应用   |     是    |     是，如果由团队所有者启用     |

### <a name="channels"></a>频道

|***标准通道任务** _ | _ *Team Owner** | **团队成员**|
|----|----|----|
|创建/删除通道  |     是    |    是，如果由团队所有者启用      |
|编辑频道名称/说明    |    是     |     是，如果由团队所有者启用    |
|***专用频道任务***|
|创建通道    |    是     |    是，如果由团队所有者启用      |
|删除频道    |    是     |    否     |
|编辑频道名称/说明 |     否    |    不适用     |
|***共享频道任务***
|创建通道    |    是     |     否    |
|删除频道 | 是 | 否 |
|编辑频道名称/说明    |    否     |     否    |
