---
title: 设置会议迁移服务 (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: e240d9913ac543495286d8151bc0200a0f7c196d
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>设置会议迁移服务 (MMS)

Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
  
 **要求**
  
MMS 要求会议组织者使用 Exchange Online 上的邮箱。
  
 **主要场景**
  
MMS 会在下列两种主要场景中为用户更新 Skype 会议：
  
- 用户从本地 Skype for Business Server 迁移到 Skype for Business Online 时
    
- When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.
    
 **无法使用 MMS 的一般场景**
  
我们在此处列出了可能适用于你的一般场景。这些场景都支持迁移。但是，MMS 不在这些场景中运行，你需要改为使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。
  
- 用户的邮箱在本地 Exchange Server 上
    
- Using a third-party audio conferencing provider
    
- 将用户从 Skype for Business Online 迁移至本地 Skype Server
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>将本地用户迁移至 Skype for Business Online 时更新会议

这是 MMS 可以帮助你的用户顺利过渡的最常见的场景。 When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings. Any future meetings will be updated with the new information for that user.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>If you're currently using Skype Server 2015 for audio conferencing

我们建议你在此场景中使用 MMS 时遵循下列最佳做法以获得最佳体验：
  
- 由于 MMS 要求用户使用 Exchange Online 上的邮箱，如果你也将迁离本地 Exchange Server，请先将用户的邮箱迁移至 Exchange Online。
    
- Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. 如果你没有先分配许可证，在你分配许可证后 MMS 会再次更新所有会议。
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>如果你当前使用的是第三方音频会议提供商 (ACP)

With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings. You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license. 另一方面，你可能需要阻止自动替换发生，保留你的 ACP 提供的拨入号码。 To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`. 如果需要有关 PowerShell 的帮助，请参阅本文结尾处的[使用 PowerShell 管理你的 Skype for Business 组织](setting-up-the-meeting-migration-service-mms.md#WPSInfo)部分。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings. The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.
    
- If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence. The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Updating meetings when a user's audio conferencing settings change

MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:
  
- When you assign or remove **Audio Conferencing** license.
    
- When you enable or disable audio conferencing.
    
- 当你更改或重置已配置为使用公开会议的用户的会议 ID 时
    
- When you move the user to a new audio conferencing bridge.
    
- When a phone number is unassigned from a audio conferencing bridge. 这个场景比较复杂，需要执行其他步骤。 For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> [!重要信息] 仅当你使用的是 Microsoft 网桥时 MMS 才会更新会议。 If you are using a third-party audio conferencing provider, the users will need to update their meetings manually. 在这种情况下，你可以使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。 
  
Not all changes to a user's audio conferencing settings trigger MMS. 具体地说，下列两种更改不会使 MMS 更新会议：
  
- 当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时
    
- 当你使用 [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) 命令更改你的组织的会议 URL 时。
    
## <a name="what-happens-when-mms-updates-meetings"></a>MMS 更新会议时会发生什么？

当 MMS 检测到用户的会议需要更新时，它会执行以下操作：
  
1. Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future
    
  - Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped
    
  - 仅会更新该用户为组织者的会议
    
2. 替换会议详情中的联机会议信息块
    
3. 代表会议组织者将更新发送给会议所有的收件人
    
 **MMS 运行需要多长时间？**
  
The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar. 运行至少需要 10 分钟。 一些大型迁移需要的时间可能长达 12 小时，大多数迁移应该可以在 1 小时内完成。
  
 **限制和潜在问题**
  
- Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated. 换言之，如果用户将一个会议中的 Skype 联机会议信息复制并粘贴到另一个新会议中，该新会议不会更新。
    
- MMS 在迁移会议时会替换联机会议信息块中的所有内容。因此，如果用户编辑了信息块，它们的更改会被覆盖。用户拥有的所有联机会议信息块以外的内容不会受到影响。
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- 在 MMS 运行后，所有之前创建的或附加到会议的会议内容（白板、投票等）将不会保留。如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。
    
- 日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。请注意，存储在 OneNote 中的实际会议笔记会被保留，只会覆盖共享笔记的链接。
    
- 与会者超过 250（包括组织者）的会议不会迁移。
    
- 邀请正文中的一些 UNICODE 字符可能会被错误地更新为以下特殊字符之一：ï、¿、½、�。
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>MMS 更新会议时用户会为用户显示什么？

MMS 会像会议迁移工具一样代表用户发送会议更新。 因此，只会再次向用户显示其会议的会议接受通知。 This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.
  
## <a name="managing-mms"></a>管理 MMS

你需要使用 Windows PowerShell 管理 MMS 并检查进行中的迁移的状态。本部分信息的前提是你了解如何使用 PowerShell 管理你的 Skype for Business 组织。如果你不了解如何使用 PowerShell，请参阅本文结尾处的[使用 PowerShell 管理你的 Skype for Business 组织](setting-up-the-meeting-migration-service-mms.md#WPSInfo)部分。
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>我应该如何检查会议迁移的状态？

你可以使用  `Get-CsMeetingMigrationStatus` cmdlet 检查会议迁移的状态。下面列出了一些示例。
  
要获取所有 MMS 迁移的汇总状态，请运行以下命令：
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

这样会显示所有迁移状态的表格视图，如下所示：
  
State UserCount---------------<br/> Pending 21<br/>InProgress 6<br/> Failed 2 <br/> Succeeded 131
> [!IMPORTANT]
> [!重要信息] 如果看到任何失败的迁移，请尽快解决这些问题。在你解决这些问题之前，其他人将无法拨入这些用户组织的会议。有关详细信息，请参阅[出错了应该怎么办？](setting-up-the-meeting-migration-service-mms.md#Troubleshooting)部分。
  
要获取一定时间段内所有迁移的完整详细信息，你可以使用  `StartTime` 和 `EndTime` 参数。例如，运行以下命令会返回 2016 年 10 月 1 日到 2016 年 10 月 8 日之间发生的所有迁移的完整详细信息。
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

你可能也会想要检查特定用户的迁移状态，你可以使用  `UserId` 参数。例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a>出错了应该怎么办？
<a name="Troubleshooting"> </a>

在运行  `Get-CsMeetingMigrationStatus` cmdlet 获取汇总视图时，你发现有的迁移处于 已失败状态，下面列出了你需要执行的操作：
  
1. 确定受影响的用户。运行以下命令获取受影响的用户列表，以及报告的具体错误：
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. 为其中的每个用户运行[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)以手动迁移他们的会议。
    
3. 如果使用会议迁移工具还是无法完成迁移，你有两个选择：
    
  - 让用户创建新的 Skype 会议。
    
  - [联系支持人员](https://go.microsoft.com/fwlink/p/?LinkID=518322)。
    
### <a name="enabling-and-disabling-mms"></a>启用和禁用 MMS
<a name="Troubleshooting"> </a>

所有组织默认均已启用 MMS，但可以根据需要将其禁用。 For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running. 你也可以选择暂时禁用 MMS。 For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.
  
要查看你的组织是否启用了 MMS，请运行以下命令并检查  `MeetingMigrationEnabled` 参数的值。如果此参数设置为$true，则启用了 MMS。
  
```
Get-CsTenantMigrationConfiguration
```

要禁用 MMS，请运行以下命令：
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

要启用 MMS，请运行以下命令：
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Enabling and disabling MMS only for audio conferencing changes
<a name="Troubleshooting"> </a>

You can also disable MMS only for audio conferencing changes. It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online. To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter. If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

To disable MMS for audio conferencing, run the following command:
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

To enable MMS for audio conferencing, run the following command:
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>我如何手动为用户运行会议迁移？
<a name="Troubleshooting"> </a>

除了自动会议迁移之外，你还可以通过运行 cmdlet **Start-CsExMeetingMigration** 手动为用户运行会议迁移。 This cmdlet adds the user in meeting migration queue. 会议迁移服务将读取用户请求并迁移其会议。 你可以通过 cmdlet **Get-CsMeetingMigrationStatus** 检查会议迁移的状态。
  
下面是为用户 ashaw@contoso.com 启动会议迁移的示例：
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a>使用 PowerShell 管理你的 Skype for Business 组织
<a name="WPSInfo"> </a>

 **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
  
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
  
 **启动 Windows PowerShell 会话**
  
1. From the **Start Menu** > **Windows PowerShell**.
    
2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
如果想要深入了解如何启动 Windows PowerShell，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[使用 Windows PowerShell 连接到 Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。
  
- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
