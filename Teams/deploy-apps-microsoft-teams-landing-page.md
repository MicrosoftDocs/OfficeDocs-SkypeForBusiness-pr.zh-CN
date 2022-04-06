---
title: 了解 Microsoft Teams 中的应用
ms.reviewer: ''
description: 了解应用，并根据组织的用户配置和业务要求决定在 Teams 中允许哪些应用。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
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
ms.openlocfilehash: bb3d38060a9538196795e3da7b325840321814d8
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686389"
---
# <a name="about-apps-in-microsoft-teams"></a>关于 Microsoft Teams 的应用

应用是将工作区工具和服务汇集在一起并与他人协作的好方法。 应用可帮助最终用户在日常任务中提高工作效率、协作性和效率。 组织使用应用与其客户进行连接、提供服务和共享信息。 通过应用，用户可以更有效地Teams聊天、会议和频道。 例如，最终用户在Teams中使用固定日历快速与他人协作，使用机器人功能通知用户在Teams通道中使用 Web 服务的 QoS 的应用，以及用于在频道中共享任务并向各种最终用户分配任务的应用。

我们在应用商店中广泛选择经过验证和安全的应用，使最终用户能够访问组织每天需要的工具和服务。 Microsoft Teams应用是基于 Web 的 SaaS 应用，不需要部署。 最终用户只能根据你提供的权限在Teams中使用应用。 作为管理员，只需批准或阻止对组织用户使用任何应用。 可跨会议、聊天和频道控制所有用户的应用可用性。

若要为最终用户提供所需的应用，请继续阅读以了解应用类型以及用户访问这些应用的位置。 若要详细了解应用的使用情况，请阅读 [最终用户的应用概述](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

最终用户可在Teams中使用的不同类型的应用包括：

* [属于Teams的核心应用](#core-apps)。
* [Microsoft 创建的其他应用](#microsoft-provided-apps)。
* 由合作伙伴 (Microsoft) 验证的第[三方应用](#third-party-apps-validated-by-microsoft)。
* 由自己的组织创建的[自定义应用](#custom-apps)。

## <a name="core-apps"></a>核心应用

默认情况下，某些默认功能（例如活动源、Teams频道、聊天、日历和呼叫）可用并固定，以方便最终用户访问。 作为管理员，可以使用 [安装策略](/microsoftteams/teams-app-setup-policies)修改默认行为。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="核心应用是默认情况下固定在Teams中的应用。" lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Microsoft 提供的应用

Microsoft 提供了许多应用来提高工作效率和协作。 你和最终用户可以通过查找 Microsoft 作为管理中心中的Publisher或在 Team 应用商店中列为提供程序来查找这些应用。

Teams自带一组内置应用，包括列表、任务、表扬、审批等。 我们建议在最初的 Teams 推出中加入 Teams 特色应用 - 例如 Planner。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Teams管理中心的 Microsoft 应用" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>由 Microsoft 验证的第三方应用

除了 Microsoft 提供的应用，还可以使用 Microsoft 验证的第三方应用。 Microsoft 先验证这些应用的功能和安全性，然后再在 Teams 存储中提供这些应用。 若要了解应用验证的好处，请参阅 [第三方应用的验证](overview-of-app-validation.md)。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams存储中第三方应用的示例":::

## <a name="custom-apps"></a>自定义应用

组织中开发人员创建的应用称为自定义应用。 根据组织的具体要求委托开发此类应用，并且你拥有允许或禁止此类应用的控件。 组织中的开发人员可以使用与 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 的Teams集成快速生成自定义低代码解决方案。

管理员允许使用自定义应用后，最终用户通过单击Teams存储的左侧导航中 **为组织生成** 的应用来查找此类应用。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams桌面应用中Teams存储中的自定义应用" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>了解自定义应用的旁加载

开发自定义应用时，在将自定义应用分发到最终用户之前，开发人员会通过将应用添加到应用商店进行测试来自行测试，或与旁加载该应用的团队一起测试。 此方法称为应用旁加载，仅适用于自定义应用。

开发人员可以旁加载应用，使其可供特定团队的成员使用，通常用于测试开发不足的应用。 如果允许旁加载，则不需要管理员批准。 作为管理员，可以禁止任何开发人员旁加载。

如果不允许旁加载，开发人员仍然可以在 [测试租户](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)中测试其应用。 自定义应用开发完成后，开发人员会请求管理员将其自定义应用分发给最终用户。 有关详细信息，请参阅 [如何发布自定义应用](/microsoftteams/upload-custom-apps)。 作为管理员，可以允许或禁止对特定用户使用自定义应用。

### <a name="about-app-templates"></a>关于应用模板

适用于Teams的应用模板是 Microsoft 创建的功能性、生产就绪的示例应用，用于说明常用用例、展示应用开发最佳做法，并提供开发人员可以扩展的开源应用来创建自定义应用。 组织开发人员通过对GitHub中提供的代码进行简单更改，自定义组织需要的应用模板。 作为管理员，可将这些应用作为最终用户的自定义应用提供。

若要了解详细信息，请参阅[Microsoft Teams应用模板](https://adoption.microsoft.com/microsoft-teams/app-templates/)。

## <a name="understand-app-capabilities"></a>了解应用功能

为了提供丰富的体验，使最终用户能够在Teams中工作，应用开发人员可以利用以下应用功能。 消息传递扩展允许用户与 Web 服务Teams客户端交互。 它们在外部系统中搜索或启动操作。 可以将交互结果作为格式丰富的卡片发送到Teams客户端。 会议扩展性应用将开发人员的应用集成到会议中，并提供响应式会议内体验。

机器人也称为聊天机器人或聊天机器人。 它是执行简单重复任务的应用。 机器人交互可以是快速问答，也可以是提供服务访问或帮助的复杂对话。 用户可以与一对一或频道进行一对一聊天。 例如，可以使用 Polly 应用创建快速调查、获取反馈和进行脉冲检查。

选项卡Teams感知网页固定在频道或聊天的顶部。 选项卡允许你使用类似 Web 的体验与内容和服务交互。 可以将选项卡作为频道的一部分添加到团队内部，为单个用户添加群组聊天或个人应用。

Webhook 和连接器从最终用户经常使用 (（如 Jira Cloud 和 Bitbucket）的服务提供内容和更新，) 直接进入频道对话。 使用此功能的应用可以与外部应用通信，并且可以从外部服务发送或接收通知和消息。

消息传递扩展是插入应用内容或对消息执行操作的快捷方式，最终用户无需从对话中导航即可。 消息传递扩展插件可以具有搜索命令，供最终用户快速查找外部内容并将其插入消息或操作命令中。

若要查看映射到Teams功能的常见用例，请参阅[将用例映射到Teams应用功能](/microsoftteams/platform/concepts/design/map-use-cases)。

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
| <br>Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
