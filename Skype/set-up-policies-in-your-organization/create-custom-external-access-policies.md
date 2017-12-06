---
title: "创建自定义外部访问策略"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
description: "Skype for Business Online 使您可以创建其他外部访问策略。与客户端或会议的策略，在其中可以有多个组合，有三种方案的大部分的预定义的外部访问策略。以下是："
---

# 创建自定义外部访问策略

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](89cbd278-5480-473c-8cd9-04e07e5f9e0b.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/89cbd278-5480-473c-8cd9-04e07e5f9e0b) 中查找本文的英文版本以便参考。
  
Skype for Business Online 使您可以创建其他外部访问策略。与客户端或会议的策略，在其中可以有多个组合，有三种方案的大部分的预定义的外部访问策略。以下是：
  
- 无联合或 Skype 消费者访问 ( _Tag:NoFederationAndPIC_ )
    
- 仅限联盟的访问 ( _Tag:FederationOnly_ )
    
- 联合和使用者访问 ( _FederationAndPICDefault_)
    
自定义外部策略允许您创建其他策略未包含的上面的设置。 当创建策略时，您将需要设置所有必需的参数和更高版本中无法更改它们。创建新的自定义策略允许您控制功能，例如 Skype 消费者 access 或了策略来禁用公共云音频/视频，这是使用预定义的设置未包含的内容。自定义外部访问策略按照与客户端、 移动和会议策略相同的语法。您可以了解有关这些设置[下面](https://technet.microsoft.com/en-us/library/mt228132.aspx)的详细信息。
  
若要完成此操作，请用户必须使用受支持的版本的 2016年点即用 Skype for Business 应用程序的支持。下面的最小版本的 Skype for Business 2016 点即用客户端是必需的：
  
|**类型**|**发布日期**|**版本**|**内部版本**|
|:-----|:-----|:-----|:-----|
|当前频道的首次发布  <br/> |2016 年 11/17  <br/> |16.0.7571.2006  <br/> |版本 1611 （构建 7571.2006）  <br/> |
|当前频道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> | 版本 1611（内部版本 7571.2072） <br/> |
|延期频道  <br/> |2017-2/22  <br/> |16.0.7369.2118  <br/> |版本 1609 （构建 7369.2118）  <br/> |
   
> [!警告]
> 使用较旧版本的 Skype for Business Windows 应用程序或 Mac 客户端的用户仍然可以将文件传送。 
  
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
    
    > [!注释]
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
    
## 创建自定义外部访问策略的用户

若要执行此操作，运行：
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

