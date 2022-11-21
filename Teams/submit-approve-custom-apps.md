---
title: 使用 Teams 应用提交 API 提交和批准自定义应用
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/19/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中批准使用 Teams 应用提交 API 提交的自定义应用。
ms.openlocfilehash: 83a4896fbd849cf55020854fd617da003d589cb0
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131261"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>发布使用 Teams 应用提交 API 提交的自定义应用

本文提供有关如何将 Teams 应用从开发到部署到发现的过程的端到端指导。 你将大致了解 Teams 在应用生命周期内提供的连接体验，以简化如何在组织的应用商店中开发、部署和管理自定义应用。

我们将介绍生命周期的每个步骤，包括开发人员如何使用 Teams 应用提交 API 将自定义应用直接提交到 Microsoft Teams 管理中心供你查看和批准、如何设置策略来管理组织中用户的应用，以及用户如何在 Teams 中发现它们。

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="从开发到部署的应用概述。":::

本指南重点介绍应用的 Teams 方面，适用于管理员和 IT 专业人员。 有关开发 Teams 应用的信息，请参阅 [Teams 开发人员文档](/microsoftteams/platform)。

> [!NOTE]
> 发布自定义 Teams 应用时，组织应用商店中的用户可以使用它。 发布自定义应用有两种方法，使用的方式取决于获取应用的方式。 本文重点介绍如何批准和发布开发人员通过 Teams 应用提交 API 提交的自定义应用。 开发人员以 .zip 格式向你发送应用包时，将使用另一种方法（上传自定义应用）。 若要了解有关该方法的详细信息，请参阅[通过上传应用包发布自定义应用](/microsoftteams/upload-custom-apps)。 批准的应用小组件在 GCC 租户中不可用。

> [!IMPORTANT]
> 此方法在 GCC 环境中不可用。 [上传自定义应用](upload-custom-apps.md)以在 GCC 环境中发布它。

## <a name="develop"></a>开发

### <a name="create-the-app"></a>创建应用

借助 Microsoft Teams 开发人员平台，开发人员可以轻松集成自己的应用和服务，以提高工作效率、更快地做出决策，并围绕现有内容和工作流创建协作。 基于 Teams 平台构建的应用是 Teams 客户端与服务和工作流之间的桥梁，可将它们直接引入协作平台的上下文中。 有关详细信息，请转到 [Teams 开发人员文档](/microsoftteams/platform)。

### <a name="submit-the-app"></a>提交应用

当应用准备好在生产环境中使用时，开发人员可以使用 Teams 应用提交 API 提交应用，该 API 可从[图形 API](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)、集成开发环境 (IDE)（例如 Visual Studio Code）或 Power Apps 和 Power Virtual Agents 等平台进行调用。 这样做可使应用在 Teams 管理中心的“[管理应用](/microsoftteams/manage-apps)”页面上可用，你可以在这里查看和批准它。

[基于 Microsoft Graph 构建](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)的 Teams 应用提交 API 允许组织在所选平台上进行开发，并自动完成 Teams 上自定义应用的提交到批准过程。

下面是此应用提交步骤在 Visual Studio Code 中的外观示例：

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="Visual Studio Code 中应用提交的屏幕截图。":::

请记住，此操作尚未将应用发布到组织的应用商店。 此步骤会将应用提交到 Teams 管理中心，你可以在其中批准该应用，从而发布到组织的应用商店。

有关使用 Graph API 提交应用的详细信息，请参阅[此处](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true)。

## <a name="notify"></a>通知

你可以打开通知，以便了解开发人员何时提交新的应用程序以供审核和批准。 开发人员提交应用更新时，你也会收到通知。 若要在 Teams 管理中心启用应用提交通知，请转到“**通知和提醒**” > **“[规则](https://admin.teams.microsoft.com/notifications/rules)”** > “**应用提交**”，并通过将状态更改为“**活动**”来激活规则。 默认情况下，此设置已关闭。 你必须是全局管理员或 Teams 管理员才能启用此设置。

启用此设置后，你将在名为“**应用提交**”的新频道下的“**管理员提醒和通知**”团队中收到通知。 或者，可以选择现有团队和频道以将通知发送给指定的团队和频道。 为此，请按照下列步骤操作：

1. 在“**应用提交**”规则中，选择“**操作**”下的“**频道提醒**”复选框。
1. 选择“**选择频道**”按钮。
1. 搜索要添加的团队。
1. 搜索要添加的频道。
1. 选择“**应用**”。

   :::image type="content" source="media/channel-alert.png" alt-text="自定义频道提醒通知复选框。" lightbox="media/channel-alert.png":::

> [!NOTE]
> 选择“**默认频道提醒**”复选框，以将通知接收到“**应用提交**”频道中的“**管理员提醒和通知**”团队。

:::image type="content" source="media/default-channel-alert.png" alt-text="默认频道提醒通知复选框。" lightbox="media/default-channel-alert.png":::

还可以通过在选中“**Webhook**”复选框后指定公共 Webhook URL 来设置外部 Webhook 的通知。 JSON 通知有效负载将发送到 Webhook URL。

:::image type="content" source="media/app-submission-notification.png" alt-text="应用提交通知。" lightbox="media/app-submission-notification.png":::

设置应用提交规则后，可以在指定的频道中查看通知卡片以查看应用详细信息，并选择“**查看详细信息**”以在 Teams 管理中心打开应用。

## <a name="validate"></a>验证

利用 Teams 管理中心的“[管理应用](/microsoftteams/manage-apps)”页面（在左侧导航中，转到“[**Teams 应用**” > “**管理应用**](https://admin.teams.microsoft.com/manage-apps)”），可查看组织的所有 Teams 应用。 在页面顶部的“**等待审批**”小组件中，可以了解提交自定义应用以供审批的时间。

在表中，新提交的应用会自动显示 **发布状态**“**已提交**”和 **状态**“**已阻止**”。 可以按降序对“**发布状态**”列进行排序，以便快速找到应用。

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="发布状态。" lightbox="media/custom-app-lifecycle-validate-app.png":::

单击应用名称转到应用详细信息页。 在“**关于**”选项卡上，可以查看有关应用的详细信息，包括说明、状态、提交者和应用 ID。

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="提交的应用的应用详细信息页。" lightbox="media/custom-app-lifecycle-app-details.png":::

有关使用 Graph API 检查 **发布状态** 的详细信息，请参阅 [此处](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true)。

## <a name="publish"></a>发布

准备好使应用可供用户使用时，请发布该应用。

1. 登录到 Teams 管理中心，然后转到“**Teams 应用**” > “**[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**”。
1. 选择应用名称以转到应用详细信息页，然后在“**发布状态**”框中，选择“**发布**”。

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="应用详细信息页上的“发布”按钮。":::

发布应用后，**发布状态** 会更改为“**已发布**”，**状态** 会更改为“**允许**”。

## <a name="set-up-and-manage"></a>设置和管理

### <a name="control-access-to-the-app"></a>控制对应用的访问

默认情况下，组织中的所有用户都可以访问组织应用商店中的应用。 若要限制和控制谁有权使用应用，可以创建和分配应用权限策略。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>固定并安装应用供用户发现

默认情况下，用户若要查找应用，必须转到组织的应用商店并浏览或搜索它。 为了方便用户访问应用，可以将应用固定到 Teams 中的应用栏。 为此，请创建应用设置策略并将其分配给用户。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

### <a name="search-the-audit-log-for-teams-app-events"></a>搜索 Teams 应用事件的审核日志

可以搜索审核日志以查看组织中的 Teams 应用活动。 若要详细了解如何搜索审核日志并查看审核日志中记录的 Teams 活动列表，请参阅[在审核日志中搜索 Teams 事件](audit-log-events.md)。

在搜索审核日志之前，你必须先在[安全与合规中心](https://sip.protection.office.com/)中用审核。 有关详细信息，请参阅[启用或禁用审核日志搜索](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true)。 请记住，审核数据仅在你启用审核的那一刻才可用。

## <a name="discover-and-adopt"></a>发现和采用

拥有应用权限的用户可以在组织的应用商店中找到它。 转到“应用”页面上的“ **为 *组织名称* 生成** ”，查找组织的自定义应用。

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="显示已发布应用的“应用”页面。" lightbox="media/custom-app-lifecycle-discovery.png":::

如果创建并分配了应用设置策略，应用将固定到 Teams 中的应用栏，以便为分配了策略的用户轻松访问。

## <a name="update"></a>更新

若要更新应用，开发人员应继续执行“[开发](#develop)”部分中的步骤。

当开发人员将更新提交到已发布的自定义应用时，你会在“[管理应用](/microsoftteams/manage-apps)”页面的“**等待审批**”小组件中收到通知。 在表中，应用的“**发布状态**”将设置为“**已提交更新**”。 如果启用了应用提交通知，你还会在“**应用提交**”频道下的“**管理员提醒和通知**”团队中收到通知。 通知卡片将具有一个链接，可将你直接转到 Teams 管理中心内的应用。 有关如何启用应用提交通知的详细信息，请参阅[通知](#notify)。

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="“管理应用”页面，显示挂起的请求和应用状态。" lightbox="media/custom-app-lifecycle-update-submitted.png":::

若要查看和发布应用更新，请执行以下操作：

1. 在 Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
1. 单击应用名称转到应用详细信息页，然后选择“**可用更新**”以查看更新的详细信息。

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="应用详细信息页。" lightbox="media/custom-app-lifecycle-update-app.png":::

1. 准备就绪后，选择“**发布**”以发布更新。 执行此操作将替换现有应用，更新版本号，并将 **发布状态** 更改为“**已发布**”。 所有应用权限策略和应用设置策略仍会对更新后的应用强制执行。

    如果拒绝更新，应用的早期版本将保持发布状态。

请记住下列事项：

* 当应用获得批准时，任何人都可以向应用提交更新。 这意味着其他开发人员（包括最初提交应用的开发人员）可以向应用提交更新。
* 当开发人员提交应用且请求处于挂起状态时，只有同一开发人员可以向应用提交更新。 其他开发人员只能在应用获得批准后提交更新。

有关使用 Graph API 更新应用的详细信息，请参阅[此处](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true)。

## <a name="related-articles"></a>相关文章

* [通过上载应用包来发布自定义应用](upload-custom-apps.md)
* [在 Microsoft Teams 管理中心管理应用](manage-apps.md)
* [管理自定义应用的策略和设置](teams-custom-app-policies-and-settings.md)
* [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
* [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
* [Teams 监视和警报](alerts/teams-admin-alerts.md)
* [适用于 Teams 应用的 Microsoft Graph API](alerts/teams-admin-alerts.md)
