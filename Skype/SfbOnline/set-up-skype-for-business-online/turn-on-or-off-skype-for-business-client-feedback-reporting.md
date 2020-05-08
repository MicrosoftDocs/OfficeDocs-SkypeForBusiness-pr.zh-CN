---
title: 开启或关闭 Skype for Business 客户端反馈报告
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 35562b48-1da1-4081-8a3a-033d0f1986b2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 你可以使 Skype for Business 用户能够使用内置的 Skype for business 应用反馈工具，让用户能够直接向 Microsoft 报告问题并向 Microsoft 提供反馈，以了解他们的体验。
ms.openlocfilehash: 04dc6ddcb82e40bef2a0aa6a6197566d9dd8a374
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164541"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>开启或关闭 Skype for Business 客户端反馈报告

你可以启用 Skype for business Online 用户使用内置的 Skype for business 应用反馈工具，让用户能够直接向 Microsoft 报告问题并向 Microsoft 提供反馈意见。 
  
![Skype for Business client reporting.](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
使用此工具，用户可以从其设备上的应用复制日志，以帮助 Microsoft 更好地调查和解决他们可能遇到的问题。 
  
![Skype for Business client reporting.](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
你还可以使用  _EnableOnlineFeedbackScreenshot_ 设置，以便用户可以在其反馈中包含其设备的屏幕截图。
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> 在调查问题时，应用的反馈工具收集的日志最多可存储在美国的90天。 因此，如果这违反你组织的数据保护政策，请勿启用此反馈工具。 
  
## <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。 请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。 出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。
    
- **启动 Windows PowerShell 会话**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. 在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：
    
    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
 
   ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```
   如果需要有关启动 Windows PowerShell 的详细信息，请参阅[在单个 Windows powershell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[设置适用于 windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
    
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>为你组织中的所有用户开启客户端应用反馈报告

若要为组织中的用户启用反馈报告，并允许他们提交设备屏幕截图，请运行：
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？
- Windows PowerShell 全部用于管理用户以及允许或禁止用户执行的操作。使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365 和 Skype for business Online，这样你有多个任务可以简化日常工作。若要开始使用 Windows PowerShell，请参阅以下主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [可能希望使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六个原因](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。了解以下主题中的这些优势：
    
  - [通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
 
