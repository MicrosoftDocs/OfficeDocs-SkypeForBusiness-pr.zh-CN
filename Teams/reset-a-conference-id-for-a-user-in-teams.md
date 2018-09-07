---
title: 重置 Microsoft 团队中的用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解重置用户的步骤的会议中 Microsoft 团队的会议 ID 和获取链接到会议更新和迁移工具。 '
ms.openlocfilehash: d60c1a76b4e800ef07e206df31206e6d0e0bda1a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23868154"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>重置 Microsoft 团队中的用户的会议 ID

底部的会议邀请以及的拨入电话号码的呼叫者可用于向会议呼叫中包含动态的会议 ID。 当用户拨打的电话号码时，会议自动助理会要求呼叫者输入此会议 ID，以便他们可以参加会议。
  
> [!NOTE]
> 如果您的会议提供商是 Microsoft，默认情况下用户的会议 Id 设置为仅动态中。 遗憾的是，它不能更改其成为静态的因为这是现在不受支持。 为启用了音频会议的 Microsoft 团队用户只能自动设置会议 Id。 


## <a name="resetting-the-conference-id-for-a-user"></a>重置用户的会议 ID

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在页面的顶部，单击**编辑**。

3. 在**音频会议**下单击**重置的会议 ID**。

2. 在**重置的会议 ID**窗口中，单击**重置**。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 默认情况下电子邮件发送给用户，但这可以关闭。   

    
> [!NOTE]
> [!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。 此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。 电子邮件包含新的会议 ID、 默认电话拨入电话号码和更新现有会议的说明。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 您可以向中包括会议 ID 和电话拨入电话号码，通过单击**音频会议**部分中为用户的**发送电子邮件中的会议信息**的电子邮件的用户发送的所有会议信息。 它不会发送 PIN。
    
- 会议 ID 将包含 7 位数字，并且您无法更改它的长度。
    
- 重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。
    
- [!重要信息] 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 

## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。
    
## <a name="related-topics"></a>相关主题

[重置 PIN 的音频会议](reset-the-audio-conferencing-pin-in-teams.md)
