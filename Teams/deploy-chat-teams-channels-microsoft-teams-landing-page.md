---
title: Microsoft Teams 中的聊天、团队、频道和应用
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: 包含有关在 Microsoft Teams 中配置聊天、团队、应用和频道的 Teams 设置的分步指南。
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3132fdf3e8e04c0527c055435fa95e14d8ca4116
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199124"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Microsoft Teams 中的聊天、团队、频道和应用

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

首先，请观看我们的“Teams 聊天、团队和频道”短视频（4 分 30 秒）：

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj?autoplay=false]

You can use [Advisor for Teams](use-advisor-teams-roll-out.md) to help you roll out Microsoft Teams. Advisor for Teams walks you through your Teams rollout. It assesses your Microsoft 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.

> [!TIP]
> 我们建议你在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。 在推动 [Teams](deploy-apps-microsoft-teams-landing-page.md) 采用时添加其他 Teams 应用。

 > [!Note]
 > 有关不同平台上 Teams 功能的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="chat-deployment-prerequisites"></a>聊天部署先决条件

Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.

|询问你自己|操作 |
|------------|-------|
|我的组织是否已准备好部署 Teams？|为了回答此问题，请参阅： <ul><li>[为 Teams 准备贵组织的网络](prepare-network.md)</li><li>[URL 和 IP 地址范围](office-365-urls-ip-address-ranges.md)</li><li>[在创建团队时规划 Microsoft 365 组](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>核心部署决策

以下是大多数组织在默认设置不适合的情况下想要更改的聊天、团队和频道设置。

### <a name="teams-administrators"></a>Teams 管理员

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| 询问你自己 | 操作 |
|--------------|--------|
|将为谁分配 Teams 通信管理员角色？|若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。|
|将为谁分配 Teams 通信支持工程师角色？|若要分配管理员角色，请参阅[使用 Active Directory 为用户分配管理员和非管理员角色](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。|
|将为谁分配 Teams 通信支持专家角色？||

### <a name="teams-owners-and-members"></a>Teams 所有者和成员

In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.

|询问你自己|操作 |
|------------|-------|
|应该为每个角色分配哪些人员？ | 若要比较每个角色的功能，请参阅[在 Microsoft Teams 中分配团队所有者、审阅人和成员](assign-roles-permissions.md)。
|如何分配用户角色？ | 若要分配或更改角色，请参阅[分配用户角色](assign-roles-permissions.md)。
|我是否需要控制谁可以在频道中发布和答复？ | 若要配置审核，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。

### <a name="messaging-policies"></a>消息策略

Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.

|询问你自己|操作 |
|------------|-------|
|是否要自定义全局消息策略？|有关使用 Microsoft Teams 管理中心来更改全局消息策略或添加新策略的信息，请参阅[在 Teams 中管理消息策略](messaging-policies-in-teams.md)。|
|是否需要多个消息策略？|若要在 PowerShell 中创建和分配消息策略，请参阅 [PowerShell 脚本示例 - 创建和分配消息策略](scripts/powershell-script-teams-messaging-policy-edu.md)。|
|如何确定哪些用户组获取哪些消息策略？|若要了解 CsTeamsMessagingPolicy cmdlet，请参阅 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)。|

### <a name="external-access"></a>外部访问

External access (federation) lets your users communicate with people outside of your organization via chat. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access is turned on by default.

|询问你自己|操作 |
|------------|-------|
|<ul><li>我是否要为我的组织禁用外部访问？</li><li>如果启用，是否要限制我的组织可以与哪些域进行通信？</li></ul> |<br>若要打开或关闭外部会议和聊天，请参阅 [管理外部会议和聊天](manage-external-access.md)。|

### <a name="guest-access"></a>来宾访问权限

Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guests can or can't use. Guest access is turned on by default. To learn more, see [Guest access in Teams](./guest-access.md).

> [!NOTE]
> 有关外部访问和来宾访问的详细信息，请参阅此处 - [与 Microsoft Teams 中其他组织的用户通信](communicate-with-users-from-other-organizations.md)

|询问你自己|操作 |
|------------|-------|
|我是否要为我的组织禁用来宾访问？|要启用或禁用来宾访问，请参阅 [在 Teams 中启用或禁用来宾访问](set-up-guests.md)。|
|如果启用，是否要自定义可供组织中的来宾使用的功能？|若要自定义来宾访问功能可用性，请参阅[在 Teams 中授权来宾访问](teams-dependencies.md)。|

### <a name="private-channels"></a>私人频道

使用专用频道，一部分团队成员可以在其他团队成员无法查看或访问的专用空间中进行协作。 只要已是团队的成员（包括来宾），均可将其添加为专用渠道的成员。

|询问你自己|操作 |
|------------|-------|
|我是否要允许团队所有者和成员创建专用频道？|要为组织设置专用频道策略，请参阅 [在 Microsoft Teams 中管理频道策略](teams-policies.md)|

### <a name="shared-channels"></a>共享频道

使用共享频道，可以将不是团队成员的人员添加到频道。 这包括组织外部的人员。 共享频道比来宾访问更具优势，因为组织外部的人员不需要目录中的来宾帐户。

|询问你自己|操作 |
|------------|-------|
|何时使用共享频道与来宾访问？|请参阅 [ Microsoft Teams 中的共享频道](shared-channels.md)。|
|<ul><li>我是否要允许团队所有者创建共享频道？</li><li>我是否要允许团队所有者与组织外部人员共享频道？</li><li>我是否要允许用户参与组织外部的共享频道？</li></ul> |<br>要设置组织的共享频道策略，请参阅 [在 Microsoft Teams 中管理频道策略](teams-policies.md)。|

### <a name="teams-settings"></a>Teams 设置

Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).

|询问你自己|操作 |
|------------|-------|
|是否要为我的组织自定义 Teams 设置？ | 若要了解 Teams 设置以及如何自定义这些设置，请参阅 [Teams 设置](enable-features-office-365.md#teams-settings)。|

### <a name="teams-clients"></a>Teams 客户端

Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).

|询问你自己|操作 |
|------------|-------|
|是否要为我的组织自定义 Teams 客户端可用性？|请参阅 [Teams 应用的硬件要求](hardware-requirements-for-the-teams-app.md)。 |
|是否要为我的组织自定义 Teams 客户端设置？|了解如何[使用 MSI 安装 Teams](msi-deployment.md)。|

### <a name="teams-usage-reporting"></a>Teams 使用情况报告

The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).

|询问你自己|操作 |
|------------|-------|
|<br> 谁需要查看 Teams 使用情况报告，他们是否有查看这些报告的正确角色？ |<ul><li>如果用户不是管理员，请[分配报告阅读者角色](teams-activity-reports.md#reports-reader-role)。</li><li>请参阅[角色和权限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)以及[查看和分配角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)，了解如何在 Azure Active Directory 中分配管理员角色。|

### <a name="teams-default-apps"></a>Teams 默认应用

Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.

若要详细了解如何在 Teams 中推出和管理应用，请参阅我们的深入 [应用管理](deploy-apps-microsoft-teams-landing-page.md) 指南。

## <a name="additional-deployment-decisions"></a>其他部署决策

你可能需要根据组织的需求和配置更改这些设置。

### <a name="teams-licensing"></a>Teams 许可

Teams 作为许多 Microsoft 365 许可证的一部分提供。

|询问你自己|操作 |
|------------|-------|
|我的用户是否有使用要部署的所有 Teams 功能所需的许可证？ | 若要了解有关许可要求的信息，请参阅 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)。|

### <a name="exchange-and-sharepoint-interoperability"></a>Exchange 和 SharePoint 互操作性

For the full Teams experience, every user should be enabled for Exchange, SharePoint, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive.

|询问你自己|操作 |
|------------|-------|
| 是否能随当前 Exchange 和 SharePoint 部署一起部署所需的 Teams 功能？ |有关 Teams 中的 Exchange 和 SharePoint 的详细信息，请参阅：<ul><li> [Exchange 与 Teams 如何交互](exchange-teams-interact.md)</li><li>[ SharePoint Online 和 OneDrive 如何与 Teams 交互](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Teams 限制和规范

规划 Teams 的企业部署时，你应考虑任何相关的限制和规范，例如团队中的最大成员数、用户可创建的最大团队数，诸如此类。

|询问你自己|操作 |
|------------|-------|
| 我的 Teams 部署可能会遇到什么限制？ | 若要了解详细信息，请阅读 [Teams 的限制和规范](limits-specifications-teams.md)。 |

### <a name="urls-and-ports"></a>URL 和端口

Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).

|询问你自己|操作 |
|------------|-------|
| 是否需要 Internet 访问规则才能让用户使用 Teams，或者开放最少所需的端口是否足够？ | 若要了解详细信息，请参阅 [URL 和 IP 地址范围](office-365-urls-ip-address-ranges.md)。|

### <a name="governance-naming-conventions-who-can-create-teams"></a>管理（命名约定，可创建团队的人员）

Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.

| 询问你自己 | 操作 |
|--------------|--------|
|是否需要对谁可以创建团队进行控制？| 请阅读[在 Teams 中规划管理](plan-teams-governance.md)。|
|是否需要对团队的命名方式进行控制？|请阅读[在 Azure AD 中为 Microsoft 365 组实施命名策略](/azure/active-directory/users-groups-roles/groups-naming-policy)。|

### <a name="teams-application-policy-side-rail-control"></a>Teams 应用程序策略（侧边栏控制）

A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.

| 询问你自己 | 操作 |
|--------------|--------|
|是否应该创建一组预先配置的固定 Teams 应用程序？ | 请阅读 [Teams 中应用的管理员设置](admin-settings.md)。|
|如何决定哪些组接收这些应用分组？|请阅读[团队应用权限和注意事项](app-permissions.md)。|

### <a name="archiving-and-compliance"></a>存档与合规性

Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.

| 询问你自己 | 操作 |
|--------------|--------|
|是否需要配置团队保留？|若要设置保留策略，请参阅[设置 Teams 保留策略](retention-policies.md)。|
|是否需要配置团队存档？|若要存档或还原团队，请参阅[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。|
|是否需要配置其他合规性设置？|有关安全性和合规性的详细信息，请参阅 [Teams 中的安全性和合规性概述](security-compliance-overview.md)。|

### <a name="conditional-access"></a>条件访问

Teams relies heavily on Exchange and SharePoint for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.

| 询问你自己 | 操作 |
|--------------|--------|
|<br>是否需要为 Teams 配置条件访问？|<ul><li>若要了解访问策略的工作方式，请参阅[条件访问策略如何在 Teams 中发挥作用？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>若要为 Teams 设置多重身份验证 (MFA)，请参阅：<ul><li>[快速入门：具有 Azure Active Directory 条件访问权限的特定应用需要 MFA](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Azure Active Directory 条件访问设置参考](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>教育版 (EDU)

在教育行业工作的 IT 专业人员可以利用 Teams 教育版，该版本提供的许多功能经过定制，可满足学生、教职员工和更广泛行业特定于教育的方案需求。

| 询问你自己 | 操作 |
|--------------|--------|
|是否要使用特定于 EDU 的 Teams 模板？ |若要详细了解 Teams 教育版，请参阅[面向管理员的 Microsoft 教育管理常见问题](plan-teams-governance-edu.md)。|
|是否要部署范围限定的搜索？|若要为 EDU 设置 Teams，请参阅[快速入门 - Teams 教育版管理](teams-quick-start-edu.yml)。|
|是否要将 Teams 与 School Data Sync 服务集成来配置用户帐户？|[面向教育版管理员的 Teams 资源](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>政府版 - GCC 注意事项

对于在美国联邦政府、州政府、地方政府、部族政府或准州政府实体或者所处理数据遵从政府法规和要求的其他实体推动 Office 365 部署的 IT 专业人员，使用 Office 365 政府版 - GCC（政府社区云）可以适当地满足其需求。

| 询问你自己 | 操作 |
|--------------|--------|
| 是否要在 Office 365 政府版 – GCC 环境中部署 Teams？ | 有关部署注意事项，请参阅[规划 Office 365 政府版 - GCC 部署](plan-for-government-gcc.md)。|

## <a name="next-steps"></a>后续步骤

- [推动采用](adopt-microsoft-teams-landing-page.md)聊天、团队、频道和应用。
- 在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。 在推动 [Teams](deploy-apps-microsoft-teams-landing-page.md) 采用时添加其他 Teams 应用。
- [部署会议](deploy-meetings-microsoft-teams-landing-page.md)
- [部署云语音](cloud-voice-landing-page.md)
