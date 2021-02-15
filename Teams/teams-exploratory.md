---
title: 管理 Microsoft Teams Exploratory 体验
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 未获得 Microsoft Teams 许可的 Microsoft 365 或 Office 365 用户可以启动 Exploratory Teams 许可证。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9aa7b0a26e947eaa961db5d5be3b793d50474867
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196466"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a>管理 Microsoft Teams Exploratory 许可证

Microsoft Teams 探索性体验让组织中拥有 Azure 域服务（Azure AD）但未获得 Teams 许可的用户可以启动 Teams 的探索性体验。管理员可以为其组织中的用户开启或关闭此功能。The Teams Exploratory体验现在已取代了早期的 [Microsoft 商业云试用版](iw-trial-teams.md)。

## <a name="whats-in-the-teams-exploratory-experience"></a>Teams Exploratory 体验中包含哪些服务

管理员将在 Teams Exploratory 体验中看到的服务计划有：

- Exchange Online（计划 1)
- 适用于 Microsoft 365 或 Office 365 的流
- MyAnalytics 提供的见解
- Microsoft Forms（计划 E1）
- Microsoft Planner
- Microsoft 搜索
- Microsoft StaffHub
- 适用于 Microsoft 365 和 Office 365 E1 SKU 的 Microsoft Stream<sup>1</1>
- Microsoft Teams
- 适用于 Microsoft 365 或 Office 365 的移动设备管理
- 适用于 Office 365 的 Office 移动应用
- Office Online
- 适用于 Microsoft 365 或 Office 365 的 PowerApps
- SharePoint Online（计划 1）
- Sway
- 待办事项（计划 1）
- Whiteboard（计划 1）
- Yammer 企业版

  <sup>1</sup> 将会议录制从 Microsoft Stream 改为 [OneDrive for Business 和 SharePoint](tmr-meeting-recording-change.md) 将是一种分阶段的方法。 启动时，你可以选择加入此体验。 在 11 月，如果想继续使用 Stream，你将必须选择退出。 2021 年初，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行新的会议录制。

## <a name="whos-eligible"></a>符合资格的人员

用户符合 Teams 探索体验的标准，如果他们：

- 具有托管 Azure AD 域电子邮件地址。
- 属于付费订阅的租户。
- 没有有效的 Teams 许可证。
- 不在创建许可证分配策略的租户中。

必须启用用户注册应用程序和试用版（在 Microsoft 365 管理中心）。有关更多信息，请参见稍后在本文出现的[管理团队探索性体验](#manage-the-teams-exploratory-experience)。

## <a name="who-isnt-eligible"></a>谁没有资格使用

用户在以下情况下不适合条件：

- 目前或以前拥有的来自付费、未付费或试用版许可证的 Teams
- 位于至少已使用或收到一个特殊 COVID 优惠的租户中。

如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该服务。

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>如何注册 Teams 探索体验？

符合条件的用户可通过登录到 Teams 桌面版或 Web 版 ([teams.microsoft.com](https://teams.microsoft.com)) 来注册 Teams Exploratory 体验。 目前，不支持通过移动设备启用 Exploratory。 当他们注册时，系统将自动向其分配此许可证，并且租户管理员会在组织中有人首次启动 Teams Exploratory 体验时收到一封电子邮件通知。

## <a name="manage-the-teams-exploratory-experience"></a>管理 Teams 探索体验

Teams 探索体验设计为由单独的最终用户启动，你不能代表最终用户员工启动此服务。

Teams Exploratory 体验自带 Exchange Online 许可证，但在管理员分配之前将不会分配给用户。如果用户还没有 Exchange 许可证，而管理员也未分配 Exchange Online 许可证，那么用户将无法在 Teams 中安排会议，并且可能会错过其他 Teams 功能。

管理员可以通过使用 **试用版应用和服务** 开关，禁用最终用户在其组织内运行 Teams 探索体验的功能。

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>阻止用户安装试用版应用和服务

可禁止用户安装试用版应用和服务，这会阻止用户运行 Teams 探索体验。

1. 从 Microsoft 365 管理中心，转到“**设置**” > “**组织设置**”，选择“**服务**”，然后选择“**用户自有应用和服务**”。

    ![管理中心中“服务”页面的屏幕截图](media/iw-trial-services.png)

2. 清除“**允许用户安装试用版应用和服务**”的复选标记。

    ![管理中心中的“用户自有应用和服务”页面](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 如果你的组织不符合获取 Teams 探索体验的条件，你将看不到“**允许用户安装试用版应用和服务**”选项。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>为拥有包含 Teams 的许可证的用户管理可用性

已分配到包含 Teams 许可证的用户尚无资格获得 Teams 探索体验。当 Teams 服务计划开启时，用户可以登录并使用 Teams。如果已禁用服务计划，则用户无法登录，并且无法使用 Teams 探索体验。你必须拥有管理员权限。

关闭对 Teams 的访问：

1. 在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。

2. 选择用户姓名旁边的框。

3. 在“**产品许可证**”行中，选择“**编辑**”。

4. 在“**产品许可证**”窗格中，将开关切换为“**关闭**”。

    ![管理中心中的“产品许可证”页面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>为已在使用 Teams 探索体验的用户管理 Teams 可用性

如果用户正在运行 Teams Exploratory 体验，你可通过删除许可证或服务计划将其关闭。你必须拥有管理员权限。

若要关闭 Teams 探索体验许可证，请执行以下操作：

1. 在 Microsoft 365 管理中心中，选择“**用户**” > “**活动用户**”。

2. 选择用户姓名旁边的框。

3. 在“**产品许可证**”行中，选择“**编辑**”。

4. 在“**产品许可证**”窗格中，将此探索许可证的开关切换为“**关**”。

    >[!Note]
    >组织中的第一位用户启动 Teams Exploratory 体验后，将显示 Teams Exploratory 切换开关。

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>为拥有 Teams 探索许可证的用户管理 Teams

可以像管理拥有普通付费许可证的用户一样管理拥有 Teams Exploratory 许可证的用户。有关更多信息，请参见[为你的组织管理Teams 设置](enable-features-office-365.md)。

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>从 Teams 探索许可证升级用户

要从 Teams 探索许可证升级用户（必须拥有管理员权限），请执行以下操作：

1. 购买包含 Teams 的订阅。

2. 删除用户的 Teams Exploratory 订阅。

3. 分配新购买的许可证。

有关详细信息，请参阅 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

> [!NOTE]
> 如果 Teams Exploratory 许可证已结束，而用户没有立即升级到包含 Teams 的订阅，则他们有 30 天的宽限期，在这 30 天之后就要删除数据。用户仍然存在于 Azure 域服务中。如果用户在宽限期内添加订阅，则一旦为用户分配了新的许可证以再次启用 Teams 功能，所有内容将仍然存在。

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>这对旧版 Microsoft Teams 商业云试用版许可证有何影响

从2020年2月起，符合条件的用户可以开始使用最新的 Microsoft Teams 探索版体验。所有遗留的 Teams 商业云试用许可证将在试用版期满前自动转换为新的优惠。

当用户首次登录过期的 Teams 商业云试用版时，我们会自动为这些用户分配一个 Teams 探索版体验授权。在用户在登录前不会转换。

### <a name="remove-a-teams-exploratory-license"></a>删除 Teams 探索许可证

- 如果要通过 PowerShell 删除此许可证，请参阅：[使用 Office 365 PowerShell 删除用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)

- 如果要通过管理门户删除此许可证，请参阅：[从组织删除用户](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)

## <a name="what-is-the-data-retention-policy"></a>什么是数据保留策略？

请参阅 [Microsoft 365 订阅信息](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)。

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Teams 探索体验持续多长时间

自 2021 年初起，Teams Exploratory 作为12个月的订阅（从初始用户注册开始），面向所有新客户。 当组织中第一个用户注册 Teams Exploratory 时，新的 Teams Exploratory 订阅将启动，并且将在 12 个月后过期。 12个月的期限从第一个用户的注册日开始，这有效期将适用于同一租户中的所有用户。

> [!NOTE]
> 体验的结束日期是在组织层面进行配置的，这意味着它将适用于同一组织的所有用户。 例如，用户 1 于 2021 年 1 月 1 日注册订阅。 这将在 2021 年 12 月 31 日启动订阅结束日期。 另一个用户 User 2 于 2021 年 10 月 1 日注册订阅。 用户 2 可使用 Teams Exploratory 两个月，因为用户 1 和 用户 2 都属于同一个组织都订阅，所以他们的订阅都将于2021年12月31日结束。

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a>在 12 个月的 Teams Exploratory 体验结束后，管理员应该怎么做

在 12 个月的订阅结束时，管理员应将其所有 Teams Exploratory 用户转换为包括 Teams 的付费许可证。 确保在Teams Exploratory订阅到期前完成这项工作至关重要，以避免对用户的体验造成任何干扰。

有关详细信息，请参阅上文中的 [Teams Exploratory中升级用户](#upgrade-users-from-the-teams-exploratory-license))。
