---
title: 在 Microsoft Teams 中重置音频会议 PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解你应该了解的 PIN 相关信息以及如何在 Microsoft Teams 中重置 PIN。 '
ms.openlocfilehash: 778e9841d3a355597b4b048d79bb62a144eed349
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568352"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>在 Microsoft Teams 中重置音频会议 PIN

PIN 是指为启用了音频会议的每个 Microsoft Teams 用户创建的由数字组成的代码。 音频会议 PIN 由会议组织者用于标识自己是会议组织者，并且会议组织者可以使用 PIN 通过电话启动会议。 如果他们使用 Microsoft Teams 应用启动会议，则不需要 PIN。 如果用户忘记了其 PIN，并且在启用音频会议时收到的电子邮件中找不到 PIN，管理员可以重置其 PIN，或者用户可以重置自己的 PIN。
  
当经过身份验证的用户使用 Microsoft Teams 应用加入时或者当组织者通过电话使用其 PIN 加入时，可以启动会议。 如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。 如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。

## <a name="reset-a-users-pin"></a>重置用户的 PIN

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，单击 "**用户**"，然后从可用用户列表中选择用户。

2. 单击 "**编辑**"。

3. 在 "**音频会议**" 下，单击 "**重置 PIN**"。

4. 单击 "**重置**"。
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>让用户重置其自己的 PIN

1. 让用户转到[https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。
2. 单击 "**重置 PIN**"。 


## <a name="what-else-should-you-know-about-pins"></a>你还应该知道有关 PIN 的哪些信息？

- 出于安全考虑，PIN 仅在重置时向管理员显示一次。 管理员重置 PIN 后，PIN 将被列为 * * * * * * * * *。
    
- 默认情况下启用 "自动向用户发送电子邮件"，用户在启用音频会议或 PIN 重置时，将收到一封电子邮件及其 PIN。 但是，如果您已禁用自动发送电子邮件，则 PIN 重置电子邮件不会发送给用户，您将必须手动向用户发送 PIN 信息。
    
- 当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议启动之前尝试加入会议，他们将进入会议厅并将收听保持音乐，当会议组织者通过电话使用 PIN 加入时，该会议将启动，会议厅中的参与者将加入会议。
    
- 默认设置是不允许匿名呼叫者启动会议。
    
- 当为用户启用音频会议时，默认情况下，会向他们发送包含会议信息的电子邮件及其 PIN 码。 用户必须拥有 Office 365 邮箱，因为当重置 PIN 时，将向用户发送电子邮件中的新 PIN，以发送到为用户设置的主 SMTP 地址（别名）。
    
- 设置音频会议时，设置您的组织中的 Pin 所需的数字。 PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。 如果您更改了 "引脚长度" 设置，则该设置仅应用于新生成的引脚，并且不会应用到已启用音频会议的现有用户的引脚设置。 请参阅[设置音频会议会议的 PIN 长度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。
    
- 默认情况下，电子邮件将设置为用户的 Office 365 主 SMTP 地址。 您可以向非 Office 365 地址（如 Hotmail 或 MSN 电子邮件地址）发送电子邮件。 你可以使用 Windows PowerShell 替代默认电子邮件地址。 如果用户在 Office 365 中没有 Exchange 邮箱，则此功能非常有用。

    

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
  
## <a name="related-topics"></a>相关主题

[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)
