---
title: "设置会议迁移服务 (MMS)"
ms.author: tonysmit
author: tonysmit
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
description: "会议迁移服务 (MMS) 是 Skype for Business 服务，在后台运行并自动更新的业务 Microsoft 小组会议的用户的 Skype。MMS 设计，从而消除了用户运行会议迁移工具时需要更新其 Skype for Business 和 Microsoft 小组会议。"
---

# 设置会议迁移服务 (MMS)

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/031f09c0-9d2a-487a-b6db-b5d4bed6d16a) 中查找本文的英文版本以便参考。
  
会议迁移服务 (MMS) 是 Skype for Business 服务，在后台运行并自动更新的业务 Microsoft 小组会议的用户的 Skype。MMS 设计，从而消除了用户运行会议迁移工具时需要更新其 Skype for Business 和 Microsoft 小组会议。
  
 **要求**
  
MMS 要求会议组织者使用 Exchange Online 上的邮箱。
  
 **主要场景**
  
MMS 会在下列两种主要场景中为用户更新 Skype 会议：
  
- 当用户从迁移本地 Skype for Business Server 到 Skype for Business Online。
    
- 当管理员进行了更改用户的音频会议设置，将要求您更新该用户的会议中的音频会议信息。
    
 **无法使用 MMS 的一般场景**
  
我们在此处列出了可能适用于你的一般场景。这些场景都支持迁移。但是，MMS 不在这些场景中运行，你需要改为使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。
  
- 用户的邮箱在本地 Exchange Server 上
    
- 使用第三方音频会议提供商
    
- 将用户从 Skype for Business Online 迁移到内部部署 Skype 服务器
    
## 将本地用户迁移至 Skype for Business Online 时更新会议

这是最常见的方案位置 MMS 可帮助创建更顺利过渡为您的用户。当迁移用户从内部部署 Skype for Business Server 到 Skype for Business Online 时，MMS 将检测到的新用户，并且将扫描该用户的日历 Skype for Business 和 Microsoft 小组会议。将与该用户的新信息更新任何将来的会议。
  
### 如果您目前正在使用 Skype Server 2015 音频会议

我们建议你在此场景中使用 MMS 时遵循下列最佳做法以获得最佳体验：
  
- 由于 MMS 要求用户使用 Exchange Online 上的邮箱，如果你也将迁离本地 Exchange Server，请先将用户的邮箱迁移至 Exchange Online。
    
- 将 **音频会议**许可证分配给用户之前运行 `Move-CSUser` cmdlet 迁移用户。这是因为 MMS 也会更新会议时音频会议设置的更改的用户。如果您没有首先将许可证分配，MMS 将更新的所有会议重新分配许可证时。
    
### 如果你当前使用的是第三方音频会议提供商 (ACP)

与第三方 ACP，MMS 运行取决于您的组织的音频会议设置。您可以选择 **音频会议**许可证分配用户时自动替换您 ACP 拨入号码。另一方面，您可能需要防止发生并保留您 ACP 拨入号码。要查看您的组织的设置，请运行以下 Windows PowerShell 命令，然后检查 `AutomaticallyReplaceAcpProvider`参数的值。如果您需要使用 PowerShell 帮助，请参阅本文末尾处的[使用 PowerShell 管理你的 Skype for Business 组织](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo)一节。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- 如果此参数的值， $trueMMS 将为用户分配 **音频会议**许可证时运行和更新他们的会议。从您 ACP 拨入号码将保留，直到 **音频会议**许可证分配。
    
- 如果此参数的值是$false，MMS 不会更新的会议，即使在为用户分配了 **音频会议**许可证。从您 ACP 拨入号码将保留，直到用户手动设置为在 Skype for Business 管理中心或使用 Windows PowerShell 的音频会议。
    
## 当用户的音频会议设置更改更新会议

MMS 将更新现有 Skype 的业务和 Microsoft 小组会议在以下情况：
  
- 当您分配或删除 **音频会议**许可证。
    
- 当您启用或禁用音频会议。
    
- 当您更改或重置用户配置为使用公共会议会议 ID。
    
- 当您将用户移动到新的音频会议网桥。
    
- 电话号码时未从音频会议网桥分配。这是一个复杂情形这需要额外步骤。有关详细信息，请参阅[更改收费电话或音频会议网桥上的免费电话号码](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md)。
    
> [!IMPORTANT]
> 当您使用的 Microsoft 网桥，MMS 只更新的会议。如果您正在使用第三方音频会议提供商，用户需要更新其会议手动。在此例中，您可以使用[会议迁移工具](https://go.microsoft.com/fwlink/p/?linkid=626047)。 
  
对用户的音频会议设置的不是所有更改都触发 MMS。具体而言，以下两项更改不会导致 MMS 更新会议：
  
- 当你更改会议组织者的 SIP 地址（其 SIP 用户名或 SIP 域）时
    
- 当你使用 [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) 命令更改你的组织的会议 URL 时。
    
## MMS 更新会议时会发生什么？

当 MMS 检测到用户的会议需要更新时，它会执行以下操作：
  
1. 识别所有 Skype for Business 和 Microsoft 团队用户具有计划在将来的会议
    
  - 跳过业务或 Microsoft 小组会议时所发生之前 MMS 运行的任何 Skype
    
  - 仅会更新该用户为组织者的会议
    
2. 替换会议详情中的联机会议信息块
    
3. 代表会议组织者将更新发送给会议所有的收件人
    
 **MMS 运行需要多长时间？**
  
一段时间花费的 MMS 迁移会议因多少位用户的影响，并具有其日历上的每个用户的业务或 Microsoft 小组会议 Skype 的总数。至少需要 10 分钟运行。某些大型迁移可能需要多达 12 小时，同时大多数迁移应完成 1 小时内。
  
 **限制和潜在问题**
  
- 仅为业务或 Microsoft 团队通过单击在 Outlook 网页版中的 **添加 Skype 会议**按钮或 Skype 会议加载项中使用 outlook 的计划的会议 Skype 迁移。换言之，如果用户将复制和粘贴到新的会议的 Skype 联机会议信息从一次会议时，该新的会议不会更新。
    
- MMS 在迁移会议时会替换联机会议信息块中的所有内容。因此，如果用户编辑了信息块，它们的更改会被覆盖。用户拥有的所有联机会议信息块以外的内容不会受到影响。
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- 在 MMS 运行后，所有之前创建的或附加到会议的会议内容（白板、投票等）将不会保留。如果你的会议组织者提前对会议附加了内容，在 MMS 运行之后需要重新创建该内容。
    
- 日历项以及 Skype 会议中共享会议笔记的链接也会被覆盖。请注意，存储在 OneNote 中的实际会议笔记会被保留，只会覆盖共享笔记的链接。
    
- 与会者超过 250（包括组织者）的会议不会迁移。
    
- 邀请正文中的一些 UNICODE 字符可能会被错误地更新为以下特殊字符之一：ï、¿、½、�。
    
### MMS 更新会议时用户会为用户显示什么？

会议迁移工具时，就像 MMS 发送会议更新代表用户。因此，的唯一您的用户将看到的是另一轮会议接受通知他们的会议。这可能是混乱的用户，以便我们建议您提前不仅当您将它们迁移从内部部署到 Skype for Business Online，但当您更改音频会议，也会触发 MMS 通知您的用户。
  
## 管理 MMS

你需要使用 Windows PowerShell 管理 MMS 并检查进行中的迁移的状态。本部分信息的前提是你了解如何使用 PowerShell 管理你的 Skype for Business 组织。如果你不了解如何使用 PowerShell，请参阅本文结尾处的[使用 PowerShell 管理你的 Skype for Business 组织](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo)部分。
  
### 我应该如何检查会议迁移的状态？

你可以使用  `Get-CsMeetingMigrationStatus` cmdlet 检查会议迁移的状态。下面列出了一些示例。
  
要获取所有 MMS 迁移的汇总状态，请运行以下命令：
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

这样会显示所有迁移状态的表格视图，如下所示：
  
状态 用户数----- ---------待处理 21进行中 6已失败 2已成功 131
> [!IMPORTANT]
> 如果看到任何失败的迁移，请尽快解决这些问题。在你解决这些问题之前，其他人将无法拨入这些用户组织的会议。有关详细信息，请参阅[出错了应该怎么办？](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#Troubleshooting)部分。 
  
要获取一定时间段内所有迁移的完整详细信息，你可以使用  `StartTime` 和 `EndTime` 参数。例如，运行以下命令会返回 2016 年 10 月 1 日到 2016 年 10 月 8 日之间发生的所有迁移的完整详细信息。
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

你可能也会想要检查特定用户的迁移状态，你可以使用  `UserId` 参数。例如，运行以下命令会返回用户 ashaw@contoso.com 的状态：
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### 出错了应该怎么办？
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
    
### 启用和禁用 MMS
<a name="Troubleshooting"> </a>

MMS 启用默认情况下，所有组织，但可以根据需要将禁用。例如，如果您想要手动迁移所有会议，或者使用第三方音频会议提供商，您可能不需要 MMS 运行。您也可以选择暂时禁用 MMS。例如，您可能进行重大更改的音频会议设置为您的组织，并且不希望 MMS 运行，直到所有更改都已都完成。
  
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

### 启用和禁用 MMS 仅对音频会议的更改
<a name="Troubleshooting"> </a>

仅对音频会议的更改，您还可以禁用 MMS。迁移用户从 Skype for Business 本地到 Skype for Business Online 时，它将仍运行。若要检查的音频会议更新的当前 MMS 状态，请运行以下命令，并检查 `AutomaticallyMigrateUserMeetings`参数的值。如果此参数设置为$true，MMS 设置时音频会议设置的更改更新用户的会议。
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

若要禁用 MMS 的音频会议，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

若要启用 MMS 的音频会议，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### 我如何手动为用户运行会议迁移？
<a name="Troubleshooting"> </a>

除了自动会议迁移中，您还可以通过运行 cmdlet **Start-CsExMeetingMigration** 运行用户手动将会议迁移。此 cmdlet 会议迁移队列中添加用户。会议迁移服务将读取用户请求和迁移他们的会议。您可以检查会议 cmdlet **Get-CsMeetingMigrationStatus** 迁移的状态。
  
下面是为用户 ashaw@contoso.com 启动会议迁移的示例：
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## 使用 PowerShell 管理你的 Skype for Business 组织
<a name="WPSInfo"> </a>

 **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
  
1. 若要验证运行的是 3.0 版本或更高版本：" **开始菜单**">" **Windows PowerShell**"。
    
2. 通过在" **Windows PowerShell**"窗口中键入  _Get-Host_ 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。
  
 **启动 Windows PowerShell 会话**
  
1. 从" **开始菜单**">" **Windows PowerShell**"。
    
2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
    > [!NOTE]
    > 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

如果想要深入了解如何启动 Windows PowerShell，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[使用 Windows PowerShell 连接到 Skype for Business Online](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)。
  
- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

