---
title: "重置用户的音频会议 PIN"
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Find out what you should know about PINs and how to reset them for your users. '
ms.openlocfilehash: eca48bb053459b568edc415d712a289be0aef4ff
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="reset-the-audio-conferencing-pin-for-a-user"></a>重置用户的音频会议 PIN

PIN 是创建为每个业务和 Microsoft 小组为音频会议启用用户的 Skype 的数字组成的代码。 音频会议的针脚都使用会议组织者来标识它们是会议组织者，并允许他们通过电话召开会议。 他们使用 Skype 业务或 Microsoft 小组应用程序的启动会议，如果不要求 PIN。 如果用户忘记了其 PIN，他们已启用音频会议时向其发送的电子邮件中找不到它，管理员将需要重置其 PIN。 用户不能重置自己的 PIN。
  
当身份验证的用户加入使用 Skype 业务或 Microsoft 小组应用程序或组织者加入与他或她的针通过电话时，可以开始会议。 当会议要求 PIN 来启动，用户通过电话连接将被放置在大厅，将听音乐暂候状态中，直到会议开始。 如果会议组织者不要求 PIN 开始举行会议，通过电话，然后将不要求调用方在他们加入会议时提供一个 PIN。
  
## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **业务的 Skype**，并在左边的导航，请单击**音频会议**。
    
3. 在**用户**单击，选择要重置 pin 码以进行用户。
    
4. 在操作窗格中下**针**，单击**重置**。
    
## <a name="what-else-should-you-know-about-pins"></a>你还应该知道有关 PIN 的哪些信息？

- 为安全起见，PIN 仅显示给管理员上重置 PIN 时的一次。 针针由管理员重置后，均被列为 *** 在**业务管理中心的 Skype**和它们在 Windows PowerShell 使用 Get CsCsOnlineDialInConfencingUser 的结果。
    
- 默认情况下，启用了自动向用户发送电子邮件，当他们正在启用音频会议或 PIN 重置时，用户将收到一封电子邮件与他们的 PIN。 但是，如果禁用了自动发送电子邮件、 PIN 重置电子邮件不会发送给用户，您必须手动向用户发送的 PIN 信息。
    
- 当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。
    
- 默认设置为不允许由匿名调用启动的会议。
    
- 当您启用音频会议的用户时，默认情况下发送电子邮件，其中包括会议信息和他们的 PIN。 用户必须具有 Office 365 的邮箱，因为一个新的 PIN 时重置 PIN，将发送到用户在发送电子邮件至为用户设置其主 SMTP 地址 （别名）。
    
- 当您设置了音频会议时，您设置的数字所需的组织中的针脚。 针脚可以从 4 到 12 位数字-缺省值为 5。 如果您更改 PIN 的长度设置，设置仅应用于新生成的针脚并不适用于启用音频会议的现有用户的 PIN 设置。 请参阅[设置音频会议的会议的 PIN 的长度](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。
    
- 默认情况下该电子邮件将设置为用户的 Office 365 主 SMTP 地址。 您可以向 Office 365 地址如 Hotmail 或 MSN 电子邮件地址发送一封电子邮件。 可以通过使用 Windows PowerShell 来覆盖默认的电子邮件地址。 这是非常有用的如果用户不能在 Office 365 的 Exchange 邮箱。
    
- 若要重写默认的用户地址发送电子邮件的位置，租户管理员可以使用以下 cmdlet： 集 CsOnlineDialInConferencingUser-amos.marble-ResetLeaderPIN-SendEmail-SendEmailToAddress"u@hotmail.com"。 SendEmail 参数需要重写用户的电子邮件地址。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet。
    
- 你可以通过运行以下命令来设置 Amos Marble 的 PIN：
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如当您所更改的设置对于许多用户一次。 了解这些优势中的以下主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)
