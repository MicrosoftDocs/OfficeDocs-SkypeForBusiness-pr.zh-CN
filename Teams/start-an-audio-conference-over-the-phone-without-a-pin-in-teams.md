---
title: 在 Teams 中不带 PIN 的手机启动音频会议
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '了解如何从 Teams 管理中心启用或禁用匿名呼叫者加入会议。 '
ms.openlocfilehash: a858c95527d09e24004d025787bee52c0de84705
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641943"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>在 Microsoft Teams 中在没有 PIN 的情况下通过电话启动音频会议

由于 Microsoft Teams 会议组织者尚未启动会议，因此拨入会议的用户在会议大厅中收听音乐可能会令人沮丧。
  
如果会议组织者默认调用会议，则需要 PIN 才能启动会议。 你可以设置它，以便任何人都可以拨入会议，而不会提示 PIN 启动会议。 可以使用管理中心为单个用户启用或禁用此设置。
  
如果某人已从 Microsoft Teams 应用启动会议，则会议组织者不需要 PIN。 只有当会议组织者通过电话加入会议时，才需要 PIN。 为会议分配 **音频会议** 许可证并启用音频会议时，会将会议 PIN 发送给音频用户。 请参阅 [向用户发送电子邮件，其中包含其音频会议信息](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 以及 [在用户的音频会议设置更改时自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>启用或禁用匿名呼叫者加入会议

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，单击 **“用户**”。

2. 在列表中选择用户，然后单击页面顶部的 **“编辑** ”。

3. 在 **音频会议** 旁边，单击 **编辑**。

4. 在 **“音频会议”** 窗格中，启用或禁 **用拨入呼叫者可以是会议中的第一个人**。

5. 单击“**应用**”。

### <a name="using-windows-powershell"></a>使用 Windows PowerShell

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps) 。

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 如果要重置 PIN，请参阅 [重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。

- 如果禁用匿名访问或不要求 PIN 启动会议：

  - 如果会议尚未开始 (会议中还没有人) ：如果呼叫者是组织者，将提示呼叫者：如果他说是，系统会提示他输入 PIN，输入 PIN 后，会议将开始，用户将加入会议。

  - 如果会议已启动（有人已在会议中）：如果呼叫者是组织者，则不会提示您提供 PIN；会议已启动，并将呼叫者将加入。

- 如果启用了匿名访问或不需要 PIN 来启动会议，

  - 如果尚未启动会议（还没有会议）：如果呼叫者是组织者，将不会收到提示，并且从不提示她提供 PIN。 由于组织者的设置已设置为“关闭”，因此会议将开始，匿名呼叫者将加入会议。

  - 如果会议已经开始 (其他人已经在会议) ：如果呼叫者是组织者，则不会提示呼叫者，并且她永远不会被提示输入 PIN;会议已开始，调用方将加入会议。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 借助Windows PowerShell，可以使用单个管理点来管理 Microsoft 365 或 Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。
  
## <a name="related-topics"></a>相关主题

[尝试或购买 Microsoft 365 for Microsoft Teams 中的音频会议](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
