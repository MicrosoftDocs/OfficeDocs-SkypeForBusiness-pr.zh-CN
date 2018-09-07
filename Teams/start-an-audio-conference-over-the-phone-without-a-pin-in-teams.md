---
title: 开始音频会议中的 Microsoft 团队 PIN 不电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何启用或禁用匿名呼叫者加入会议从团队管理中心。 '
ms.openlocfilehash: f85cd3e2ae0c1f87810f5b5312ba8bc9dc9d34c9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861040"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>开始音频会议中的 Microsoft 团队 PIN 不电话

可能会干扰拨入会议以将其保留在收听音乐，因为 Microsoft 团队会议组织者尚未启动会议的会议的会议厅中的用户。 
  
如果会议组织者在调用会议，默认情况下，启动会议需要 PIN。 您可以将它设置以便任何人都可以拨号加入会议并不会提示输入 PIN 才能启动会议。 您可以使用管理中心启用或禁用此设置为单个用户。
  
PIN 不需要会议组织者，如果某人具有来自 Microsoft 团队应用程序启动会议。 只有当会议组织者通过电话加入会议时，才需要 PIN。 已分配的**音频会议**许可证并启用了音频会议时，将向音频用户发送会议的 PIN。 请参阅[发送对其进行音频会议信息的用户电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)和[自动发送给其音频会议设置更改时的用户的电子邮件](emails-sent-to-users-when-their-settings-change-in-teams.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>启用或禁用匿名呼叫者加入会议

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**。 

2. 在列表中，选择一个用户，然后单击页面顶部的**编辑**。 

3. **音频会议**，旁边单击**编辑**。

4. 在**音频会议**窗格中，启用或禁用**未经身份验证的呼叫者可以在会议中的第一个人**。
    
4. 单击" **保存**"。 

**使用 Windows Powershell**
  
请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 如果您想要重置 PIN，请参阅[重置的音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
    
- 如果启用了匿名访问，或不需要 PIN 才能启动会议时，:
    
  - 如果尚未启动会议 （没有一种-会议尚未）： 将提示呼叫者，如果他是组织者;如果他说是时，他将提示您为其 PIN，他输入 PIN 之后，会议的开始和用户将加入会议。
    
  - 如果会议已启动 （人已在会议中）： 如果他是组织者和他将永远不会提示您提供 PIN; 不会提示呼叫者会议已启动，并将呼叫者将对其进行联接。
    
- 如果禁用匿名访问，或不需要 PIN 才能开始会议，则：
    
  - 如果尚未启动会议 （没有一种-会议尚未）： 如果她是组织者，并且用户将从不提示您提供 PIN，不会提示呼叫者。 组织者的设置设置为关闭，因为会议将启动，匿名呼叫者将加入会议。
    
  - 如果会议已启动 （人已在会议中）： 如果她是组织者，并且用户将从不提示您的 PIN，将不提示呼叫者; 会议已启动，并呼叫者将对其进行联接。
    
## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
