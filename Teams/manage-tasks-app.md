---
title: 在 Microsoft Teams 中管理组织任务应用
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
audience: admin
description: 了解如何为组织中的用户管理任务应用。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 48465336e0c3657b8bfd1d3adb1eb69c239ecdb6
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814228"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理组织任务应用

> **此功能目前处于私人预览版。**

## <a name="overview-of-tasks"></a>任务概述

"任务"应用为 Microsoft Teams 带来一致的任务管理体验，并集成 [由 Microsoft To Do](https://todo.microsoft.com/tasks/) 提供支持的各个任务，并集成由 Planner 提供支持的单个任务。 用户可以通过 Teams 左侧的一个选项卡作为一个选项卡访问任务，并在各个团队内作为频道。 **任务中的** 我的 **任务和共享** 计划让用户可以查看和管理其所有个人和工作组任务，以及对其工作设置优先级。 任务在 Teams 桌面客户端、Web 和移动客户端中可用。 

> [!NOTE]
> 在 Teams 桌面客户端上，提供的是 Teams 桌面客户端上的任务体验，最初将显示为 **Planner** 的用户。 然后，该名称将通过 **Planner**和待办事项和更高版本暂时更改为"任务"，之后将重命名为 **"任务**"。 在 Teams 移动客户端中，用户将始终看到显示为"任务" **的应用名称**。 在桌面体验可用后，移动体验的可用性可能会较短。

   ![Teams 列表上的任务列表视图的屏幕截图](media/manage-tasks-app-tasks.png)

对于希望简化一线员工任务管理的组织，任务还包括一些功能，使你能够在一线员工中以比例定位、发布和跟踪任务。 例如，公司和区域前导可以创建面向相关位置（例如特定存储项和通过实时报告跟踪进度）并发布。 经理可以将任务分配给其人员，直接在其位置内直接活动，而一线员工在移动或桌面上拥有其已分配任务的优先级列表。 要 [启用任务发布](#task-publishing)，您首先需要为组织建设团队定位层次结构，它可定义层次结构中的所有团队相对于其如何关联。

## <a name="what-you-need-to-know-about-tasks"></a>有关"任务"的了解

任务以应用和频道中的选项卡的形式提供。 请注意，此应用通过 Planner 将在"待办事项"和"团队"任务中同时包含各个任务，而"Planner"选项卡仅显示团队任务。

使用任务，用户可以获得桌面体验、Web 和移动体验。 如果 Teams 桌面客户端上安装了任务，用户也会在其 Teams Web 和移动客户端上看到该任务。 例外是来宾用户。 了解来宾只能从 Teams 移动客户端以应用程序形式访问任务，这一点很重要。 来宾将在 Teams 桌面客户端和 Web 客户端上看到"任务"选项卡。

**"** 我的任务"显示用户的个人任务。 **共享计划** 显示整个团队正在处理的任务，并包括添加为"任务"选项卡到频道的任何任务列表。 请注意以下几项：

- 用户在"任务"应用中创建的任务列表也会显示在该用户的待办事项客户端中。 同样，用户创建的任务列表中将显示该用户的"我的任务"中的"我的**My tasks**任务"中。 对于单个任务同样如此。

- 添加到频道的任何"任务"选项卡也将显示在 Planner 客户端中。 用户在 Planner 中创建计划时，该计划不会显示在"任务"或"Planner"应用中，除非该计划将作为选项卡添加到频道中。 当用户添加新的"任务"选项卡时，他们可以创建新列表或计划或选择现有列表。

## <a name="set-up-tasks"></a>设置任务

> [!IMPORTANT]
> 为 Planner 配置的设置和策略也适用于任务。

### <a name="enable-or-disable-tasks-in-your-organization"></a>启用或禁用组织中的任务

默认情况下，会为组织中的所有 Teams 用户启用任务。 你可以在 Microsoft Teams 管理中心的"管理应用"页面下关闭 [或](manage-apps.md) 关闭应用级别的应用。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。
2. 在应用列表中，执行下列操作之一：

    - 若要为组织关闭任务，请搜索"任务"应用，选择它，然后单击 **"块"。**
    - 若要为组织开启任务，请搜索任务应用程序，选择它，然后单击" **允许**"。

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>为组织中的特定用户启用或禁用任务

要允许或阻止组织中的特定用户使用"任务"，请确保在"管理应用"页面上为你的组织[Manage apps](manage-apps.md)启用"任务"，然后创建自定义应用权限策略并将其分配给这些用户。 若要了解详细信息，请参阅 [Teams 中的"管理应用权限策略](teams-app-permission-policies.md)"。

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>使用应用设置策略将任务固定到 Teams

通过应用设置策略，可自定义 Teams，以突出显示对组织中用户最重要的应用。 你在策略中设置的应用固定到 Teams 桌面客户端侧面的应用栏，用户可以在其中快速而轻松地访问 &mdash; &mdash; 它们。

若要为用户固定"任务"应用，可以在全局 (默认策略或) 创建和分配自定义应用设置策略。 若要了解详细信息，请参阅 [Teams 中的"管理应用设置策略](teams-app-setup-policies.md)"。

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>如果用户为 Exchange Online 授权，则显示用户的"我的任务"

如果您不希望用户看到我的 **任务，** 则可以隐藏它。 为此， [请删除用户的 Exchange Online 许可证](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)。 请务必知道在删除 Exchange Online 许可证后，用户将无法再访问其邮箱。  邮箱数据将保留 30 天，之后将删除数据且无法恢复，除非该邮箱设置在 [就地保留或三元修订上](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)。

我们不建议对信息工作者使用此方法，但也有些情况可能会适用，例如对不依赖电子邮件的一线工作者。

## <a name="task-publishing"></a>任务发布

使用任务发布功能，您的组织可以将任务列表发布到组织的 (团队) 的特定位置，以定义和共享要在这些位置完成的工作计划。

- 有关发布团队（如公司或区域主管）的人员可以创建任务列表并将其发布到特定团队。<br>
    ![任务发布的屏幕截图](media/manage-tasks-app-publish.png)
- 收件人团队的管理员可以审阅已发布的任务列表，并向团队成员分配单个任务。<br>
    ![分配任务的屏幕截图](media/manage-tasks-app-assign.png)
- 一线员工具有简单的移动体验，可查看分配给他们的任务。 他们可以附加照片以在适当时显示其工作，并将其任务标记为已完成。
- 发布者和经理可以查看每个级别任务的报告，包括按位置 (团队) 任务、任务列表和单个任务进行查看。<br>
    ![移动设备上已分配任务的屏幕截图](media/manage-tasks-app-reporting.png)

用户在"任务"应用的"已发布列表 **"选项卡上创建、管理** 和发布任务列表。 仅当组织设置了一个目标层次结构且[set up a team targeting hierarchy](#set-up-your-team-targeting-hierarchy)用户位于层次结构中包含的团队时，此选项卡仅为该用户显示。 该层次结构决定用户是否可以发布或接收任务列表以及查看接收的列表报告。

### <a name="example-scenario"></a>示例方案

下面是任务发布工作原理的一个示例。

Contoso 即将推出新的职品并推广。 为了保持一致的品牌体验，他们需要在 300 以上的统一的存储位置来执行一致的作用。

市场营销团队通过 Retail Communications Manager 共享促销详细信息和相应的任务列表。 Retail Communications Manager，其用作店网关，查看信息，创建促销任务列表，然后为每个受影响的应用商店都需要执行的每个工作单元的任务。 任务列表完成时，她需要选择必须完成工作的商店。 在此情况下，促销仅适用于具有商店内预期的美国商店商店。 在"任务"中，她基于店中的预索图属性筛选存储列表，选择层次结构中匹配的美国位置，然后将任务列表发布到这些存储。

每个位置的应用商店经理会收到已发布任务的副本，并将这些任务分配给其团队成员。 管理者可以使用任务体验了解其应用商店中所有必需的工作。 他们还可以使用可用的筛选器来重点关注一组特定的工作，例如今天到期的工作或在特定区域工作。

每个应用商店位置的第一线工作者现在在其移动设备上拥有其工作的优先级列表。 任务完成后，会将它标记为完成。 某些联系人甚至还有选择上传照片并将照片附加到任务以显示其工作。

Contoso 总部和中级管理员可以查看报告，以查看每个应用商店和各个应用商店中任务的工作分配和完成状态。 他们还可以向下钻取至特定任务，以查看不同商店内的状态。 随近发布日期，他们可以一下任何主题，并根据需要与团队确认。 此可见性让 Contoso 提高回退的效效，并在其应用商店中提供更一致的体验。

### <a name="set-up-your-team-targeting-hierarchy"></a>设置面向层次结构的团队

要在您的组织中启用任务发布，您首先必须在一个团队定位架构中设置您的团队定位架构。CSV 文件。 此方案定义层次结构中的所有团队如何相关联，以及用于筛选和选择团队的属性。 创建架构后，将其上传到 Teams 以应用于你的组织。 发布团队的成员（例如示例方案中的"发布通信管理器"）可以按层次结构、属性或两者的组合来筛选团队，以选择应接收任务列表的相关团队，然后将任务列表发布到这些团队。

有关如何设置团队面向层次结构的步骤， [请参阅"设置面向层次结构的团队](set-up-your-team-hierarchy.md)"。

## <a name="power-automate-and-graph-api"></a>Power Automate 和 Graph API

任务支持"待办事项"和 Planner 的 PowerGraph API。 要了解详细信息，请参阅：

- [规划器任务和计划 API 概述](https://docs.microsoft.com/graph/planner-concept-overview)
- [将微软待办与 Power Automate 结合使用](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
