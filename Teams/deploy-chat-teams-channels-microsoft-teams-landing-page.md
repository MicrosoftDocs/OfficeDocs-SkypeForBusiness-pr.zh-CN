---
title: Microsoft Teams 中的聊天、团队、频道和应用
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 在 Microsoft Teams 中部署聊天、团队、频道和应用的分步指导
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28eaee5b413444c9123f2334f38d599b6f753a5
ms.sourcegitcommit: 2af4c9e3a8374d9a6995e36604d8b0b8eff23b34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2019
ms.locfileid: "35133904"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Microsoft Teams 中的聊天、团队、频道和应用

Teams 为组织提供了现成的出色协作体验，并且大多数组织发现默认设置适合它们。 本文可帮助你决定是否要根据组织的情况和业务需求更改任何默认设置，然后引导你完成每项更改。 我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。 第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。

> [!TIP]
> 我们建议你在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。 在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。

## <a name="chat-deployment-prerequisites"></a>聊天部署先决条件

在整个组织内部署 Teams 之前，请花些时间确认你环境已准备好使用 Teams。 查看以下信息，并对你的环境进行任何必需的更改。

- 若要获得完整的 Teams 体验，你的组织必须部署了 [Exchange Online 和 SharePoint Online](#exchange-and-sharepoint-interoperability)，并且你必须有适用于 Office 365 的已验证域（例如，contoso.com）。

- 若要在整个组织内大规模部署聊天、团队和频道，请确保所有地点都权访问 Internet，以便可以连接到 Office 365。 至少确保以下常用端口在所有地点已向 Internet 开放：

    - 为将使用 Teams 的客户端发出的传出流量开放 **TCP** 端口 80 和 443
    - 为将使用 Teams 的客户端发出的传出流量开放 **UDP** 端口 3478 至 3481 

|询问你自己|操作 |
|------------|-------|
|我的组织是否已准备好部署 Teams？|为了回答此问题，请参阅： <ul><li> [检查 Teams 的环境准备情况](environment-readiness.md)</li><li>[为 Teams 准备贵组织的网络](prepare-network.md)</li><li>[Office 365 URL 和 IP 地址范围](office-365-urls-ip-address-ranges.md)</li><li>[在创建团队时规划 Office 365 组](plan-office-365-groups.md)|
|||

## <a name="core-deployment-decisions"></a>核心部署决策

以下是大多数组织在默认设置不适合的情况下想要更改的聊天、团队和频道设置。

### <a name="teams-administrators"></a>Teams 管理员

Teams 提供了一组可用于为组织管理 Teams 的自定义管理员角色。 这些角色为管理员提供各种能力。 

| 询问你自己 | 操作 |
|--------------|--------|
|将为谁分配 Teams 通信管理员角色？|若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。|
|将为谁分配 Teams 通信支持工程师角色？|若要分配管理员角色，请参阅[使用 Active Directory 为用户分配管理员和非管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。|
|将为谁分配 Teams 通信支持专家角色？||
|||

### <a name="messaging-policies"></a>消息策略

消息策略控制为 Teams 中的用户提供哪些聊天和频道消息功能。 例如，谁可以编辑和删除已发送的消息、谁可以使用聊天、谁可以在对话中使用 Meme，等等。 默认情况下，会为用户分配全局消息策略，所有功能均**开启**。 可以使用默认全局策略，或者为组织中的人员创建一个或多个自定义消息策略。 

|询问你自己|操作 |
|------------|-------|
|是否要自定义全局消息策略？|有关使用 Microsoft Teams 管理中心来更改全局消息策略或添加新策略的信息，请参阅[什么是 Teams 中的消息策略？](messaging-policies-in-teams.md)。|
|是否需要多个消息策略？|若要在 PowerShell 中创建和分配消息策略，请参阅 [PowerShell 脚本示例 - 创建和分配消息策略](scripts/powershell-script-teams-messaging-policy-edu.md)。|
|如何确定哪些用户组获取哪些消息策略？|若要了解 CsTeamsMessagingPolicy cmdlet，请参阅 [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。|
||| 

### <a name="external-access"></a>外部访问

利用外部访问功能（以前称为联合），你的 Teams 和 Skype for Business 用户可以与组织外部的用户通信。 通过启用此功能并将域添加到允许的列表，你的用户将能与其他域和组织中的用户通信。外部访问与来宾访问的不同之处在于，将为整个域（而不是个人）授予访问权限。 默认情况下会关闭外部访问。

|询问你自己|操作 |
|------------|-------|
|<ul><li>是否要为我的组织启用外部访问？</li><li>如果启用，是否要限制我的组织可以与哪些域进行通信？</li></ul> |<br>若要启用外部访问，请参阅[让你的 Teams 用户与其他 Teams 组织中的用户聊天和通信](manage-external-access.md#let-your-teams-users-chat-and-communicate-with-users-in-another-organization)。|
|||

### <a name="guest-access"></a>来宾访问

Teams 中的来宾访问可让组织外部的个人访问团队和频道。 可以使用来宾访问设置来控制来宾用户能够使用或无法使用哪些功能。 默认情况下会关闭来宾访问。 若要了解详细信息，请参阅 [Teams 中的来宾访问](https://docs.microsoft.com/microsoftteams/guest-access)。

|询问你自己|操作 |
|------------|-------|
|是否要为我的组织启用来宾访问？|若要启用来宾访问，请参阅[在 Teams 中启用或禁用来宾访问](set-up-guests.md)。|
|如果启用，是否要自定义可供组织中的来宾使用的功能？|若要自定义来宾访问功能可用性，请参阅[在 Teams 中授权来宾访问](teams-dependencies.md)。|
|||

### <a name="teams-settings"></a>Teams 设置

Teams 设置允许你针对诸如电子邮件集成、云存储选项、组织选项卡、会议室设备设置和搜索范围等功能设置团队。 更改这些设置时，所做更改将应用于组织中的所有团队。若要了解详细信息，请参阅 [Teams 设置](enable-features-office-365.md#teams-settings)。

|询问你自己|操作 |
|------------|-------|
|是否要为我的组织自定义 Teams 设置？ | 若要了解 Teams 设置以及如何自定义这些设置，请参阅 [Teams 设置](enable-features-office-365.md#teams-settings)。|
|||

### <a name="teams-clients"></a>Teams 客户端

Teams 支持从 Web 到桌面直至移动客户端的多种客户端，默认配置允许用户选择所需的任一客户端。若要了解详细信息，请参阅[获取 Teams 客户端](get-clients.md)。

|询问你自己|操作 |
|------------|-------|
|是否要为我的组织自定义 Teams 客户端可用性？|请参阅 [Teams 应用的硬件要求](hardware-requirements-for-the-teams-app.md)。 |
|是否要为我的组织自定义 Teams 客户端设置？|了解如何[使用 MSI 安装 Teams](msi-deployment.md)。|
|||


### <a name="teams-usage-reporting"></a>Teams 使用情况报告

Office 365 中的全局管理员、Teams 服务管理员和报表阅读者角色可以查看 Teams 使用情况报告。 若要了解详细信息，请参阅 [Microsoft 365 使用情况分析](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide)文章。

|询问你自己|操作 |
|------------|-------|
|<br> 谁需要查看 Teams 使用情况报告，他们是否有查看这些报告的正确角色？ |<ul><li>如果用户不是管理员，请[分配报告阅读者角色](teams-activity-reports.md#reports-reader-role)。</li><li>请参阅[角色和权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)以及[查看和分配角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)，了解如何在 Azure Active Directory 中分配管理员角色。 |
|||

### <a name="teams-default-apps"></a>Teams 默认应用 

Teams 提供一些第一方（Microsoft 提供）和第三方应用来吸引用户、支持高效工作，并在 Teams 中集成了常用的业务服务。 从 Teams 应用商店获取应用。 默认情况下 Teams 中已启用应用。 

若要详细了解如何在 Teams 中部署和管理应用，请参阅我们深入的[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)指引。


## <a name="additional-deployment-decisions"></a>其他部署决策

你可能需要根据组织的需求和配置更改这些设置。

### <a name="teams-licensing"></a>Teams 许可

Teams 作为许多 Office 365 许可证的一部分提供。 若要详细了解 Teams 许可，请参阅[适用于 Teams 的 Office 365 许可](office-365-licensing.md)。

|询问你自己|操作 |
|------------|-------|
|我的用户是否有使用要部署的所有 Teams 功能所需的许可证？ | 若要了解许可要求，请阅读[适用于 Teams 的 Office 365 许可](office-365-licensing.md)。|
|||

### <a name="exchange-and-sharepoint-interoperability"></a>Exchange 和 SharePoint 互操作性 

为了获得全面的 Teams 体验，应该为每个用户启用 Exchange Online、SharePoint Online 和 Office 365 组创建。 下列文章概述的信息与以下各项相关：各种环境中托管的 Exchange 邮箱、Exchange 与 Teams 的交互方式，以及 SharePoint 和 OneDrive for Business 的类似注意事项。 

|询问你自己|操作 |
|------------|-------|
| 是否能随当前 Exchange 和 SharePoint 部署一起部署所需的 Teams 功能？ |有关 Teams 中的 Exchange 和 SharePoint 的详细信息，请参阅：<ul><li> [Exchange 与 Teams 如何交互](exchange-teams-interact.md)</li><li>[SharePoint Online 和 OneDrive for Business 与 Teams 如何交互](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a>Teams 限制和规范 

规划 Teams 的企业部署时，你应考虑任何相关的限制和规范，例如团队中的最大成员数、用户可创建的最大团队数，诸如此类。

|询问你自己|操作 |
|------------|-------|
| 我的 Teams 部署可能会遇到什么限制？ | 若要了解详细信息，请阅读 [Teams 的限制和规范](limits-specifications-teams.md)。 |
|||

### <a name="office-365-urls-and-ports"></a>Office 365 URL 和端口

对其 Internet 流量保持精细控制的组织应阅读 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)，了解必须为 Teams 正确配置的 URL、IP 地址、端口和协议的最新列表。 Microsoft 一直在改进 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。 建议你通过 RSS 订阅，以在此信息更新或更改时收到通知。 至少需确保你已打开在上述[聊天部署先决条件](#chat-deployment-prerequisites)中列出的端口。

|询问你自己|操作 |
|------------|-------|
| 是否需要 Internet 访问规则才能让用户使用 Teams，或者开放最少所需的端口是否足够？ | 若要了解详细信息，请参阅 [Office 365 URL 和 IP 地址范围](office-365-urls-ip-address-ranges.md)。|
|||


### <a name="governance-naming-conventions-who-can-create-teams"></a>管理（命名约定，可创建团队的人员）

你的组织可能需要你对团队的命名和分类方式、谁可以创建团队以及团队到期、保留和存档加以控制。 这称为管理。 你可以使用 Azure Active Directory (Azure AD) 来配置各个方面。


| 询问你自己 | 操作 |
|--------------|--------|
|是否需要对谁可以创建团队进行控制？| 请阅读[在 Teams 中规划管理](plan-teams-governance.md)。|
|是否需要对团队的命名方式进行控制？|请阅读[在 Azure AD 中为 Office 365 组实施命名策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。|
|||

### <a name="teams-application-policy-side-rail-control"></a>Teams 应用程序策略（侧边栏控制）

固定的应用显示在 Teams 的侧边栏中。 通过创建 Teams 应用程序策略，你可以预先配置一组固定的 Teams 应用，以便针对经过挑选的用户组个性化 Teams。 默认情况下，“**在 Microsoft Teams 中允许外部应用**”设置处于启用状态。

| 询问你自己 | 操作 |
|--------------|--------|
|是否应该创建一组预先配置的固定 Teams 应用程序？ | 请阅读 [Teams 中应用的管理员设置](admin-settings.md)。|
|如何决定哪些组接收这些应用分组？|请阅读[团队应用权限和注意事项](app-permissions.md)。|
|||

### <a name="archiving-and-compliance"></a>存档与合规性 

你的组织可能要求你对团队的存档方式以及某些类型的团队中包含的数据类型加以控制。 请阅读 [Teams 中的的安全性和合规性概述](security-compliance-overview.md)，了解哪些设置默认情况下已启用。

| 询问你自己 | 操作 |
|--------------|--------|
|是否需要配置团队保留？|若要设置保留策略，请参阅[设置 Teams 保留策略](retention-policies.md)。|
|是否需要配置团队存档？|若要存档或还原团队，请参阅[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。|
|是否需要配置其他合规性设置？|有关安全性和合规性的详细信息，请参阅 [Teams 中的安全性和合规性概述](security-compliance-overview.md)。|
|||

### <a name="conditional-access"></a>条件访问 

对于核心工作效率方案（包括会议、日历、互操作聊天和文件共享），Teams 高度依赖 Exchange Online、SharePoint Online 和 Skype for Business Online。 当用户在任何客户端上直接登录 Teams 时，为这些云应用设置的条件访问策略将应用于 Teams。 为这些云应用设置的条件访问策略控制各个方面，例如用户是否可从某些网络访问 Teams 服务。

| 询问你自己 | 操作 |
|--------------|--------|
|<br>是否需要为 Teams 配置条件访问？|<ul><li>若要了解访问策略的工作方式，请参阅[条件访问策略如何在 Teams 中发挥作用？](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams)</li><li>若要为 Teams 设置多重身份验证 (MFA)，请参阅：<ul><li>[快速入门：具有 Azure Active Directory 条件访问权限的特定应用需要 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Azure Active Directory 条件访问设置参考](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a>教育版 (EDU) 

在教育行业工作的 IT 专业人员可以利用 Teams 教育版，该版本提供的许多功能经过定制，可满足学生、教职员工和更广泛行业特定于教育的方案需求。

| 询问你自己 | 操作 |
|--------------|--------|
|是否要使用特定于 EDU 的 Teams 模板？ |若要详细了解 Teams 教育版，请参阅[面向管理员的 Microsoft 教育管理常见问题](plan-teams-governance-edu.md)。|
|是否要部署范围限定的搜索？|若要为 EDU 设置 Teams，请参阅[快速入门 - Teams 教育版管理](teams-quick-start-edu.yml)。|
|是否要将 Teams 与 School Data Sync 服务集成来配置用户帐户？|[面向教育版管理员的 Teams 资源](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a>政府版 - GCC 注意事项

对于在美国联邦政府、州政府、地方政府、部族政府或准州政府实体或者所处理数据遵从政府法规和要求的其他实体推动 Office 365 部署的 IT 专业人员，使用 Microsoft 365 政府版 - GCC（政府合格证书）可以适当地满足其需求。

| 询问你自己 | 操作 |
|--------------|--------|
| 是否要在 Microsoft 365 政府版 – GCC 环境中部署 Teams？ | 有关部署注意事项，请参阅[规划 Microsoft 365 政府版 - GCC 部署](plan-for-government-gcc.md)。|
|||

## <a name="next-steps"></a>后续步骤
- [推动采用](adopt-microsoft-teams-landing-page.md)聊天、团队、频道和应用。
- 在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。 在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。
- [部署会议](deploy-meetings-microsoft-teams-landing-page.md)
- [部署云语音](cloud-voice-landing-page.md)

