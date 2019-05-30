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
description: 了解如何移动 Microsoft StaffHub 团队并将数据安排到 Microsoft 团队中的倒班。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548291"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>将 Microsoft StaffHub 团队移动到 Microsoft 团队中的倒班

> [!IMPORTANT]
> 2019年10月1日生效, Microsoft StaffHub 将停用。 我们正在将 StaffHub 功能构建到 Microsoft 团队中。 今天, 团队包括 "倒班" 应用, 用于计划管理, 而其他功能将随着时间的推移而推出。 StaffHub 将停止为2019年10月1日的所有用户工作。 任何试图打开 StaffHub 的人都将显示一条消息, 指导他们下载团队。 若要了解详细信息, 请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。

> 本文中讨论的功能尚未发布。 它已宣布推出, 即将在2019年6月早些时候推出。 如果您是管理员, 则可以在邮件中心 (在[Microsoft 365 管理中心](https://portal.office.com/adminportal/home)) 中了解何时将提供此功能。

团队中的倒班应用提供了一种简单的方法来管理计划, 以及每天发生的班次交换和取消的持续流。 团队成员可以直接在应用和其设备上访问其计划和转移信息, 以设置其首选项、管理其计划和请求超时。

本文将向你介绍如何移动组织的 StaffHub 团队并将数据安排到团队中的倒班。 无论您是拥有一个或两个 StaffHub 团队的小型企业, 还是有数百个 StaffHub 团队的大型企业, 在这里, 您将找到所需的管理员指南, 帮助您成功过渡到团队。

只有全局管理员才能执行本文中的步骤。 如果尚未执行此操作, 请查看[StaffHub 退休常见问题](microsoft-staffhub-to-be-retired.md), 获取你可能遇到的任何问题的答案。 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>您需要了解的有关迁移到团队的哪些信息

### <a name="when-to-move-to-teams"></a>何时转到团队

将在2019年10月1日生效, StaffHub 将停用。 我们鼓励你立即开始使用团队, 并开始从 StaffHub 过渡你的组织的团队和用户。 在 StaffHub 中, 如果计划管理是最常用的功能, 我们建议你使用团队中的倒班应用继续。

### <a name="what-is-moved-to-teams"></a>哪些内容被移动到团队

用户详细信息、日程安排信息和聊天和文件数据将转换为团队。 这包括过去90天的团队成员身份、团队日程安排以及聊天和文件。

每个 StaffHub 团队都需要一个相应的 Office 365 组。 如果 StaffHub 团队没有与之关联的 Office 365 组, 则会自动为您创建一个以支持切换。 由于团队和 StaffHub 之间的团队和组命名之间的差异, 团队中可能会显示不同的团队名称。

当您将团队从 StaffHub 过渡到团队时, 用户将无法再访问其在 StaffHub 中的日程安排, 并且会被重定向到团队中的倒班。 我们建议你将此更改与你的组织进行沟通, 以最大限度地减少中断, 并鼓励用户采纳和探索团队。 如果你有 Azure AD Premium, 则可以[运行报表](run-report-to-show-staffhub-usage.md)来获取组织中需要了解此更改的 StaffHub 用户的列表。  

将 StaffHub 团队移动到团队后, 没有回滚选项。

### <a name="user-experience-when-you-move-a-team"></a>移动团队时的用户体验

当用户的团队从 StaffHub 切换到团队成员时, 停机时间最少 (如果有)。 用户可以继续使用 StaffHub, 直到完成到团队的移动。 完成移动后, 团队成员将看到一条消息, 告知他们需要开始使用团队中的倒班访问其团队日程。 下面是用户在 StaffHub 团队移到团队后在 StaffHub 中看到的消息的示例。

![用户看到的消息的示例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "用户在 StaffHub 团队移到团队后在 StaffHub 中看到的消息示例")

## <a name="prepare"></a>准备

下面介绍了如何准备迁移到团队。

### <a name="assign-teams-licenses"></a>分配 Teams 许可证

每个用户都必须具有[符合条件的计划](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)的活动 Microsoft 365 或 Office 365 许可证, 并且必须分配有团队许可证。 为用户分配团队许可证后, 他们可以访问团队。

可在 Microsoft 365 管理中心内管理团队许可证。 若要了解详细信息, 请参阅[管理用户对团队的访问权限](../../user-access.md)。

> [!NOTE]
> 如果你的组织使用 Skype for Business, 并且尚未准备好将所有用户移到团队, 你可以为你的一线工作人员启用团队, 然后将团队与 Skype for Business 一起运行。 在此共存模式 (名为 "*岛*") 中, 每个客户端应用都作为单独的解决方案运行。 若要了解详细信息, 请参阅[了解团队和 Skype for business 共存和互操作性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>为在 Azure AD 中没有标识的 StaffHub 用户设置帐户

每个管理者和团队成员都必须在 Azure Active Directory (Azure AD) 中拥有一个标识。 如果用户在 Azure AD 中尚没有标识, 请为其设置帐户。 方法如下。

- StaffHub 团队所有者和经理可以通过将用户的电子邮件地址更改为 "StaffHub 团队设置" 页面上的有效 UPN 来转换虚拟或非活动帐户并将其链接到 StaffHub 中的预配帐户。

- 管理员可以运行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)和[StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet 从 StaffHub 团队中删除非预配帐户, 并使用 UPN 重新添加帐户。

### <a name="install-the-staffhub-powershell-module"></a>安装 StaffHub PowerShell 模块

如果尚未安装, 请[安装 StaffHub PowerShell 模块](install-the-staffhub-powershell-module.md)。

移动 StaffHub 团队时, 移动请求将检查系统必备。 以下是移动请求可能失败的原因:

- 登录用户不是全局管理员
- 已针对租户中的所有用户禁用团队
- 租户中已禁用 Office 365 组创建
- StaffHub teamId 无效或没有成员
- StaffHub 团队包含未链接到 Azure AD 帐户的成员  

## <a name="run-a-pilot"></a>运行试验

我们建议您首先将两个或三个 StaffHub 团队移动到一组早期采纳者。 运行试验可帮助你优化过渡计划, 并确保你已准备好将组织的所有 StaffHub 团队移动到团队。 它还标识了可帮助推动组织内采用的拥护者。 如果您是不需要分阶段方法的小型企业, 那么本部分中的步骤可能是您将从 StaffHub 切换到团队的所有步骤。

### <a name="identify-pilot-teams"></a>确定试生产团队

联系以确定两个或三个试验团队。 所有团队成员都应承诺使用团队中的倒班管理其日程并相互沟通和协作。

### <a name="identify-team-champions"></a>确定团队拥护人员

在试点团队中确定拥护人员, 并登记它们以帮助布道倒班。 团队拥护者热心他们所做的工作, 分享他们自己的发现以向团队成员提供支持和指导。 团队拥护者可以是团队所有者或经理。

团队拥护者应确保团队成员可以通过专门的时间让每个人[获得团队客户](../../get-clients.md), 登录团队并查看他们的日程安排, 并相互开始聊天。 已熟悉 StaffHub 的用户将在倒班中快速启动并运行。 你还可以指向它们以[移动帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)以获取其他帮助。

### <a name="move-a-staffhub-team-coming-soon"></a>移动 StaffHub 团队 (即将推出)

使用以下步骤一次移动一个 StaffHub 团队。 我们建议你的试点团队采用此方法。 稍后, 当你准备好移动组织的所有 StaffHub 团队时, 请参阅[移动你的 StaffHub 团队](#move-your-staffhub-teams-coming-soon), 了解如何一次移动多个团队的步骤。

运行以下操作以移动 StaffHub 团队。

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

下面是提交请求以将 StaffHub 团队移动到团队时收到的答复的示例。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

若要检查移动请求的状态, 请运行以下。

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

下面是在移动进行过程中获取的响应的示例。

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>从 StaffHub 切换到团队

### <a name="raise-awareness"></a>提高意识

当您准备好超越试点团队, 并将组织的 StaffHub 团队移动到团队时, 首先要在组织中传达更改, 这一点非常重要。 传播关于倒班和过渡到团队的内容, 以提高意识、产生兴奋和推动采纳。

### <a name="move-your-staffhub-teams-coming-soon"></a>移动 StaffHub 团队 (即将推出)

使用以下步骤批量移动 StaffHub 团队。 你可以选择移动组织的所有 StaffHub 团队或移动特定的 StaffHub 团队。 如果想要一次移动一个团队, 请参阅[移动 StaffHub 团队](#move-a-staffhub-team-coming-soon)。

#### <a name="move-all-staffhub-teams-coming-soon"></a>移动所有 StaffHub 团队 (即将推出)

运行以下操作以获取组织中所有 StaffHub 团队的列表。

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

然后, 运行以下操作以移动所有团队。

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

下面是该响应的一个示例。

对于已迁移到团队或已存在于团队中的任何团队, 作业 Id 将为 "null", 因为不需要提交作业即可移动该团队。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>移动特定的 StaffHub 团队 (即将推出)

运行以下操作以获取组织中所有 StaffHub 团队 Id 的列表。

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

在之前运行的`Get-StaffHubteamsForTenant` cmdlet 返回的结果中, 选择要移动的团队 id, 然后将其添加到逗号分隔值 (CSV) 文件。

下面是如何设置 CSV 文件格式的示例。

|标识号  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

创建 CSV 文件后, 请运行以下操作以移动您在 CSV 文件中指定的团队。

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>确认你的 StaffHub 团队已迁移到团队 (即将推出)

运行以下操作, 获取组织中所有团队成员的列表。 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>监视团队使用情况

使用情况报告可帮助你更好地了解使用模式, 并向你提供有关在你的组织中对培训和沟通工作进行排序的位置的见解。 由于倒班是团队中的应用, 因此你可以通过团队报表查看使用情况。 有关详细信息, 请参阅 Microsoft[团队管理中心中的团队报告](../../teams-analytics-and-reports/teams-reporting-reference.md)和[microsoft 365 管理中心中的团队活动报表](../../teams-activity-reports.md)。

## <a name="related-topics"></a>相关主题
- [Microsoft StaffHub 将停用](microsoft-staffhub-to-be-retired.md)
- [在 Microsoft Teams 中为组织管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell 参考](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
