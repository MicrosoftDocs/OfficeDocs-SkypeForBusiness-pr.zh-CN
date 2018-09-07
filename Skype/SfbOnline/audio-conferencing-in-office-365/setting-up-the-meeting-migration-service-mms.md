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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 会议迁移服务 (MMS) 是一项 Skype for Business 服务，它在后台运行，可以自动为用户更新 Skype for Business 和 Microsoft Teams 会议。MMS 旨在使用户无需运行会议迁移工具即可更新其 Skype for Business 和 Microsoft Teams 会议。
ms.openlocfilehash: 562cc616af59ee2fb87b5a2a023c9efe6c3093c3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854312"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>设置会议迁移服务 (MMS)

会议迁移服务 (MMS) 是一项 Skype for Business 服务，它在后台运行，可以自动为用户更新 Skype for Business 和 Microsoft Teams 会议。 MMS 旨在使用户无需运行会议迁移工具即可更新其 Skype for Business 和 Microsoft Teams 会议。  此工具不会将 Skype for Business 会议迁移到 Microsoft Teams 会议。  
  
 **要求**
  
MMS 要求会议组织者使用 Exchange Online 上的邮箱。
  
 **主要场景**
  
MMS 会在下列两种主要场景中为用户更新 Skype 会议：
  
- 用户从本地 Skype for Business Server 迁移到 Skype for Business Online 时。
    
- 当管理员更改用户的音频会议设置（这要求更新该用户会议的音频会议信息）时。
    
 **无法使用 MMS 的一般场景**
  
我们在此处列出了可能适用于你的一般场景。这些场景都支持迁移。但是，MMS 不在这些场景中运行，你需要改为使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。
  
- 用户的邮箱在本地 Exchange Server 上
    
- 使用第三方音频会议提供程序
    
- 将用户从 Skype for Business Online 迁移到本地 Skype Server
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>将本地用户迁移到 Skype for Business Online 时更新会议

这是 MMS 可以帮助你的用户顺利转换的最常见的场景。 当用户从本地 Skype for Business Server 迁移到 Skype for Business Online 时，MMS 会检测新用户并扫描该用户的 Skype for Business 和 Microsoft Teams 会议日历。 所有未来会议都将用该用户的新信息更新。
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>如果你当前正在使用 Skype Server 2015 进行音频会议

我们建议你在此场景中遵循下面最佳做法以获得使用 MMS 的最佳体验：
  
- 由于 MMS 要求用户使用 Exchange Online 上的邮箱，如果你也将迁离本地 Exchange Server，请先将用户的邮箱迁移至 Exchange Online。
    
- 分配**音频会议**许可证给用户，然后运行 `Move-CSUser` cmdlet 来迁移用户。 这是因为当更改用户的音频会议设置后，MMS 也将更新会议。 如果你没有事先分配许可证，则 MMS 将在你分配许可证时再次更新所有会议。
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>如果你当前正在使用第三方音频会议提供程序 (ACP)

使用第三方 ACP 时， MMS 运行与否取决于你的组织的音频会议设置。 当为用户分配**音频会议**许可证时，你可以选择自动替换 ACP 提供的拨入号码。 另一方面，你可能需要防止自动替换发生，并保留 ACP 提供的拨入号码。 要查看组织的设置，请运行以下 Windows PowerShell 命令并检查 `AutomaticallyReplaceAcpProvider` 参数的值。 如果需要有关 PowerShell 的帮助，请参阅本文结尾处的[使用 PowerShell 管理你的 Skype for Business 组织](setting-up-the-meeting-migration-service-mms.md#WPSInfo)部分。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- 如果该参数的值为 $true，则当用户分配到**音频会议**许可证时，MMS 将会运行并更新他们的会议。 在分配**音频会议**许可证之前，你的 ACP 提供的拨入号码会被保留。
    
- 如果该参数的值为 $false，则即使用户分配到**音频会议**许可证，MMS 也不会更新会议。 你的 ACP 提供的拨入号码会一直保留，直到用户在 Skype for Business 管理中心或使用 Windows PowerShell 手动配置了音频会议。
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>当用户的音频会议设置发生更改时更新会议

在下列情况下，MMS 会更新现有 Skype for Business 和 Microsoft Teams 会议：
  
- 当你分配或删除**音频会议**许可证时。
    
- 当你启用或禁用音频会议时。
    
- 当你更改或重置用户配置的会议 ID 以使用公开会议时。
    
- 当你将用户移动到新的音频会议网桥时。
    
- 当从音频会议网桥取消分配某个电话号码时。 这是一个复杂的场景，需要执行其他步骤。 有关详细信息，请参阅[更改用于音频会议网桥的收费或免费号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。
    
> [!IMPORTANT]
> MMS 仅当你正使用 Microsoft 网桥时才更新会议。 如果你正使用第三方音频会议提供程序，则用户将需要手动更新其会议。 在这种情况下，你可以使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。 
  
并不是对用户音频会议设置的更改都会触发 MMS。 具体而言，下列两种更改不会使 MMS 更新会议：
  
- 当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时
    
- 当你使用 [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) 命令更改你的组织的会议 URL 时。
    
## <a name="what-happens-when-mms-updates-meetings"></a>MMS 更新会议时会发生什么？

当 MMS 检测到用户的会议需要更新时，它会执行以下操作：
  
1. 确定用户已安排在将来的所有 Skype for Business 和 Microsoft Teams 会议
    
  - 将跳过发生在 MMS 运行之前的任何 Skype for Business 或 Microsoft Teams 会议
    
  - 仅更新用户为组织者的会议
    
2. 替换会议详情中的联机会议信息块
    
3. 代表会议组织者将更新发送给会议所有的收件人
    
 **MMS 运行需要多长时间？**
  
MMS 迁移会议所需要的时间不等，具体取决于受影响的用户数以及每个用户日历上的 Skype for Business 或 Microsoft Teams 会议总数。 运行至少需要 10 分钟。 一些大型迁移需要的时间可能长达 12 小时，大多数迁移应该可以在 1 小时内完成。
  
 **限制和潜在问题**
  
- 只会迁移通过单击 Outlook 网页版中的**添加 Skype 会议**按钮或使用 Outlook 的 Skype 会议外接程序来安排的 Skype for Business 或 Microsoft Teams 会议。 换言之，如果用户将一个会议中的 Skype 联机会议信息复制并粘贴到另一个新会议中，该新会议不会更新。
    
- MMS 在迁移会议时会替换联机会议信息块中的所有内容。因此，如果用户编辑了信息块，它们的更改会被覆盖。用户拥有的所有联机会议信息块以外的内容不会受到影响。
    
     ![由 MMS 更新的会议块](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- 在 MMS 运行后，所有之前创建的或附加到会议的会议内容（白板、投票等）将不会保留。如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。
    
- 日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。请注意，存储在 OneNote 中的实际会议笔记会被保留，只会覆盖共享笔记的链接。
    
- 与会者超过 250（包括组织者）的会议不会迁移。
    
- 邀请正文中的一些 UNICODE 字符可能会被错误地更新为以下特殊字符之一：ï、¿、½、�。
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>MMS 更新会议时用户将看见什么？

MMS 会像会议迁移工具一样代表用户发送会议更新。 因此，你的用户将看见的唯一东西是其会议的另一轮会议接受通知。 这可能会让用户混乱，因此我们建议你提前通知用户，不管是当你将他们从本地迁移到 Skype for Business Online，还是当你进行会触发 MMS 的音频会议更改时。
  
## <a name="managing-mms"></a>管理 MMS

你需要使用 Windows PowerShell 管理 MMS 并检查进行中的迁移的状态。 本部分信息假设你对使用 PowerShell 管理你的 Skype for Business 组织很熟悉。 如果你不熟悉 PowerShell，请参阅本文结尾处的[使用 PowerShell 管理你的 Skype for Business 组织](setting-up-the-meeting-migration-service-mms.md#WPSInfo)部分。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>我该如何检查会议迁移的状态？

你可以使用  `Get-CsMeetingMigrationStatus` cmdlet 检查会议迁移的状态。下面列出了一些示例。
  
要获取所有 MMS 迁移的汇总状态，请运行以下命令：
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

这将使你看见所有迁移状态的表格视图，如下所示：
  
状态 用户计数--<br/> 挂起 21<br/>正在进行 6<br/> 失败的 2 <br/> 成功的 131
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

所有组织均默认启用 MMS，但可以根据需要将其禁用。 例如，如果你想要手动迁移所有会议或使用第三方音频会议提供程序，你可能不需要运行 MMS。 你还可以选择暂时禁用 MMS。 例如，你要对你的组织的音频会议设置执行大量更改，且在完成所有更改前你不希望 MMS 运行。
  
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

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>启用和禁用 MMS 仅用于音频会议的更改
<a name="Troubleshooting"> </a>

您还可以仅禁用 MMS 以更改音频会议。 将用户从本地 Skype for Business 迁移到 Skype for Business Online 时，MMS 仍会运行。 要为音频会议更新检查 MMS 的当前状态，请运行以下命令并检查 `AutomaticallyMigrateUserMeetings` 参数的值。 如果此参数设置为 $true，则 MMS 会设置为当音频会议设置发生更改时更新用户会议。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

若要为音频会议禁用 MMS，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

若要为音频会议启用 MMS，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>我该如何为用户手动运行会议迁移？
<a name="Troubleshooting"> </a>

除了自动会议迁移之外，你还可以通过运行 cmdlet **Start-CsExMeetingMigration** 为用户手动运行会议迁移。 此 cmdlet 将用户添加到会议迁移队列中。 会议迁移服务将读取用户请求并迁移其会议。 你可以通过 cmdlet **Get-CsMeetingMigrationStatus** 检查会议迁移的状态。
  
下面是为用户 ashaw@contoso.com 启动会议迁移的示例：
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a>使用 PowerShell 管理你的 Skype for Business 组织
<a name="WPSInfo"> </a>

 **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
  
1. 若要验证正在运行的版本是 3.0 或更高：**开始菜单** > **Windows PowerShell**。
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
  
 **启动 Windows PowerShell 会话**
  
1. 从 **开始菜单** > **Windows PowerShell**。
    
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
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
