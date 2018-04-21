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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 42aa17866c286c5d57fa3cd4962ecf6a16e2438a
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>请参阅、 更改和重置会议 ID 分配给用户

会议 ID 自动分配给为业务或 Microsoft 小组的用户 Skype 为 Office 365 中的音频会议设置并使用 Microsoft 作为音频会议提供商时。 指定的会议 ID 可以是静态或动态，以及时安排的会议，在会议邀请中发送。
  
当您组织中的人不想记得的随机数; 使用静态标识符他们可以选择一定数量或使用一个容易记住。 当使用动态会议 Id 时，每个会议用户计划将获得分配唯一的会议 id。 如果您想要分配动态而非静态的会议 Id，[转到此处](using-audio-conferencing-dynamic-ids-in-your-organization.md)。
  
一个静态的会议 ID 将自动创建并指派给用户，尽管有时可能当用户不想使用它并且想要将其设置为某个数字、 或当用户忘记或丢失了他们的会议 id。 您可以使用**业务管理中心的 Skype**和 Windows PowerShell 查看、 更改和重置其会议 id。
  
电子邮件将被发送到用户的会议 ID 和默认音频会议电话号码，或如果您重置会议 ID 将会包含会议 ID，但不是一个 PIN 发送不同的电子邮件。
  
## <a name="view-and-change-conference-ids"></a>查看和更改会议 Id

### <a name="to-view-the-conference-id"></a>若要查看会议 ID

您可以查看其会议 ID 并将其发送给用户。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**Skype 的业务管理中心**> **音频会议** > **用户**，选择的用户的需求会议 id。
    
4. 在操作页上，查看在**会议 ID**下。
    
    > [!TIP]
    > 可以在包含会议 ID 和音频的电话号码后，通过单击**将会议信息通过电子邮件发送**链接选择**用户**页上的用户的电子邮件向用户发送所有会议信息。
  
    您可以使用 Windows PowerShell 来查看用户的会议 ID。 为此，请运行：
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    请参阅[获取 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 )以了解有关该 cmdlet。
    
### <a name="to-assign-or-change-the-conference-id"></a>若要分配或更改会议 ID

您可以分配或更改用户的会议 ID，如果，例如，某人想很容易记住一个会议 ID。

  > [!NOTE]
  > 业务管理中心为 Skype 不能用于编辑自动创建后，一个会议 ID，但您可以使用 Windows PowerShell 编辑或更改已设置一个会议 ID。 
     
若要编辑或更改用户的会议 ID，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > 会议 ID 必须包含 7 位数字，并不能在 Skype 业务管理中心或使用 Windows PowerShell 中进行更改。 
  
### <a name="to-reset-the-conference-id"></a>若要重置的会议 ID

您可以重置用户的会议 ID 如果，例如，如果他们忘记了。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**Skype 的业务管理中心**> **音频会议** > **用户**，在**会议 ID**、 操作窗格中单击**重置**。
    
4. 在**会议 ID 重置？**窗口中，单击**是**。 A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    可以通过使用 Windows PowerShell 重置用户的会议 ID。 若要执行此操作，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

   > [!IMPORTANT]
   >  创建新的会议 ID 或其中一个将被重置后，调用方不能使用旧的会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用 Skype 业务会议迁移工具来更新其现有的会议。 若要了解如何下载、 安装和运行该工具，请参阅：[为业务和 Lync Skype 会议更新工具](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype 业务在线，会议迁移工具 （64 位）](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 的业务联机，会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。
  
- 请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。
    
- 会议 ID 必须满足中位数设置音频会议桥的长度。 不能使用字母或特殊字符在会议 Id;可以使用数字。
    
- 会议 ID 的所有音频会议用户将默认情况下，7 位，不能更改的数字位数。
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

