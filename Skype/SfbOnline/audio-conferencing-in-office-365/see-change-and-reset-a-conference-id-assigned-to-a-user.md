---
title: 请参阅、 更改和重置会议 ID 分配给用户
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 4922f896daa2bec976d7fb72dd519e9dd91d74f4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>请参阅、 更改和重置会议 ID 分配给用户

自动分配给业务或 Microsoft 团队用户 Skype 会议 ID，在为 Office 365 中的音频会议设置并使用 Microsoft 作为音频会议提供商。 安排会议时，将会议邀请中发送分配的会议 ID。 将获取每个用户安排的会议分配一个唯一的会议 id。 
  
虽然会议 ID 将自动创建并分配给用户，有时可能时用户不是要使用此并且您希望将其设置为一个特定号码，或当用户忘记或丢失其会议 id。 您可以使用**Skype 的业务管理中心**和 Windows PowerShell 查看、 更改和重置用户的会议 id。
  
电子邮件将发送到用户的会议 ID 和默认音频会议的电话号码，或如果重置的会议 ID 将将包括会议 ID，但不是 PIN 发送不同的电子邮件。 有关重置会议组织者的 PIN，[转到此处](reset-a-conference-id-for-a-user.md)的详细信息。 
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-view-and-change-conference-ids"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) 查看和更改会议 Id

### <a name="to-view-the-conference-id"></a>若要查看的会议 ID

您可以查看其会议 ID，并将其发送给用户。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**> **音频会议** > **用户**选择的用户需要会议 id。
    
4. 在操作页上，在**会议 ID**下查看。
    
    > [!TIP]
    > 您可以向中包括的会议 ID 和音频的电话号码后，通过单击**发送电子邮件的会议信息**链接选择**用户**页上的用户的电子邮件的用户发送的所有会议信息。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

您可以使用 Windows PowerShell 查看用户的会议 ID。 为此，请运行：
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
### <a name="to-assign-or-change-the-conference-id"></a>分配或更改会议 ID

您可以分配或更改用户的会议 ID，如果，例如，某人希望易于记住一个会议 ID。

  > [!NOTE]
  > 业务管理中心的 Skype 不能用于编辑的会议 ID 已自动创建，但您可以使用 Windows PowerShell 编辑或更改在设置了一个会议 ID。 
     
若要编辑或更改用户的会议 ID，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > 会议 ID 必须包含 7 位，并且不能在 Skype 业务管理中心或使用 Windows PowerShell 中进行更改。 
  
### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-to-reset-the-conference-id"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) 若要重置的会议 ID

您可以重置用户的会议 ID if，例如，如果他们忘记了。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**> **音频会议** > **用户**，在**会议 ID**下的操作窗格中单击**重置**。
    
4. 在**重置的会议 ID？**窗口中，单击**是**。 A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    您可以通过使用 Windows PowerShell 重置用户的会议 ID。 若要执行此操作，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

   > [!IMPORTANT]
   >  创建新的会议 ID 或一个将重置之后，呼叫者不能使用旧的会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用业务会议迁移工具的 Skype 更新其现有会议。 若要查看如何下载、 安装和运行该工具，请参阅： [Skype 商业和 Lync 会议更新工具](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[业务 online，会议迁移工具 （64 位） 的 Skype](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 业务 online，会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。
  
- 请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。
    
- 会议 ID 必须满足的长度，以设置音频会议桥的数字。 会议 Id; 不能使用字母或特殊字符可以使用只有数字。
    
- 所有音频会议用户的会议 ID 将 7 位数字，默认情况下，并且不能更改的位数。
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么您需要使用 Office 365 PowerShell 中](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

