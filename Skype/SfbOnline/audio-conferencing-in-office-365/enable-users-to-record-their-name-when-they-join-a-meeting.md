---
title: 使用户能够在加入会议时录制其姓名
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 'Learn how to enable or disable whether your users can record their names when they join a meeting '
ms.openlocfilehash: 6f1c5c9c86f4b0296340c9185acdc9d505baeda7
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a>使用户能够在加入会议时录制其姓名

当您设置 Office 365 中的音频会议时，您将收到的电话号码和所谓的音频会议桥。 会议网桥可以包含一个或多个电话号码，这些号码可以是专用或共享电话号码。
  
会议网桥负责应答使用电话拨入会议的用户的呼叫。 会议桥从自动助理，回答带语音提示的调用方，然后，根据其设置中，可以播放通知，要求调用方记录其姓名，并对会议组织者针安全设置。 向会议组织者提供的针脚，让他们可以开始会议。 然而，你也可以将其设置为无需 PIN 即可启动会议。
  
## <a name="set-whether-callers-should-record-their-name"></a>设置呼叫者是否应录制其姓名

**使用 Microsoft 小组和 Skype 业务管理中心**

1. 在左侧的导航中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**桥接器设置**。 

3. 启用或禁用**启用会议进入和退出通知以打开**。

4. 单击“**应用**”。


**使用 Skype 业务管理中心**
    
1. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。
    
2. 在**会议连接体验**，请参阅**启用会议进入和退出通知以打开**标记的复选框。
    
  - **选择**将要求调用方才能进入会议记录他们的姓名。 默认情况下，此选项处于选中状态。
    
  - **清除**调用方不需要记下其名称才能进入会议。
    
3. 完成更改后，单击" **保存**"。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
-  所有有关管理用户和哪些用户有权执行此是 Windows PowerShell。 使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如，当将设置更改为许多用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
