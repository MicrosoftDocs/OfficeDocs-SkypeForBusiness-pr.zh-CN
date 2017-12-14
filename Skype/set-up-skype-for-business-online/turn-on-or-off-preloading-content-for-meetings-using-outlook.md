---
title: "打开或关闭允许使用 Outlook 为会议预加载内容"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
description: "See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. "
---

# 打开或关闭允许使用 Outlook 为会议预加载内容

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](d217d422-f7e9-433d-ad24-bf41751f65ca.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/d217d422-f7e9-433d-ad24-bf41751f65ca) 中查找本文的英文版本以便参考。
  
用户可以预加载的内容、 文件或附加到 Skype for Business Online 会议，Outlook 会议邀请的附件，但您可以将其打开或关闭。默认情况下，所有组织所使用的 Skype for Business Online，它处于打开状态。请参阅如何[为 Skype for Business 会议预加载附件](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。
  
> [!NOTE]
> 目前，没有 cmdlet 中有 Skype for Business Online 设置或查看 _MaxContentStorageMB_和 _MaxUploadFileMB_联机值。它们只是可用于本地部署。请务必了解如果的附加的内容超过 _MaxUploadFileSizeMB_或 _MaxContentStorageMB_达到该内容将不会上载到会议。 
  
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
  
## 打开或关闭该功能

默认情况下，能够预加载附加到 Outlook 会议邀请给 Skype for Business Online 会议内容已打开，但您可能需要防止用户在您的组织从预加载其会议中的内容。
  
> [!IMPORTANT]
> 此设置可以仅打开或关闭您的整个组织;您不能为一位用户可以将其打开或关闭。 
  
 **若要将其关闭，请打开 Windows PowerShell 并执行下列操作：**
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **如果想要将其重新打开，请打开 Windows PowerShell 并执行下列操作：**
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
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
  

