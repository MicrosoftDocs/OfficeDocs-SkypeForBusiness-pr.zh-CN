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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 会议迁移服务 (MMS) 是在后台运行并自动更新用户Skype for Business和Microsoft Teams会议的服务。
ms.openlocfilehash: a7e917a5b579c60ff84c3e1a5e6468a28f75faff
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671638"
---
# <a name="using-the-meeting-migration-service-mms"></a>使用会议迁移服务 (MMS)

会议迁移服务 (MMS) 是在以下方案中更新用户现有会议的服务：

- 当用户从本地迁移到云时。
- 当管理员更改用户的音频会议设置时
- 当联机用户仅升级到Teams时，或者当 TeamsUpgradePolicy 中的用户模式设置为 SfBwithTeamsCollabAndMeetings 时
- 使用 PowerShell 时

默认情况下，在每个情况下都会自动触发 MMS。 此外，管理员可以使用 PowerShell cmdlet 手动触发给定用户的会议迁移。

**限制**：如果应用以下任一项，则无法使用会议迁移服务：

- 用户的邮箱托管在本地Exchange。
- 用户正从云迁移到本地Skype for Business Server。

## <a name="how-mms-works"></a>MMS 的工作原理

为给定用户触发 MMS 时，该用户的迁移请求将放置在队列中。 为了避免任何比赛条件，排队的请求被故意不处理，直到至少 90 分钟过去了。 MMS 处理请求后，它将执行以下任务：

1. 它会在该用户的邮箱中搜索该用户组织的所有现有会议，并计划将来进行。
2. 根据用户邮箱中找到的信息，它会根据具体方案更新或安排Teams中的新会议。
3. 在电子邮件中，它将替换会议详细信息中的联机会议块。
4. 它代表会议组织者将该会议的更新版本发送给所有会议收件人。 会议受邀者将在其电子邮件中收到包含更新的会议坐标的会议更新。

    ![由 MMS 更新的会议块。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

从触发 MMS 的时间开始，通常需要大约 2 个小时才能迁移用户的会议。 但是，如果用户有大量会议，则可能需要更长的时间。 如果 MMS 在为用户迁移一个或多个会议时遇到错误，它将在 24 小时内定期重试最多 9 次。

**备注**：

- MMS 在迁移会议时会替换联机会议信息块中的所有内容。 因此，如果用户编辑了信息块，它们的更改会被覆盖。 用户拥有的所有联机会议信息块以外的内容不会受到影响。 这意味着附加到会议邀请的任何文件仍将包括在内。
- 仅迁移通过单击 Web **Outlook 中的“添加Skype会议**”按钮或使用Outlook的Skype 会议外接程序安排的Skype for Business或Microsoft Teams会议。 如果用户将Skype联机会议信息从一个会议复制并粘贴到新会议，则不会更新该新会议，因为原始服务中没有会议。
- 在运行 MMS 后，创建或附加到会议 (白板、轮询等) 的会议内容将不会保留。 如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。
- 日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。 请注意，存储在OneNote中的实际会议笔记仍将存在;它只是覆盖的共享笔记的链接。
- 与会者超过 250（包括组织者）的会议不会迁移。
- 邀请正文中的某些 UNICODE 字符可能错误地更新为以下特殊字符之一：ï、¿、1/2、 。

## <a name="triggering-mms-for-a-user"></a>为用户触发 MMS

本部分介绍在以下每个情况下触发 MMS 时会发生什么情况：

- 当用户从本地迁移到云时
- 当管理员更改用户的音频会议设置时
- 当 TeamsUpgradePolicy 中的用户模式设置为 TeamsOnly 或 SfBWithTeamsCollabAndMeetings (时，请使用 Powershell 或 Teams 管理员 门户) 
- 使用 PowerShell cmdlet 时，Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>将本地用户移到云时更新会议

这是最常见的方案，其中 MMS 有助于为用户创建更顺畅的转换。 如果不进行会议迁移，用户在本地Skype for Business Server组织的现有会议在用户联机后将不再工作。 因此，使用本地管理工具 (`Move-CsUser`或管理员 控制面板) 将用户移到云时，现有会议会自动移动到云并转换为 TeamsOnly。

如果用户在迁移到云之前已分配音频会议许可证，则会使用拨入坐标创建会议。 如果将用户从本地移动到云，并且你打算让该用户使用音频会议，我们建议在移动用户之前先分配音频会议，以便仅触发 1 个会议迁移。

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>当用户的音频会议设置更改时更新会议

在以下情况下，MMS 将更新现有Skype for Business和Microsoft Teams会议以添加、删除或修改拨入坐标：

- 向用户分配或删除 Microsoft 音频会议服务许可证，并且该用户未为第三方音频会议提供商启用。
- 将用户的音频会议提供商从任何其他提供商更改为 Microsoft 时，前提是为用户分配了 Microsoft 音频会议 许可证。 有关详细信息，请参阅 [将 Microsoft 分配为音频会议提供商](./assign-microsoft-as-the-audio-conferencing-provider.md)。 另请注意，对第三方音频会议提供商 [ACP] 的支持计划于 2019 年 4 月 1 日结束，如 [前所述](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)。
- 为用户启用或禁用音频会议时。
- 更改或重置配置为使用公共会议的用户的会议 ID 时。
- 将用户移动到新的音频会议网桥时。
- 未分配音频会议网桥的电话号码时。 这是一个复杂的方案，需要执行其他步骤。 有关详细信息，请参阅 [更改音频会议桥上的电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。

并非对用户的音频会议设置所做的所有更改都会触发 MMS。 具体地说，下列两种更改不会使 MMS 更新会议：

- 当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时
- 使用 `Update-CsTenantMeetingUrl` 命令更改组织的会议 URL 时。

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>在分配 TeamsUpgradePolicy 时更新会议

默认情况下，当向用户授予包含或`mode= SfBWithTeamsCollabAndMeetings`的实例`TeamsUpgradePolicy``mode=TeamsOnly`时，会自动触发会议迁移。 如果在授予上述任一模式时不想迁移会议，请在 (中`Grant-CsTeamsUpgradePolicy`指定`MigrateMeetingsToTeams $false`是使用 PowerShell) 还是在使用Teams管理门户) 时 (设置用户共存模式时取消选中用于迁移会议的框。

另请注意以下内容：

- 仅在为特定用户授予许可 `TeamsUpgradePolicy` 时才调用会议迁移。 如果在 *租户范围内或在租户范围内* 授予`TeamsUpgradePolicy` `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings`，则不会调用会议迁移。
- 仅当用户处于联机状态时，才能向用户授予 TeamsOnly 模式。 必须按 `Move-CsUser` 前面所述移动本地托管的用户。
- 授予 TeamsOnly 或 SfBWithTeamsCollabAndMeetings 以外的模式不会将现有Teams会议转换为Skype for Business会议。

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>通过 PowerShell cmdlet 手动触发会议迁移

除了自动会议迁移，管理员还可以通过运行 cmdlet `Start-CsExMeetingMigration`来手动触发用户的会议迁移。 此 cmdlet 会为指定用户的迁移请求排队。  除了所需的 `Identity` 参数，它还需要两个可选参数， `SourceMeetingType` 并 `TargetMeetingType`允许指定如何迁移会议：

**TargetMeetingType：**

- 使用`TargetMeetingType Current`指定Skype for Business会议保留Skype for Business会议，Teams会议保留Teams会议。 但是，音频会议坐标可能会更改，任何本地Skype for Business会议都将迁移到 Skype for Business Online。 这是 TargetMeetingType 的默认值。
- Using `TargetMeetingType Teams` 指定必须将任何现有会议迁移到Teams，无论会议是在Skype for Business联机还是本地托管，以及是否需要任何音频会议更新。

**SourceMeetingType：**

- 使用`SourceMeetingType SfB`指示仅Skype for Business会议 (是应更新本地会议还是联机) 。
- 使用`SourceMeetingType Teams`指示仅应更新Teams会议。
- 使用`SourceMeetingType All`指示应更新Skype for Business会议和Teams会议。 这是 SourceMeetingType 的默认值。

以下示例演示如何为用户 ashaw@contoso.com 启动会议迁移，以便将所有会议迁移到Teams：

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

## <a name="managing-mms"></a>管理 MMS

使用Windows PowerShell，可以检查正在进行的迁移的状态、手动触发会议迁移，以及完全禁用迁移。

### <a name="check-the-status-of-meeting-migrations"></a>检查会议迁移的状态

`Get-CsMeetingMigrationStatus`使用该 cmdlet 检查会议迁移的状态。 下面列出了一些示例。

- 若要获取所有 MMS 迁移的摘要状态，请运行以下命令，该命令提供所有迁移状态的表格视图：

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed        2
    Succeeded   131
    ```

- 若要获取特定时间段内所有迁移的完整详细信息，请使用这些 `StartTime` 和 `EndTime` 参数。 例如，以下命令将返回 2018 年 10 月 1 日至 2018 年 10 月 8 日期间发生的所有迁移的完整详细信息。

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```

- 若要检查特定用户的迁移状态，请使用 `Identity` 该参数。 例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```

如果看到任何迁移失败，请采取措施尽快解决这些问题，因为在解决这些问题之前，用户将无法拨入这些用户组织的会议。 如果 `Get-CsMeetingMigrationStatus` 显示处于失败状态的任何迁移，请执行以下步骤：

1. 确定受影响的用户。 运行以下命令获取受影响的用户列表，以及报告的具体错误：

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```

2. 对于每个受影响的用户，请查看 LastMessage 属性的值，以确定会议迁移失败的原因以及要采取的纠正措施。 执行纠正措施后，使用 `Start-CsExMeetingMigration` PowerShell cmldet 为受影响的用户重新触发会议迁移，如上所述。

3. 如果迁移仍然不起作用，则有两个选项：

    - 让用户创建新的 Skype 会议。
    - [联系支持人员](/microsoft-365/Admin/contact-support-for-business-products)。

该 `Get-CsMeetingMigrationStatus` cmdlet 可用于检索在过去 150 天内触发的迁移的状态。 超过 150 天的迁移记录将从系统中清除。

### <a name="enabling-and-disabling-mms"></a>启用和禁用 MMS

默认情况下，所有组织都启用了 MMS，但可以按如下所示禁用：

- 完全禁用租户。
- 仅对与音频会议相关的更改禁用。 在这种情况下，当用户从本地迁移到云，或者在授予 TeamsOnly 模式或 SfBWithTeamsCollabAndMeetings 模式 `TeamsUpgradePolicy`时，MMS 仍将运行。

例如，可能需要手动迁移所有会议或暂时禁用 MMS，同时对组织的音频会议设置进行重大更改

若要查看是否为组织启用了 MMS，请运行以下命令。 如果 `MeetingMigrationEnabled` 参数为 `$true`，则启用 MMS。

```PowerShell
Get-CsTenantMigrationConfiguration
```

如果在组织中启用了 MMS，并且你想要检查它是否已启用音频会议更新，请检查输出中的参数值`AutomaticallyMigrateUserMeetings``Get-CsOnlineDialInConferencingTenantSettings`。 若要为音频会议启用或禁用 MMS，请使用 `Set-CsOnlineDialInConferencingTenantSettings`。 例如，若要禁用音频会议的 MMS，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>相关主题

[尝试或购买Microsoft 365或Office 365中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[在本地和云之间移动用户](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
