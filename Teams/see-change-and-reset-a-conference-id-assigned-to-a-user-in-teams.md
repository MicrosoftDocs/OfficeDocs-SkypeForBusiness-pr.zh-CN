---
title: 在 Microsoft Teams 中查看、更改和重置分配给用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何在 Microsoft Teams 中为用户分配会议 ID 以及应使用的会议 ID 参数。 '
ms.openlocfilehash: 317216f84044eb404541a98d24c69b2f7fb61bc4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017082"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>在 Microsoft Teams 中查看和重置分配给用户的会议 ID

自动分配给 Microsoft 团队用户会议 ID，在为 Office 365 中的音频会议设置并使用 Microsoft 作为音频会议提供商。 安排会议时，将会议邀请中发送分配的会议 ID。 用户安排的每次会议将分配到一个唯一的会议 id。 
  
虽然会议 ID 将自动创建并分配给用户，有时可能时用户不是要使用此并且您希望将其设置为一个特定号码，或当用户忘记或丢失其会议 id。 您可以使用的 Microsoft 团队管理中心或 Windows PowerShell 查看、 更改和重置用户的会议 id。
  
电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。 有关重置会议组织者 PIN 的详细信息，请[转到此处](reset-a-conference-id-for-a-user-in-teams.md)。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>查看和重置会议 ID

### <a name="to-view-the-conference-id"></a>查看会议 ID

![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在页面顶部，单击“**编辑**”。

3. 在“**音频会议**”下，查看“**会议 ID**”下方内容。

    > [!TIP]
    > 你可以单击“**通过电子邮件发送会议信息**”，通过电子邮件向用户发送所有会议信息（包括会议 ID 和音频电话号码）。
  
**使用 Windows PowerShell**

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
    
  
### <a name="to-reset-the-conference-id"></a>重置会议 ID

你可以为用户重置会议 ID（例如，当用户忘记了会议 ID 时）。
  
![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在页面顶部，单击“**编辑**”。

3. 在“**音频会议**”下，单击“**重置会议 ID**”。

4. 在**重置的会议 ID**窗口中，单击**重置**。 A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
**使用 Windows PowerShell**

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。


## <a name="what-else-should-you-know"></a>你还应该了解哪些信息？

   > [!IMPORTANT]
   >  创建新的会议 ID 或一个将重置之后，呼叫者不能使用旧的会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 
  
    
- 会议 ID 必须满足的长度，以设置音频会议桥的数字。 会议 Id; 不能使用字母或特殊字符可以使用只有数字。
    
- 默认情况下，你的所有音频会议用户的会议 ID 都将为 7 位数，且位数不可更改。
    
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

