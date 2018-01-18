---
title: "设置音频会议的会议的针长度"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 853a8ed74377dd76b38eab62b04fc75e3295df2d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>设置音频会议的会议的针长度

当您设置中的音频会议为 Skype 业务或 Microsoft 小组时，您将看到音频会议桥。 会议桥可以包含一个或多个电话号码。 您设置的电话号码将包括在会议邀请的 Skype 业务和 Microsoft 小组应用程序。
  
音频会议桥的拨入会议使用电话的人应答呼叫。 从自动助理，然后根据您的设置，它会回答带语音提示的调用方，可以播放通知并要求调用方来记录他们的姓名。 **Microsoft 网桥的设置**允许您更改的设置会议通知和会议加入体验，并将由会议组织者的针脚长度设置。 会议组织者使用针脚来启动会议，如果他们不能参加会议的业务或 Microsoft 小组应用程序使用 Skype。
  
## <a name="setting-the-pin-length"></a>设置 PIN 长度

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **业务的 Skype**。
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**安全**下 > **针长度**，选择的针，所需的位数，然后单击**保存**。
    
> [!NOTE]
> [!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。 
  
## <a name="want-to-know-more-about-pin-settings"></a>想知道更多有关 PIN 设置？

- 针脚可以从 4 到 12 位数字;默认值为 5。 创建针时只能使用数字。 不使用字母和特殊字符。
    
- PIN 只是对于会议组织者在为业务或 Microsoft 小组的用户 Skype 时没有已启动会议是必需的。 如果每个人都拨号进入会议，针是要求会议组织者开始举行会议。
    
- PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
- 若要将 PIN 的数字位数设置为 8： `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如当您所更改的设置对于许多用户一次。 了解这些优势中的以下主题： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="see-also"></a>另请参阅

[设置 Skype for Business 和 Microsoft Teams 音频会议](set-up-audio-conferencing.md)

