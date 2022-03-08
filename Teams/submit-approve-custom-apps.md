---
title: 使用 Teams 应用提交 API 提交和审批自定义应用
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何批准使用 Teams 应用提交 API 提交的自定义Microsoft Teams。
ms.openlocfilehash: a1b6778c79fd389ebfd4b3ce172daa186e92b76e
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070401"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>通过应用提交 API 发布Teams提交的自定义应用

## <a name="overview"></a>概述

> [!NOTE]
> 当你发布自定义Teams应用时，该应用可供组织应用商店中的用户使用。 有两种方法可发布自定义应用，使用方式取决于获取应用的方式。 **本文重点介绍如何批准** 和发布开发人员通过应用提交 API 提交的Teams应用。 当开发人员以其他格式将应用包发送给你时，会使用另一种方法.zip应用。 若要详细了解该方法，请参阅通过上传应用包 [发布自定义应用](/microsoftteams/upload-custom-apps)。 审批应用小组件在租户中GCC可用。

> [!IMPORTANT]
> 此方法目前不适用于GCC环境。 必须使用上传 *自定义应用方法* 。

本文提供端到端指南，指导如何将应用从Teams到部署到发现。 你将获得整个应用生命周期中Teams连接体验的概述，以简化如何在你的组织的应用商店中开发、部署和管理自定义应用。

我们将介绍生命周期的每个步骤，包括开发人员如何使用 Teams 应用提交 API 将自定义应用直接提交到 Microsoft Teams 管理中心，以便你审阅和批准、如何设置策略以管理组织中用户的应用，以及用户如何在 Teams 中发现它们。

![从开发到部署的应用概述。](media/custom-app-lifecycle.png)

本指南重点介绍应用Teams面向管理员和 IT 专业人员。 有关开发 Teams 应用的信息，请参阅 Teams [开发人员文档](/microsoftteams/platform)。

## <a name="develop"></a>开发

### <a name="create-the-app"></a>创建应用

开发人员Microsoft Teams开发人员平台，开发人员可以轻松集成自己的应用和服务，以提高工作效率、更快地做出决策，以及围绕现有内容和工作流创建协作。 基于 Teams 平台构建的应用是 Teams 客户端与服务和工作流之间的桥梁，可将它们直接带到协作平台的上下文中。 有关详细信息，请转到开发人员Teams[文档](/microsoftteams/platform)。

### <a name="submit-the-app"></a>提交应用

当应用准备好在生产环境中使用时，开发人员可以使用 Teams 应用提交 API 提交应用，该应用可以从 [Graph API](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog)、集成开发环境 (IDE) （如 Visual Studio Code）或平台（如 Power Apps 和 Power Virtual Agents）. 这样，应用就可以在管理中心的"[](/microsoftteams/manage-apps)管理Microsoft Teams页面上使用，可以在其中查看和批准该应用。

基于 [Microsoft Graph](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog) 构建的 Teams 应用提交 API 允许组织在自己选择的平台上进行开发，并自动执行自定义应用在 Teams 上的提交审批过程。

下面是此应用提交步骤在应用中的外观Visual Studio Code：

![在 Visual Studio Code 中提交应用。](media/custom-app-lifecycle-submit-app.png)

请记住，这不会将应用发布到组织的应用商店。 此步骤将应用提交到Microsoft Teams管理中心，可以在其中批准该应用发布到组织的应用商店。

有关使用 Graph API 提交应用的信息，请参阅[此处](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog)。

## <a name="notify"></a>通知

可以启用通知，以便了解开发人员何时提交新应用程序进行审阅和审批。 开发人员提交应用更新时，你还将收到通知。 若要在管理中心Teams应用提交通知，请转到通知&[**通知""警报** >  > ](https://admin.teams.microsoft.com/notifications/rules)""应用提交"，然后通过将状态更改为"活动"来激活 **规则**。 默认情况下，此设置已关闭。 只有全局管理员或Teams才能启用此设置。

启用此设置后，你将在"管理通知和通知"团队的名为"应用提交"的新频道 **下收到通知**。 或者，可以选择现有团队和频道，将通知传送到指定的团队和频道。 为此，请按照下列步骤操作：

1. 在"**应用提交规则"** 中，选中"**操作"下的"通道警报****"复选框**。
1. 选择" **选择频道"** 按钮。
1. 搜索要添加的团队。
1. 搜索要添加的通道。
1. 选择" **应用"**。

    !["自定义通道警报通知"复选框。](media/channel-alert.png)

> [!NOTE]
> 选中" **默认通道警报** "复选框，以在应用提交通道中向管理员 **通知** 和通知 **团队接收** 通知。

![默认通道警报通知复选框。](media/default-channel-alert.png)

还可在选中"Webhook"复选框后指定公共 Webhook URL，设置到 **外部 Webhook** 的通知。 JSON 通知有效负载将发送到 Webhook URL。

![应用提交通知。](media/app-submission-notification.png)

设置应用提交规则后，可以在指定的通道中查看通知卡以查看应用详细信息，然后选择"查看详细信息"以在管理中心Teams应用。

## <a name="validate"></a>验证

左侧 [导航](/microsoftteams/manage-apps)栏中Microsoft Teams管理 ("管理应用"页，转到 [**"Teams 应用** > ](https://admin.teams.microsoft.com/manage-apps)""管理应用) "，查看组织的所有 Teams 应用。 页面 **顶部的** "挂起审批"小组件可让你了解何时提交自定义应用进行审批。

在表中，新提交的应用会自动显示"已提交"和"**已阻止状态****"的发布状态**。 你可以按降 **序对"发布状态** "列进行排序以快速查找应用。

![发布状态。](media/custom-app-lifecycle-validate-app.png)

单击应用名称转到应用详细信息页。 在 **"关于** "选项卡上，可以查看有关应用的详细信息，包括说明、状态、提交者以及应用 ID。

![已提交应用的应用详细信息页面。](media/custom-app-lifecycle-app-details.png)

有关使用 Graph API 检查发布 **状态的信息**，请参阅 [此处](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id)。

## <a name="publish"></a>发布

当你准备好使应用可供用户使用时，请发布该应用。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 单击应用名称转到应用详细信息页，然后在 **"发布状态** "框中选择"发布 **"**。

    ![应用详细信息页上的"发布"按钮。](media/submitted-app-pending-action.png)

发布应用后，"发布状态 **"将更改** 为"已发布 **"，"****状态"** 会自动更改为"允许 **"**。

## <a name="set-up-and-manage"></a>设置和管理

### <a name="control-access-to-the-app"></a>控制对应用的访问

默认情况下，组织中的所有用户都可以访问组织应用商店中的应用。 若要限制和控制谁有权使用应用，可以创建并分配应用权限策略。 要了解详细信息，请参阅<a href="/microsoftteams/teams-app-permission-policies" target="_blank">在 Teams 中管理应用权限策略</a>。

### <a name="pin-and-install-the-app-for-users-to-discover"></a>固定并安装应用供用户发现

默认情况下，用户若要查找应用，必须转到组织的应用商店并浏览或搜索该应用。 为了方便用户访问该应用，你可以将应用固定到应用中的Teams。 为此，请创建应用设置策略并将其分配给用户。 要了解详细信息，请参阅<a href="/microsoftteams/teams-app-setup-policies" target="_blank">在 Teams 中管理应用设置策略</a>。

### <a name="search-the-audit-log-for-teams-app-events"></a>在审核日志搜索Teams事件

可以搜索应用审核日志查看Teams应用中的活动。 若要详细了解如何搜索 审核日志 并查看 审核日志 中记录的 Teams 活动的列表，请参阅在 Teams 中搜索 审核日志 <a href="/microsoftteams/audit-log-events" target="_blank">事件。</a>

在搜索审核日志之前，你必须先在<a href="https://protection.office.com" target="_blank">安全与合规中心</a>中用审核。 有关详细信息，请参阅<a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">启用或禁用审核日志搜索</a>。 请记住，审核数据仅在你启用审核的那一刻才可用。

## <a name="discover-and-adopt"></a>发现和采用

对应用具有权限的用户可以在组织的应用商店中查找该应用。 转到 **"应用 *"页上*** 的"为组织名称构建"，查找组织的自定义应用。

![显示已发布应用的应用页面。](media/custom-app-lifecycle-discovery.png)

如果创建并分配了应用设置策略，该应用将固定到 Teams 中的应用栏，以便分配了该策略的用户轻松访问。

## <a name="update"></a>更新

若要更新应用，开发人员应继续按照开发部分中 [的步骤](#develop) 操作。

当开发人员将更新提交到已发布的自定义应用时，您将在"管理应用"页面的"挂起 **审批** "小组件 [中](/microsoftteams/manage-apps) 收到通知。 在表中， **应用的发布** 状态将设置为"已 **提交更新"**。 如果启用应用提交通知，则还会在应用提交通道下的"管理员通知和通知"团队中收到通知。 通知卡将具有一个链接，可让你直接在管理中心Teams应用。 若要详细了解如何启用应用提交通知，请参阅 [通知](#notify)。

![显示挂起的请求和应用状态的"管理应用"页面。](media/custom-app-lifecycle-update-submitted.png)

查看和发布应用更新：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 单击应用名称转到应用详细信息页，然后选择"可用更新"查看更新的详细信息。

    ![应用详细信息页面。](media/custom-app-lifecycle-update-app.png)
3. 准备就绪后，选择" **发布** "以发布更新。 执行此操作会替换现有应用，更新版本号，将发布 **状态更改为** "已发布 **"**。 对于更新的应用，所有应用权限策略和应用设置策略仍然强制实施。

    如果你拒绝更新，则应用的早期版本将保持发布状态。

请记住以下事项：

- 应用获得批准后，任何用户都可以向应用提交更新。 这意味着其他开发人员（包括最初提交该应用的开发人员）可以提交应用更新。
- 当开发人员提交应用并且请求挂起时，只有该开发人员才能向应用提交更新。 其他开发人员只能在应用获得批准后提交更新。

有关使用 Graph API 更新应用的信息，请参阅<a href="/graph/api/teamsapp-update">此处</a>。

## <a name="related-topics"></a>相关主题

- [通过上传应用包发布自定义应用](upload-custom-apps.md)
- [在管理中心内Microsoft Teams应用](manage-apps.md)
- [在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
- [在 Teams 中管理应用设置策略](teams-app-setup-policies.md)
- [Teams监视和警报](alerts/teams-admin-alerts.md)
- <a href="/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">适用于 Graph 应用的 Microsoft Teams API</a>
