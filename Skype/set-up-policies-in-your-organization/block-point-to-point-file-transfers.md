---
title: "阻止点对点文件传输"
ms.author: tonysmit
author: tonysmit
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
description: "在 Skype for Business Online，必须为现有会议策略设置一部分的控件点对点 (P2P) 文件传输的能力。但是，这使或块文件传输他们将文件传输到同一个组织中的用户或联盟用户从另一个组织的用户。按照下列步骤操作，您可以阻止与联合的组织或合作伙伴的 P2P 文件传输。"
---

# 阻止点对点文件传输

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
在 Skype for Business Online，必须为现有会议策略设置一部分的控件点对点 (P2P) 文件传输的能力。但是，这使或块文件传输他们将文件传输到同一个组织中的用户或联盟用户从另一个组织的用户。按照下列步骤操作，您可以阻止与联合的组织或合作伙伴的 P2P 文件传输。
  
您希望允许使用 P2P 文件传输，但与联盟伙伴阻止文件传输到内部用户时的常见方案。此方案中，您将需要执行：
  
- 将会议策略启用 P2P 文件传输 ( _EnableP2PFileTransfer_设置为 _True_) 与分配给您的组织中的用户。
    
- 创建 aglobal 外部用户的通信策略设置为阻止外部 P2P 文件传输 （  _False_到 _EnableP2PFileTransfer_设置），并将其分配给您的组织中的用户。
    
您可以了解有关这些设置[下面](https://technet.microsoft.com/en-us/library/mt228132.aspx)的详细信息。
  
如果您的组织外部的联合的用户尝试向用户发送文件的策略应用位置，他们将收到 **传输失败**的错误。然后，如果用户尝试发送文件，他们将收到的 **文件传输处于关闭状态**的错误。
  
若要完成此操作，请用户必须使用受支持的版本的 2016年点即用 Skype for Business 应用程序的支持。下面的最小版本的 Skype for Business 2016 点即用客户端是必需的：
  
|**类型**|**发布日期**|**版本**|**内部版本**|
|:-----|:-----|:-----|:-----|
|当前频道的首次发布  <br/> |2016 年 11/17  <br/> |16.0.7571.2006  <br/> |版本 1611 （构建 7571.2006）  <br/> |
|当前频道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> | 版本 1611（内部版本 7571.2072） <br/> |
|延期频道  <br/> |2017-2/22  <br/> |16.0.7369.2118  <br/> |版本 1609 （构建 7369.2118）  <br/> |
   
> [!CAUTION]
> 使用较旧版本的 Skype for Business Windows 应用程序或 Mac 客户端的用户仍然无法传输文件。 
  
## 验证并启动 Windows PowerShell

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
    
## 禁用为您的组织的 P2P 文件传输

默认情况下，对公司的全局策略启用了 _EnableP2PFileTransfer_ 。当创建它时，您的用户分配给 _BposSAllModality_ 策略。
  
> 若要允许为您的组织，但阻止的外部的文件传输到另一个组织内的 P2P 传输，只需将其更改全局级别。若要执行此操作，运行：
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## 禁用用户 P2P 文件传输

- 您可以将此应用于用户通过创建新的策略和授予该用户。若要执行此操作，运行：
    
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```

> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
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
  

