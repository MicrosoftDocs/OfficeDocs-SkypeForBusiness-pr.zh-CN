---
title: 了解 Microsoft Teams 中的应用
ms.reviewer: ''
description: 了解应用，并根据组织的用户配置和业务要求决定在 Teams 中允许哪些应用。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b6fd5ef344550cf85420faef1748c34f6e87e88b
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556523"
---
# <a name="about-apps-in-microsoft-teams"></a>关于 Microsoft Teams 的应用

应用允许用户从他们喜爱的服务中查找内容，并在 Teams 中共享。 它们使你能够执行多种任务，例如在频道顶部固定服务、使用机器人自动执行通知或共享和分配任务。 若要详细了解应用的用途，请阅读 [针对最终用户的应用概述](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

最终用户可在 Teams 中使用的不同类型的应用包括 Microsoft 创建的应用、经过认证的第三方应用以及你自己的组织创建的自定义应用。

## <a name="use-microsoft-provided-apps"></a>使用 Microsoft 提供的应用

Teams自带一组内置应用，包括列表、任务、表扬、审批等。 我们建议在最初的 Teams 推出中加入 Teams 特色应用 - 例如 Planner。 在你推动 Teams 采用时添加其他应用。 某些默认功能（如活动流、聊天、日历和通话）默认为可用，并已固定以方便最终用户访问。

## <a name="use-third-party-apps"></a>使用第三方应用

除了 Microsoft 提供的应用，还可以使用经 Microsoft 验证的第三方应用。Microsoft 与 Microsoft 365 开发人员合作伙伴合作，提供加快使用 Teams 应用决策所需的信息。有关详细信息，请参阅 [Microsoft Teams 应用安全性和合规性](/microsoft-365-app-certification/teams/teams-apps)。

## <a name="use-open-source-sample-apps-provided-by-microsoft"></a>使用 Microsoft 提供的开源示例应用

你也可以使用 [Teams模板](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)，Microsoft Teams 生产就绪的应用是由社区驱动，开源，且在GitHub上可用的。

## <a name="create-custom-apps"></a>创建自定义应用

可以通过使用 Teams 与[Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions)的集成，快速构建自定义的低代码解决方案。 也可以根据自己的业务需求，创建自己的定制应用。 有关更多信息，请参阅 [为 Microsoft Teams 构建应用](/microsoftteams/platform/overview)。  

## <a name="apps-deployment-decisions"></a>应用部署决策

Teams 为组织提供了现成的出色协作体验，并且大多数组织发现默认设置适合它们。本文可帮助你决定是否要根据组织的情况和业务需求更改任何默认设置，然后引导你完成每项更改。我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。

## <a name="core-deployment-decisions"></a>核心部署决策

以下是大多数组织在默认设置不适合的情况下想要更改的应用设置。

### <a name="app-availability-settings"></a>应用可用性设置

Teams 提供了许多由 Microsoft 和第三方发布的应用，以吸引用户、支持生产力，以及将常用的业务服务集成到 Teams 中。
从 Teams 应用商店获取应用。 默认情况下，所有应用（包括你通过 [Teams 应用商店审批流程](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)提交的自定义应用）均对所有用户开启。 例如，用户可以使用 Planner 应用在 Teams 中构建和管理团队任务。

默认情况下，所有 Microsoft 提供的应用、第三方和自定义应用均可用，且你可启用或关闭单独的应用。 可通过一项全组织范围内的设置来为整个组织启用或禁用所有第三方和/或自定义应用。

| 询问你自己 | 操作 |
|--------------|--------|
|是否要更改默认 Teams 应用设置？ | 要详细了解可用于管理组织内部应用的策略和设置，请参阅 [Microsoft Teams 中针对应用的管理员设置](admin-settings.md)。|

### <a name="app-permissions-and-other-considerations"></a>应用权限和其他注意事项

应用由用户允许，并由管理员或 IT 专业人员通过策略进行管理。 但是，应用权限和风险配置文件在应用本身中定义。

| 询问你自己 | 操作 |
|--------------|--------|
|<br>希望允许访问哪些应用？ 不希望允许访问哪些应用？  | <ul><li>有关在允许访问应用、聊天机器人、选项卡或连接器时要考虑的事项的列表，请参阅 [Microsoft Teams 应用权限和注意事项](app-permissions.md)。</li><li>有关将应用提供给组织中的用户的信息，请参阅“[在 Microsoft Teams 管理中心管理应用](manage-apps.md)”。</li></ul>|

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

## <a name="additional-deployment-decisions"></a>其他部署决策

可以根据组织的需求和配置更改这些设置。

### <a name="activity-reports"></a>活动报告

你可以使用活动报告来查看组织中的用户使用 Teams 的情况。 例如，如果某些用户尚未使用 Teams，他们可能不知道如何开始使用或了解如何使用 Teams 提高工作效率和改善协作。 组织可以使用活动报告来决定在何处优先安排培训和沟通工作。 若要查看活动报告，你必须是 Microsoft 365 或 Office 365 中的全局管理员、Teams 服务管理员或 Skype for Business 管理员。

| 询问你自己 | 操作 |
|--------------|--------|
| <br>谁需要查看活动报告，他们是否有查看这些报告的正确权限？ |<ul><li>如果不想为用户分配管理员角色，则可以[分配报告阅读者角色](teams-activity-reports.md#reports-reader-role)。</li><li>有关在 Azure Active Directory 中分配管理员角色的信息，请参阅[角色和权限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)以及[查看和分配角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</li></ul> |

### <a name="app-templates"></a>应用模板

应用模板是适用于 Microsoft 的生产就绪应用，它们由社区驱动、开源，并可在 GitHub 上使用。 每个应用都包含为组织部署和安装它的详细说明，并且是一个随时可用的应用，你可以立即安装并开始使用。

此外，还提供完整的源代码，以便你可以对其进行详细的研究，或获取相应代码并进行更改以满足你的特定需求。

| 询问你自己 | 操作 |
|--------------|--------|
| 我是否想要安装任何 Teams 应用模板，例如 Icebreaker？ |若要了解详细信息，请参阅[适用于 Teams 的应用模板](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json)。|
