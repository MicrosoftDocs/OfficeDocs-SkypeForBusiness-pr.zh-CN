---
title: "打开或关闭脱机消息（面向管理员）"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
description: "Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell."
---

# 打开或关闭脱机消息（面向管理员）

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
您可以向您的联系人的业务 im 发送 Skype 即使未登录。此功能使您知道您有已尝试与他们联系的联系人。您不需要等待，直至是某人发送邮件之前联机。
  
对于脱机消息，请务必了解：
  
- 脱机消息不会在用户的邮箱中存档。
    
- 脱机消息将发送到用户的邮箱，然后登录到 Skype for Business 时，用户会得到通知。
    
- 如果邮件收件人的状态设置为 **'请勿打扰'**或 **正在演示**，他们将收到错过发送消息，从收件人的 Skype for Business 客户端。
    
有关详细信息，请参阅[在 Skype for Business 中使用脱机消息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。
  
## 开始使用

### 

 **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
  
1. 若要验证运行的是 3.0 版本或更高版本：" **开始菜单**">" **Windows PowerShell**"。
    
2. 通过在" **Windows PowerShell**"窗口中键入  _Get-Host_ 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。
  
### 

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
  
## 打开或关闭脱机即时消息

> [!NOTE]
> 脱机邮件 **仅** 在最新版本的即点即用 Skype for Business 客户端中可用，并使用较旧的即点即用 Skype for Business 或使用 *.msi 文件安装 Skype for Business 客户端时不可用。
  
若要启用或禁用脱机邮件发送脱机邮件为您的组织中的用户，请到 `True`或 `False`设置 _EnableIMAutoArchiving_ 。默认情况下，此设置为 `True`。
  
要将其禁用，请使用 **Set-CsClientPolicy** cmdlet 并运行：
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

若要启用或禁用脱机邮件发送脱机邮件用户，请到 `True`或 `False`设置 _EnableIMAutoArchiving_ 。默认情况下，此设置为 `True`。 您可以使用现有策略或创建类似于下面的示例。
  
> 
  ```
  New-CsClientPolicy -Identity OfflineIM
  ```

> 
  ```
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  ```

> 
  ```
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

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
  

