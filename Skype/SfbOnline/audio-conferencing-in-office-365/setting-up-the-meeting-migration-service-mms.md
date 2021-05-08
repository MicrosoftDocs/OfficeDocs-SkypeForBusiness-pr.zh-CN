---
title: 使用会议迁移服务 (MMS)
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
description: 会议迁移 (MMS) 是在后台运行的服务，可Skype for Business Microsoft Teams会议。 MMS 旨在消除用户运行会议迁移工具以更新其会议Skype for Business Microsoft Teams的需求。
ms.openlocfilehash: 3866a11144ef6566422f4e7478b3e0e63ed4a0c5
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237608"
---
# <a name="using-the-meeting-migration-service-mms"></a>使用会议迁移服务 (MMS)

会议迁移服务 (MMS) 是一种在下列情况下更新用户现有会议的服务：

- 当用户从本地迁移到云环境时 (是Skype for Business Online 还是 TeamsOnly) 。
- 当管理员更改用户的音频会议设置时 
- 将联机用户升级到Teams，或者 TeamsUpgradePolicy 中的用户模式设置为 SfBwithTeamsCollabAndMeetings 时
- 使用 PowerShell 时 


默认情况下，MMS 会在每种情况下自动触发，尽管管理员可以在租户级别禁用 MMS。 此外，管理员可以使用 PowerShell cmdlet 为给定用户手动触发会议迁移。


**限制**：如果满足以下任一条件，将不能使用会议迁移服务：

- 用户的邮箱托管在本地Exchange中。
- 用户正在从云迁移到Skype for Business Server本地。

在这些情况下，最终用户可以使用会议迁移 [工具来](https://www.microsoft.com/download/details.aspx?id=51659) 迁移自己的会议。

## <a name="how-mms-works"></a>MMS 的工作原理

为给定用户触发 MMS 时，该用户的迁移请求将置于队列中。 为避免出现任何竞争情况，在至少 90 分钟之前，特意不处理排队的请求。 MMS 处理请求后，会执行以下任务：

1. 它会在用户的邮箱中搜索该用户组织的所有现有会议，并计划在将来。
2. 根据在用户的邮箱中发现的信息，它会在 Teams 或 Skype for Business Online 中为该用户更新或安排新会议，具体取决于具体方案。
3. 在电子邮件中，它将替换会议详细信息中的联机会议块。
4. 它代表会议组织者将会议的更新版本发送给所有会议收件人。 会议被邀请者将收到其电子邮件中更新的会议坐标的会议更新。 

    ![由 MMS 更新的会议块](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

从 MMS 触发起，通常需要大约 2 小时，直到用户的会议迁移完成。 但是，如果用户具有大量会议，可能需要更长时间。 如果 MMS 在迁移用户的一个或多个会议时遇到错误，它将在 24 小时内定期重试最多 9 次。

**注意**：

- MMS 在迁移会议时会替换联机会议信息块中的所有内容。 因此，如果用户编辑了信息块，它们的更改会被覆盖。 用户拥有的所有联机会议信息块以外的内容不会受到影响。 这意味着，附加到会议邀请的任何文件仍将包含在内。 
- 仅Skype for Business Microsoft Teams Web 上单击 Outlook 中的"添加 Skype 会议"按钮或者使用 Outlook 的 Skype 会议 加载项安排的 Outlook 会议。 如果用户将联机会议信息Skype粘贴到新会议，则新会议不会更新，因为原始服务中没有任何会议。
- 创建或附加到会议的会议内容 (白板、投票等) MMS 运行后不会保留。 如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。
- 日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。 请注意，存储在会议记录中OneNote会议笔记仍将存在;它是唯一覆盖的共享笔记的链接。
- 与会者超过 250（包括组织者）的会议不会迁移。
- 邀请正文中的某些 UNICODE 字符可能会错误地更新为以下特殊字符之一：ï、-、1/2、 。

## <a name="triggering-mms-for-a-user"></a>为用户触发 MMS

本部分介绍以下情况中触发 MMS 时会发生什么情况：

- 当用户从本地迁移到云时
- 当管理员更改用户的音频会议设置时 
- 当用户在 TeamsUpgradePolicy 中的模式设置为 TeamsOnly 或 SfBWithTeamsCollabAndMeetings (使用 Powershell 或 Teams 管理门户) 
- 使用 PowerShell cmdlet 时，Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>将本地用户移动到云时更新会议

这是 MMS 可帮助为用户创建更平滑过渡的最常见方案。 如果不进行会议迁移，则由本地用户Skype for Business Server的现有会议在用户联机移动后将不再有效。 因此，使用本地管理工具 (管理控制面板) 将用户移动到云时，现有会议会自动移动到 `Move-CsUser` 云，如下所示：

- 如果指定了 中的开关，会议将直接迁移到Teams `MoveToTeams` `Move-CsUser` 用户将进入 TeamsOnly 模式。 此开关的使用要求在 2015 Skype for Business Server CU8 或更高版本。 这些用户仍可使用 Skype for Business Skype for Business 客户端或 Skype 会议 App 加入他们受邀参加的任何Skype 会议会议。
- 否则，会议将迁移到 Skype for Business Online。

在任一情况下，如果在将用户移动到云之前为用户分配了音频会议许可证，则使用拨入坐标创建会议。 如果将用户从本地移动到云，并且希望该用户使用音频会议，我们建议在移动用户之前先分配音频会议，以便仅触发 1 个会议迁移。


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>当用户的音频会议设置更改时更新会议

在下列情况下，MMS 将更新Skype for Business Microsoft Teams会议以添加、删除或修改拨入坐标：

- 向用户分配或删除 Microsoft 音频会议服务许可证时，并且未为该用户启用第三方音频会议提供商。
- 将用户的音频会议提供商从任何其他提供商更改为 Microsoft 时，只要为该用户分配了 Microsoft 音频会议许可证。 有关详细信息，请参阅将 [Microsoft 分配为音频会议提供商](./assign-microsoft-as-the-audio-conferencing-provider.md)。 另请注意，对第三方音频会议提供商 [ACP] 的支持计划于 2019 年 4 月 1 日结束，正如之前 [宣布的](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)。
- 为用户启用或禁用音频会议时。
- 更改或重置配置为使用公用会议的用户的会议 ID 时。
- 将用户移动到新的音频会议网桥时。
- 取消分配来自音频会议网桥的电话号码时。 这是一个复杂的方案，需要其他步骤。 有关详细信息，请参阅 [更改音频会议网桥上的电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

并非用户的音频会议设置的所有更改都触发 MMS。 具体地说，下列两种更改不会使 MMS 更新会议：

- 当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时
- 使用 命令更改组织的会议 URL `Update-CsTenantMeetingUrl` 时。


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>分配 TeamsUpgradePolicy 时更新会议

默认情况下，当向用户授予 具有 或 的实例时，会自动 `TeamsUpgradePolicy` 触发 `mode=TeamsOnly` 会议迁移 `mode= SfBWithTeamsCollabAndMeetings` 。 如果在授予上述任一模式时不想迁移会议，则使用 PowerShell) 时，在 (中指定 ，或者取消选中用于迁移会议的框（如果使用 Teams 管理门户) ，则设置用户的共存模式 `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` (）。

另请注意以下事项：

- 只有当为特定用户授予权限时， `TeamsUpgradePolicy` 才调用会议迁移。 如果在租户范围内使用 或 进行授权，则不 `TeamsUpgradePolicy` `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` 调用会议迁移。 
- 如果用户是在线家庭用户，则只能向用户授予 TeamsOnly 模式。 必须如前所述使用 移动本地 `Move-CsUser` 用户。
- 授予 TeamsOnly 或 SfBWithTeamsCollabAndMeetings Teams模式不会将现有会议Skype for Business会议。

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>通过 PowerShell cmdlet 手动触发会议迁移

除了自动会议迁移外，管理员可以通过运行 cmdlet 手动为用户触发会议迁移 `Start-CsExMeetingMigration` 。 此 cmdlet 将指定用户的迁移请求排队。  除了所需的参数外，它还采用两个可选参数 和 ，这允许你 `Identity` `SourceMeetingType` `TargetMeetingType` 指定如何迁移会议：

**TargetMeetingType：**

- 使用 `TargetMeetingType Current` 指定Skype for Business保留Skype for Business，Teams保留Teams会议。 但是，音频会议坐标可能会更改，任何本地会议Skype for Business迁移到 Skype for Business Online。 这是 TargetMeetingType 的默认值。
- 使用 指定必须将任何现有会议迁移到 Teams，无论会议是托管在 Skype for Business 在线还是本地，也无论是否需要任何音频会议更新 `TargetMeetingType Teams` 。 

**SourceMeetingType：**
- `SourceMeetingType SfB`使用 指示仅Skype for Business会议 (是本地还是联机) 更新。
- `SourceMeetingType Teams`使用 指示仅Teams更新会议。
- `SourceMeetingType All`使用 指示应Skype for Business会议Teams会议。 这是 SourceMeetingType 的默认值。
    

以下示例演示如何为用户启动会议迁移 ashaw@contoso.com 以便所有会议迁移到Teams：

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>管理 MMS

使用Windows PowerShell，可以检查正在进行的迁移的状态、手动触发会议迁移，以及完全禁用迁移。 

### <a name="check-the-status-of-meeting-migrations"></a>检查会议迁移的状态

使用 `Get-CsMeetingMigrationStatus` cmdlet 检查会议迁移的状态。 下面列出了一些示例。

- 若要获取所有 MMS 迁移的摘要状态，请运行以下命令，该命令提供所有迁移状态的表格视图：

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- 若要获取特定时段内所有迁移的完整详细信息，请使用 `StartTime` 和 `EndTime` 参数。 例如，以下命令将返回 2018 年 10 月 1 日到 2018 年 10 月 8 日发生的所有迁移的完整详细信息。

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- 若要检查特定用户的迁移状态，请使用 `Identity` 参数。 例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
如果看到任何迁移失败，请尽快采取措施解决这些问题，因为用户无法拨入由这些用户组织的会议，直到你解决这些问题。 如果 `Get-CsMeetingMigrationStatus` 显示任何迁移都为失败状态，请执行以下步骤：
 
1. 确定受影响的用户。运行以下命令获取受影响的用户列表，以及报告的具体错误：

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. 对于每个受影响的用户，请运行会议迁移工具以手动迁移其会议。

3. 如果使用会议迁移工具还是无法完成迁移，你有两个选择：

    - 让用户创建新的 Skype 会议。
    - [联系支持人员](/microsoft-365/Admin/contact-support-for-business-products)。


### <a name="enabling-and-disabling-mms"></a>启用和禁用 MMS

MMS 默认为所有组织启用，但可禁用，如下所示：

- 完全禁用租户。 
- 仅对与音频会议相关的更改禁用。 在这种情况下，当用户从本地迁移到云时，或者当你在 中授予 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式时，MMS 仍将运行 `TeamsUpgradePolicy` 。

例如，你可能希望手动迁移所有会议或暂时禁用 MMS，同时对组织的音频会议设置进行重大更改

若要查看是否为组织启用了 MMS，请运行以下命令。 如果参数为 ，则启用 `MeetingMigrationEnabled` `$true` MMS。
```PowerShell
Get-CsTenantMigrationConfiguration
```
若要完全启用或禁用 MMS，请使用 `Set-CsTenantMigrationConfiguration` 命令。 例如，若要禁用 MMS，请运行以下命令：

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
如果在组织中启用了 MMS，并且你想要检查是否为音频会议更新启用了 MMS，请检查 的输出中的 `AutomaticallyMigrateUserMeetings` 参数值 `Get-CsOnlineDialInConferencingTenantSettings` 。 若要为音频会议启用或禁用 MMS，请使用 `Set-CsOnlineDialInConferencingTenantSettings` 。 例如，若要为音频会议禁用 MMS，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[在本地和云之间移动用户](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
