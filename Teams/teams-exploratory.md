---
title: 管理 Microsoft Teams 探索体验
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: 未获得 Microsoft Teams 许可的 Microsoft 365 或 Office 365 用户可以启动探索 Teams 许可证。
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f27dc7e8772e25b6dcc91622cabec421e058af7b
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031478"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>管理 Microsoft Teams 探索许可证
=======================================================

Microsoft Teams 探索性体验让组织中拥有 Azure 域服务（Azure AD）但未获得 Teams 许可的用户可以启动 Teams 的探索性体验。管理员可以为其组织中的用户开启或关闭此功能。The Teams Exploratory体验现在已取代了早期的 [Microsoft 商业云试用版](iw-trial-teams.md)。

## <a name="whats-in-the-teams-exploratory-experience"></a>Teams 探索体验中包含哪些服务

管理员将在 Teams 探索体验中看到的服务计划有：

- Exchange Online（计划 1）
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
- Yammer Enterprise

  <sup>1</sup> 从使用 Microsoft Stream 到使用 [OneDrive for Business 和 SharePoint for meeting 进行会议录制](tmr-meeting-recording-change.md)到改变将是一个分阶段的方式。 在发布时，你将可以选择加入这种体验。在11月，如果你必须选择是否要继续使用Stream。在2021年初，我们将要求所有客户使用OneDrive for Business 和 SharePoint 获取新的会议录制。

## <a name="whos-eligible"></a>谁有资格使用

用户符合 Teams 探索体验的标准，如果他们：

- 具有托管 Azure AD 域电子邮件地址。
- 属于付费订阅的租户。

必须启用用户注册应用程序和试用版（在 Microsoft 365 管理中心）。有关更多信息，请参见稍后在本文出现的[管理团队探索性体验](#manage-the-teams-exploratory-experience)。

## <a name="who-isnt-eligible"></a>谁没有资格使用

用户在以下情况下不适合条件：

- 目前或以前拥有的来自付费、未付费或试用版许可证的 Teams 
- 位于至少已使用或收到一个特殊 COVID 优惠的租户中。

如果你是联合合作伙伴客户，或者是 GCC、GCC High、DoD 或 EDU 客户，则你的组织没有资格使用该服务。

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>如何注册 Teams 探索体验？

符合条件的用户可以通过登录 Teams（[teams.microsoft.com ](https://teams.microsoft.com)）来注册 Teams Exploratory 体验。将自动向他们分配此许可证，并且当组织中有人首次启动 Teams Exploratory 体验时，租户管理员将收到电子邮件通知。

## <a name="manage-the-teams-exploratory-experience"></a>管理 Teams 探索体验

Teams 探索体验设计为由单独的最终用户启动，你不能代表最终用户员工启动此服务。

Teams Exploratory 体验自带 Exchange Online 许可证，但在管理员分配之前将不会分配给用户。如果用户还没有 Exchange 许可证，而管理员也未分配 Exchange Online 许可证，那么用户将无法在 Teams 中安排会议，并且可能会错过其他 Teams 功能。

管理员可以通过使用 **试用版应用和服务** 开关，禁用最终用户在其组织内运行 Teams 探索体验的功能。

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>阻止用户安装试用版应用和服务

可禁止用户安装试用版应用和服务，这会阻止用户运行 Teams 探索体验。

1. 从 Microsoft 365 管理中心，转到“ **设置** ” > “ **组织设置** ”，选择“ **服务** ”，然后选择“ **用户自有应用和服务** ”。

    ![管理中心中“服务”页面的屏幕截图](media/iw-trial-services.png)

2. 清除“ **允许用户安装试用版应用和服务** ”复选框。

    ![管理中心中的“用户自有应用和服务”页面](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 如果你的组织不符合获取 Teams 探索体验的条件，你将看不到“ **允许用户安装试用版应用和服务** ”选项。

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>为拥有包含 Teams 的许可证的用户管理可用性

已分配到包含 Teams 许可证的用户尚无资格获得 Teams 探索体验。当 Teams 服务计划开启时，用户可以登录并使用 Teams。如果已禁用服务计划，则用户无法登录，并且无法使用 Teams 探索体验。你必须拥有管理员权限。

关闭对 Teams 的访问：

1. 在 Microsoft 365 管理中心中，选择“ **用户** ” > “ **活动用户** ”。

2. 选择用户姓名旁边的框。

3. 在“ **产品许可证** ”行中，选择“ **编辑** ”。

4. 在“ **产品许可证** ”窗格中，将开关切换为“ **关闭** ”。

    ![管理中心中的“产品许可证”页面。](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>为已在使用 Teams 探索体验的用户管理 Teams 可用性

如果用户正在运行 Teams Exploratory 体验，你可通过删除许可证或服务计划将其关闭。你必须拥有管理员权限。

若要关闭 Teams 探索体验许可证，请执行以下操作：

1. 在 Microsoft 365 管理中心中，选择“ **用户** ” > “ **活动用户** ”。

2. 选择用户姓名旁边的框。

3. 在“ **产品许可证** ”行中，选择“ **编辑** ”。

4. 在“ **产品许可证** ”窗格中，将此探索许可证的开关切换为“ **关** ”。

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

在下一个 **协议周年纪念日** 或 2021 年 1 月或之后的 **续约** 之前，Microsoft Teams 探索体验无需支付额外费用。届时，使用 Microsoft 探索体验许可证的最终用户将需要转为包含 Teams 的付费许可证。在此后启动的任何 Microsoft 探索体验许可证将始终可用，且在你的下一个 **周年纪念日** 或 **续约周期** 之前无需支付额外费用。

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a>如果最终用户刚好在我的周年纪念或续订日期前启动 Microsoft Teams 探索体验，会发生什么情况

在 **协议周年日** 或 **续订** 后的 90 天内启动的 Microsoft Teams 探索体验许可证无需迁移到付费许可证，直到下一个周年日或续订周期。

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a>如果我的协议没有周年日或每年的续约日期（例如逐月协议），该怎么办

对于没有周年纪念日或年度续约日期的协议，将会将第一个最终用户激活 Microsoft Teams 探索体验许可证后的下一年视为周年纪念日或续约日。Microsoft Teams 探索许可证上的用户必须根据本文中概述的政策，在每年的该日期之前转换为付费许可证。

例如，如果第一位最终用户在 2020 年 6 月 19 日激活了 Microsoft Teams 探索，则他们和客户租户中的所有其他符合条件的用户必须在 2021 年 6月 19 日之前转换为 Teams 付费许可证。

> [!Note]
> 在上一个探索体验许可证到期后的 3 个月内客户将被禁用并阻止开始新的探索试用许可证。
