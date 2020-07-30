---
title: 使用团队应用提交 API 提交和批准自定义应用
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用 Microsoft 团队中的团队应用提交 API 批准已提交的自定义应用。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4c3563dc028c8566d29906e4e42a2002a197e71d
ms.sourcegitcommit: 8812db47b45d171d47e71f87e84ab1828590392d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46523671"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>发布通过团队应用提交 API 提交的自定义应用

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>概述

> [!NOTE]
> 发布自定义团队应用时，用户可在组织的应用商店中使用。 发布自定义应用的方法有两种，使用方式取决于你获取该应用的方式。 **本文重点介绍如何批准和发布开发人员通过团队应用提交 API 提交的自定义应用**。 当开发人员以 .zip 格式发送应用包时，将使用另一种方法，即上载自定义应用。 若要了解有关该方法的详细信息，请参阅[通过上载应用包发布自定义应用](manage-your-custom-apps.md)。
 
本文提供了有关如何将你的团队应用从开发转到部署到发现的端到端指南。 你将大致了解团队在应用生命周期中提供的连接体验，以简化如何在组织的应用商店中开发、部署和管理自定义应用。

我们将介绍生命周期的每个步骤，包括开发人员如何使用团队应用提交 API 将自定义应用直接提交到 Microsoft 团队管理中心供你查看和批准，如何设置策略以管理你组织中的用户的应用，以及你的用户如何在团队中发现这些应用。

![从开发到部署概述应用](media/custom-app-lifecycle.png)

本指南重点介绍应用的团队方面，并面向管理员和 IT 专业人士。 有关开发团队应用的信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">团队开发人员文档</a>。

## <a name="develop"></a>开发

### <a name="create-the-app"></a>创建应用

Microsoft 团队开发人员平台使开发人员可以轻松地集成你自己的应用和服务，以提高工作效率、更快地做出决策以及围绕现有内容和工作流创建协作。 在团队平台上构建的应用是团队客户端和你的服务和工作流之间的桥梁，可直接将它们引入协作平台的上下文中。 有关详细信息，请转到<a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">团队开发人员文档</a>。

### <a name="submit-the-app"></a>提交应用

当应用准备好在生产中使用时，开发人员可以使用团队应用提交 API 提交应用，该 API 可以从 Graph API、集成开发环境（IDE）（如 Visual Studio 代码）或平台（如 Power App 和 Power Virtual Agent）进行调用。 执行此操作将使应用在 Microsoft 团队管理中心的 "<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理应用</a>" 页面上可用，你的管理员可以在其中查看和批准该应用。 

在 Microsoft Graph 上构建的团队应用提交 API 允许你的组织在你选择的平台上进行开发，并为团队中的自定义应用自动执行提交到审批流程。

下面是此应用提交步骤在 Visual Studio 代码中的外观示例：

![在 Visual Studio 代码中提交应用的屏幕截图](media/custom-app-lifecycle-submit-app.png)

请记住，这并不会将应用发布到你的组织的应用商店。 此步骤将应用提交到 Microsoft 团队管理中心，你可以在其中批准将其发布到你的组织的应用商店。

## <a name="validate"></a>复核

Microsoft 团队管理中心中的 "<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理应用</a>" 页面（在左侧导航中，转到 "**团队应用**  >  **管理应用**"）可为你的组织提供所有团队应用的视图。 页面顶部的 "**待定审批**" 小组件可让你知道何时提交自定义应用以供审批。

在表格中，新提交的应用会自动显示已提交**状态**的 "已**提交**" 和 "已**阻止**"**状态**。 可以按降序对 "**发布状态**" 列进行排序，以便快速找到该应用。

!["管理应用" 页面的屏幕截图，显示挂起的请求和应用状态 ](media/custom-app-lifecycle-validate-app.png)

单击应用名称以转到 "应用详细信息" 页面。 在 "**关于**" 选项卡上，您可以查看有关应用的详细信息，包括说明、状态、提交者和应用 ID。

![已提交应用的应用程序详细信息页面的屏幕截图](media/custom-app-lifecycle-app-details.png)

## <a name="publish"></a>发布

当你准备好使应用可供用户使用时，请发布应用。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。
2. 单击应用名称转到 "应用程序详细信息" 页，然后在 "**发布状态**" 框中，选择 "**发布**"。

    发布应用后，**发布状态**将更改为 "**已发布**"，"**状态**" 将自动更改为 "**允许**"。

## <a name="set-up-and-manage"></a>设置和管理

### <a name="control-access-to-the-app"></a>控制对应用的访问

默认情况下，组织中的所有用户都可以访问组织的应用商店中的应用。 若要限制和控制谁有权使用该应用程序，你可以创建并分配应用权限策略。 若要了解详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">管理团队中的应用权限策略</a>。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>固定并安装应用以供用户发现

默认情况下，用户可以使用该应用程序找到你的组织的应用商店所需的应用，然后浏览或搜索它。 若要使用户可以轻松访问应用，可以将应用固定到团队中的应用栏。 若要执行此操作，请创建应用设置策略并将其分配给用户。 若要了解详细信息，请参阅<a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">管理团队中的应用设置策略</a>。

## <a name="discover-and-adopt"></a>探索和采纳

具有应用权限的用户可以在你的组织的应用商店中找到它。 转到 "应用" 页面上的 "为***你的组织名称*生成**" 以查找你的组织的自定义应用。

![显示已发布应用的 "应用" 页面的屏幕截图 ](media/custom-app-lifecycle-discovery.png)

如果你创建并分配了应用设置策略，应用将固定到团队中的应用栏，以便为分配了该策略的用户轻松访问。

## <a name="update"></a>更新

若要更新应用，开发人员应继续按照 "[开发](#develop)" 部分中的步骤操作。

当开发人员向已发布的自定义应用程序提交更新时，将在 "<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">管理应用程序</a>" 页面的 "**挂起审批**" 小组件中收到通知。 在表中，应用的**发布状态**将设置为 "已**提交更新**"。

!["管理应用" 页面的屏幕截图，显示挂起的请求和应用状态 ](media/custom-app-lifecycle-update-submitted.png)

要查看和发布应用更新，请执行以下操作：

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。
2. 单击应用名称转到 "应用详细信息" 页面，然后选择 "**更新可用**" 以查看更新的详细信息。

    !["管理应用" 页面的屏幕截图，显示挂起的请求和应用状态 ](media/custom-app-lifecycle-update-app.png)
3. 准备就绪后，选择 "**发布**" 以发布更新。 执行此操作将替换现有应用、更新版本号，并将**发布状态**更改为 "**已发布**"。 所有应用权限策略和应用设置策略对于更新的应用均保持强制实施。

    如果拒绝更新，则早期版本的应用仍将发布。

请记住以下事项：

- 当应用获得批准后，任何人都可以向应用提交更新。 这意味着其他开发人员（包括最初提交该应用的开发人员）可以提交对该应用的更新。
- 当开发人员提交应用且请求处于挂起状态时，仅该开发人员可以向该应用提交更新。 其他开发人员只能在应用获得批准后提交更新。

### <a name="update-experience-for-users"></a>用户更新体验

在大多数情况下，发布应用更新后，将自动为用户显示新版本。 但是，对<a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft 团队清单</a>有一些更新需要用户接受才能完成：

* 已添加或删除机器人
* 现有 bot 的 "botId" 属性已更改
* 现有 bot 的 "isNotificationOnly" 属性已更改
* Bot 的 "supportsFiles" 属性已更改
* 添加或删除了消息传递扩展
* 添加了新的连接器
* 添加了新的静态选项卡
* 添加了新的 "可配置" 选项卡
* "WebApplicationInfo" 中的属性已更改

![显示新版本可用的应用的屏幕截图](media/manage-your-custom-apps-update1.png)

![应用的升级选项的屏幕截图](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>相关主题

- [在 Microsoft 团队管理中心中管理你的应用](manage-apps.md)
- [在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
- [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
