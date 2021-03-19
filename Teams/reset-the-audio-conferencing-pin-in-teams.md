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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 了解如何在 Microsoft Teams 中重置用户的音频会议 PIN，并了解有关 PIN 的重要事实。
ms.openlocfilehash: 1ee3360668084bf6bf99b3ede25584ce9800dd5b
ms.sourcegitcommit: b4b2c7e79679cce6cf5f863ddf708e50164f9a9d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50861436"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>在 Microsoft Teams 中重置音频会议 PIN

PIN 是由为启用了音频会议的每个 Microsoft Teams 用户创建的号码所创建的代码。 音频会议 PIN 由会议组织者用来标识他们是会议组织者并允许他们通过电话启动会议。 如果他们使用 Microsoft Teams 应用启动会议，则不需要 PIN。 如果用户忘记了 PIN，在启用音频会议时发送给他们的电子邮件中找不到 PIN，则管理员可以重置其 PIN，也可以重置自己的 PIN。
  
当经过身份验证的用户使用 Microsoft Teams 应用加入时，或者当组织者通过电话使用 PIN 加入时，可以开始会议。 如果会议要求提供 PIN 才能启动，则通过电话加入会议的所有用户都将进入会议厅并将收听保持音乐，直至会议启动。 如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。

## <a name="reset-a-users-pin"></a>重置用户的 PIN

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 单击"**编辑"。**

3. 在 **"音频会议"下**，单击"**重置 PIN"。**

4. 单击"**重置"。**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>让用户重置其自己的 PIN

1. 让用户转到 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 。
2. 单击"**重置 PIN"。** 

> [!NOTE]
> 对于 GCCH，请转到 https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing ：。

## <a name="what-else-should-you-know-about-pins"></a>你还应该知道有关 PIN 的哪些信息？

- 出于安全目的，PIN 仅在重置 PIN 时向管理员显示一次。 管理员重置 PIN 后，PIN 将列为 ***********。
    
- 默认情况下，会自动向用户发送电子邮件，并且当用户启用音频会议或重置 PIN 时，将收到一封包含其 PIN 的电子邮件。 但是，如果已禁用自动发送电子邮件，则 PIN 重置电子邮件不会发送给用户，您必须手动将 PIN 信息发送给用户。
    
- 当会议启动时，会议厅中的所有用户都将自动加入该会议。 例如，如果两个参与者在会议开始之前尝试加入会议，他们将进入会议厅并收听保持音乐，当会议组织者通过电话使用其 PIN 加入时，会议将开始，会议厅中的参与者将加入会议。
    
- 默认设置是不允许匿名呼叫者启动会议。
    
- 当你为用户启用音频会议时，默认情况下会向用户发送包含会议信息和 PIN 的电子邮件。 用户必须具有 Microsoft 365 或 Office 365 邮箱，因为重置 PIN 时，将在电子邮件中向用户发送新的 PIN，并发送到用户设置的主要 SMTP 地址 (别名) 。
    
- 设置音频会议时，设置组织中 PIN 所需的数字。 PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。 如果更改 PIN 长度设置，该设置将仅应用于新生成的 PIN，不会应用于为音频会议启用的现有用户的 PIN 设置。 请参阅 [设置音频会议 PIN 的长度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。
    
- 默认情况下，电子邮件将设置为用户的 Microsoft 365 或 Office 365 主 SMTP 地址。 您可以向非 Microsoft 365 或非 Office 365 地址（如 Hotmail 或 MSN 电子邮件地址）发送电子邮件。 可以使用默认电子邮件地址替代Windows PowerShell。 如果用户在 Microsoft 365 或 Office 365 中没有 Exchange 邮箱，此功能非常有用。

    

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
  
## <a name="related-topics"></a>相关主题

[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)
