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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 了解表示 PIN 的长度和要求的参数，并了解如何在 Microsoft Teams 中设置会议的 PIN 长度。
ms.openlocfilehash: db7c62920dc7440cc8356dd3f5275dd551cdfd78
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014914"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>在 Microsoft Teams 中设置音频会议的 PIN 长度

当您要设置的 Microsoft 团队音频会议时，您将看到音频会议桥。 会议网桥可以包含一个或多个电话号码。 设置您的电话号码将包含在会议邀请的 Microsoft 团队应用程序。
  
音频会议桥的会议使用电话拨入的人员接听电话。 其接听呼叫者使用语音提示从自动助理，然后，具体取决于您的设置，可以播放通知以及提出呼叫者在记录其姓名。 **Microsoft 桥设置**允许您更改会议通知的设置和会议加入体验，并设置由会议组织者 Pin 长度。 会议组织者使用 Pin 启动会议，如果无法加入会议使用 Microsoft 团队应用程序。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>设置 PIN 长度

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中的“**PIN 长度**”下，为 PIN 选择所需的位数。

4. 单击“**保存**”。

> [!NOTE]
> [!注释] PIN 与会议 ID 不同。 会议 ID 由呼叫者在加入会议时使用。 它们用于标识会议。 PIN 用于对作为会议组织者的呼叫者进行身份验证。 

## <a name="want-to-know-more-about-pin-settings"></a>想要了解有关 PIN 设置的详细信息？

- 旋转中心点到 12 个数字; 可以是从 4默认值为 5。 在创建 PIN 时只能使用数字。 不能使用字母和特殊字符。
    
- PIN，仅当 Microsoft 团队用户已尚未启动会议所需的会议组织者。 如果每个人都是拨号进入会议，则会议组织者需要 PIN 才能启动会议。
    
- PIN 安全设置适用于与 Microsoft 网桥相关联的所有电话号码。它们将应用于使用与给定网桥相关联的电话号码的所有会议。 
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
    
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
