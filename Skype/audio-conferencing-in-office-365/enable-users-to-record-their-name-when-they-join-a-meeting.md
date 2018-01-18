---
title: "使用户能够在加入会议时录制其姓名"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 'Learn how to enable or disable whether your users can record their names when they join a meeting '
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a>使用户能够在加入会议时录制其姓名

当您设置 Office 365 中的音频会议时，您将收到的电话号码和所谓的音频会议桥。 会议桥可以包含一个或多个可以是专用或共享电话号码的电话号码。
  
会议桥的会议使用电话拨入用户应答呼叫。 会议桥从自动助理，回答带语音提示的调用方，然后，根据其设置中，可以播放通知，要求调用方记录其姓名，并对会议组织者针安全设置。 向会议组织者提供的针脚，让他们可以开始会议。 但是，您可以设置它以便 PIN 不需要召开会议。
  
## <a name="set-whether-callers-should-record-their-name"></a>设置呼叫者是否应录制其姓名

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **业务的 Skype**。
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**会议连接体验**，请参阅**启用会议进入和退出通知以打开**标记的复选框。
    
  - **选择**将要求调用方才能进入会议记录他们的姓名。 默认情况下选择此选项。
    
  - **清除**调用方不需要记下其名称才能进入会议。
    
5. 完成更改后，单击" **保存**"。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
-  所有有关管理用户和哪些用户有权执行此是 Windows PowerShell。 使用 Windows PowerShell 可以管理 Office 365 使用单点管理，可以简化您的日常工作时必须要执行多个任务。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如，当将设置更改为许多用户一次。了解这些优势中的以下主题： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[设置 Skype for Business 和 Microsoft Teams 音频会议](set-up-audio-conferencing.md)

