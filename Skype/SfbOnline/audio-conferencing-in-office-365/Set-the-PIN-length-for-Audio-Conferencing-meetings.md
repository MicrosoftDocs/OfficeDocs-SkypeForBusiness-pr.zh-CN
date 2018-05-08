---
title: 设置音频会议的 PIN 长度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 318e24bf30563d0a790584f9c1ccceb01d93c793
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>设置音频会议的 PIN 长度

当您要设置音频会议的 Skype 适用于商务或 Microsoft 团队时，您将看到音频会议桥。 会议网桥可以包含一个或多个电话号码。 设置您的电话号码将包含在会议邀请上的 Skype 业务和 Microsoft 团队的应用程序。
  
音频会议桥的会议使用电话拨入的人员接听电话。 其接听呼叫者使用语音提示从自动助理，然后，具体取决于您的设置，可以播放通知以及提出呼叫者在记录其姓名。 **Microsoft 桥设置**允许您更改会议通知的设置和会议加入体验，并设置由会议组织者 Pin 长度。 会议组织者使用 Pin 如果无法加入会议的业务或 Microsoft 团队应用程序使用 Skype 启动会议。
  
## <a name="setting-the-pin-length"></a>设置 PIN 长度

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，在**PIN 长度**，下选择所需的 pin 的位数。

4. 单击“**应用**”。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**
 
1. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。
    
2. 在**安全**下 > **PIN 长度**，选择 PIN，所需的位数，然后单击**保存**。
    
> [!NOTE]
> [!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="want-to-know-more-about-pin-settings"></a>想知道 PIN 设置的详细信息吗？

- 旋转中心点到 12 个数字; 可以是从 4默认值为 5。 在创建 PIN 时只能使用数字。 不能使用字母和特殊字符。
    
- PIN 才所需的会议组织者时为业务或 Microsoft 团队用户 Skype 不起作用已经启动会议。 如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。
    
- PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet。
    
- 若要将 PIN 的数字位数设置为 8： `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell 中](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="see-also"></a>另请参阅

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
