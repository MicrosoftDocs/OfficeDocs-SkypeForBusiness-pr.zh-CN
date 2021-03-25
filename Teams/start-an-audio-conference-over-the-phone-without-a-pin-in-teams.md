---
title: 在 Teams 中通过电话在没有 PIN 的情况下启动音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '了解如何启用或禁用匿名呼叫者从 Teams 管理中心加入会议。 '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116960"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>在 Microsoft Teams 中在没有 PIN 的情况下通过电话启动音频会议

拨入会议的用户在会议大厅中收听音乐可能令人沮丧，因为 Microsoft Teams 会议组织者尚未启动会议。 
  
默认情况下，如果会议组织者呼叫呼叫会议，则启动会议需要 PIN。 您可以设置它，以便任何人都可以拨入会议，并且系统不会提示输入 PIN 以启动会议。 可以使用管理中心为单个用户启用或禁用此设置。
  
如果有人从 Microsoft Teams 应用启动了会议，会议组织者不需要 PIN。 只有当会议组织者通过电话加入会议时，才需要 PIN。 为音频用户分配音频会议许可证并启用音频会议时，会议 PIN将发送给音频用户。 请参阅 [向用户发送](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 包含其音频会议信息的电子邮件，以及当用户的音频会议设置更改时 [自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>启用或禁用匿名呼叫者加入会议

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，单击"用户 **"。** 

2. 在列表中选择一个用户，然后单击 **页面顶部的"** 编辑"。 

3. 在 **音频会议** 旁边，单击 **编辑**。

4. 在 **"音频会议"** 窗格中，启用或禁用拨入呼叫者可以是 **会议的第一人**。
    
4. 单击“**应用**”。 

**使用Windows PowerShell**
  
有关详细信息， [请参阅 Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) 参考。

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 如果要重置 PIN，请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin-in-teams.md)
    
- 如果禁用了匿名访问，或者不需要 PIN 来启动会议：
    
  - 如果会议尚未开始 (则会议中还没有人) ：如果呼叫者是组织者，则系统将会提示呼叫者;如果说"是"，系统会提示他输入 PIN，输入 PIN 后，会议将开始，用户将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
- 如果启用了匿名访问，或者不需要 PIN 来启动会议：
    
  - 如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。 由于组织者的设置设置为"关"，会议将开始，匿名呼叫者将加入会议。
    
  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。
    
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。
  
## <a name="related-topics"></a>相关主题

[在 Microsoft 365 或 Office 365 中试用或购买音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)