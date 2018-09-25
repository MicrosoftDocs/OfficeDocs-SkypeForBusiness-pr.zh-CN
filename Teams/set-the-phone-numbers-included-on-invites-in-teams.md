---
title: 设置的电话号码包含在邀请中的 Microsoft 团队
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: '获取创建默认的电话号码的呼叫者加入 Microsoft 团队会议的步骤。 '
ms.openlocfilehash: f62a6e63181c474d19f403d6c81f858177bd8cd0
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016194"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>在 Microsoft Teams 中设置包含在邀请中的电话号码

Office 365 中的音频会议，组织中的用户创建的 Microsoft 团队会议，然后允许这些会议使用电话拨入的用户。 在 Office 365 中，您可以使用 Microsoft 音频会议网桥或位于由已批准的音频会议提供商 (ACP) 的第三方音频会议桥的选择。
  
会议桥为你的组织提供了一套拨入电话号码。 它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。
  
> [!NOTE]
> 会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>为会议组织者或用户设置或更改默认音频会议电话号码。

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

    ![显示在 Microsoft Teams 和 Skype for Business 管理中心中选择用户](media/teamsselectusers.png)

2. 在页面顶部，单击“**编辑**”。

    ![在 Microsoft Teams 和 Skype for Business 管理中心中单击“编辑”](media/teamsedituser.png)

3. 在“**音频会议**”旁边，单击“**编辑**”。 
    
    ![单击“音频会议”旁边的“编辑”](media/teamseditaudioconf.png)

4. 使用“**收费电话号码**”或“**免费电话号码**”字段为用户输入电话号码。


> [!IMPORTANT]
> 更改用户的音频会议设置时，必须更新定期和将来的 Microsoft Teams 会议并向与会者发送更新信息。 

## <a name="want-to-use-windows-powershell"></a>想要使用 Windows PowerShell？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。 
  
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
