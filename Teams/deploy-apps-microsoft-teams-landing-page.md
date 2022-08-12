---
title: 了解 Microsoft Teams 中的应用
ms.reviewer: ''
description: 了解应用，并根据组织的用户配置和业务要求决定在 Teams 中允许哪些应用。
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: b7e95c04a2a8632fbda566c322e474809703de03
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "67298911"
---
# <a name="understand-microsoft-teams-apps"></a>了解 Microsoft Teams 应用

应用是将工作区工具和服务汇集在一起并与他人协作的好方法。 应用可帮助最终用户在日常任务中提高工作效率、协作性和效率。 组织使用应用与其客户进行连接、提供服务和共享信息。 例如，最终用户在 Teams 中使用固定日历应用快速与他人协作，使用带有机器人功能的应用可以通知用户在 Teams 频道中使用 Web 服务质量的应用，以及用于在频道中共享任务，并向各种最终用户分配任务的应用。

Teams 应用商店提供各种经过验证、具有安全性应用的大量目录，让最终用户能够使用组织每天所需的工具和服务。 Microsoft Teams 应用是基于 Web 的 SaaS 应用，无需部署。 最终用户只能根据 [你提供的权限](app-policies.md) 在 Teams 中使用应用。 作为管理员，可以使用企业级策略来允许或阻止组织用户的任何应用。 可在各种上下文（如会议、聊天和频道）中控制每个用户的应用可用性。

本文可帮助你了解应用的类型以及用户访问这些应用的位置。 若要详细了解应用的用途，请阅读 [针对最终用户的应用概述](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

最终用户可在 Teams 中使用不同类型的应用包括：

* [属于 Teams 的核心应用](#core-apps)。
* [Microsoft 创建的其他应用](#microsoft-provided-apps)。
* 合作伙伴[提供的第三方应用](#third-party-apps-validated-by-microsoft) （由 Microsoft 验证）。
* 由自己组织创建的[自定义应用](#custom-apps)。

## <a name="core-apps"></a>核心应用

一些 Teams 功能（例如活动源、团队、聊天、日历、通话、文件和作业 [教育版租户]）是默认可用的，并且默认固定，以便最终用户可以轻松访问。 对于一线工作人员，则仅提供和固定了活动、班次、聊天和通话功能。 作为管理员，可以使用 [安装策略](/microsoftteams/teams-app-setup-policies)修改默认行为。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="核心应用是默认情况下固定在 Teams 中的应用。" lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Microsoft 提供的应用

Microsoft 提供了许多应用来提高工作效率和协作。 若要找到这些应用，你和最终用户可以在 Teams 管理中心中查找发布者为 Microsoft 的应用，或在 Team 应用商店中查找提供者为 Microsoft 的应用。

Teams自带一组内置应用，包括列表、任务、表扬、审批等。 建议在初始 Teams 推出中包括 Planner 等特色应用。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Teams 管理中心中 Microsoft 应用的屏幕截图。" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>由 Microsoft 验证的第三方应用

除了 Microsoft 提供的应用，可使用 Microsoft 认证第三方应用。 Microsoft 在 Teams 应用商店中提供这些应用之前，先验证这些应用的功能和安全性。 若要了解应用验证的优势，请参阅 [第三方应用的验证](overview-of-app-validation.md)。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams 应用商店中第三方应用示例的屏幕截图。":::

## <a name="custom-apps"></a>自定义应用

组织中开发人员创建的应用称为自定义应用（或业务线应用）。 组织可以根据组织特定的要求委托创建自定义应用。 你有权为整个组织或特定用户允许或阻止此类应用。 组织中的开发人员可以通过使用 Teams 与 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 集成，快速构建自定义低代码解决方案。

管理员允许使用自定义应用后，最终用户在 Teams 应用商店的左侧导航中选择“**专为组织构建**”即可找到此类应用。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 桌面应用中 Teams 应用商店中自定义应用的屏幕截图。" lightbox="media/built-for-your-org2.png":::

有关详细信息，请参阅[了解和管理自定义和旁加载应用](custom-app-overview.md)。

## <a name="about-app-templates"></a>关于应用模板

Teams 的应用模板是 Microsoft 为实现以下目的而创建的功能性和生产就绪示例应用：

* 说明常用用例。
* 展示应用开发最佳做法。
* 提供开发人员可扩展以创建自定义应用的开源应用。

组织开发人员通过对 GitHub 中提供的代码进行简单更改来自定义应用模板。 为满足任何组织需求，可将这些应用作为自定义应用提供给最终用户。

若要了解详细信息，请参阅 [Microsoft Teams 应用模板](https://adoption.microsoft.com/microsoft-teams/app-templates/)。

## <a name="understand-app-capabilities"></a>了解应用功能

为了提供丰富的体验，让最终用户能够在 Teams 内部工作，应用开发人员可以使用以下应用功能。 消息传递扩展允许用户与 Web 服务 Teams 客户端进行交互。 在外部系统中搜索或启动操作。 可以将交互结果作为丰富地格式化卡片发送到 Teams 客户端。 会议扩展性应用将开发人员的应用集成到会议中，并提供响应式的会议体验。

机器人也称为聊天机器人或对话机器人。 它是执行简单重复任务的应用。 机器人交互可以是快速问答，也可以是提供服务或协助访问的复杂对话。 用户可以一对一或在频道里进行聊天。 例如，可以使用 Polly 应用创建快速调查、获取反馈和进行脉冲检查。

选项卡是固定在频道顶部或聊天的 Teams 感知网页。 选项卡允许你使用类似 Web 的体验与内容和服务交互。 可以将选项卡作为频道的一部分添加到团队内部，为单个用户添加群组聊天或个人应用。

Webhook 和连接器将最终用户经常使用的服务（如 Jira Cloud 和 Bitbucket）内容和更新直接传送到频道对话中。 使用此功能应用可以与外部应用通信，并且可以从外部服务发送或接收通知和消息。

消息传递扩展是插入应用内容或对消息执行操作的快捷方式，最终用户无需从对话中导航即可。 消息传递扩展插件可以具有搜索命令，供最终用户快速查找外部内容，并将其插入消息或操作命令中。

若要查看映射到 Teams 功能的常见用例，请参阅 [将用例映射到 Teams 应用功能](/microsoftteams/platform/concepts/design/map-use-cases)。

<!--- TBD: Admins do many considerations and decisions around app adoption and app governance. These are to be covered in a separate article. Commenting the below content for now as part of this article revamp.

## Apps deployment decisions

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

## Core deployment decisions

These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).

### App availability settings

Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.
Get apps from the Teams Store. By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users. For example, users can use the Planner app to build and manage team tasks in Teams.

By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off. There are org-wide settings that let you turn all third-party and/or custom apps on or off for your entire organization.

| Ask yourself | Action |
|--------------|--------|
|Will you change the default Teams apps settings? | For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### App permissions and other considerations

Apps are consented to by users and managed by the admin or IT pro through policies. However, app permissions and risk profile are defined in the app itself.

| Ask yourself | Action |
|--------------|--------|
|<br>Which apps do I want to allow access to? Which ones do I not want to allow access to?  | <ul><li>See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</li><li>See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</li></ul>|

--->

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
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](/microsoftteams/platform/tabs/what-are-tabs).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

<!--- TBD: Activity reports is not part of app overview. Commenting for now. To be reused in a different article later.

### Activity reports

You can use activity reports to see how users in your organization are using Teams. For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative. Your organization can use the activity reports to decide where to prioritize training and communication efforts. To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.

| Ask yourself | Action |
|--------------|--------|
| Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
