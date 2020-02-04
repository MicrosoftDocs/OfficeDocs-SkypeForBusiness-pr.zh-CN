---
title: 在 Microsoft Teams 中设置音频会议的 PIN 长度
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 了解 PIN 长度和要求的参数，了解如何在 Microsoft 团队中设置会议的长度。
ms.openlocfilehash: 7f7f477d14556baa7d2a47e5062aacd5de5796fd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693997"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>在 Microsoft Teams 中设置音频会议的 PIN 长度

当你为 Microsoft Teams 设置音频会议时，你将获得一个音频会议网桥。 会议网桥可以包含一个或多个电话号码。 你设置的电话号码将包含在 Microsoft Teams 应用的会议邀请中。
  
会议网桥负责应答使用电话拨入会议的人员的呼叫。 它通过来自自动助理的语音提示应答呼叫者，然后根据你的设置，可以播放通知并让呼叫者录制其姓名。 在 **Microsoft 网桥设置**中，你可以更改会议通知和会议加入体验的设置，并设置会议组织者使用的 PIN 的长度。 如果会议组织者无法使用 Microsoft Teams 应用加入会议，可使用 PIN 启动会议。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>设置 PIN 长度

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在 "**桥设置**" 窗格中的 " **PIN 长度**" 下，选择要用于 pin 的数字位数。

4. 单击“**保存**”。

> [!NOTE]
> [!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。 

## <a name="want-to-know-more-about-pin-settings"></a>想要了解有关 PIN 设置的详细信息？

- 引脚可以是4到12位数字;默认值为5。 在创建 PIN 时只能使用数字。 不能使用字母和特殊字符。
    
- 只有当 Microsoft 团队用户尚未启动会议时，会议组织者才需要 PIN。 如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。
    
- PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。 
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
    
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
