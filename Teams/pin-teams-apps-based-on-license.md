---
title: 根据许可证Teams自定义应用
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何根据Teams为组织的用户固定应用。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 774688012d4e70a20897cd45aa78883ba7985e68
ms.sourcegitcommit: 1190cd73656dbc9131d46e0a827e28bcd960dfc5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2022
ms.locfileid: "62864035"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>根据许可证Teams自定义应用

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> 目前，此功能适用于 F 许可证。 因此，本文重点介绍一线员工体验。 将来将支持其他许可证类型。

## <a name="overview"></a>概述

Teams提供了一种基于许可证固定应用的方法。 当用户登录并Teams应用体验时，用户会获得基于其许可证定制的应用体验。

此功能为用户提供了应用中最相关的Teams，无需管理员执行任何操作。

## <a name="tailored-app-experience"></a>定制的应用体验

应用固定到应用栏，应用栏位于 Teams 桌面客户端一侧，位于 Teams 移动客户端 (iOS 和 Android) 。

为具有 F 许可证的用户固定的应用：

- 活动
- 聊天
- Teams
- 班次
- 任务

## <a name="admin-controls"></a>管理员控件

> [!NOTE]
> 必须在组织范围的全局应用默认 (启用用户固定) [此功能](teams-app-setup-policies.md) 生效的应用设置策略。

定制应用体验功能由管理中心的"管理应用"页面上的"基于许可证组织范围的应用显示定制应用"Teams[](manage-apps.md#manage-org-wide-app-settings)控制。 如果此功能已打开，则组织中具有 F 许可证的所有用户都将获得定制的应用体验。

请记住，分配给用户的任何自定义应用设置策略优先。 这意味着，如果用户已分配有自定义应用设置策略，则用户获取自定义应用设置策略中定义的配置。 若要详细了解该功能如何与组织中应用的现有应用设置策略一起工作，请参阅本文的 ["](#scenarios) 方案"部分。

默认情况下，启用此功能。 但是，如果不需要 Microsoft 提供的定制应用体验，可以关闭该功能。 若要关闭或打开该功能，请：

1. 在管理中心的左侧导航Microsoft Teams，转到"Teams **"** > "管理 **应用**"，然后选择"**组织范围的应用设置"**。
2. 在 **"定制应用"下**，将"显示 **基于许可证的** 定制应用"切换为" **关"或** " **开"**。

## <a name="scenarios"></a>方案

使用下表中的信息，了解定制应用体验功能在各种方案中的工作原理，包括应用现有应用设置策略时的情况。

|如果...  |然后... |
|---------|---------|
|用户具有全局应用设置策略，并且该功能已打开。     | 用户获取定制的应用体验。        |
|用户具有自定义应用设置策略，并且该功能已打开。    |用户获取自定义应用设置策略中定义的配置。          |
|该功能已打开，你更新了全局应用设置策略。     |用户根据许可证获取定制的应用体验。 全局应用设置策略中定义的应用仍固定，并进一步显示在已固定应用列表中。          |
|该功能已关闭。   | 用户获取在全局应用设置策略或分配给他们的自定义应用设置策略中定义的体验。          |
|用户具有 E、A 或 G 许可证，并且该功能已打开。   | 用户不会获得定制的应用体验。 目前，定制的应用体验仅适用于具有 F 许可证的用户。        |
|为用户或组织阻止定制应用体验中的应用。      |定制的应用体验遵守应用权限策略。 如果应用被阻止，用户将看不到被阻止的应用。           |
|定制应用体验中的应用已在应用设置策略中定义，并且该功能已打开。 |应用根据定制应用体验定义的顺序进行固定。        |

> [!NOTE]
> 你无法更改定制应用体验中的应用或应用顺序。 现在，如果要进行更改，可以设置自己的自定义体验。 为此，请首先关闭该功能。 然后 [创建自定义应用设置策略](teams-app-setup-policies.md)， [并将其分配给用户或组](assign-policies-users-and-groups.md)。

## <a name="related-articles"></a>相关文章

- [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
