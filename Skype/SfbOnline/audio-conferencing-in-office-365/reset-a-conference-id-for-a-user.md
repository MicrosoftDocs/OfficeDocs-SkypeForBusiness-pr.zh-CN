---
title: 重置用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 077b35169b3829262c38c9ebc44451aba8bd110d
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="reset-a-conference-id-for-a-user"></a>重置用户的会议 ID

您的组织尚未为动态会议 Id 已启用，Skype 为业务或 Microsoft 小组的用户启用了使用 Microsoft 提供的音频会议时，将自动创建一个静态的会议 ID。 此会议 ID 将包括底部的会议邀请以及调用方可以用于对会议所拨入的电话号码。 当用户拨打的电话号码时，自动助理会议会要求调用方输入此会议 ID，这样他们可以参加会议。
  
> [!NOTE]
> 如果是您的会议提供商，默认情况下用户的会议 Id 设置为仅动态中。 遗憾的是，您不能将业务管理中心或使用 Windows Powershell Skype。 您将需要与 Microsoft 支持部门联系。 
  
当您组织中的人不想记得的随机数; 使用静态标识符他们可以选择一定数量或使用一个容易记住。 当使用动态会议 Id 时，每个会议用户计划将获得分配唯一的会议 id。 如果您想要分配动态而非静态的会议 Id，[转到此处](using-audio-conferencing-dynamic-ids-in-your-organization.md)。
  
会议 Id 只能自动设置只能用于 Skype 业务和 Microsoft 小组为启用的用户的音频会议作为其音频会议提供商使用 Microsoft。 如果您需要重置用户正在使用第三方音频会议提供商 (ACP) 的会议 ID，您需要为该用户在属性页上手动输入会议 ID。
  
## <a name="resetting-the-conference-id-for-a-user"></a>重置用户的会议 ID

**使用 Microsoft 小组和 Skype 业务管理中心**

1. 在左侧的导航中，单击**用户**，然后从可用的用户列表中选择用户。

2. 在页面的顶部，单击**编辑**。

3. 单击**会议桥**边上的菜单，然后单击下拉列表中的**重置会议 id** 。

2. 在**重置会议 id**窗口中，单击**确定**。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 默认情况下，电子邮件将发送给用户，但这可以被关闭。   

**使用 Skype 业务管理中心**
    
1. 在**Skype 的业务管理中心**，单击**音频会议** > **用户**选择一个用户，然后在**会议 ID**下的操作窗格中单击**重置**。
    
2. 在**会议 ID 重置？**窗口中，单击**是**。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 默认情况下，电子邮件将发送给用户，但这可以被关闭。
    
> [!NOTE]
> [!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。此电子邮件将发送到主电子邮件地址，大多数情况下是其 Office 365 邮箱。电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。 
  
## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 可以在电子邮件的用户在操作窗格中单击**将会议信息通过电子邮件发送**包含会议 ID 和拨入电话号码向用户发送的所有会议信息。 它不会发送 PIN。
    
- 会议 ID 将包含 7 位数字，并且您无法更改其长度在 Skype 业务管理中心或使用 Windows PowerShell。
    
- 重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。
    
- 当您选择**用户**页上的用户可以查看用户的音频会议的会议 ID 底部的操作窗格下**音频会议**。
    
- 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用 Skype 业务会议工具，以更新其现有的会议。 若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：
    
  - [Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会议迁移工具（64 位）](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会议迁移工具（32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)
