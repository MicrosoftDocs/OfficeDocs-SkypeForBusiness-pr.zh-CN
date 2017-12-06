---
title: "为用户设置来电显示"
ms.author: tonysmit
author: tonysmit
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
description: "在 Office 365 中电话系统提供的用户分配的电话号码的默认呼叫者 ID。您可以更改，或为用户阻止呼叫方 ID （也称为呼叫行 ID）。您可以了解有关如何使用您的组织中的呼叫方 ID，通过转如何在你的组织中使用来电显示。"
---

# 为用户设置来电显示

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](c7323490-d9b7-421a-aa76-5bd485f80583.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/c7323490-d9b7-421a-aa76-5bd485f80583) 中查找本文的英文版本以便参考。
  
在 Office 365 中电话系统提供的用户分配的电话号码的默认呼叫者 ID。您可以更改，或为用户阻止呼叫方 ID （也称为呼叫行 ID）。您可以了解有关如何使用您的组织中的呼叫方 ID，通过转[如何在你的组织中使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。
  
> [!TIP]
> 您不能阻止 for Business Online 的 Skype 中当前的传入呼叫。 
  
你可以更改以下设置：
  
> [!NOTE]
> 这一点 **不适用于** 使用 Lync 或 Skype for Business Server 的内部部署组织。
  
- **更改其传出来电显示** 你可以用其他电话号码替换用户的来电显示（默认情况下，显示的是用户的电话号码）。例如，你可以将用户的来电显示从其电话号码改为企业的主要电话号码，或者将用户的主叫号码从其电话号码改为法律部门的主要电话号码。你可以将来电显示号码改为任何在线 **服务** 号码（收费或免费）。
    
    > [!NOTE]
    > 如果要使用  _Service_ 参数，必须指定有效的服务号码。
  
- **阻止他们的出站呼叫者 ID** 您可以阻止用户传出 PSTN 呼叫在发送传出呼叫者 ID。执行此操作将阻止从被称为人员的电话上显示其电话号码。
    
- **阻止其传入的呼叫者 ID** 您可以阻止用户从任何传入 PSTN 呼叫接收呼叫者 ID。
    
> [!IMPORTANT]
> 紧急呼叫始终发送用户的电话号码（来电显示号码）。 
  
默认情况下，所有这些来电显示设置都为 **关闭** 状态。这表示当 Skype for Business Online 用户呼叫某个 PSTN 电话时，将显示该用户的电话号码。
  
要了解有关这些设置以及如何使用它们的详细信息，请访问[如何在你的组织中使用来电显示](how-can-caller-id-be-used-in-your-organization.md)。
  
## 设置你的来电显示策略设置

> [!NOTE]
> 对于所有Skype for Business Online中的呼叫者 ID 设置，您必须都使用 Windows PowerShell 和您都 **不能都使用** **Skype for Business 管理中心**。 
  
### 验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. 若要验证运行的是 3.0 版本或更高版本：" **开始菜单**">" **Windows PowerShell**"。
    
2. 通过在" **Windows PowerShell**"窗口中键入  _Get-Host_ 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
    如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。
    
- **启动 Windows PowerShell 会话**
    
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
    
### 查看你组织中的所有来电显示策略设置

- 若要查看您的组织中的所有呼叫者 ID 策略设置，请运行：
    
  - 
  ```
  Get-CsCallingLineIdentity |fl
  ```

    [获取 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx)，请参阅详细示例和详细信息。
    
### 为你的组织创建新的来电显示策略

- 若要创建新的呼叫者 ID 策略设置为匿名的呼叫方 ID，请运行：
    
  - 
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

    [新建 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)，请参阅详细示例和详细信息。
    
- 若要将新创建的策略应用于 Amos 大理石，运行：
    
  - 
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```

    请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 的更多信息。
    
如果您已创建的策略，您可以[设置 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet 用于向现有的策略，进行更改，然后使用[授予 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 以应用您的用户设置。
  
### 对其进行设置以阻止传入来电显示

- 若要阻止传入的呼叫方 ID，请运行：
    
  - 
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```

    请参阅[设置 CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)更多示例和详细信息。
    
- 若要将您创建的策略设置应用于您的组织中的用户，请运行：
    
  - 
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```

    请参阅有关 [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet 的更多信息。
    
### 删除来电显示策略

要删除组织的策略，请运行：
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```

要删除用户的策略，请运行：
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```

## 要了解有关 Windows PowerShell 的详细信息？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 相关主题

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)
  
[音频会议免费拨出时间段](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

