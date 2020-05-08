---
title: 使用会议迁移服务（MMS）
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 会议迁移服务（MMS）是一种在后台运行的服务，可自动更新用户的 Skype for business 和 Microsoft 团队会议。 MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: 81bd5f1e9304ff3ff6eedb901a50632aa6edd73a
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163951"
---
# <a name="using-the-meeting-migration-service-mms"></a>使用会议迁移服务（MMS）

会议迁移服务（MMS）是在以下情况下更新用户现有会议的服务：

- 当用户从本地迁移到云（无论是 Skype for business Online 还是 TeamsOnly）时。
- 管理员对用户的音频会议设置进行更改时 
- 当联机用户仅升级到团队时，或者当 TeamsUpgradePolicy 中的用户模式设置为 SfBwithTeamsCollabAndMeetings 时
- 使用 PowerShell 时 


默认情况下，在这些情况下，MMS 会自动触发，尽管管理员可以在租户级别禁用它。 此外，管理员可以使用 PowerShell cmdlet 为给定用户手动触发会议迁移。


**限制**：如果满足以下任一条件，则无法使用会议迁移服务：

- 用户的邮箱托管在本地 Exchange 中。
- 用户正在从云迁移到本地 Skype for Business 服务器。

在这些情况下，最终用户可以使用[会议迁移工具](https://www.microsoft.com/download/details.aspx?id=51659)来迁移其自己的会议。

## <a name="how-mms-works"></a>MMS 的工作原理

为给定用户触发 MMS 时，将向队列中放置该用户的迁移请求。 为了避免任何争用条件，已对排队的请求进行有意处理，直到至少90分钟后才会被处理。 MMS 处理请求后，它会执行以下任务：

1. 它将在该用户的邮箱中搜索该用户组织的所有现有会议，将来安排该用户。
2. 根据用户邮箱中的信息，在团队或 Skype for Business Online 中为该用户更新或安排新会议，具体取决于具体的方案。
3. 在电子邮件中，它将替换会议详细信息中的联机会议阻止。
4. 它代表会议组织者将该会议的更新版本发送给所有会议收件人。 会议被邀请者将通过其电子邮件中的已更新会议坐标接收会议更新。 

    ![由 MMS 更新的会议块](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

从 MMS 触发时起，通常需要大约2小时才会迁移用户的会议。 但是，如果用户拥有大量的会议，可能需要更长时间。 如果 MMS 在为用户迁移一个或多个会议时遇到错误，将在24小时范围内定期重试最多9次。

**备注**：

- MMS 在迁移会议时会替换联机会议信息块中的所有内容。因此，如果用户编辑了信息块，它们的更改会被覆盖。用户拥有的所有联机会议信息块以外的内容不会受到影响。
- 只有通过在 Outlook 网页版中单击 "**添加 skype 会议**" 按钮或使用 Outlook 的 skype 会议外接程序进行安排的 Skype for Business 或 Microsoft 团队会议才会被迁移。 如果用户将一个会议中的 Skype online 会议信息复制并粘贴到新会议中，则不会更新新会议，因为原始服务中没有会议。
- 在 MMS 运行后，已创建或附加到会议（白板、投票等）的会议内容将不会保留。 如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。
- 日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。 请注意，OneNote 中存储的实际会议笔记仍将保留在其中。只有指向共享笔记的链接被覆盖。
- 与会者超过 250（包括组织者）的会议不会迁移。
- 邀请正文中的一些 UNICODE 字符可能会错误地更新为下列特殊字符之一：ï、¿、1/2、。

## <a name="triggering-mms-for-a-user"></a>为用户触发 MMS

本部分介绍在以下每种情况下会触发 MMS 的情况：

- 用户从本地迁移到云时
- 管理员对用户的音频会议设置进行更改时 
- 当 TeamsUpgradePolicy 中的用户模式设置为 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 时（使用 Powershell 或团队管理门户）
- 使用 PowerShell cmdlet 时，Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>将本地用户移动到云时更新会议

这是一种最常见的情况，MMS 可帮助用户创建更流畅的切换效果。 如果没有会议迁移，在用户联机移动后，在本地 Skype for business 服务器中由用户组织的现有会议将不再有效。 因此，当你使用本地管理员工具（ `Move-CsUser`或 "管理员" 控制面板）将用户移动到云时，现有会议将按如下方式自动移到云：

- 如果指定`MoveToTeams`了开关`Move-CsUser` ，会议将直接迁移到团队，并且用户将处于 TeamsOnly 模式。 使用此开关需要使用 CU8 或更高版本的 Skype for business Server 2015。 通过使用 Skype for business 客户端或 Skype 会议应用，这些用户仍然可以加入任何受邀参加的 Skype for Business 会议。
- 否则，会议将迁移到 Skype for business Online。

在任何一种情况下，如果用户在被移动到云之前已分配了音频会议许可证，则将使用拨入坐标创建会议。 如果你将用户从本地移动到云，并且希望该用户使用音频会议，我们建议你在移动用户之前先分配音频会议，以便仅触发1个会议迁移。


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>当用户的音频会议设置更改时更新会议

在以下情况下，MMS 将更新现有 Skype for Business 和 Microsoft 团队会议以添加、删除或修改拨入坐标：

- 向用户分配或删除 Microsoft 音频会议服务许可证时，该用户未启用第三方音频会议提供商。
- 如果将用户的音频会议提供商从任何其他提供商更改为 Microsoft，前提是该用户分配有 Microsoft 音频会议许可证。 有关详细信息，请参阅[将 Microsoft 分配为音频会议提供商](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。 另请注意，第三方音频会议提供商 [ACP] 的支持计划于2019年4月1日（如[以前宣布](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)）的生命周期结束。
- 启用或禁用用户的音频会议时。
- 当您更改或重置配置为使用公共会议的用户的会议 ID 时。
- 将用户移动到新的音频会议桥时。
- 当音频会议桥的电话号码未分配时。 这是一个需要额外步骤的复杂方案。 有关详细信息，请参阅[更改音频会议桥中的电话号码](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

对用户的音频会议设置的所有更改都不会触发 MMS。 具体地说，下列两种更改不会使 MMS 更新会议：

- 当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时
- 使用`Update-CsTenantMeetingUrl`命令更改组织的会议 URL 时。


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>分配 TeamsUpgradePolicy 时更新会议

默认情况下，当向用户授予`TeamsUpgradePolicy` with `mode=TeamsOnly`或`mode= SfBWithTeamsCollabAndMeetings`的实例时，将自动触发会议迁移。 如果你不希望在授予其中任一种模式时迁移会议，请在设置`MigrateMeetingsToTeams $false`用户`Grant-CsTeamsUpgradePolicy`的共存模式（如果使用团队管理门户）时，指定 In （如果使用 PowerShell）或取消选中 "迁移会议" 框。

另请注意以下事项：

- 仅当你授予`TeamsUpgradePolicy`特定用户时，才会调用会议迁移。 如果你在`TeamsUpgradePolicy` *租户范围内*授予`mode=TeamsOnly`或`mode=SfBWithTeamsCollabAndMeetings` ，则不会调用会议迁移。
- 如果用户处于联机状态，则仅可向用户授予 TeamsOnly 模式。 必须按照前面所述，使用`Move-CsUser`托管内部部署的用户进行移动。
- 授予除 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 以外的其他模式时，不会将现有团队会议转换为 Skype for Business 会议。

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>通过 PowerShell cmdlet 手动触发会议迁移

除了自动会议迁移之外，管理员还可以通过运行 cmdlet `Start-CsExMeetingMigration`手动为用户触发会议迁移。 此 cmdlet 将针对指定用户的迁移请求排队。  除了所需`Identity`参数之外，它还带有两个可选参数`SourceMeetingType` ， `TargetMeetingType`并允许你指定如何迁移会议：

**TargetMeetingType:**

- 使用`TargetMeetingType Current`指定 skype for business 会议保持 skype for business 会议和团队会议保持团队会议。 但是音频会议坐标可能会更改，并且任何本地 Skype for business 会议都将迁移到 Skype for business Online。 这是 TargetMeetingType 的默认值。
- 使用`TargetMeetingType Teams`指定无论是否需要进行任何音频会议更新，任何现有会议都必须迁移到团队，无论该会议是托管在 Skype for business online 还是内部部署中。 

**SourceMeetingType:**
- 使用`SourceMeetingType SfB`表示只有 Skype for business 会议（本地还是联机）应更新。
- 使用`SourceMeetingType Teams`指示仅应更新团队会议。
- " `SourceMeetingType All`使用" 表示应更新 Skype for business 会议和团队会议。 这是 SourceMeetingType 的默认值。
    

下面的示例演示了如何为用户 ashaw@contoso.com 启动会议迁移，以便将所有会议迁移到团队：

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>管理 MMS

使用 Windows PowerShell，你可以检查正在进行的迁移的状态，手动触发会议迁移，并完全禁用迁移。 

### <a name="check-the-status-of-meeting-migrations"></a>检查会议迁移的状态

使用`Get-CsMeetingMigrationStatus` cmdlet 检查会议迁移的状态。 下面列出了一些示例。

- 若要获取所有 MMS 迁移的摘要状态，请运行以下命令，其中提供了所有迁移状态的表格视图：

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 若要获取特定时间段内所有迁移的完整详细信息，请`StartTime`使用`EndTime` "和" 参数。 例如，以下命令将返回从2018年10月1日到2018年10月8日的所有迁移的完整详细信息。

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 若要检查特定用户的迁移状态，请使用该`Identity`参数。 例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
如果你看到任何失败的迁移，请尽快采取措施解决这些问题，因为用户无法在你解决这些问题之前使用这些用户进行组织。 如果`Get-CsMeetingMigrationStatus`显示处于失败状态的任何迁移，请执行以下步骤：
 
1. 确定受影响的用户。 运行以下命令获取受影响的用户列表，以及报告的具体错误：

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. 对于每个受影响的用户，运行会议迁移工具以手动迁移其会议。

3. 如果使用会议迁移工具还是无法完成迁移，你有两个选择：

    - 让用户创建新的 Skype 会议。
    - [联系支持人员](https://go.microsoft.com/fwlink/p/?LinkID=518322)。


### <a name="enabling-and-disabling-mms"></a>启用和禁用 MMS

默认情况下，将为所有组织启用 MMS，但可以禁用它，如下所示：

- 完全禁用租户。 
- 仅针对与音频会议相关的更改禁用。 在这种情况下，当用户从本地迁移到云或在中`TeamsUpgradePolicy`授予 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式时，MMS 仍将运行。

例如，你可能希望手动迁移所有会议或暂时禁用 MMS，同时对你的组织的音频会议设置进行重大更改

若要查看你的组织是否已启用 MMS，请运行以下命令。 如果`MeetingMigrationEnabled`参数为`$true`，则启用 MMS。
```PowerShell
Get-CsTenantMigrationConfiguration
```
若要完全启用或禁用 MMS，请`Set-CsTenantMigrationConfiguration`使用命令。 例如，若要禁用 MMS，请运行以下命令：

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
如果组织中已启用 MMS，并且你想要检查它是否已启用音频会议更新，请在的 "输出" `AutomaticallyMigrateUserMeetings`中检查该参数的`Get-CsOnlineDialInConferencingTenantSettings`值。 若要启用或禁用音频会议的 MMS， `Set-CsOnlineDialInConferencingTenantSettings`请使用。 例如，若要为音频会议禁用 MMS，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>相关主题

[在 Microsoft 365 或 Office 365 中试用或购买音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
