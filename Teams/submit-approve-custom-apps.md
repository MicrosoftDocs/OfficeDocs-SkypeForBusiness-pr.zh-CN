---
title: 使用 Teams 应用提交 API 提交和批准自定义应用
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
description: 了解如何批准使用 Microsoft Teams 中的 Teams 应用提交 API 提交的自定义应用。
ms.openlocfilehash: bdd13dbe4db46110250ea380eebd0ea1d011a322
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824913"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>发布通过 Teams 应用提交 API 提交的自定义应用

## <a name="overview"></a>概述

> [!NOTE]
> 在你发布自定义 Teams 应用时，它可供组织的应用商店中的用户使用。 发布自定义应用的方法有两种，而根据获取应用的方式，具体取决于获取应用的方式。 **本文重点介绍了开发人员**通过 Teams 应用提交 API 提交的自定义应用。 当开发人员使用 .zip 格式向你发送应用包时，会使用上传自定义应用。 若要了解有关该方法的详细信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">"通过上载应用包发布自定义应用</a>"。
 
本文提供端到端指导，指导如何让 Teams 应用开发到部署到发现。 你将概述 Teams 在应用生命周期内获得概述，简化了如何在组织的应用商店中开发、部署和管理自定义应用。

我们将介绍生命周期的每个步骤，包括开发人员可如何使用 Teams 应用提交 API 将自定义应用直接提交到 Microsoft Teams 管理中心，以便你审查和批准，如何设置策略以管理组织中用户的应用以及用户在 Teams 中发现它们的方式。

![应用从开发到部署的概述](media/custom-app-lifecycle.png)

本指南侧重于 Teams 应用的一个方面，并适用于管理员和 IT 专业人员。 有关开发 Teams 应用的信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams 开发人员文档</a>。

## <a name="develop"></a>开发

### <a name="create-the-app"></a>创建应用

Microsoft Teams 开发人员平台可让开发人员轻松集成你自己的应用和服务，从而提高工作效率、更快决策，并围现现有内容和工作流进行协作。 Teams 平台上构建的应用是 Teams 客户端与你的服务和工作流之间的聚合，并将其直接放入协作平台的上下文中。 有关详细信息，请转到 Teams <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">开发人员文档</a>。

### <a name="submit-the-app"></a>提交应用

当应用准备好在生作环境中使用时，开发人员可以使用 Teams 应用提交 API 提交应用，可以从 <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">图形 API、集</a>成的开发环境 (IDE) Visual Studio）或 Power 应用和 Power Virtual 代理等平台上提交应用。 这样，可在 Microsoft Teams 管理中心的"管理 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">应用</a> "页面上访问该应用，而你和管理员可以在此查看和批准它。更改 

这些 Teams 应用提交 API <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">是在 Microsoft Graph</a>基上构建的，允许组织开发你选择的平台，并自动为 Teams 上的自定义应用提供提交到审批流程。

下面是此应用提交步骤在代码中的Visual Studio示例：

![使用代码提交应用Visual Studio屏幕截图](media/custom-app-lifecycle-submit-app.png)

请记住，这不会将应用发布到你的组织的应用商店。 此步骤会将应用提交到 Microsoft Teams 管理中心，在这里，你可以批准该应用以便发布到组织的应用商店。

有关使用图形 API 提交应用的详细信息，<a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">请参阅此处。</a>

## <a name="validate"></a>Validate

在<a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Microsoft</a> Teams 管理中心 (的"管理应用"页面的左侧导航**Teams apps**  >  **Manage apps**栏中，转到 Teams 应用管理) ，它将介绍你组织的所有 Teams 应用。 页面 **顶部的待** 定审批小组件可使你知道何时提交自定义应用以供审批。

在表中，新提交的应用会自动**显示"已**提交 **"** 和"被阻止**状态****"的发布状态**。 你可以按 **降序对** "发布状态"列进行排序，以便快速找到应用。

![显示待处理请求和应用状态的"管理应用"页面的屏幕截图 ](media/custom-app-lifecycle-validate-app.png)

单击应用名称转到应用详细信息页面。 在" **关** 于"选项卡上，您可以查看有关该应用的详细信息，包括说明、状态、子项目栏和应用 ID。

![已提交应用的应用详细信息页面的屏幕截图](media/custom-app-lifecycle-app-details.png)

有关使用图形 API 检查发布状态的详细信息 **，**<a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">请参阅此处</a>。

## <a name="publish"></a>发布

当准备好向用户提供应用时，请发布应用。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。
2. 单击应用名称转到应用详细信息页，然后在"发布 **状态"** 框中选择" **发布**"。

    在发布应用后，发布 **状态将** 更改为已 **发布状态** ， **状态会** 自动更改为 **"已允许**"。

## <a name="set-up-and-manage"></a>设置和管理

### <a name="control-access-to-the-app"></a>控制对应用的访问

默认情况下，组织中的所有用户都可以访问你组织的应用商店中的应用。 若要限制和控制谁有权使用此应用，可以创建和分配应用许可策略。 若要了解详细信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Teams 中的"管理应用权限策略</a>"。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>固定并安装可供用户发现的应用

默认情况下，用户可找到他们需要转到你组织的应用商店、浏览或搜索它所必要的应用。 要使用户可以轻松地访问应用，你可以将应用固定到 Teams 中的应用栏。 若要执行此操作，请创建应用设置策略并将其分配给用户。 若要了解详细信息，请参阅 <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Teams 中的"管理应用设置策略</a>"。

### <a name="search-the-audit-log-for-teams-app-events"></a>在审核日志 Teams 应用事件的屏幕截图

你可以搜索审核日志以查看组织中的 Teams 应用活动。 若要深入了解如何搜索 审核日志 并查看在 审核日志 中记录的 Teams 活动列表，请参阅 <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">"在 Teams 审核日志中搜索事件</a>"。

必须先在审核日志应用合规中心中打开 <a href="https://protection.office.com" target="_blank">审&审</a>。 要了解详细信息， <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">请参阅审核日志搜索和关闭</a>。 请记住，审计数据仅在打开审计时时提供。

## <a name="discover-and-adopt"></a>发现和接受

对应用具有此权限的用户可以在组织的应用商店中找到它。 转到" **应用 *"页面上为组织名称*** 构建，以查找组织的自定义应用。

![显示已发布应用的"应用"页面的屏幕截图 ](media/custom-app-lifecycle-discovery.png)

如果创建并分配了应用安装策略，则会将应用固定到 Teams 中的应用栏，以便这些用户都可以轻松访问该策略。

## <a name="update"></a>更新

若要更新应用，开发人员应该继续按照"开发"部分 [中的步骤](#develop) 操作。

当开发人员向已发布的自定义应用提交更新时，你会在"管理 **应用"页面的"待** 定审批"小组件中 <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">收到</a> 通知。 在表格中 **，应用的**发布状态将设置为 **"更新"。**

![显示待处理请求和应用状态的"管理应用"页面的屏幕截图 ](media/custom-app-lifecycle-update-submitted.png)

若要查看并发布应用更新，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到**Teams 应用**  >  **管理应用**。
2. 单击应用名称转到应用详细信息页，然后选择 **"更新"以** 查看更新详细信息。

    ![显示待处理请求和应用状态的"管理应用"页面的屏幕截图 ](media/custom-app-lifecycle-update-app.png)
3. 准备就绪后，选择" **发布"** 以发布更新。 执行此操作会替换现有应用，更新版本号，并将 **"发布"状态更改为****"已发布**"。 已对更新的应用执行所有应用权限策略和应用设置策略。

    如果你拒绝更新，则会保持已发布的早期版本的应用。

请记住以下事项：

- 批准应用后，任何人都可以提交应用更新。 这意味着包括最初提交应用的开发人员）可以向应用提交更新。
- 当开发人员提交应用并且请求挂起时，仅当同一开发人员才能向应用提交更新。 其他开发人员只能在审批应用后提交更新。

有关使用图形 API 更新应用的详细信息，请参阅 <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">此处</a>。

### <a name="update-experience-for-users"></a>更新用户体验

在大多数情况下，发布应用更新后，会自动为用户显示新版本。 但是 <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">，Microsoft Teams</a> 清单会有一些更新，要求用户接受才能完成：

* 已添加或删除自动程序
* 已更改一个现有机器的 "botId" 属性
* 已更改一个现有机器的"isNotificationOnly"属性
* 已更改 bot 的"supportsFiles"属性
* 添加或删除了一个邮件扩展
* 已添加一条新连接线
* 已添加新的"静态"选项卡
* 已添加新的可配置选项卡
* 已更改"webApplicationInfo"内的属性

![显示有新版本可用的应用的屏幕截图](media/manage-your-custom-apps-update1.png)

![应用升级选项的屏幕截图](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>相关主题

- [通过上载应用包发布自定义应用](upload-custom-apps.md)
- [在 Microsoft Teams 管理中心中管理应用](manage-apps.md)
- [在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
- [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">适用于 Teams 应用的 Microsoft Graph API</a>
