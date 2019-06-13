---
title: 将 StaffHub 团队迁移到 Microsoft Teams 中的排班
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何将 Microsoft StaffHub 团队和日程安排数据迁移到 Microsoft Teams 中的排班。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780806"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>将 Microsoft StaffHub 团队迁移到 Microsoft Teams 中的排班

> [!IMPORTANT]
> 自 2019 年 10 月 1 日起，Microsoft StaffHub 将停用。 我们正在为 Microsoft Teams 构建 StaffHub 功能。 如今，Teams 包含用于日程安排管理的排班应用，并且随着时间推移将推出其他功能。 StaffHub 将于 2019 年 10 月 1 日停止为所有用户工作。 尝试打开 StaffHub 的任何用户都会看到一则提示其下载 Teams 的消息。 若要了解详细信息，请参阅 [Microsoft StaffHub 将停用](microsoft-staffhub-to-be-retired.md)。

Teams 中的排班应用提供了一种简单的方法来管理日程安排以及每天发生的换班和班次取消的持续流程。 团队成员可以直接在该应用及其设备上访问他们的日程安排和排班信息，以便设置他们的偏好、管理日程安排和申请休假。

本文将介绍如何将组织的 StaffHub 团队和日程安排数据迁移到 Teams 中的排班。 它包含以下内容：

- [迁移到 Teams 的必备知识](#what-you-need-to-know-about-the-move-to-teams)
- [准备](#prepare)
- [执行试点](#conduct-a-pilot) 
- [超越试点并迁移所有 StaffHub 团队](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [监视 Teams 使用情况](#monitor-teams-usage)
- [疑难解答](#troubleshooting)

无论你拥有包含一个或两个 StaffHub 团队的小型企业，还是拥有包含数百个 StaffHub 团队的大型企业，你都可以在这里找到帮助你成功过渡到 Teams 所需的管理员指南。

只有全局管理员才能执行本文所述的步骤。 如果你尚未这样做，请查看 [StaffHub 停用常见问题解答](microsoft-staffhub-to-be-retired.md)，以获取你可能遇到的任何问题的答案。

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>迁移到 Teams 的必备知识

### <a name="when-to-move-to-teams"></a>何时迁移到 Teams

自 2019 年 10 月 1 日起，StaffHub 将停用。 我们鼓励你立即开始使用 Teams，并开始从 StaffHub 迁移组织的团队和用户。 由于日程安排管理是 StaffHub 中的最常用功能，我们建议你使用 Teams 中的排班应用继续执行相关操作。

### <a name="what-is-moved-to-teams"></a>可将哪些内容迁移到 Teams

可将用户详细信息、日程安排信息以及聊天记录和文件数据迁移到 Teams。 这包括团队成员资格、团队日程安排以及过去 90 天内的聊天记录和文件。

每个 StaffHub 团队都需要一个相应的 Office 365 组。 如果 StaffHub 团队没有与之关联的 Office 365 组，则系统会自动创建一个以支持迁移。 鉴于 Teams 与 StaffHub 之间的团队和组命名有所不同，你可能会在 Teams 中看到不同的团队名称。

将团队从 StaffHub 迁移到 Teams 时，用户将无法再访问 StaffHub 中的日程安排，并且将重定向到 Teams 中的排班应用。 我们建议你在整个组织内传达此更改，以最大限度地减少中断并鼓励用户采用和探索 Teams。 如果你拥有 Azure AD Premium，则可以[运行报告](run-report-to-show-staffhub-usage.md)以获取组织内需要了解此更改的 StaffHub 用户列表。  

将 StaffHub 团队迁移至 Teams 后，不提供任何回滚选项。

### <a name="user-experience-when-you-move-a-team"></a>迁移团队时的用户体验

将团队从 StaffHub 切换到 Teams 中的排班应用时，用户的停机时间很短（不到一秒钟，如果有的话）。 用户可以继续使用 StaffHub，直到完成向 Teams 的迁移为止。 完成迁移后，团队成员将看到一则消息，提示他们需要开始使用 Teams 中的排班应用来访问其团队日程安排。 以下是将 StaffHub 团队迁移到 Teams 后用户将在 StaffHub 中看到的消息示例。

![用户看到的消息示例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "将 StaffHub 团队迁移到 Teams 后用户将在 StaffHub 中看到的消息示例")

## <a name="prepare"></a>准备

下文介绍了迁移到 Teams 的准备工作。

### <a name="check-that-prerequisites-are-met"></a>检查是否满足先决条件

将 StaffHub 团队迁移到 Teams 之前，请确保：

- 已登录的用户是全局管理员。
- 已为租户中的所有用户启用 Teams。
- 已在租户中启用 Office 365 组创建。
- StaffHub teamId 有效。
- StaffHub 团队包含成员。 
- 所有 StaffHub 团队成员均已链接到 Azure AD 帐户。 

如果不满足这些先决条件，则迁移请求将失败。 

### <a name="assign-teams-licenses"></a>分配 Teams 许可证

每个用户都必须已通过[符合条件的计划](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)获得有效的 Microsoft 365 或 Office 365 许可证，并且已分配一个 Teams 许可证。 为用户分配 Teams 许可证可使他们获得 Teams 的访问权限。

你可以在 Microsoft 365 管理中心管理 Teams 许可证。 若要了解详细信息，请参阅[管理用户对 Teams 的访问权限](../../user-access.md)。

> [!NOTE]
> 如果贵组织使用 Skype for Business，而你尚未准备好将所有用户迁移到 Teams，则可以为你的一线员工启用 Teams，随后他们可以将 Teams 与 Skype for Business 一起运行。 在这种称为“*并行*”的共存模式中，每个客户端应用都作为单独的解决方案运行。 要了解详细信息，请阅读[了解 Teams 和 Skype for Business 的共存和互操作性](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

### <a name="install-the-staffhub-powershell-module"></a>安装 StaffHub PowerShell 模块

如果你没有此模块，请[安装 StaffHub PowerShell 模块](install-the-staffhub-powershell-module.md)。 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>为在 Azure AD 中没有标识的 StaffHub 用户预配帐户

每个经理和团队成员都必须在 Azure Active Directory (Azure AD) 中具有标识。 如果用户在 Azure AD 中没有标识，请为其预配帐户。 方法如下。 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a>获取 TeamHub 团队中所有用户的列表，其团队成员未预配 Azure AD 帐户

运行下面的命令：
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a>预配帐户

请执行下列操作之一：

- 转换帐户并将其链接到预配帐户。

  StaffHub 团队所有者和经理可以转换虚拟或非活动帐户，并将其链接到 StaffHub 中的预配帐户，方法是在 StaffHub 团队设置页面上将用户的电子邮件地址更改为有效 UPN。

- 删除未设置的帐户，然后使用 UPN 重新添加帐户。
    1. 运行 [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet 以从 StaffHub 团队中删除未配置的帐户。
    2. 运行 [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet 以使用 UPN 将帐户添加回 StaffHub 团队。 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>为用户分配 FirstlineWorker 应用设置策略

Teams 包含内置的 FirstlineWorker 应用设置策略，你可以使用该策略来自定义 Teams，以突出显示对组织内的一线员工最重要的应用。 为用户分配此策略时，策略中的应用程序将固定到 Teams 中的应用栏，以便快速轻松地进行访问。 通过单击 Teams 桌面和 Web 客户端中的“**...更多应用**”或在 Teams 移动客户端中向上滑动，可以在应用栏中找到添加到 Teams 的其他应用。 默认情况下，FirstlineWorker 应用设置策略包括活动、排班、聊天和呼叫应用。

有关如何为用户分配 FirstlineWorker 应用设置策略的步骤，请参阅[使用 FirstlineWorker 应用设置策略将排班固定到 Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)。 分配策略后，最长可能需要 24 小时才能生效。

我们建议你将 StaffHub 团队和用户迁移到 Teams 之前至少提前一周完成此步骤。 当用户在 Teams 中时，请确认他们可以查看和访问排班应用。

你还可以创建自定义应用设置策略，并在全局应用设置策略中编辑设置。 若要了解详细信息，请参阅[在 Teams 中管理应用设置策略](../../teams-app-setup-policies.md)。

### <a name="onboard-users-to-teams"></a>为用户提供 Teams 培训

作为入职策略的一部分，为用户提供培训和指导，帮助他们熟悉 Teams。 与用户共享以下资源，以便他们知道从何处获得 Teams 客户端、培训和支持：

- [Teams Web 客户端](https://teams.microsoft.com)
- [桌面和移动客户端下载链接](https://teams.microsoft.com/downloads)
- [Teams 培训视频](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Teams 帮助文档](https://support.office.com/teams)

有关部署 Teams 和推动 Teams 采用的指南，请参阅[如何部署 Teams](../../How-to-roll-out-teams.md) 和[采用 Teams](../../adopt-microsoft-teams-landing-page.md)。

## <a name="conduct-a-pilot"></a>执行试点

我们建议你先为一组早期采用者迁移两个或三个 StaffHub 团队。 运行试点可帮助你优化过渡计划，并确保你已准备好将组织的所有 StaffHub 团队迁移到 Teams。 它还将确定有助于推动整个组织采用的支持者。 如果你拥有一家不需要分阶段方法的小型企业，那么本节所述的步骤即为从 StaffHub 过渡到 Teams 所需执行的全部步骤。

### <a name="identify-pilot-teams"></a>确定试点团队

请联系各个团队以确定两个或三个试点团队。 所有团队成员都应承诺使用 Teams 中的排班应用来管理其日程安排，并相互沟通和协作。

### <a name="identify-team-champions"></a>确定团队支持者

确定试点团队的支持者，并让他们帮助宣传排班应用。 团队支持者对他们的工作充满热情，将分享他们自己的知识，并为团队成员提供支持和指导。 团队支持者可以是团队所有者或经理。

通过致力于让每位团队成员[获取 Teams 客户端](../../get-clients.md)、登录 Teams 并在排班应用中查看其日程安排以及开始相互聊天，团队支持者应确保这些成员参与其中。 已熟悉 StaffHub 的用户可在排班应用中快速启动并运行。 你还可以指向[排班帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)以获取更多帮助。

### <a name="move-a-staffhub-team"></a>迁移 StaffHub 团队

使用这些步骤一次迁移一个 StaffHub 团队。 我们建议为你的试点团队推荐这种方法。 之后，当你准备好迁移组织的所有 StaffHub 团队时，请参阅[迁移 StaffHub 团队](#move-your-staffhub-teams)，了解有关如何一次迁移多个团队的步骤。

运行以下命令以迁移 StaffHub 团队。

```
Move-StaffHubTeam -TeamId <String>
```
示例：

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

以下是当你提交将 StaffHub 团队迁移到 Teams 的请求时获得的响应示例。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

若要检查迁移请求的状态，请运行以下命令。

```
Get-TeamMigrationJobStatus <String>
```
示例：

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

以下是你在迁移过程中获得的响应示例。

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>将文件从 StaffHub 团队迁移到 Teams

此步骤仅适用于以下情形，即已迁移到 Teams 的 StaffHub 团队还包含要迁移到 Teams 的文件。 你可以直接在 SharePoint Online 中或使用 PowerShell 来迁移这些文件。 

#### <a name="in-sharepoint-online"></a>在 SharePoint Online 中

请参阅[如何在 SharePoint Online 中迁移文件](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)。

#### <a name="using-powershell"></a>使用 PowerShell

下载并安装 [SharePoint Online 命令行管理程序](https://www.microsoft.com/download/details.aspx?id=35588)（如果尚未安装）。 其中包含迁移文件所需的 cmdlet。  

使用 [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet 连接到 SharePoint Online 团队网站。

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

对于要从 StaffHub 迁移到 Teams 的每个文件，请使用 [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet 来迁移这些文件。

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

若要迁移多个文件，请遍历各个文件并在循环时运行第二个命令。 如果会话保持活动状态，则无需重复第一个命令。

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>超越试点并迁移所有 StaffHub 团队

### <a name="raise-awareness"></a>提高意识

如果你已准备好超越试点团队并将组织的 StaffHub 团队迁移到 Teams，则需要在整个组织内传达更改，这一点非常重要。 宣传关于排班应用和向 Teams 过渡的信息，以提高意识、激发热情并推动采用。

### <a name="move-your-staffhub-teams"></a>迁移 StaffHub 团队

使用这些步骤批量迁移 StaffHub 团队。 你可以选择迁移组织的所有 StaffHub 团队或迁移特定 StaffHub 团队。 如果你希望一次迁移一个 StaffHub 团队，请参阅[迁移 StaffHub 团队](#move-a-staffhub-team)。

#### <a name="move-all-staffhub-teams"></a>迁移所有 StaffHub 团队

运行以下命令以获取组织中所有 StaffHub 团队的列表。

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

然后，运行以下命令以迁移所有团队。

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

以下是响应示例。

对于已迁移到 Teams 或已存在于 Teams 的任何团队，jobId 将为“null”，因为无需提交作业即可迁移该团队。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>迁移特定 StaffHub 团队

运行以下命令以获取组织中所有 StaffHub 团队 ID 的列表。

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

在由先前运行的 `Get-StaffHubteamsForTenant` cmdlet 返回的结果中，选择要迁移的团队 ID，然后将它们添加到逗号分隔值 (CSV) 文件中。

以下是如何格式化 CSV 文件的示例。

|Id  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

创建 CSV 文件后，运行以下命令以迁移你在 CSV 文件中指定的团队。

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>确认你的 StaffHub 团队已迁移到 Teams

运行以下命令以获取组织的排班应用中的所有团队列表。 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>将文件从 StaffHub 团队迁移到 Teams

如果已迁移的 StaffHub 团队还包含要迁移到 Teams 的文件，请参阅[将文件从 StaffHub 团队迁移到 Teams](#move-files-from-a-staffhub-team-to-teams)。

## <a name="monitor-teams-usage"></a>监视 Teams 使用情况

使用情况报告可以帮助你更好地了解使用模式，并为你提供相关见解，让你了解在组织内的何处设置培训和通信工作的优先级。 由于排班是 Teams 中的应用，因此你可以通过 Teams 报告查看使用情况。 有关详细信息，请参阅 [Microsoft Teams 管理中心中的 Teams 报告](../../teams-analytics-and-reports/teams-reporting-reference.md)和 [Microsoft 365 管理中心中的 Teams 活动报告](../../teams-activity-reports.md)。

## <a name="troubleshooting"></a>疑难解答 

**当你尝试将文件从 StaffHub 迁移到 Teams 时，你会收到“权限被拒绝”错误消息。**

如果你尝试在自己不是其成员的私有 Office 365 组中迁移文件，则可能会发生这种情况。 如果是这种情况，请使用 [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet 将自己添加到 StaffHub 团队，然后迁移这些文件。 迁移文件后，请使用 [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet 将你自己从团队中删除。 

**当你尝试将文件从 StaffHub 迁移到 Teams 时，你会收到一则错误消息，指出“常规”文件夹不存在。**

运行以下命令以将“常规”文件夹添加到 SharePoint，然后重试：

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>相关主题
- [如何部署 Microsoft Teams](../../How-to-roll-out-teams.md)
- [Microsoft StaffHub 将停用](microsoft-staffhub-to-be-retired.md)
- [在 Microsoft Teams 中为组织管理排班应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell 参考](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
