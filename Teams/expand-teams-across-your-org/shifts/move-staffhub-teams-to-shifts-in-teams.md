---
title: 将 StaffHub 团队迁移到 Microsoft Teams 中的排班
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何移动 Microsoft StaffHub 团队和安排到班次的 Microsoft 团队中的数据。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74a9b23479f5357c0014ef5ef88b3f5da03ace7f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865045"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>将 Microsoft StaffHub 团队移动到引进中的 Microsoft 团队

> [!IMPORTANT]
> 有效 2019 年 10 月 1，，Microsoft StaffHub 将要停用。 我们 StaffHub 功能构建到 Microsoft 团队。 如今，团队包括日程管理引进相关应用程序和其他功能将随着时间的推移推出。 StaffHub 上 2019 年 10 月 1，将停止的所有用户的工作。 尝试打开 StaffHub 的任何人都将显示一条消息，来下载团队。 若要了解详细信息，请参阅[Microsoft StaffHub 要停用](microsoft-staffhub-to-be-retired.md)。

> 本文中讨论的功能不起作用尚未释放。 它已公布，并且即将提供，向 2019 年 5 的中部。 如果您是管理员，您可以了解时这将会出现在邮件中心 （在[Microsoft 365 管理中心](https://portal.office.com/adminportal/home)）。

团队中的班次应用程序提供管理计划和常量流 shift 交换和取消通知发生在每天的简单方法。 团队成员可以访问其日程安排和班次信息直接应用程序中以及跨其设备设置其首选项，管理其日程安排，关闭请求的时间。

本文将指导您完成如何移动贵组织的 StaffHub 团队和安排到引进团队中的数据。 无论您是具有一个或两个 StaffHub 团队的小型企业或大型企业与数百个 StaffHub 团队，在此可以找到您需要帮助团队对成功进行转换的管理指南。

您必须是全局管理员才能执行本文中的步骤。 如果您尚未这样做，必须通过[StaffHub 退休常见问题](microsoft-staffhub-to-be-retired.md)查看获取您可能遇到的任何问题的解答。 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>您需要了解的有关移动到团队

### <a name="when-to-move-to-teams"></a>何时将移动到团队

有效 2019 年 10 月 1，，StaffHub 将要停用。 我们建议您开始立即使用团队并开始转换贵组织的团队和 StaffHub 用户。 与计划管理正在 StaffHub 中的最常用的功能，我们建议您使用引进应用程序在工作组中向前移动。

### <a name="what-is-moved-to-teams"></a>什么被移动到团队

用户的详细信息、 日程安排信息和聊天和文件数据转为团队。 这包括团队成员资格、 工作组计划，和聊天室和最近 90 天的文件。

每个 StaffHub 团队需要相应的 Office 365 组。 如果 StaffHub 团队没有与其关联的 Office 365 组，将自动为您支持转换创建一个。 给定团队和组命名团队和 StaffHub 之间的差异，可能会看到团队中的不同的工作组名称。

如转换团队从 StaffHub 团队，用户在 StaffHub 中将不再有权访问其日程安排和重定向到团队中的变化。 我们建议您在整个组织大程度地减少中断并鼓励用户采用和研究团队通信此更改。 如果您有 Azure AD Premium，才能[运行报表](run-report-to-show-staffhub-usage.md)以获取 StaffHub 用户需要了解的有关此更改的组织中的列表。  

移到团队 StaffHub 团队后没有回滚的选项。

### <a name="user-experience-when-you-move-a-team"></a>移动团队时的用户体验

没有尽量减少停机时间 （少于 1 秒，如果确有） 的用户时其工作组从 StaffHub 切换到团队中的变化。 用户可以继续使用 StaffHub，直到完成移动到团队。 完成移动后，工作组成员将看到一条消息，告知他们需要启动团队中使用引进访问其团队日程安排。 下面是消息的一个示例的用户看到。

![StaffHub 团队移动到团队后，用户在 StaffHub 中看到邮件的示例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "用户在 StaffHub 后 StaffHub 团队将被移动到团队中看到邮件的示例")

## <a name="prepare"></a>准备

下面是如何准备要移到团队。

### <a name="assign-teams-licenses"></a>分配 Teams 许可证

每个用户必须具有活动的 Microsoft 365 或 Office 365 许可证从[合格的计划](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)，并且必须分配团队许可证。 向用户分配的工作组许可证，这些访问团队。

管理 Microsoft 365 管理中心中的团队许可证。 若要了解详细信息，请参阅[管理用户对团队的访问权限](../../user-access.md)。

> [!NOTE]
> 如果您的组织使用 Skype for Business 并且您并不准备要迁移到团队的所有用户，可以将团队启用然后，可以运行旁 for Business 的 Skype 团队您 Firstline 工作者。 在此共存模式，调用*群岛*，每个客户端应用程序运行作为单独的解决方案。 若要了解详细信息，请参阅[了解团队和 Skype 的业务共存及互操作性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>设置的 Azure AD 中未标识 StaffHub 用户帐户

每个管理器和团队成员必须在 Azure Active Directory (Azure AD) 中具有标识。 如果用户在 Azure AD 中没有 identity，这些设置的帐户。 方法如下。

- StaffHub 团队所有者和管理员可以将转换的虚拟或非活动帐户，并将其链接到 StaffHub 中的已设置帐户更改为有效的 UPN StaffHub 工作组设置页上的用户的电子邮件地址。

- 管理员可以运行[添加 StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)并通过使用 UPN 备份[删除 StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet 从 StaffHub 团队中移除的非设置的帐户和添加的帐户。

### <a name="install-the-staffhub-powershell-module"></a>安装 StaffHub PowerShell 模块

如果尚未[安装 StaffHub PowerShell 模块](install-the-staffhub-powershell-module.md)。

当移动 StaffHub 团队，先决条件检查的移动请求。 下面是移动请求可能无法的原因：

- 已登录的用户不是全局管理员
- 团队禁用租户中的所有用户
- 租户中禁用了组创建 office 365
- StaffHub 团队 Id 无效或不包含任何成员
- StaffHub 团队包括未链接到的 Azure AD 帐户的成员  

## <a name="run-a-pilot"></a>试运行

我们建议您通过移动两个或三个 StaffHub 团队的一组选定的前期应用启动。 运行试验可帮助您优化您转换的计划，并确保您准备要迁移到团队贵组织的所有 StaffHub 小组。 它还标识拥护者可帮助您的组织内的推动采纳率。 如果您是小型企业用户不需要的阶段性的方法，此部分中的步骤可能只需向工作组从 StaffHub 进行切换。

### <a name="identify-pilot-teams"></a>确定试点团队

到达标识两个或三个试点团队。 所有团队成员应都提交到使用团队中引进管理其日程安排和通信和相互协作。

### <a name="identify-team-champions"></a>确定团队拥护者

跨试点团队确定拥护者和登记它们可帮助宣传引进。 团队拥护者是有关用途，热心共享他们自己的经验教训到团队成员提供支持和指导。 团队拥护者可以是团队所有者或管理员。

工作组成员都设置按专用时间让每个人都[获取团队客户端](../../get-clients.md)，登录到团队和签出其日程安排中引进，并启动彼此聊天，应确保团队拥护者。 用户已熟悉 StaffHub 将启动并正在运行快速引进中。 您还可以指向其[引进](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)帮助以获取其他帮助。

### <a name="move-a-staffhub-team-coming-soon"></a>移动 StaffHub 团队 （即将推出）

使用以下步骤一次移动一个 StaffHub 团队。 我们建议您的试点工作组此方法。 更高版本，当您准备要迁移贵组织的所有 StaffHub 团队，请参阅[移动 StaffHub 团队](#move-your-staffhub-teams-coming-soon)有关的操作步骤一次移动多个团队。

运行以下命令以移动 StaffHub 团队。

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

下面是一个示例获取提交一个请求将 StaffHub 团队移动到团队时的响应。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

要检查的移动请求的状态，请运行以下命令。

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

下面是一个示例获取移动时的响应。

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>向工作组从 StaffHub 进行转换

### <a name="raise-awareness"></a>认知度

在您准备好超越您的试点工作组并将您的组织 StaffHub 团队移至团队非常重要首先在组织间通信更改。 分布有关引进并切换到团队认知度，生成兴奋，并决定采用的单词。

### <a name="move-your-staffhub-teams-coming-soon"></a>移动 StaffHub 团队 （即将推出）

使用以下步骤来批量移动 StaffHub 团队。 您可以选择移动贵组织的所有 StaffHub 小组或移动特定 StaffHub 团队。 如果您想要移动 StaffHub 团队需要一次，请参阅[移动 StaffHub 团队](#move-a-staffhub-team-coming-soon)。

#### <a name="move-all-staffhub-teams-coming-soon"></a>移动所有 StaffHub 团队 （即将推出）

运行以下命令以获取您的组织中的所有 StaffHub 团队的列表。

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

然后，运行以下命令以移动所有团队。

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

下面是响应的一个示例。

对于已被移动到团队或团队中已存在的任何团队，jobId 将"null"，如作业不需要提交移动该团队。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>移动特定 StaffHub 团队 （即将推出）

运行以下命令以获取您的组织中的所有 StaffHub 团队 Id 的列表。

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

在返回的结果`Get-StaffHubteamsForTenant`cmdlet 运行之前，请选择要移动，团队 Id，然后将它们添加到逗号分隔值 (CSV) 文件。

下面是举例说明如何设置 CSV 文件格式。

|Id  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0 fc 9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0 fc 9-408b-85ff-c14a26700000|

创建 CSV 文件后，运行以下命令以移动 CSV 文件中指定的团队。

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>确认您 StaffHub 团队已移至团队 （即将推出）

运行以下命令以获取引进中的所有团队的列表，您的组织中。 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>监视团队使用率

使用率报告可帮助您更好地了解使用模式并为您在何处针对性，培训和通信在整个组织提供见解。 由于引进团队中的应用程序，您可以查看使用率通过团队报告。 有关详细信息，请参阅[团队报告在管理中心中的 Microsoft 团队](../../teams-analytics-and-reports/teams-reporting-reference.md)和[Microsoft 365 管理中心中的团队活动报告](../../teams-activity-reports.md)。

## <a name="related-topics"></a>相关主题
- [Microsoft StaffHub 将停用](microsoft-staffhub-to-be-retired.md)
- [在 Microsoft Teams 中为组织管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell 参考](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
