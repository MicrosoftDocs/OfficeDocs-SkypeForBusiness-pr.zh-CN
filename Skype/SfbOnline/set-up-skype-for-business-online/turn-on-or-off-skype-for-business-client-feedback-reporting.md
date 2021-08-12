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
description: 可让 Skype for Business 使用内置的 Skype for Business 应用反馈工具，让用户直接向 Microsoft 报告问题并提供有关其体验的反馈。
ms.openlocfilehash: e480f9446f3418b2c68d2c74388b60009b81bc13f76e47c15c1f4e8e3f882984
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281335"
---
# <a name="turn-on-or-off-skype-for-business-client-feedback-reporting"></a>开启或关闭 Skype for Business 客户端反馈报告

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

可让 Skype for Business Online 用户使用内置的 Skype for Business 应用反馈工具，让用户直接向 Microsoft 报告问题并提供有关其体验的反馈。 
  
!["提供反馈"图标](../images/eac13837-04d9-4da1-8e80-54612cf6650d.png)
  
使用此工具，用户可以从设备上的应用复制日志，以帮助 Microsoft 更好地调查和排查他们可能存在的问题。 
  
![使用"报告问题"设置图标](../images/2dfb5603-1d69-41fc-a43e-91a3379acbe0.png)
  
你还可以使用  _EnableOnlineFeedbackScreenshot_ 设置，以便用户可以在其反馈中包含其设备的屏幕截图。
  
![Skype for Business client reporting form.](../images/d859578d-8116-4d4b-a08f-c0cae28b8b76.png)
  
> [!IMPORTANT]
> 在调查问题期间，应用的反馈工具收集的日志将在美国最多存储 90 天。 因此，如果这违反你组织的数据保护政策，请勿启用此反馈工具。 
  
## <a name="start-windows-powershell"></a>启动Windows PowerShell

> [!NOTE]
> Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。
1. 安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 打开Windows PowerShell命令提示符并运行以下命令： 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
   如果需要有关启动 Windows PowerShell Windows PowerShell，请参阅在单个 Microsoft 365 窗口中连接所有 Microsoft 365 或[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务Windows PowerShell或为计算机设置[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
## <a name="turn-on-client-app-feedback-reporting-for-all-the-users-in-your-organization"></a>为你组织中的所有用户开启客户端应用反馈报告

若要为组织中用户启用反馈报告并允许他们提交设备屏幕截图，请运行：
 
  ```PowerShell
  Set-CsClientPolicy -Identity EnableOnlineFeedback -EnableOnlineFeedback $true -EnableOnlineFeedbackScreenshots $true
  ```
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [你可能希望使用 Windows PowerShell 管理Microsoft 365或Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell比仅使用 Microsoft 365 管理中心（例如，一次为许多用户进行设置更改时）在速度、简单性和工作效率方面具有许多优势。 通过以下主题了解这些优势：
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
