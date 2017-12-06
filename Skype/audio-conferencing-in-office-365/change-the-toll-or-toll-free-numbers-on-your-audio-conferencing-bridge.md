---
title: "更改收费电话或音频会议网桥上的免费电话号码"
ms.author: tonysmit
author: tonysmit
ms.date: 11/29/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PSTNConferencingRemovePhoneNumberFromBridge
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
description: "当您购买音频会议许可证时，Microsoft 承载您为您的组织的音频会议网桥 。音频会议网桥提供出不同位置的拨入电话号码，因此会议组织者和参与者可以使用它们来使用电话的业务或 Microsoft 小组会议加入 Skype。"
---

# 更改收费电话或音频会议网桥上的免费电话号码

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/6403f6d1-c05a-44ab-a6e0-558000e246f4) 中查找本文的英文版本以便参考。
  
当您购买 **音频会议**许可证时，Microsoft 承载您为您的组织的 *音频会议网桥*  。音频会议网桥提供出不同位置的拨入电话号码，因此会议组织者和参与者可以使用它们来使用电话的业务或 Microsoft 小组会议加入 Skype。
  
除了已分配给会议网桥的电话号码，则可以[获取 Skype for Business 服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)（收费和用于音频会议的免费电话号码） 从其他位置、 然后分配给会议联系以便您可以展开报道为您的用户。
  
> [!NOTE]
> 为能够分配/取消会议网桥的电话号码，电话号码必须是 *服务*  数字。您可以看到的是通过导航到 **语音**的数字类型 > **电话号码**，然后在 **数字类型**列中查找。 > Office 365 通信贷项必须设置拨入网桥上免费电话号码的用户的顺序中的第一个。请参阅[更改收费电话或音频会议网桥上的免费电话号码](6403f6d1-c05a-44ab-a6e0-558000e246f4.md)。 
  
## 将新的服务电话号码分配给会议网桥的操作步骤

### 第 1 步-为您的音频会议网桥分配新的电话号码

1. 使用你的工作帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **管理员中心**> **Skype for Business** > **语音**> **电话号码**。
    
3. 从列表中，并在操作窗格中选择的电话号码，请单击 **分配**。
    
4. 在" **分配**"页面上，单击" **保存**"。
    
    可以为您的会议网桥; 默认号码设置仅服务收费电话号码 **不能服务免费电话号码设置为默认会议网桥的数** 。如果您要分配服务收费电话号码，并且您想要将其设置为新默认号码的音频会议网桥，选择 **使用此号码为默认值**。
    
    > [!NOTE]
    > 被分配了新的电话号码，即使数成为新的默认号码后，不会更改现有用户的默认号码。若要设置默认收费或免费电话号码添加到组织者的会议邀请，请参阅[为会议组织者包含在邀请中设置音频会议电话号码](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)。 
  
### 第 2 步 - 更改用户的会议邀请中包含的默认电话号码（可选）

为用户的默认电话号码是其会议包括的那些邀请时，他们安排会议。有关详细信息，请参阅[为会议组织者包含在邀请中设置音频会议电话号码](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **管理员中心**> **Skype for Business** > **音频会议**> **用户**，然后选择列表中的用户。
    
3. 在"操作"窗格中单击" **编辑**"。
    
4. 在 **默认收费电话号码**或 **默认免费电话号码**下，选择列表中的数字，然后单击 **保存**。
    
在保存所做的更改后，新默认电话号码将包含在会议邀请的下次他们安排新会议组织者。
  
### 第 3 步 - 使用会议迁移服务更新用户的现有会议邀请（可选）

下两个步骤中，您将需要启动 Windows PowerShell。若要查看如何执行此操作，请单击[想知道如何使用 Windows PowerShell 进行管理吗？](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#bk_PowerShell)。
  
使用会议迁移服务，您可以选择更新已更改其默认电话号码之前已发送到您的组织中的用户的会议邀请。其他信息，请参阅[设置会议迁移服务 (MMS)](setting-up-the-meeting-migration-service-mms.md)。
  
- 运行已在步骤 2 中更改其默认电话号码的用户的会议迁移服务 (MMS)。若要执行此操作，请运行以下命令：
    
```
	Start-CsExMeetingMigration user@contoso.com

```

- 你还可以查看会议迁移状态。一旦没有处于 *待处理*  或 *进行中*  状态的操作时，将会重新安排会议。
    
```
	Get-CsMeetingMigrationStatus -SummaryOnly
```

## 取消为会议网桥分配的服务电话号码的操作步骤
<a name="bk_StartPowerShell"> </a>

当您取消会议网桥的电话号码时，用户将无法加入不再使用的电话号码的任何会议。因为更改电话号码，很重要更新可能有电话号码为其默认号码 （如果有） 的所有用户，并都更新现有会议邀请之前的电话号码是未从音频会议网桥分配。
  
如果删除电话号码时没有通知用户及更新其会议，那么他们的现有会议邀请可能包含无法再用于加入其会议的电话号码。
  
前三个步骤，您将需要启动 Windows PowerShell。若要查看如何执行此操作，请单击[想知道如何使用 Windows PowerShell 进行管理吗？](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#bk_PowerShell)。
  
### 第 1 步 - 通知其默认号码之一是要取消分配的电话号码的用户

为其默认号码是要取消分配的号码的用户替换默认的收费或免费号码，并开始重新安排其会议的过程。要执行此操作，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

> [!NOTE]
> 根据组织的规模，这可能需要一段时间才能完成。 
  
您还可以更改默认收费或 Skype for Business 管理中心中的用户的免费电话号码的 **。但是，这不会自动重排其会议** 。其他信息，请参阅[为会议组织者包含在邀请中设置音频会议电话号码](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)。
  
### 第 2 步 - 使用 Windows PowerShell 查看会议迁移状态

没有州 *挂起*  或 *正在进行*  的操作后，将重新安排的所有会议。
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

有关会议迁移服务的详细信息，请参阅[设置会议迁移服务 (MMS)](setting-up-the-meeting-migration-service-mms.md)。
  
### 第 3 步-音频会议网桥取消旧的电话号码

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **管理员中心**> **Skype for Business** > **语音**> **电话号码**。
    
3. 从列表中，并在操作窗格中选择的电话号码，请单击 **取消分配**。
    
4. 在确认窗口中，单击 **是**。
    
> [!IMPORTANT]
> 未从音频会议网桥分配电话号码后，将不再可供用户加入新的或现有会议的电话号码。 
  
## 想知道如何使用 Windows PowerShell 进行管理吗？
<a name="bk_PowerShell"> </a>

### 确认 Windows PowerShell 是否准备就绪

 **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
  
1. 若要验证运行的是 3.0 版本或更高版本：" **开始菜单**">" **Windows PowerShell**"。
    
2. 通过在" **Windows PowerShell**"窗口中键入  _Get-Host_ 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。
  
### 启动 Windows PowerShell

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
  
### 节省时间或自动执行

为节省时间或自动执行此过程，您可以使用[设置 CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688)或 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet。
  
- 使用 [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。
    
  - 若要更改用户的默认免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。
    
    > [!NOTE]
    > 注意：若要查找 BridgeID，请使用 **Get-CsOnlineDialInConferencingBridge** 。
  
  - 若要为没有默认免费电话号码的所有用户将默认免费电话号码设置为 8005551234，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 若要为默认免费电话号码已设置为 8005551234 的所有用户将默认免费电话号码更改为 8005551239，并自动重新安排其会议，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 若要为位于美国的所有用户将默认免费电话号码设置为 8005551234，并自动重新安排其会议，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上面使用的位置信息需要与 Office 365 管理中心中设置的用户联系信息匹配。 
  
### 了解更多信息

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
  

