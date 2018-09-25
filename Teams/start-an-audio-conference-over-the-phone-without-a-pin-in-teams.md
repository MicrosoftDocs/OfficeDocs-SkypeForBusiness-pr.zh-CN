---
title: 在 Microsoft Teams 中在没有 PIN 的情况下通过电话启动音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service:
- -msteams
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
description: '了解如何从 Teams 管理中心启用或禁用匿名呼叫者加入会议。 '
ms.openlocfilehash: 4aec566b165385a111162641f233cd1b1e3027f4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014104"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>在 Microsoft Teams 中在没有 PIN 的情况下通过电话启动音频会议

拨入会议后在会议厅中听音乐等候的用户可能会感到沮丧，因为 Microsoft Teams 会议组织者尚未启动会议。 
  
如果会议组织者在调用会议，默认情况下，启动会议需要 PIN。 您可以将它设置以便任何人都可以拨号加入会议并不会提示输入 PIN 才能启动会议。 您可以使用管理中心启用或禁用此设置为单个用户。
  
PIN 不需要会议组织者，如果某人具有来自 Microsoft 团队应用程序启动会议。 只有当会议组织者通过电话加入会议时，才需要 PIN。 已分配的**音频会议**许可证并启用了音频会议时，将向音频用户发送会议的 PIN。 请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)和[自动发送给其音频会议设置更改时的用户的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>启用或禁用匿名呼叫者加入会议

![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**

1. 在左侧导航中，单击“**用户**”。 

2. 在列表中选择用户，然后单击页面顶部的“**编辑**”。 

3. 在“**音频会议**”旁边，单击“**编辑**”。

4. 在“**音频会议**”窗格中，启用或禁用“**未经身份验证的呼叫者可以是第一个参加会议的人**”。
    
4. 单击“**保存**”。 

**使用 Windows PowerShell**
  
有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。

## <a name="what-else-should-you-know"></a>你还应该了解哪些信息？

- 如果要重置 PIN，请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
    
- 如果已启用匿名访问或不要求使用 PIN 来启动会议：
    
  - 如果会议尚未启动（会议中还没有人）：系统将提示呼叫者确认是否是组织者，如果呼叫者确认是，则系统将提示其输入自己 PIN，在呼叫者输入 PIN 后，会议将启动，用户将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
- 如果已禁用匿名访问或不要求使用 PIN 来启动会议：
    
  - 如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。 组织者的设置设置为关闭，因为会议将启动，匿名呼叫者将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
