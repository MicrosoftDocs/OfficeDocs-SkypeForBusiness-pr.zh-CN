---
title: 将 StaffHub 团队迁移到 Microsoft Teams 中的排班
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何移动 Microsoft StaffHub 团队并将数据安排到 Microsoft 团队中的倒班。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4a14c7cbca85be266347cd6777ea1108cc63d065
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992839"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>将 Microsoft StaffHub 团队移动到 Microsoft 团队中的倒班

> [!IMPORTANT]
> 2019年12月31日生效，Microsoft StaffHub 将停用。 我们正在将 StaffHub 功能构建到 Microsoft 团队中。 今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。 StaffHub 将停止为2019年12月31日的所有用户工作。 任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。 若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。

团队中的倒班应用提供了一种简单的方法来管理计划，以及每天发生的班次交换和取消的持续流。 团队成员可以直接在应用和其设备上访问其计划和转移信息，以设置其首选项、管理其计划和请求超时。

本文将向你介绍如何移动组织的 StaffHub 团队并将数据安排到团队中的倒班。 它包括：

- [您需要了解的有关迁移到团队的哪些信息](#what-you-need-to-know-about-the-move-to-teams)
- [准备](#prepare)
- [执行试验](#conduct-a-pilot) 
- [超越您的试点和移动所有 StaffHub 团队](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [监视团队使用情况](#monitor-teams-usage)
- [过程](#troubleshooting)

无论您是拥有一个或两个 StaffHub 团队的小型企业，还是有数百个 StaffHub 团队的大型企业，在这里，您将找到所需的管理员指南，帮助您成功过渡到团队。

只有全局管理员才能执行本文中的步骤。 如果尚未执行此操作，请查看[StaffHub 退休常见问题](microsoft-staffhub-to-be-retired.md)，获取你可能遇到的任何问题的答案。

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>您需要了解的有关迁移到团队的哪些信息

### <a name="when-to-move-to-teams"></a>何时转到团队

将在2019年12月31日生效，StaffHub 将停用。 我们鼓励你立即开始使用团队，并开始从 StaffHub 过渡你的组织的团队和用户。 在 StaffHub 中，如果计划管理是最常用的功能，我们建议你使用团队中的倒班应用继续。

### <a name="what-is-moved-to-teams"></a>哪些内容被移动到团队

移动 StaffHub 团队时，团队成员、用户详细信息、工作组日程和聊天数据将移到团队。 移动 StaffHub 团队时，文件不会移动。 如果 StaffHub 团队包含你还想要移动到团队的文件，请在单独的步骤中移动文件。

每个 StaffHub 团队都需要一个相应的 Office 365 组。 如果 StaffHub 团队与 Office 365 组关联，则当您移动团队时，将保留该组的隐私设置。 如果 StaffHub 团队没有与之关联的 Office 365 组，则会自动为您创建一个私密隐私设置的组以支持该切换。  由于团队和 StaffHub 之间的团队和组命名之间的差异，团队中可能会显示不同的团队名称。 

当您将团队从 StaffHub 过渡到团队时，用户将无法再访问其在 StaffHub 中的日程安排，并且会被重定向到团队中的倒班。 我们建议你将此更改与你的组织进行沟通，以最大限度地减少中断，并鼓励用户采纳和探索团队。 如果你有 Azure AD Premium，则可以[运行报表](run-report-to-show-staffhub-usage.md)来获取组织中需要了解此更改的 StaffHub 用户的列表。  

将 StaffHub 团队移动到团队后，没有回滚选项。

### <a name="user-experience-when-you-move-a-team"></a>移动团队时的用户体验

当用户的团队从 StaffHub 切换到团队成员时，停机时间最少（如果有）。 用户可以继续使用 StaffHub，直到完成到团队的移动。 完成移动后，团队成员将看到一条消息，告知他们需要开始使用团队中的倒班访问其团队日程。 下面是用户在 StaffHub 团队移到团队后在 StaffHub 中看到的消息的示例。

![用户看到的消息的示例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "用户在 StaffHub 团队移到团队后在 StaffHub 中看到的消息示例")

## <a name="prepare"></a>准备

下面介绍了如何准备迁移到团队。

### <a name="check-that-prerequisites-are-met"></a>检查是否满足先决条件

将 StaffHub 团队移动到团队之前，请确保：

- 登录用户是全局管理员。
- 已为租户中的所有用户启用团队。
- 租户中已启用 Office 365 组创建。
- StaffHub teamId 有效。
- StaffHub 团队至少有一个团队所有者。
- StaffHub 团队包含成员。
- 所有 StaffHub 团队成员均链接到 Azure AD 帐户。
- 所有 StaffHub 团队成员均分配有一个团队许可证。  

如果不满足这些先决条件，则移动请求将失败。

### <a name="assign-teams-licenses"></a>分配 Teams 许可证

每个用户都必须具有[符合条件的计划](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)的活动 Microsoft 365 或 Office 365 许可证，并且必须分配有团队许可证。 为用户分配团队许可证后，他们可以访问团队。

可在 Microsoft 365 管理中心内管理团队许可证。 若要了解详细信息，请参阅[管理用户对团队的访问权限](../../user-access.md)。

> [!NOTE]
> 如果你的组织使用 Skype for Business，并且尚未准备好将所有用户移到团队，你可以为你的一线工作人员启用团队，然后将团队与 Skype for Business 一起运行。 在此共存模式（名为 "*岛*"）中，每个客户端应用都作为单独的解决方案运行。 若要了解详细信息，请参阅[了解团队和 Skype for business 共存和互操作性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a>安装 StaffHub PowerShell 模块的预发布版本

如果尚未安装，请[安装 StaffHub PowerShell 模块的预发布版本](install-the-staffhub-powershell-module.md)。

必须安装预发行版本的模块才能将 StaffHub 团队移动到团队。

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a>为没有联系人的 StaffHub 团队成员链接 Azure AD 帐户

每个 StaffHub 团队成员都必须链接到 Azure Active Directory （Azure AD）帐户。 如果以下任何情形适用，组织中的用户将不会链接到 Azure AD 帐户：

- 团队所有者添加的用户没有 Azure AD 帐户。
- 团队所有者邀请用户加入 StaffHub 团队，而该用户未接受邀请。

这些用户具有非活动帐户并显示未知、受邀请或 InviteRejected 的用户状态。 你可以链接这些用户的 Azure AD 帐户。  方法如下。

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a>获取 StaffHub 团队中所有非活动帐户的列表

运行以下命令系列以获取 StaffHub 团队中所有非活动帐户的列表，并将列表导出到 CSV 文件。 每个命令都应单独运行。

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a>链接帐户

请执行下列操作之一：

- 转换和链接帐户。

  StaffHub 团队所有者和管理者可以转换非活动帐户并将其链接到 StaffHub 中的 Azure AD 帐户，方法是将用户的电子邮件地址更改为 "StaffHub 团队设置" 页面上的有效 UPN。

- 删除未链接的帐户，然后使用 UPN 重新添加帐户。
    1. 运行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet 以从 StaffHub 团队中删除未预配的帐户。
    2. 运行[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet，使用 UPN 将帐户重新添加到 StaffHub 团队。

- 删除非活动帐户。 如果不再需要用户帐户，请使用此选项。

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>将 FirstlineWorker 应用设置策略分配给用户

团队包含内置的 FirstlineWorker 应用设置策略，可用于自定义团队，以突出显示对于组织中的一线工作人员而言最重要的应用。 向用户分配此策略时，策略中的应用将固定到团队中的应用栏，以便快速轻松地访问。 添加到团队的其他应用可以通过单击 "..." 在应用栏中找到 **。** 团队桌面和 web 客户端中的更多应用，并可通过团队移动客户端向上轻扫。 默认情况下，FirstlineWorker 应用设置策略包括活动、班次、聊天和调用应用。

有关如何将 FirstlineWorker 应用设置策略分配给用户的步骤，请参阅[使用 FirstlineWorker 应用设置策略固定对团队的倒班](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)。 分配策略后，可能需要长达24小时才能生效。

我们建议您至少一周完成此步骤，然后再将 StaffHub 团队和用户移到团队。 当用户位于团队中时，请确认他们可以查看和访问 "倒班" 应用。

你还可以创建自定义应用设置策略，并编辑全局应用设置策略中的设置。 若要了解详细信息，请参阅[管理团队中的应用设置策略](../../teams-app-setup-policies.md)。

### <a name="onboard-users-to-teams"></a>向团队中的用户的板载用户

作为加入策略的一部分，为用户提供培训和指导，帮助他们熟悉团队。 与用户共享以下资源，以便他们知道团队客户端、培训和支持的位置：

- [Teams Web 客户端](https://teams.microsoft.com)
- [桌面和移动客户端下载链接](https://teams.microsoft.com/downloads)
- [Teams 培训视频](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Teams 帮助文档](https://support.office.com/teams)

有关部署团队和推动团队采纳的指南，请参阅[如何推广团队](../../How-to-roll-out-teams.md)和[采纳团队](../../adopt-microsoft-teams-landing-page.md)。

## <a name="conduct-a-pilot"></a>执行试验

我们建议您首先将两个或三个 StaffHub 团队移动到一组早期采纳者。 运行试验可帮助你优化过渡计划，并确保你已准备好将组织的所有 StaffHub 团队移动到团队。 它还标识了可帮助推动组织内采用的拥护者。 如果您是不需要分阶段方法的小型企业，那么本部分中的步骤可能是您将从 StaffHub 切换到团队的所有步骤。

### <a name="identify-pilot-teams"></a>确定试生产团队

联系以确定两个或三个试验团队。 所有团队成员都应承诺使用团队中的倒班管理其日程并相互沟通和协作。

### <a name="identify-team-champions"></a>确定团队拥护人员

在试点团队中确定拥护人员，并登记它们以帮助布道倒班。 团队拥护者热心他们所做的工作，分享他们自己的发现以向团队成员提供支持和指导。 团队拥护者可以是团队所有者或经理。

团队拥护者应确保团队成员可以通过专门的时间让每个人[获得团队客户](../../get-clients.md)，登录团队并查看他们的日程安排，并相互开始聊天。 已熟悉 StaffHub 的用户将在倒班中快速启动并运行。 你还可以指向它们以[移动帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)以获取其他帮助。

### <a name="move-a-staffhub-team"></a>移动 StaffHub 团队

使用以下步骤一次移动一个 StaffHub 团队。 我们建议你的试点团队采用此方法。 稍后，当你准备好移动组织的所有 StaffHub 团队时，请参阅[移动你的 StaffHub 团队](#move-your-staffhub-teams)，了解如何一次移动多个团队的步骤。

运行以下操作以移动 StaffHub 团队。

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
上例

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

下面是提交请求以将 StaffHub 团队移动到团队时收到的答复的示例。

```output
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

若要检查移动请求的状态，请运行以下。

```PowerShell
Get-TeamMigrationJobStatus <String>
```
上例

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

下面是在移动进行过程中获取的响应的示例。

```output
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>将文件从 StaffHub 团队移动到团队

此步骤仅适用于你已移动到团队的 StaffHub 团队是否具有你希望还希望迁移到团队的文件。 你可以直接在 SharePoint Online 或使用 PowerShell 中移动文件。

#### <a name="in-sharepoint-online"></a>在 SharePoint Online 中

了解[如何在 SharePoint Online 中移动文件](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)。

#### <a name="using-powershell"></a>使用 PowerShell

下载并安装[SharePoint Online 命令行管理](https://www.microsoft.com/download/details.aspx?id=35588)程序（如果尚未安装）。 它包含移动文件所需的 cmdlet。  

使用[admin.sharepoint.com](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet 连接到 SharePoint Online 团队网站。

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

对于要从 StaffHub 移动到团队的每个文件，请使用[PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet 移动文件。

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

若要移动多个文件，请循环访问这些文件，然后在循环中运行第二个命令。 如果会话保持活动状态，则无需重复第一个命令。

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>超越您的试点和移动所有 StaffHub 团队

### <a name="raise-awareness"></a>提高意识

当您准备好超越试点团队，并将组织的 StaffHub 团队移动到团队时，首先要在组织中传达更改，这一点非常重要。 传播关于倒班和过渡到团队的内容，以提高意识、产生兴奋和推动采纳。

### <a name="move-your-staffhub-teams"></a>移动 StaffHub 团队

使用以下步骤批量移动 StaffHub 团队。 你可以选择移动组织的所有 StaffHub 团队或移动特定的 StaffHub 团队。 如果想要一次移动一个团队，请参阅[移动 StaffHub 团队](#move-a-staffhub-team)。

#### <a name="move-all-staffhub-teams"></a>移动所有 StaffHub 团队

运行以下操作以获取组织中所有 StaffHub 团队的列表。

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

然后，运行以下操作以移动所有团队。

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

下面是该响应的一个示例。

对于已迁移到团队或已存在于团队中的任何团队，作业 Id 将为 "null"，因为不需要提交作业即可移动该团队。

```output
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>移动特定的 StaffHub 团队

运行以下操作以获取组织中所有 StaffHub 团队 Id 的列表。

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

在之前运行的`Get-StaffHubteamsForTenant` cmdlet 返回的结果中，选择要移动的团队 id，然后将其添加到逗号分隔值（CSV）文件。

下面是如何设置 CSV 文件格式的示例。

|标识号  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

创建 CSV 文件后，请运行以下操作以移动您在 CSV 文件中指定的团队。

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>确认你的 StaffHub 团队是否已迁移到团队

运行以下操作，获取组织中所有团队成员的列表。 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>将文件从 StaffHub 团队移动到团队

如果你移动的 StaffHub 团队包含你还想要移动到团队的文件，请参阅[将文件从 StaffHub 团队移动到团队](#move-files-from-a-staffhub-team-to-teams)。

## <a name="monitor-teams-usage"></a>监视团队使用情况

使用情况报告可帮助你更好地了解使用模式，并向你提供有关在你的组织中对培训和沟通工作进行排序的位置的见解。 你可以运行报表，显示总体团队使用情况、用户在团队中执行的活动类型、用户如何连接到团队等。 有关详细信息，请参阅 Microsoft[团队管理中心中的团队报告](../../teams-analytics-and-reports/teams-reporting-reference.md)和[microsoft 365 管理中心中的团队活动报表](../../teams-activity-reports.md)。

## <a name="troubleshooting"></a>疑难解答

**如何获取有关失败错误的详细信息**

运行以下内容，获取有关尝试移动团队时发生的 "失败" 错误的详细信息：

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

你将看到返回以下状态之一： "成功"、"失败"、"正在排队"。

如果返回 "失败"，请运行以下内容以获取有关错误的详细信息：

```PowerShell
$res.Result.Error.Innererror
```

**当您尝试移动 StaffHub 团队时，状态将显示为 "失败"，并且收到 "无法检索用户适用的 SKU 类别" 错误消息**

如果一个或多个团队成员没有团队许可证，则可能会发生这种情况。 转到 portal.office.com，找到该组，然后确认组成员分配有团队许可证。

**当你尝试移动 StaffHub 团队时，状态将显示为 "失败"，你将收到 "未找到团队所有者" 错误消息**

如果与 StaffHub 团队关联的组没有团队所有者，则可能会发生这种情况。 转到 portal.office.com，找到组，然后向该组添加一个或多个所有者。

**当您尝试将文件从 StaffHub 移动到团队时，会收到 "权限被拒绝" 错误消息。**

如果你尝试将文件移动到你不是其成员的专用 Office 365 组中，可能会出现此情况。 如果是这种情况，请使用[AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet 将自己添加到 StaffHub 团队，然后移动文件。 移动文件后，请使用[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet 将自己从团队中删除。 

**当您尝试将文件从 StaffHub 移动到团队时，将收到一条错误消息，指出 "常规" 文件夹不存在。**

运行以下命令以将常规文件夹添加到 SharePoint，然后重试：

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>相关主题
- [如何部署 Microsoft Teams](../../How-to-roll-out-teams.md)
- [Microsoft StaffHub 将停用](microsoft-staffhub-to-be-retired.md)
- [在 Microsoft Teams 中为组织管理 Shifts 应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell 参考](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
