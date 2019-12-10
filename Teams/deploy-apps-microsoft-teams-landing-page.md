---
title: Microsoft Teams 中的应用、聊天机器人和连接器
ms.reviewer: ''
description: 使用这些部署资源帮助你在 Microsoft Teams 中部署应用。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: c808c8a44a649a37f6d13d31538dd08797d56b24
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909448"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a>Microsoft Teams 中的应用、聊天机器人和连接器

应用使你能通过收藏夹服务查找内容，并就在 Teams 中分享内容。 应用可帮助你执行某些操作，例如将服务固定在频道的顶部、与聊天机器人聊天，或者共享和分配任务。 若要了解详细信息，请阅读 [Teams 中的应用概述](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

我们建议你在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。 在推动 Teams 采用的过程中添加其他应用、聊天机器人和连接器。

此外，还提供用于创建自定义应用程序的选项。 有关详细信息，请参阅“[开发人员文档](/microsoftteams/platform/overview)”。

## <a name="apps-deployment-decisions"></a>应用部署决策

Teams 为组织提供了现成的出色协作体验，并且大多数组织发现默认设置适合它们。 本文可帮助你决定是否要根据组织的情况和业务需求更改任何默认设置，然后引导你完成每项更改。 我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。 第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。

## <a name="core-deployment-decisions"></a>核心部署决策

以下是大多数组织在默认设置不适合的情况下想要更改的应用设置。

### <a name="app-availability-settings"></a>应用可用性设置 

Teams 提供了一些由 Microsoft 和第三方发布的应用来吸引客户、支持高效工作，而且 Teams 中还集成了常用的业务服务。 从 Teams 应用商店获取应用。 默认情况下，所有应用（包括你通过 [Teams 应用商店审批流程](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)提交的自定义应用）均对所有用户开启。 例如，用户可以使用 Planner 应用在 Teams 中构建和管理团队任务。

默认情况下，所有 Microsoft 提供的应用和自定义应用均可用，且你可启用或关闭单独的应用。 可通过一项全组织范围内的设置来为整个组织启用或关闭所有自定义应用。

| 询问您自己 | 操作 |
|--------------|--------|
|是否要更改默认 Teams 应用设置？ | 要详细了解可用于管理组织内部应用的策略和设置，请参阅 [Microsoft Teams 中针对应用的管理员设置](admin-settings.md)。|
|||

### <a name="app-permissions-and-other-considerations"></a>应用权限和其他注意事项

应用由用户允许，并由管理员或 IT 专业人员通过策略进行管理。 但是，在大多数情况下，应用的权限和风险状况是在应用本身内定义的。 

| 询问你自己 | 操作 |
|--------------|--------|
|<br>希望允许访问哪些应用？ 不希望允许访问哪些应用？  | <ul><li>有关在允许访问应用、聊天机器人、选项卡或连接器时要考虑的事项的列表，请参阅 [Microsoft Teams 应用权限和注意事项](app-permissions.md)。</li><li>有关将应用提供给组织中的用户的信息，请参阅[在 Teams 租户应用目录中发布应用](tenant-apps-catalog-teams.md)。</li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a>用于私人聊天和频道的聊天机器人

聊天机器人是自动化程序，它们可响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。 聊天机器人允许用户与云服务交互，例如任务管理、计划以及在 Teams 聊天中投票。 Teams 支持在私人聊天和频道中使用聊天机器人。 管理员可以控制是否允许在 Office 365 租户中使用聊天机器人。

| 询问你自己 | 操作 |
|--------------|--------|
|是否要允许在我的 Office 365 租户中使用自定义聊天机器人？|有关添加聊天机器人的详细信息，请参阅[为 Microsoft Teams 中的私人聊天和频道添加聊天机器人](add-bots.md)。 有关开启或关闭聊天机器人的信息，请参阅[在 Microsoft Teams 中管理应用设置](admin-settings.md)。|
|||

### <a name="built-in-and-custom-tabs"></a>内置和自定义选项卡

所有者和团队成员可以向频道、私人聊天和群组聊天中添加选项卡，以帮助集成其云服务。 添加选项卡可帮助用户访问并管理自己需要或最常用的数据。 在频道中，默认情况下已创建了“对话”和“文件”选项卡。 在私人聊天中，默认情况下已创建了“对话”、“文件”、“组织”和“活动”选项卡。 除了这些内置选项卡外，你还可以设计和添加自定义选项卡。 若要了解如何为你的组织开启或关闭 Teams 应用，请阅读[在 Teams 中管理应用设置](admin-settings.md)。

| 询问你自己 | 操作 |
|--------------|--------|
|是否要允许在我的 Office 365 租户中使用自定义选项卡？|有关详细信息，请参阅[在 Teams 中使用内置和自定义选项卡](built-in-custom-tabs.md)。|
|||

### <a name="office-365-and-custom-connectors"></a>Office 365 和自定义连接器

连接器可将内容和更新从你经常使用的服务直接传递到频道中，从而使你的团队能够获得最新内容。 通过使用连接器，你的 Teams 用户可以在其 Teams 聊天中接收来自常用服务（例如 Twitter、Trello、Wunderlist、GitHub 和 Azure DevOps Services）的更新。

| 询问你自己 | 操作 |
|--------------|--------|
|是否希望允许用户创建自定义连接器？|有关详细信息，请参阅[在 Teams 中使用 Office 365 和自定义连接器](office-365-custom-connectors.md)。|
|||

## <a name="additional-deployment-decisions"></a>其他部署决策

你可能需要根据组织的需求和配置更改这些设置。

### <a name="activity-reports"></a>活动报告

你可以使用活动报告来查看组织中的用户使用 Teams 的情况。 例如，如果某些用户尚未使用 Teams，他们可能不知道如何开始使用或了解如何使用 Teams 提高效率和改善协作。 组织可以使用活动报告来决定在何处优先安排培训和沟通工作。 若要查看活动报告，你必须是 Office 365 中的全局管理员、Teams 服务管理员或 Skype for Business 管理员。

| 询问你自己 | 操作 |
|--------------|--------|
| <br>谁需要查看活动报告，他们是否有查看这些报告的正确权限？ |<ul><li>如果不想为用户分配管理员角色，则可以[分配报告阅读者角色](teams-activity-reports.md#reports-reader-role)。</li><li>有关在 Azure Active Directory 中分配管理员角色的信息，请参阅[角色和权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)以及[查看和分配角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</li></ul> |
|||

### <a name="app-templates"></a>应用模板

应用模板是适用于 Microsoft Teams 的生产就绪型应用，它们由社区驱动、开放源代码且可在 GitHub 上获取。 每个模板都包含为组织部署和安装该应用的详细说明，从而提供了一个可立即安装并开始使用的即用型应用。 此外，还提供完整的源代码，以便你可以对其进行详细的研究，或获取相应代码并进行更改以满足你的特定需求。

| 询问你自己 | Action |
|--------------|--------|
| 我是否想要安装任何 Teams 应用模板，例如 Icebreaker？ |若要了解详细信息，请参阅[适用于 Teams 的应用模板](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。|
|||


## <a name="next-steps"></a>后续步骤
- [推动采用](adopt-microsoft-teams-landing-page.md)特别推荐的应用，例如 Planner。
- [部署会议](deploy-meetings-microsoft-teams-landing-page.md)
- [部署云语音](cloud-voice-landing-page.md)


