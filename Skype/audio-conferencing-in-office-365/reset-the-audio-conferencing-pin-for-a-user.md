---
title: "重置用户的音频会议 PIN"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
description: "Find out what you should know about PINs and how to reset them for your users. "
---

# 重置用户的音频会议 PIN

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
PIN 是为每个 Skype 业务和 Microsoft 团队启用音频会议的用户创建的数字组成的代码。音频会议 Pin 用于通过会议组织者标识它们是会议组织者，并让他们可以通过电话启动会议。如果他们使用 Skype for Business 或 Microsoft 团队应用启动会议，PIN 不需要。如果用户忘记他们的 PIN，他们在他们已启用的音频会议时发送给他们的电子邮件中无法找到它，管理员需要重置其 PIN。用户无法重置他们自己的 PIN。
  
当经过验证的用户加入使用 Skype for Business 或 Microsoft 团队应用或组织者加入与他或她 PIN 通过电话，则可以启动会议。启动会议时需要 PIN 若要开始，用户通过电话加入将放入会议厅和将收听音乐置于保持状态中，直到会议。如果会议组织者不需要 PIN 通过电话启动会议，然后不要求呼叫者加入会议时提供 PIN。
  
## 重置会议组织者的 PIN

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **Skype for Business**，然后在左侧导航中，单击 **音频会议**
    
3. 单击打开 **用户**，选择您想要重置 PIN 的用户。
    
4. 在操作窗格中，在 **固定**下单击 **重置**。
    
## 你还应该知道有关 PIN 的哪些信息？

- 出于安全原因，PIN 仅显示管理员到上一次，当重置 PIN。由管理员重置 PIN 之后，PIN 将列为 ***** **Skype for Business 管理中心**和结果中使用 Windows PowerShell 中获取 CsCsOnlineDialInConfencingUser 时。
    
- 默认情况下，启用自动向用户发送电子邮件和已启用音频会议或重置 PIN 时用户将收到一封电子邮件与他们的 PIN。但如果您已禁用自动发送电子邮件、 PIN 重置电子邮件不会发送给用户和您将需要手动向用户发送的 PIN 信息。
    
- 当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。
    
- 不允许会议由匿名呼叫者启动的默认设置。
    
- 启用用户的音频会议时，默认情况下它们是发送电子邮件包含会议信息和其 PIN。用户必须具有 Office 365 邮箱，因为重置 PIN，将向用户发送给他们的主要 SMTP 地址 （别名） 为用户设置电子邮件中发送一个新的 PIN。
    
- 设置音频会议时，您可以设置所需的 Pin，您的组织中的数字。默认为 5-Pin 可以包含 4 至 12 个数字。如果更改 PIN 长度设置，请设置仅应用于新生成的 Pin，并不应用于现有用户启用了音频会议的 PIN 设置。请参阅[设置音频会议的 PIN 的长度](set-the-length-of-the-pin-for-audio-conferencing-meetings.md)。
    
- 默认情况下的电子邮件将设置为 Office 365 主 SMTP 地址的用户。您可以向 Office 365 地址，如 Hotmail 或 MSN 电子邮件地址发送一封电子邮件。使用 Windows PowerShell，可以覆盖默认电子邮件地址。这是非常有用，如果用户没有 Office 365 中的 Exchange 邮箱。
    
- 若要覆盖默认用户地址发送电子邮件的位置，租户管理员可以使用以下 cmdlet： 设置 CsOnlineDialInConferencingUser-amos.marble-ResetLeaderPIN-SendEmail-SendEmailToAddress"u@hotmail.com"。SendEmail 参数需要重用户的电子邮件地址。
    
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用[设置 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
- 你可以通过运行以下命令来设置 Amos Marble 的 PIN：
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell 是有关管理用户和允许或不可以执行哪些用户的所有信息。使用 Windows PowerShell，您可以管理Office 365使用单一管理，当您有多个要执行的任务可以简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有许多优于速度、 简单起见和工作效率中的仅使用 Office 365 管理中心中，例如，当您正在进行设置更改为许多用户，一次。了解有关以下主题中的以下优势：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

