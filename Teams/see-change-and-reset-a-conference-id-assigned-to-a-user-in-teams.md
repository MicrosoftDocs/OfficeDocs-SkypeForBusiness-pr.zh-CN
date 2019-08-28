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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何在 Microsoft Teams 中为用户分配会议 ID 以及应使用的会议 ID 参数。 '
ms.openlocfilehash: 8c4832050626dadd1bec068be262281d1303ef46
ms.sourcegitcommit: 26b3d786da07fde20878b0f4a1656070fe01d918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "36645277"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>在 Microsoft Teams 中查看和重置分配给用户的会议 ID

在 Office 365 中为 Microsoft Teams 用户设置音频会议以及 Microsoft Teams 用户使用 Microsoft 作为音频会议提供商时会自动为其分配会议 ID。 在安排会议时将在会议邀请中发送分配的会议 ID。 用户安排的每次会议将分配到一个唯一的会议 id。 
  
虽然会自动创建会议 ID 并将其分配给用户，但有时可能会存在以下情况：用户不希望使用此会议 ID，你希望将其设置为特定号码，或者你的用户记不住或丢失了其会议 ID。 你可以使用 Microsoft Teams 管理中心或 Windows PowerShell 来查看、更改和重置其会议 ID。
  
电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。 有关重置会议组织者 PIN 的详细信息，请[转到此处](reset-a-conference-id-for-a-user-in-teams.md)。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>查看和重置会议 ID

### <a name="to-view-the-conference-id"></a>查看会议 ID

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在页面顶部，单击“**编辑**”。

3. 在“**音频会议**”下，查看“**会议 ID**”下方内容。

    > [!TIP]
    > 你可以单击“**通过电子邮件发送会议信息**”，通过电子邮件向用户发送所有会议信息（包括会议 ID 和音频电话号码）。
  
**使用 Windows PowerShell**

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
    
  
### <a name="to-reset-the-conference-id"></a>重置会议 ID

你可以为用户重置会议 ID（例如，当用户忘记了会议 ID 时）。
  
![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在页面顶部，单击“**编辑**”。

3. 在“**音频会议**”下，单击“**重置会议 ID**”。

4. 在“**重置会议 ID**”窗口中，单击“**重置**”。 将自动创建一个会议 ID，并向用户发送包含新会议 ID 的电子邮件。
  
**使用 Windows PowerShell**

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。


## <a name="what-else-should-you-know"></a>你还应该了解哪些信息？

   > [!IMPORTANT]
   >  创建新会议 ID 或重置会议 ID 后，呼叫者不能使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 
  
    
- 会议 ID 必须符合在音频会议网桥上设置的位数长度。 不能在会议 ID 中使用字母和特殊字符，只能使用数字。
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

