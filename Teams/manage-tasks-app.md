---
title: 在 Microsoft Teams 中为组织管理 Tasks 应用
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
audience: admin
description: 了解如何在组织中管理 Tasks 应用。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.openlocfilehash: 01be1cfada2ac772723ca1ef2850c6cdc437bc22
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131011"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理 Tasks 应用

## <a name="overview-of-tasks"></a>Tasks 概述

Tasks 应用为 Microsoft Teams 带来紧密的任务管理体验，通过[微软待办](https://todo.microsoft.com/tasks/)整合个人任务，通过 Planner 整合团队任务。 用户可以在 Teams 左侧访问 Tasks 应用，或在单个团队中的频道访问 Tasks 选项卡。 使用 **“我的任务****”和“共享计划”**，用户可以查看和管理其所有个人和团队任务，并确定其工作的优先级。 Tasks 在 Teams 桌面、web 以及移动客户端均可用。

> [!NOTE]
> 我们正在推出 Teams 桌面客户端上的 Tasks 体验，应用会首先显示为 **Planner**。 然后，此名称会暂时更改为 **Tasks by Planner 和微软代办**，之后会重命名为 **Tasks**。 在 Teams 移动客户端上，用户会始终看到应用名为 **Tasks**。 桌面体验可用后，移动体验的可用性可能会有短暂的延迟。

:::image type="content" source="media/manage-tasks-app-tasks.png" alt-text="任务列表视图的屏幕截图。" lightbox="media/manage-tasks-app-tasks.png":::

对于想要简化对前线工作者任务管理的组织，Tasks 也有在前线工作人员中大规模确定目标、发布以及跟踪任务的功能。 比如，企业和地区领导可以创建并发布面向相关地区的任务列表，例如具体的零售店，并通过实时报告跟踪进度。 管理者可以分配任务给员工和地区内的直接活动，前线工作者会在手机和桌面上收到分配任务的优先级清单。 若要启用 [任务发布](#task-publishing)，请首先为组织设置团队目标层次结构，该层次结构定义层次结构中的所有团队彼此之间的关系。

## <a name="what-you-need-to-know-about-tasks"></a>你需要了解的 Tasks 的相关信息

Tasks 同时作为应用和频道中的选项卡存在。 该应用同时显示“To Do”中的单个任务和 Planner 中的团队任务。 选项卡仅显示团队任务。

用户可以获得桌面、web 以及移动端的 Tasks 体验。 如果 Tasks 安装在 Teams 桌面客户端中，用户也可以在 Teams 的 web 和移动客户端上找到它。 来宾除外。 需要注意的是，使用 Teams 移动客户端的来宾只能访问 Tasks 应用。  来宾会在 Teams 桌面和 web 客户端中看到 Tasks 选项卡。

**我的任务** 显示用户的个人任务。 **共享计划** 显示全队当前任务，且包含任何作为选项卡添加到频道的任务列表。 请注意 Tasks、To Do 和 Planner 中任务之间的以下关系：

- 用户在 Tasks 应用中创建的任务列表也会显示在该用户的微软代办客户端中。 同样地，用户在微软代办中创建的任务列表也会显示在用户在 Tasks 中的 **我的任务** 里。 个人任务也是这样。

- 任何添加到频道的 Tasks 选项卡都会显示在 Planner 客户端中。 当用户在 Planner 中创建计划时，该计划不会在 Tasks 或 Planner 应用中显示，除非已作为选项卡添加到频道。 当用户添加新的 Tasks 选项卡时，可以选择创建新列表或计划，或使用现有的。

## <a name="set-up-tasks"></a>设置任务

> [!IMPORTANT]
> 配置到 Planner 的设置和策略也会应用到 Tasks。

### <a name="enable-or-disable-tasks-in-your-organization"></a>在你的组织中启用或禁用 Tasks

Tasks 在你的组织中默认为所有 Teams 用户启用。 你可以在 Microsoft Teams 管理中心的[管理应用](manage-apps.md)页面在组织级别关闭或打开此应用。

1. 在 Microsoft Teams 管理中心的左侧窗格中，转到“**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，执行下列操作之一：

    - 若要关闭组织的“任务”，请搜索“任务”应用，将其选中，然后选择“ **阻止**”。
    - 若要为组织启用“任务”，请搜索“任务”应用，将其选中，然后选择“ **允许**”。

> [!NOTE]
> 如果你找不到 Tasks 应用，请在本文第一个备注中搜索名称。 此应用可能仍在经历重命名过程。

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>在你的组织中为某个特定用户启用或禁用 Tasks

若要允许或阻止组织中的特定用户使用“任务”，请确保在 [“管理应用](manage-apps.md) ”页上为组织启用“任务”，然后为应用权限创建自定义策略并将其分配给这些用户。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

### <a name="pin-tasks-to-teams"></a>将任务固定到 Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-tasks-and-other-apps-to-teams"></a>使用定制的一线应用体验将任务和其他应用固定到 Teams

Teams 中定制的一线应用体验为拥有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的用户固定 Teams 中最相关的应用。 固定的应用包括任务、Walkie Talkie、排班和审批。 默认情况下，此功能处于打开状态，为一线员工提供适合其需求的开箱即用体验。

应用固定到应用栏（Teams 桌面客户端一侧和 Teams 移动客户端底部的栏），用户可以快速轻松地访问应用栏。

若要了解详细信息，包括体验如何与设置的应用策略配合使用，请参阅 [为一线员工定制 Teams 应用](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

#### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>使用应用设置策略来固定 Tasks 到 Teams

应用设置策略允许自定义 Teams，以固定用户中最重要的应用。

若要为用户固定 Tasks 应用，可以编辑全局 (组织范围的默认) 策略，或在应用设置策略中创建和分配自定义策略。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>如果用户具有 Exchange Online 许可证，“我的任务”会对用户可见。

如果你不想让某个用户看到“**我的任务**”，可以将其隐藏。 若要隐藏 **“我的任务**[”，请删除用户的Exchange Online许可证](/microsoft-365/admin/manage/remove-licenses-from-users)。 需要记住的是，在删除 Exchange Online 许可后，用户不再能够访问他们的邮箱。  邮箱数据会保留 30 天，之后数据会被清除且无法恢复，除非邮箱处于[就地保留或诉讼保留](/exchange/security-and-compliance/in-place-and-litigation-holds)状态。

我们不建议删除信息工作者的Exchange Online许可证，但在某些情况下，你可以以这种方式隐藏 **“我的任务”**，例如不依赖于电子邮件的一线员工。

## <a name="task-publishing"></a>发布任务

通过发布任务，你的组织可以发布在组织内针对特定地点（团队）的任务列表，来定义并共享需要在那些地点完成的工作计划。

- 在发布团队的人员，例如企业或地区领导，可以创建任务列表并发布给特定团队。

    :::image type="content" source="media/manage-tasks-app-publish.png" alt-text="任务发布的屏幕截图。" lightbox="media/manage-tasks-app-publish.png":::
- 收件团队的管理者可以检查发布的任务列表并分配个人任务给团队成员。
    :::image type="content" source="media/manage-tasks-app-assign.png" alt-text="分配任务的屏幕截图。" lightbox="media/manage-tasks-app-assign.png":::
- 前线工作者有查看已分配任务的简便移动体验。 他们可以在适当的时候附加照片来展示工作并标记任务为已完成。
- 发布者和管理者可以查看报告来了解各个级别的任务分配和完成状态，包括以地点（团队）、任务列表以及个人任务查看。
    :::image type="content" source="media/manage-tasks-app-reporting.png" alt-text="已发布任务的屏幕截图。" lightbox="media/manage-tasks-app-reporting.png":::

用户在 Tasks 应用中的 **已发布列表** 选项卡创建、管理以及发布任务列表。 此选项卡只在组织已经[设置团队目标层次结构](#set-up-your-team-targeting-hierarchy)并且用户所在团队在该结构中时显示。 此层次结构决定用户是否能够发布或接收任务列表并查看已接收列表的报告。

### <a name="example-scenario"></a>应用场景示例

下面是发布任务的例子。

Contoso 正在推出新的餐饮外卖和外送促销。  为了保持一致的品牌体验，他们需要在 300 多家门店之间协调统一的推出计划。

营销团队和零售通讯经理共享了促销的具体信息以及对应的任务列表。 零售通信经理（充当商店的看门人）审查信息。 然后，为促销创建任务列表，并为受影响的商店需要执行的每个工作单元创建一个任务。 任务列表完成后，他们需要选择必须完成工作的存储。 这种情况下，促销只对在美国有实体餐厅的门店生效。 在“任务”中，他们基于店内餐厅属性筛选商店列表，在层次结构中选择匹配美国位置，然后将任务列表发布到这些商店。

每个地区的门店经理会收到一份已发布任务的副本，他们将任务再分配给他们的团队成员。 经理可以使用 Tasks 体验来理解店内所有需要完成的工作。 他们也可以使用可用的筛选器来聚焦某组具体工作，比如今天截止的或者某个方面的工作。

每个门店地区的前线工作者现在可以在移动设备上查看 Tasks 中的工作优先级列表。 当他们完成一项任务时，可以标记任务为完成。 他们甚至可以选择上传照片并将其附加到任务以显示其工作。

Contoso 总部和中级经理可以查看报告来了解每个门店和所有门店的任务分配及完成状态。 他们也可以查看某个特定任务在不同店内的完成情况。 随着发布日越来越近，他们可以发现任何异常问题并在需要的时候介入到团队中。 这种可见性让 Contoso 可以提升推出的效率并提供更加一致的管理体验。

### <a name="set-up-your-team-targeting-hierarchy"></a>设置团队目标层次结构

要在组织中启用发布任务，你需要首先用 .CSV 文件设置团队的目标架构。 该架构定义了层次结构中的所有团队彼此之间的关系，还定义了可用于筛选和选择团队的属性。 在创建架构之后，请上传到 Teams 以应用到你的组织。 发布团队的成员，比如例子中的零售通讯经理，可以通过层次结构、属性或两者的组合来筛选团队，选中应该接收任务列表的相关团队，将任务列表发布给他们。

有关如何设置团队的目标层次结构，请参阅[设置团队目标层次结构](set-up-your-team-hierarchy.md)。

## <a name="power-automate-and-graph-api"></a>Power Automate 和 Graph API

微软代办中 Tasksk 支持 Power Automate，Planner 中 Tasks 支持 Graph API。 若要了解详细信息，请参阅：

- [Planner 任务和计划 API 概述](/graph/planner-concept-overview)
- [将微软待办与 Power Automate 结合使用](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
