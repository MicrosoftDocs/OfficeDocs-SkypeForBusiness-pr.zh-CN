---
title: 为Teams员工定制应用
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解为应用程序中的一线员工量身定制的应用Teams。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774181"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>为Teams员工定制应用

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>概述

Teams提供了一种为一线工作者固定应用的简便方法。 此功能基于许可证固定应用，为一线员工提供满足其需求的Teams即用即用体验。

借助定制的一线应用体验，一线员工无需管理员Teams即可获取最相关的应用。

## <a name="tailored-frontline-app-experience"></a>定制的一线应用体验

应用固定到应用栏，应用栏位于 Teams 移动客户端 (iOS 和 Android) 底部以及 Teams 桌面客户端的一侧。 对于具有 F 许可证的用户，将固定以下 [应用](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)：

- [活动](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [聊天](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [对讲机](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [任务](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [排班](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [审批](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams移动版**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="在移动设备上定制的一线应用Teams体验" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams桌面**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="桌面版定制一线应用Teams体验" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>管理员控件

> [!NOTE]
> 必须在 **组织范围的** 全局应用 (应用设置策略中) [用户](teams-app-setup-policies.md) 固定设置，此功能生效。

定制的一线应用体验由管理中心的"管理应用"页面上的"显示定制应用组织范围的应用"[](manage-apps.md#manage-org-wide-app-settings)设置Teams控制。 如果此功能已打开，则组织中具有 F 许可证的所有用户都将获得定制的应用体验。

请记住，分配给用户 [的任何](teams-app-setup-policies.md) 自定义应用设置策略优先。 这意味着，如果用户已分配有自定义应用设置策略，则用户获取自定义应用设置策略中定义的配置。 若要详细了解该功能如何与应用Teams（包括全局应用设置策略）一起工作，请参阅本文稍后的"方案"[](#scenarios)部分。

默认情况下，启用此功能。 但是，如果不希望 Microsoft 提供定制的一线应用体验，可以关闭该功能。 若要关闭或打开该功能，请：

1. 在管理中心的左侧导航Microsoft Teams，转到"Teams **应用** > ""管理 **应用**"，然后选择"**组织范围的应用设置"**。
2. 在 **"定制应用"下**，将"显示 **定制应用"** 切换为"**关"或****"开"**。

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="屏幕管理中心的"管理应用"页上的"显示定制应用Teams屏幕截图" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>方案

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>定制的一线应用体验如何影响我的全局应用设置策略？

了解定制一线应用体验如何与全局应用设置策略协同工作。 此表中的方案适用于具有 F 许可证和全局应用设置策略的一线工作者，并且用户 **固定** 已打开。

|如果... |然后... |
|---------|---------|
|一线辅助角色具有全局应用设置策略，并且该功能已关闭。 |一线辅助角色获取全局应用设置策略中定义的应用。|
|一线辅助角色具有全局应用设置策略，并且该功能已打开。     | 一线辅助角色获得定制的一线应用体验。 全局应用设置策略中定义的应用固定在定制应用下方。      |
|更新全局应用设置策略，该功能已打开。     |一线辅助角色获取定制的一线应用体验，全局应用设置策略中定义的应用固定在定制应用下方。         |
|一线辅助角色具有全局应用设置策略， **并且** 用户固定已关闭。 |一线辅助角色获取全局应用设置策略中定义的应用。|
|一线辅助角色具有全局应用设置策略，全局应用设置策略已更改为在应用列表中的第二个位置包含业务线 (LOB) 应用。 |LOB 应用固定在定制应用下方。 如果用户固定已打开，一线辅助 **角色可以更改应用** 顺序。         |
|一线工作人员具有全局设置策略，全局应用设置策略已更改为将 Shifts 纳入第一个位置。  |按定制一线应用体验的定义，将 Shift 固定到第六个位置。 如果用户固定已打开，一线辅助 **角色可以更改应用** 顺序。          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>定制一线应用体验如何与其他应用Teams一起工作？

了解定制一线应用体验如何与其他应用Teams一起工作。

|如果...  |然后... |
|---------|---------|
该功能已关闭。   | 一线辅助角色获取在全局应用设置策略或分配给他们的自定义应用设置策略中定义的应用。          |
|一线辅助角色具有自定义应用设置策略，并且该功能已打开。    |一线辅助角色获取自定义应用设置策略中定义的应用。          |
|为用户或组织阻止了定制一线应用体验中的应用。      |定制的一线应用体验遵守 [应用权限策略](teams-app-permission-policies.md)。 如果应用被阻止，则一线辅助角色不会看到阻止的应用。           |
|定制一线应用体验中的应用已在应用设置策略中定义，并且该功能已打开。 |应用根据定制应用列表定义的顺序进行固定。        |
|用户具有 E、A 或 G 许可证，并且该功能已打开。   | 用户不会获得定制的一线应用体验。 目前，体验仅适用于具有 F 许可证的用户。        |

> [!NOTE]
> 在定制的一线应用体验中，你无法更改应用或应用顺序。 现在，如果要进行更改，可以设置自己的自定义体验。 为此，请首先关闭该功能。 然后 [创建自定义应用设置策略](teams-app-setup-policies.md)， [并将其分配给用户或组](assign-policies-users-and-groups.md)。

## <a name="related-articles"></a>相关文章

- [在应用中管理 Walkie Talkie Teams](walkie-talkie.md)
- [管理任务应用中Teams](manage-tasks-app.md)
- [在应用程序中管理 Shifts Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [在应用程序中管理审批Teams](approval-admin.md)
- [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
