---
title: 设置您的组织的移动策略
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 您可以设置如何您的用户连接到 Skype 的在线业务的业务应用程序等功能，使用户可以拨打和接听电话在他们的移动电话而不是他们的移动电话 nu 通过其单位电话号码的移动设备上使用 Skypember。 还需要使用移动策略来要求在拨打或接听电话时使用 Wi-Fi 连接。
ms.openlocfilehash: cbd981285f6c4dfacf09597b2bd8e687ba124ad8
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-mobile-policies-for-your-organization"></a>设置您的组织的移动策略

您可以设置如何您的用户连接到 Skype 的在线业务的业务应用程序等功能，使用户可以拨打和接听电话在他们的移动电话而不是他们的移动电话 nu 通过其单位电话号码的移动设备上使用 Skypember。 还需要使用移动策略来要求在拨打或接听电话时使用 Wi-Fi 连接。
  
移动的策略设置可以配置在创建策略时，也可以使用**一组 CsMobilityPolicy** cmdlet 要修改的现有策略设置。
  
## <a name="set-your-mobile-policies"></a>设置你的移动策略

> [!NOTE]
> 对于所有的移动策略设置在 Skype 业务联机，您必须使用 Windows PowerShell 并且您**不能使用** **Skype 的业务管理中心**。 
  
### <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

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
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  如果希望在启动 Windows PowerShell 的详细信息，请参阅[连接到一个 Windows PowerShell 窗口中的所有 Office 365 提供服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[连接到使用 Windows PowerShell 在线业务 Skype](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>要求用户进行视频操作时使用 WiFi 连接

- 若要创建新的策略，这些设置，请运行：
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  请参阅详细信息[新建 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet。
    
- 若要授予组织中为所有用户都创建新策略，请运行：
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  请参阅详细信息[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet。
    
  如果您已经创建一个策略，可以使用[一组 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet 可以更改现有的策略，并将[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 将设置应用到您的用户。
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>禁止用户使用 Skype for Business 应用

- 若要创建新的策略，这些设置，请运行：
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  请参阅详细信息[新建 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet。
    
- 若要创建新策略授予 Amos 大理石，运行：  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  请参阅详细信息[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet。
    
  如果您已经创建一个策略，可以使用[一组 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet 可以更改现有的策略，并将[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 将设置应用到您的用户。
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>禁止用户使用移动设备拨打 IP 语音电话。

- 若要创建新的策略，这些设置，请运行：
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  请参阅详细信息[新建 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet。
    
- 若要授予组织中为所有用户都创建新策略，请运行：
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  请参阅详细信息[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet。
    
如果您已经创建一个策略，可以使用[一组 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet 可以更改现有的策略，并将[授予 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet 将设置应用到您的用户。
  
## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[块的点对点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[设置您的组织中的会议策略](set-up-conferencing-policies-for-your-organization.md)

  
 