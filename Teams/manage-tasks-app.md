---
title: 在 Microsoft 团队中管理组织的 "任务" 应用
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
audience: admin
description: 了解如何为组织中的用户管理 "任务" 应用。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d06c42691874b8defa86e993727bc1fe38ee67b3
ms.sourcegitcommit: 4afb9617c1734d2f18e833fd9a22f4eda79f8c3b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331657"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft 团队中管理组织的 "任务" 应用

## <a name="overview-of-tasks"></a>任务概述

"任务" 应用为 Microsoft 团队带来了一种内聚的任务管理体验，将由 [microsoft](https://todo.microsoft.com/tasks/) 支持的单个任务与由 Planner 提供的团队任务集成在一个位置。 用户可以将任务作为应用访问到团队的左侧，以及在单个团队中的频道中作为选项卡。 **"任务" 中的 "我的任务" 和 "** **共享计划** " 允许用户查看和管理其所有个人和工作组任务，并确定其工作优先级。 任务在团队桌面版、web 版和移动客户端中可用。 

> [!NOTE]
> 当我们推出团队桌面客户端的任务体验时，应用名称最初将显示为用户的 **Planner** 。 该名称随后会暂时更改为 " **按 Planner" 和 "待办事项**"，稍后将重命名为 " **任务**"。 在团队移动客户端上，用户将始终看到应用名称为 " **任务**"。 桌面体验推出后，移动体验的可用性可能会出现短暂延迟。

   ![团队列表上任务列表视图的屏幕截图](media/manage-tasks-app-tasks.png)

对于想要为一线工作者简化任务管理的组织，任务还包括使你能够以横向方式在一线劳动力范围内进行任务的目标、发布和跟踪任务的功能。 例如，公司和区域领导可以创建和发布针对相关位置（如特定零售商店）的任务列表，并通过实时报表跟踪进度。 经理可以将任务分配给其员工和其所在位置的直接活动，并且一线工作者在移动或桌面上拥有其分配任务的优先级列表。 若要启用 [任务发布](#task-publishing)，首先需要为组织设置团队目标层次结构，以定义层次结构中的所有团队如何相互关联。

## <a name="what-you-need-to-know-about-tasks"></a>您需要了解的有关任务的信息

任务作为应用和频道中的选项卡提供。 请记住，应用包括来自 Planner 的单个任务和团队任务，而选项卡仅显示团队任务。

通过任务，用户可以获得桌面版、web 和手机体验。 如果在团队桌面客户端上安装了任务，用户还将在其团队 web 和移动客户端上看到该任务。 例外情况是来宾用户。 请务必了解，来宾只能从团队移动客户端以应用的形式访问任务。 来宾将在两个团队桌面和 web 客户端上看到 "任务" 选项卡。

**"我的任务"** 显示用户的单个任务。 **共享计划** 显示整个团队正在处理的任务，包括作为 "任务" 选项卡添加到频道的任何任务列表。 请注意以下事项：

- 用户在 "任务" 应用中创建的任务列表也会显示在 "为该用户执行客户端" 中。 同样，用户在 "任务" 中创建的任务列表将显示在该用户任务的 **"任务"** 中。 对于单个任务，也是如此。

- 添加到频道的任何 "任务" 选项卡也将显示在 Planner 客户端中。 当用户在 Planner 中创建计划时，计划将不会显示在 "任务" 或 "Planner" 应用中，除非该计划已作为选项卡添加到频道。 当用户添加新的 "任务" 选项卡时，他们可以创建新的列表或计划，或选择现有的计划。

## <a name="set-up-tasks"></a>设置任务

> [!IMPORTANT]
> 为 Planner 配置的设置和策略也将应用于任务。

### <a name="enable-or-disable-tasks-in-your-organization"></a>启用或禁用组织中的任务

默认情况下，将为组织中的所有团队用户启用任务。 你可以在 Microsoft 团队管理中心的 " [管理应用](manage-apps.md) " 页面上，关闭或打开组织级别的应用。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。
2. 在应用列表中，执行下列操作之一：

    - 若要为你的组织关闭任务，请搜索 "任务" 应用，选择它，然后单击 " **阻止**"。
    - 若要为你的组织启用任务，请搜索 "任务" 应用，选择它，然后单击 " **允许**"。

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>为组织中的特定用户启用或禁用任务

若要允许或阻止组织中的特定用户使用任务，请确保在 " [管理应用](manage-apps.md) " 页面上为你的组织启用任务，然后创建自定义应用权限策略并将其分配给这些用户。 若要了解详细信息，请参阅 [管理团队中的应用权限策略](teams-app-permission-policies.md)。

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>使用应用设置策略将任务固定到团队

应用设置策略允许你自定义团队，以突出显示你的组织中的用户最重要的应用。 你在策略中设置的应用将固定到应用程序栏，应用栏 &mdash; 位于团队桌面客户端和团队移动客户端的底部， &mdash; 用户可以快速轻松地访问它们。

若要为你的用户固定 "任务" 应用，你可以编辑全局 (组织范围的默认) 策略，或者创建并分配自定义应用设置策略。 若要了解详细信息，请参阅 [管理团队中的应用设置策略](teams-app-setup-policies.md)。

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>如果用户已获得 Exchange Online 许可，用户的 "我的任务" 将可见

如果不希望用户看到 **我的任务**，您可以将其隐藏。 若要执行此操作，请 [删除用户的 Exchange Online 许可证](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)。 请务必注意，在删除 Exchange Online 许可证后，用户将不再有权访问其邮箱。  邮箱数据保留30天，在此之后将删除数据，并且不能恢复，除非邮箱被置于 [现场保留或诉讼保留](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)。

我们不建议为信息工作者提供此信息，但可能会出现这种情况，例如适用于不依赖电子邮件的一线工作人员。

## <a name="task-publishing"></a>任务发布

通过任务发布，你的组织可以发布针对特定位置的任务列表 (团队) 组织中定义和共享要在这些位置完成的工作计划。

- 发布团队中的人员（如企业或区域领导）可以创建任务列表并将其发布到特定团队。<br>
    ![任务发布的屏幕截图](media/manage-tasks-app-publish.png)
- 收件人团队的经理可以查看已发布的任务列表，并将单个任务分配给团队成员。<br>
    ![分配任务的屏幕截图](media/manage-tasks-app-assign.png)
- 一线工作者具有简单的移动体验，可查看分配给他们的任务。 他们可以附加照片，以便在需要时显示其工作，并将其任务标记为 "已完成"。
- 发布者和经理可以查看报表，以查看每个级别的任务的作业作业和完成状态，包括按位置 (工作组) 、任务列表和单个任务。<br>
    ![移动设备上已分配任务的屏幕截图](media/manage-tasks-app-reporting.png)

用户在 "任务" 应用中的 " **已发布的列表** " 选项卡上创建、管理和发布任务列表。 仅当你的组织 [设置团队目标层次结构](#set-up-your-team-targeting-hierarchy) ，并且用户位于层次结构中包含的团队时，此选项卡才会向用户显示。 层次结构确定用户是否可以发布或接收任务列表和查看已接收列表的报告。

### <a name="example-scenario"></a>示例方案

下面是有关任务发布工作原理的示例。

Contoso 正在推出新的食物 takeout 和交付优惠。 为保持一致的品牌体验，他们需要协调跨300应用商店位置的推出一致的执行。

市场营销团队与零售通信管理器共享促销详细信息和相应的任务列表。 零售通信管理员（充当商店的网关守卫）可查看信息、为促销创建任务列表，然后为每个受影响的存储需要执行的每个工作单元创建任务。 任务列表完成后，她需要选择必须完成工作的商店。 在这种情况下，促销仅适用于具有内部商店餐馆的美国商店。 在 "任务" 中，她根据 "存储区餐馆" 属性筛选应用商店列表，在层次结构中选择匹配的美国位置，然后将任务列表发布到这些商店。

每个位置的商店经理接收已发布任务的副本并将这些任务分配给其团队成员。 经理可以使用 "任务" 体验来了解其应用商店所需的所有工作。 他们还可以使用可用的筛选器重点关注特定的工作集，如 "今天到期的工作" 或特定区域中的工作。

每个应用商店位置的一线工作者现在在其移动设备上的任务中有一个按优先级排列的工作人员列表。 完成任务后，他们将其标记为 "完成"。 某些人甚至可能选择将照片上传和附加到任务以显示其工作。

Contoso 总部和中级经理可以查看报告，以查看每个商店和商店内任务的作业和完成状态。 他们还可以向下钻取到特定任务，以查看不同商店中的状态。 随着启动日期更近，他们可以发现任何 abnormalities，并根据需要与团队成员一起登记。 此可见性使 Contoso 能够提高推出的效率，并在其存储中提供更一致的体验。

### <a name="set-up-your-team-targeting-hierarchy"></a>设置团队目标层次结构

若要在你的组织中启用任务发布，你必须首先在中设置你的团队目标架构。CSV 文件。 该架构定义层次结构中的所有团队如何相互关联以及用于筛选和选择团队的属性。 创建架构后，将其上载到团队以将其应用于你的组织。 发布团队的成员（如示例方案中的零售通信管理器）可以按层次结构、属性或组合筛选团队，以选择应收到任务列表的相关团队，然后将任务列表发布给这些团队。

有关如何设置团队目标层次结构的步骤，请参阅 [设置团队目标层次结构](set-up-your-team-hierarchy.md)。

## <a name="power-automate-and-graph-api"></a>自动处理电源和图形 API

任务支持为 Planner 执行 "待办事项" 和 "图形 Api" 的 "电源自动化"。 要了解详细信息，请参阅：

- [Planner 任务和计划 API 概述](https://docs.microsoft.com/graph/planner-concept-overview)
- [使用 Microsoft 对电源进行自动化](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
