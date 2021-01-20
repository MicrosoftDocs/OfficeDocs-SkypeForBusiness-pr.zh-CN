---
title: 在 Microsoft Teams 中管理组织的任务应用
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: 了解如何管理组织中用户的任务应用。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cc477b9589aeebb8dcd486e7f85ca04daf6ff4d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909396"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理"任务"应用

## <a name="overview-of-tasks"></a>任务概述

"任务"应用为 Microsoft Teams 带来了一致的任务管理体验，将 [Microsoft](https://todo.microsoft.com/tasks/) 微软支持的任务与 Planner 支持的团队任务集成在一处。 用户可以以 Teams 左侧的应用和各个团队中频道中的选项卡访问任务。 **"任务"** 中 **的任务和共享** 计划允许用户查看和管理其所有个人和团队任务，并设置其工作的优先级。 任务在 Teams 桌面、Web 和移动客户端中可用。 

> [!NOTE]
> 在 Teams 桌面客户端上推出"任务"体验时，应用名称最初会作为 **Planner** 向用户显示。 然后，该名称将暂时更改为 **Planner 和"要** 执行的任务"，稍后将重命名为 **"任务"。** 在 Teams 移动客户端上，用户始终会看到应用名称为 **"任务"。** 在提供桌面体验后，移动体验的可用性可能会短暂延迟。

   ![Teams 列表中任务的列表视图的屏幕截图](media/manage-tasks-app-tasks.png)

对于想要简化一线员工的任务管理的组织，"任务"还包括一些功能，可让你跨一线员工大规模定位、发布和跟踪任务。 例如，公司和区域领导层可以创建和发布面向相关位置（例如特定零售店）的任务列表，并通过实时报告跟踪进度。 经理可以将任务分配给其员工并在其位置内直接进行活动，一线员工在移动或桌面上有分配任务的优先级列表。 若要 [启用任务](#task-publishing)发布，首先需要为组织设置面向团队的层次结构，该层次结构定义层次结构中所有团队的相互关联。

## <a name="what-you-need-to-know-about-tasks"></a>有关任务所需的信息

任务以应用和频道中的选项卡提供。 请记住，该应用包含"要执行"中的单个任务和 Planner 中的团队任务，而选项卡只显示团队任务。

使用"任务"，用户可以获得桌面、Web 和移动体验。 如果任务安装在 Teams 桌面客户端上，用户还会在 Teams Web 和移动客户端上看到任务。 来宾用户除外。 必须知道，来宾只能从 Teams 移动客户端以应用访问任务。 来宾将在 Teams 桌面客户端和 Web 客户端上看到"任务"选项卡。

**我的任务** 显示用户的单个任务。 **共享计划** 显示整个团队正在处理的任务，并包括作为"任务"选项卡添加到频道的任何任务列表。 请注意以下事项：

- 用户在"任务"应用中创建的任务列表也会显示在该用户的"要执行"客户端中。 同样，用户在"任务"中为该用户创建的任务列表将显示在"我的任务"中。 对于单个任务也是如此。

- 添加到频道的任何"任务"选项卡也会显示在 Planner 客户端中。 当用户在 Planner 中创建计划时，该计划不会显示在"任务"或"Planner"应用中，除非它作为选项卡添加到频道。 当用户添加新的"任务"选项卡时，他们可以创建一个新列表或计划或选择现有列表或计划。

## <a name="set-up-tasks"></a>设置任务

> [!IMPORTANT]
> 为 Planner 配置的设置和策略也将应用于任务。

### <a name="enable-or-disable-tasks-in-your-organization"></a>在组织中启用或禁用任务

默认情况下，为组织的所有 Teams 用户启用任务。 可以在 Microsoft Teams 管理中心的"管理应用"页面上关闭或[](manage-apps.md)打开组织级别的应用。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**
2. 在应用列表中，执行下列操作之一：

    - 若要为您的组织关闭"任务"，请搜索"任务"应用，将其选中，然后单击"阻止 **"。**
    - 若要为组织启用"任务"，请搜索"任务"应用，将其选中，然后单击"允许 **"。**

> [!NOTE]
> 如果找不到"任务"应用，请搜索本文第一个注释中的名称。 应用可能仍处于重命名过程中。

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>为组织中特定用户启用或禁用任务

若要允许或阻止组织中特定用户使用"任务"，请确保在"管理应用"页面上为组织启用"任务"，[](manage-apps.md)然后创建自定义应用权限策略并将其分配给这些用户。 若要了解有关详细信息，请参阅["在 Teams 中管理应用权限策略"。](teams-app-permission-policies.md)

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>使用应用设置策略将任务固定到 Teams

应用设置策略可让你自定义 Teams，突出显示对组织中用户最重要的应用。 在策略中设置的应用将固定到 Teams 桌面客户端一侧的应用栏，以及 Teams 移动客户端底部的应用栏，用户可以在这里快速 &mdash; &mdash; 轻松地访问它们。

若要为用户固定"任务"应用，可以编辑全局 (组织范围内的默认) 策略，或者创建和分配自定义应用设置策略。 若要了解有关详细信息，请参阅["在 Teams 中管理应用设置策略"。](teams-app-setup-policies.md)

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>如果用户已获得 Exchange Online 许可，则用户"我的"任务可见

如果不希望用户看到 **"我的任务**"，可以将其隐藏。 为此，请 [删除用户的 Exchange Online 许可证](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)。 必须知道，删除 Exchange Online 许可证后，用户不再有权访问其邮箱。  邮箱数据将保留 30 天，之后数据将被删除且无法恢复，除非将邮箱置于就地保留或诉讼 [保留状态](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)。

我们不建议信息工作者这样做，但在某些情况下可能会适用，例如对于不依赖电子邮件的一线工作者。

## <a name="task-publishing"></a>任务发布

通过任务发布，组织可以发布面向特定位置的任务列表， (团队) 在整个组织中定义和共享在这些位置完成的工作计划。

- 发布团队中的人员（例如公司或区域领导）可以创建任务列表，并发布到特定团队。<br>
    ![任务发布屏幕截图](media/manage-tasks-app-publish.png)
- 收件人团队的经理可以审阅已发布的任务列表，并将单个任务分配给团队成员。<br>
    ![分配任务的屏幕截图](media/manage-tasks-app-assign.png)
- 一线员工有一个简单的移动体验，可以查看分配给他们的任务。 他们可附加照片以在适当的时候显示他们的工作，并将其任务标记为已完成。
- 发布者和经理可以查看报表，查看每个级别的任务的分配和完成状态，包括按位置 (团队) 、任务列表和单个任务。<br>
    ![移动设备上已分配任务的屏幕截图](media/manage-tasks-app-reporting.png)

用户在"任务"应用中的"已发布列表"选项卡上创建、管理和发布任务列表。 如果组织设置了面向层次结构的团队，并且该用户位于[](#set-up-your-team-targeting-hierarchy)层次结构中包含的团队中，则此选项卡仅针对用户显示。 层次结构确定用户是否可以发布或接收任务列表并查看已接收列表的报告。

### <a name="example-scenario"></a>示例方案

下面是任务发布工作原理的示例。

Contoso 正在推出新的食品外卖和递送促销。 为了保持一致的品牌体验，他们需要在 300 多个商店位置协调一致的推出执行。

营销团队与零售通信经理共享促销详细信息和相应的任务列表。 零售通信管理器（充当商店的守护程序）查看信息，创建促销任务列表，然后为每个受影响的商店需要执行的每单位工作创建一个任务。 任务列表完成后，她需要选择必须完成工作的商店。 在这种情况下，促销仅适用于美国具有商店内餐厅的商店。 在"任务"中，她基于商店内餐馆属性筛选商店列表，在层次结构中选择匹配的美国位置，然后将任务列表发布到这些商店。

每个位置的商店经理会收到已发布任务的副本，并将这些任务分配给团队成员。 经理可以使用"任务"体验了解整个存储中所需的全部工作。 他们还可使用可用的筛选器专注于一组特定工作，例如今天到期的工作或特定区域中的工作。

现在，每个商店位置的一线员工在移动设备上的任务中都有一个优先级列表。 完成任务后，将其标记为完成。 一些用户甚至可能会选择将照片上载并附加到任务以显示他们的工作。

Contoso 总部和中级经理可以查看报告，以查看每个商店以及各个商店的任务分配和完成状态。 他们还可以向下钻取到特定任务，以查看不同存储中的状态。 随着发布日期的临近，他们可以发现任何异常，并根据需要与团队核实。 这种可见性可让 Contoso 提高推出效率，并跨应用商店提供更一致的体验。

### <a name="set-up-your-team-targeting-hierarchy"></a>设置团队目标层次结构

若要在组织中启用任务发布，首先必须设置团队目标架构。CSV 文件。 架构定义层次结构中所有团队之间的关联方式，以及用于筛选和选择团队的属性。 创建架构后，将其上传到 Teams 以将其应用到组织。 然后，发布团队成员（例如示例方案中的零售通信经理）可以按层次结构、属性或两者的组合筛选团队，以选择应接收任务列表的相关团队，然后将任务列表发布到这些团队。

有关设置团队目标层次结构的步骤，请参阅"设置团队[目标层次结构"。](set-up-your-team-hierarchy.md)

## <a name="power-automate-and-graph-api"></a>Power Automate 和图形 API

任务支持 Power Automate for Do 和 Graph API for Planner。 要了解详细信息，请参阅：

- [Planner 任务和计划 API 概述](https://docs.microsoft.com/graph/planner-concept-overview)
- [将 Microsoft To Do 与 Power Automate 一起](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
