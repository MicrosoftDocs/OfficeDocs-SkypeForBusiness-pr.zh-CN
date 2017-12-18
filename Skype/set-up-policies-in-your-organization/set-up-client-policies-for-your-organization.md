---
title: "设置为您的组织的客户端策略"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
description: "客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。"
---

# 设置为您的组织的客户端策略

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。
  
客户端策略设置可以配置时创建的策略，也可以使用设置 CsClientPolicy cmdlet 来修改现有策略设置。
  
## 设置你的客户端策略

> [!NOTE]
> 对于所有在 Skype for Business Online 的客户端策略设置，您必须使用 Windows PowerShell 和您 **不能使用** **Skype for Business 管理中心**。 
  
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
    
### 禁用图释和状态通知，并防止保存的即时消息

- 若要创建新的策略，这些设置，请运行：
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

    请参阅有关 [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet 的更多信息。
    
- 若要授予您的组织中创建的所有用户到新的策略，运行：
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

    请参阅有关 [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 的更多信息。
    
如果您已创建的策略，您可以[设置 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet 用于向现有的策略，进行更改，然后使用[授予 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 以对其应用设置您的用户。
  
### 启用要在即时消息中可单击的 URL 或超链接

- 若要创建新的策略，这些设置，请运行：
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

    请参阅有关 [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet 的更多信息。
    
- 若要授予您的组织中创建的所有用户到新的策略，运行：
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

    请参阅有关 [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 的更多信息。
    
如果您已创建的策略，您可以[设置 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet 用于向现有的策略，进行更改，然后使用[授予 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 以对其应用设置您的用户。
  
### 禁止显示最近的联系人

- 若要创建新的策略，这些设置，请运行：
    
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

    请参阅有关 [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet 的更多信息。
    
- 若要创建的新策略授予 Amos 大理石，运行：
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

    请参阅有关 [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 的更多信息。
    
如果您已创建的策略，您可以[设置 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet 用于向现有的策略，进行更改，然后使用[授予 CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet 以对其应用设置您的用户。
  
## 要了解有关 Windows PowerShell 的详细信息？

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
  

