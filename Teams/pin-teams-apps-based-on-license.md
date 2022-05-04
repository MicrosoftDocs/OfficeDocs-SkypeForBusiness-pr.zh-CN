---
title: 为一线员工定制 Teams 应用
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解Teams中一线员工定制的应用体验。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f717672c4cb297d7f3d2e95ceaa038eeceaa2ee
ms.sourcegitcommit: ad8447b683381bc07f993bf843a93a4bdb77d840
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2022
ms.locfileid: "65187118"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>为一线员工定制 Teams 应用

> [!NOTE]
> 此功能目前正在推出，可能尚未在组织中提供。 若要随时了解即将推出的Teams功能，请查看[Microsoft 365路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。

## <a name="overview"></a>概述

Teams根据许可证固定应用，为一线员工提供适合其需求的Teams的现现体验。 

凭借量身定制的一线应用体验，你的一线员工可在Teams中获取最相关的应用，而无需管理员执行任何操作。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VuCH]

## <a name="tailored-frontline-app-experience"></a>定制的一线应用体验

应用固定到应用栏，这是 iOS 和 Android)  (Teams 移动客户端底部以及Teams桌面客户端的一侧的条形图。 以下应用针对拥有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的用户进行固定：

- [活动](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [聊天](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [对讲机](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [任务](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [排班](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [审批](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams移动设备**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="Teams移动版上定制的一线应用体验" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams桌面**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="Teams桌面上定制的一线应用体验" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>管理控件

> [!NOTE]
> 必须在全局 (组织范围的默认) [应用设置策略](teams-app-setup-policies.md)中启用 **用户固定** 设置，才能使此功能生效。

定制的一线应用体验由Teams管理中心的“[管理应用](manage-apps.md#manage-org-wide-app-settings)”页上的 **“显示定制** 应用”组织范围的应用设置控制。 如果该功能已启用，组织中拥有 F 许可证的所有用户都将获得定制的应用体验。

请记住，分配给用户的任何自定义 [应用设置策略](teams-app-setup-policies.md) 都优先。 这意味着，如果用户已向其分配了自定义应用设置策略，则用户将获取在自定义应用设置策略中定义的配置。 若要详细了解该功能如何与Teams应用策略（包括全局应用设置策略）配合使用，请参阅本文后面[的“方案”](#scenarios)部分。

默认情况下，启用此功能。 但是，如果不希望 Microsoft 提供定制的一线应用体验，则可以关闭该功能。 若要关闭或打开该功能，请执行以下操作：

1. 在Microsoft Teams管理中心的左侧导航中，转到 **Teams** **appsManage** >  应用，然后选择 **组织范围的应用设置**。
2. 在 **“定制应用**”下，将 **“显示定制应用** ”切换到 **“关闭** ”或 **“打开**”。

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Teams管理中心的“管理应用”页上的“显示定制应用”设置的屏幕截图" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>方案

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>定制的一线应用体验如何影响我的全局应用设置策略？

了解定制的一线应用体验如何与全局应用设置策略协同工作。 此表中的方案适用于具有 F 许可证和全局应用设置策略的一线工作者， **用户固定** 已打开。

|如果。。。 |然后。。。 |
|---------|---------|
|一线工作者具有全局应用设置策略，并且功能已关闭。 |一线工作者获取全局应用设置策略中定义的应用。|
|一线工作者具有全局应用设置策略，并且功能处于启用状态。     | 一线工作者可获得定制的一线应用体验。 全局应用设置策略中定义的应用固定在定制的应用下面。      |
|更新全局应用设置策略，并启用该功能。     |一线工作者可获得量身定制的一线应用体验，全局应用设置策略中定义的应用固定在定制的应用下方。         |
|一线工作者具有全局应用设置策略， **用户固定** 已关闭。 |一线工作者获取全局应用设置策略中定义的应用。|
|一线工作者具有全局应用设置策略，全局应用设置策略将更改为将业务线 (LOB) 应用包含在应用列表中的第二个位置。 |LOB 应用固定在定制的应用下方。 如果 **用户固定** 处于打开状态，一线工作者可以更改应用顺序。         |
|一线工作者具有全局设置策略，全局应用设置策略将更改为将 Shifts 包含在第一个位置。  |根据定制的一线应用体验定义，班次固定到第六个位置。 如果 **用户固定** 处于打开状态，一线工作者可以更改应用顺序。          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>定制的一线应用体验如何与其他Teams应用策略配合使用？

了解定制的一线应用体验如何与其他Teams应用策略配合使用。

|如果。。。  |然后。。。 |
|---------|---------|
该功能已关闭。   | 一线辅助角色获取在分配给它们的全局应用设置策略或自定义应用设置策略中定义的应用。          |
|一线工作者具有自定义应用设置策略，并且功能处于启用状态。    |一线辅助角色获取自定义应用设置策略中定义的应用。          |
|为用户或组织阻止定制的一线应用体验中的应用。      |定制的一线应用体验遵循 [应用权限策略](teams-app-permission-policies.md)。 如果应用被阻止，一线工作者将看不到被阻止的应用。           |
|已在应用设置策略中定义了定制的一线应用体验中的应用，并且该功能处于启用状态。 |应用是根据定制应用列表定义的顺序固定的。        |
|用户具有 E、A 或 G 许可证，并且功能处于启用中。   | 用户无法获得定制的一线应用体验。 目前，该体验仅适用于拥有 F 许可证的用户。        |

> [!NOTE]
> 无法在定制的一线应用体验中更改应用的应用或顺序。 目前，如果要进行更改，可以设置自己的自定义体验。 为此，请先关闭该功能。 然后， [创建自定义应用设置策略](teams-app-setup-policies.md)，并 [将其分配给用户或组](assign-policies-users-and-groups.md)。

## <a name="related-articles"></a>相关文章

- [在 Teams 中管理 Walkie Talkie 应用](walkie-talkie.md)
- [在Teams中管理 Tasks 应用](manage-tasks-app.md)
- [在Teams中管理 Shifts 应用](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [在Teams中管理审批应用](approval-admin.md)
- [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
