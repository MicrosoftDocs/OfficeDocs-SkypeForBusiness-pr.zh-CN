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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 会议迁移服务 (MMS) 是在后台运行，并为用户的业务和 Microsoft 团队会议将自动更新 Skype 业务服务 Skype。 MMS 旨在消除用户运行会议迁移工具需要更新其 Skype 业务和 Microsoft 团队的会议。
ms.openlocfilehash: ab2aa3925ff1313798431e8f7bdec525074d2501
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885208"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>设置会议迁移服务 (MMS)

会议迁移服务 (MMS) 是在后台运行，并为用户的业务和 Microsoft 团队会议将自动更新 Skype 业务服务 Skype。 MMS 旨在消除用户运行会议迁移工具需要更新其 Skype 业务和 Microsoft 团队的会议。  此工具不会将 Skype for Business 会议迁移到 Microsoft Teams 会议。  
  
 **要求**
  
MMS 要求会议组织者使用 Exchange Online 上的邮箱。
  
 **主要场景**
  
MMS 会在下列两种主要场景中为用户更新 Skype 会议：
  
- 当用户迁移从内部部署 Skype 业务服务器到 Skype 业务 online。
    
- 当管理员对需要更新中该用户的会议的音频会议信息的用户的音频会议设置进行了更改。
    
 **无法使用 MMS 的一般场景**
  
我们在此处列出了可能适用于你的一般场景。这些场景都支持迁移。但是，MMS 不在这些场景中运行，你需要改为使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。
  
- 用户的邮箱在本地 Exchange Server 上
    
- 使用第三方音频会议提供商
    
- 从业务 online Skype 到内部部署 Skype 服务器的迁移用户
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>将本地用户迁移至 Skype for Business Online 时更新会议

这是 MMS 可以帮助你的用户顺利过渡的最常见的场景。 当用户迁移时从内部部署 Skype 业务服务器到 Skype 业务 online 时，MMS 将检测新用户，并将扫描该用户的日历 Skype 业务和 Microsoft 团队的会议。 任何将来会议将与该用户的新信息进行了更新。
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>如果当前使用的音频会议的 Skype 服务器 2015

我们建议你在此场景中使用 MMS 时遵循下列最佳做法以获得最佳体验：
  
- 由于 MMS 要求用户使用 Exchange Online 上的邮箱，如果你也将迁离本地 Exchange Server，请先将用户的邮箱迁移至 Exchange Online。
    
- 运行之前，向用户分配**音频会议**许可`Move-CSUser`cmdlet 以将用户迁移。 这是因为 MMS 也会更新会议时音频会议设置的更改的用户。 如果你没有先分配许可证，在你分配许可证后 MMS 会再次更新所有会议。
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>如果你当前使用的是第三方音频会议提供商 (ACP)

与第三方 ACP，MMS 运行取决于组织的音频会议设置。 您可以选择自动替换从您的 ACP 的电话拨入式号码，当您向用户分配**音频会议**许可证。 另一方面，你可能需要阻止自动替换发生，保留你的 ACP 提供的拨入号码。 若要查看您的组织的设置，请运行以下 Windows PowerShell 命令并检查参数的值`AutomaticallyReplaceAcpProvider`。 如果需要有关 PowerShell 的帮助，请参阅本文结尾处的[使用 PowerShell 管理你的 Skype for Business 组织](setting-up-the-meeting-migration-service-mms.md#WPSInfo)部分。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- 如果此参数的值，$true MMS 将运行时为用户分配**音频会议**许可和更新其会议。 直到指定的**音频会议**许可证，将会保留从您的 ACP 的电话拨入式号码。
    
- 如果此参数的值，$false MMS 不会更新会议，即使为用户分配**音频会议**许可。 从您的 ACP 的电话拨入式号码将保留，直到用户手动设置为在 Skype 业务管理中心或使用 Windows PowerShell 的音频会议。
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>更新会议用户的音频会议设置更改时

MMS 会更新现有 Skype 业务和 Microsoft 团队会议在出现以下情况：
  
- 当您分配或删除**音频会议**许可证。
    
- 当您启用或禁用音频会议。
    
- 当您更改或重置用户配置为使用公开会议的会议 ID。
    
- 当您将用户移动到新的音频会议桥。
    
- 电话号码时从音频会议网桥未分配。 这个场景比较复杂，需要执行其他步骤。 有关详细信息，请参阅[更改的收费电话或音频会议网桥上的免费电话号码](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。
    
> [!IMPORTANT]
> [!重要信息] 仅当你使用的是 Microsoft 网桥时 MMS 才会更新会议。 如果您使用第三方音频会议提供商，用户将需要更新他们的会议手动。 在这种情况下，你可以使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。 
  
并非所有更改用户的音频会议设置都触发 MMS。 具体地说，下列两种更改不会使 MMS 更新会议：
  
- 当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时
    
- 当你使用 [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) 命令更改你的组织的会议 URL 时。
    
## <a name="what-happens-when-mms-updates-meetings"></a>MMS 更新会议时会发生什么？

当 MMS 检测到用户的会议需要更新时，它会执行以下操作：
  
1. 确定业务和 Microsoft 团队的会议用户已安排在将来的所有 Skype
    
  - 不跳过任何 Skype MMS 运行时出现到其正前方的业务或 Microsoft 团队会议
    
  - 仅会更新该用户为组织者的会议
    
2. 替换会议详情中的联机会议信息块
    
3. 代表会议组织者将更新发送给会议所有的收件人
    
 **MMS 运行需要多长时间？**
  
MMS 迁移会议花费的时间量有所不同，具体取决于多少用户会受到影响，和 Skype 的每个用户对他们的日历的业务或 Microsoft 团队会议的总数。 运行至少需要 10 分钟。 一些大型迁移需要的时间可能长达 12 小时，大多数迁移应该可以在 1 小时内完成。
  
 **限制和潜在问题**
  
- 仅 Skype 业务或 Microsoft 团队通过单击**添加 Skype 会议**按钮在 Web 上的 Outlook 或 outlook 使用 Skype Meeting 外接程序安排的会议都将迁移。 换言之，如果用户将一个会议中的 Skype 联机会议信息复制并粘贴到另一个新会议中，该新会议不会更新。
    
- MMS 在迁移会议时会替换联机会议信息块中的所有内容。因此，如果用户编辑了信息块，它们的更改会被覆盖。用户拥有的所有联机会议信息块以外的内容不会受到影响。
    
     ![由 MMS 更新的会议块](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- 在 MMS 运行后，所有之前创建的或附加到会议的会议内容（白板、投票等）将不会保留。如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。
    
- 日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。请注意，存储在 OneNote 中的实际会议笔记会被保留，只会覆盖共享笔记的链接。
    
- 与会者超过 250（包括组织者）的会议不会迁移。
    
- 邀请正文中的一些 UNICODE 字符可能会被错误地更新为以下特殊字符之一：ï、¿、½、�。
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>MMS 更新会议时用户会为用户显示什么？

MMS 会像会议迁移工具一样代表用户发送会议更新。 因此，只会再次向用户显示其会议的会议接受通知。 这可能是令人费解的用户，因此我们建议您事先不仅时您迁移它们从内部部署到 Skype 业务联机状态，但当您更改音频会议，也将触发 MMS 通知用户。
  
## <a name="managing-mms"></a>管理 MMS

您需要使用 Windows PowerShell 管理 MMS 和检查持续迁移的状态。 本部分信息的前提是你了解如何使用 PowerShell 管理你的 Skype for Business 组织。 如果您是新手 PowerShell，请参阅本文末尾[使用 PowerShell 管理 Business 组织您 Skype](setting-up-the-meeting-migration-service-mms.md#WPSInfo)节。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>我应该如何检查会议迁移的状态？

你可以使用  `Get-CsMeetingMigrationStatus` cmdlet 检查会议迁移的状态。下面列出了一些示例。
  
要获取所有 MMS 迁移的汇总状态，请运行以下命令：
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

这样会显示所有迁移状态的表格视图，如下所示：
  
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

所有组织默认均已启用 MMS，但可以根据需要将其禁用。 例如，如果您想要手动将迁移所有会议或使用第三方音频会议提供商，您可能不需要 MMS 运行。 你也可以选择暂时禁用 MMS。 例如，您可能要执行大量更改到音频会议设置为您的组织，并且您无需 MMS 运行，直到完成所有更改。
  
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

您还可以仅用于音频会议更改禁用 MMS。 用户迁移从 Skype 业务本地到 Skype 业务 online 时，它将仍运行。 要检查音频会议更新的当前 MMS 状态，请运行以下命令，并检查的值`AutomaticallyMigrateUserMeetings`参数。 如果此参数设置为 $true，将设置 MMS 时音频会议设置的更改更新用户会议。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

若要禁用 MMS 为音频会议，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

若要启用 MMS 为音频会议，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>我如何手动为用户运行会议迁移？
<a name="Troubleshooting"> </a>

除了自动会议迁移之外，你还可以通过运行 cmdlet **Start-CsExMeetingMigration** 手动为用户运行会议迁移。 此 cmdlet 将用户添加会议迁移队列中。 会议迁移服务将读取用户请求并迁移其会议。 你可以通过 cmdlet **Get-CsMeetingMigrationStatus** 检查会议迁移的状态。
  
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
