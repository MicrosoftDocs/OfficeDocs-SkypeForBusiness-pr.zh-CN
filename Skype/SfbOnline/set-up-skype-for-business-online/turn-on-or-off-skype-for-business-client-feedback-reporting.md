---
title: 开启或关闭 Skype for Business 客户端反馈报告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 您可以让您 Skype 业务用户使用的业务应用程序的反馈工具内置 Skype 让用户报告问题并提供反馈直接向 Microsoft 有关其体验。
ms.openlocfilehash: 3dcb003c23ca1a96a646851358d21aca5a47e674
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561616"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>开启或关闭 Skype for Business 客户端反馈报告

您可以让您 Skype 业务 Online 用户使用的业务应用程序的反馈工具内置 Skype 让用户报告问题并提供反馈直接向 Microsoft 有关其体验。 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
使用此工具，用户可以从应用程序在其设备，以帮助更好地调查和解决问题可能遇到的 Microsoft 上复制日志。 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
你还可以使用  _EnableOnlineFeedbackScreenshot_ 设置，以便用户可以在其反馈中包含其设备的屏幕截图。
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> 将存储在应用程序的反馈工具收集日志的正在问题时在美国 90 天的最多调查。 因此，如果这违反你组织的数据保护政策，请勿启用此反馈工具。 
  
## <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
    
- **启动 Windows PowerShell 会话**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
 
   ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[Windows PowerShell 将计算机设置](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>为你组织中的所有用户开启客户端应用反馈报告

若要启用报告您组织中的用户的反馈，并允许其提交设备的屏幕截图，请运行：
 
  ```
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
 
