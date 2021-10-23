---
title: 在 Microsoft Teams 中重置用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
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
description: 了解重置用户会议 ID 的步骤，Microsoft Teams会议更新和迁移工具的链接。
ms.openlocfilehash: 3a308be01f84509ea93793d7c2b1bdfd6e084268
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536483"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>在 Microsoft Teams 中重置用户的会议 ID

会议邀请底部包含动态会议 ID，以及呼叫者可用于拨入会议的拨入电话号码。 当用户拨打电话号码时，会议的自动助理将要求呼叫者输入此会议 ID，以便他们可以参加会议。
  
> [!NOTE]
> 会议 ID 将自动生成，介于 7-9 位数之间，并且会在为用户启用音频会议时设置。 **不支持静态会议 ID。** 

## <a name="resetting-the-conference-id-for-a-user"></a>重置用户的会议 ID

 **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 单击"**编辑"。**

3. 在"**音频会议"下，** 单击 **"重置会议 ID"。**

2. 在"**重置会议 ID"窗口中**，单击"重置 **"。** A conference ID will be automatically created and an email sent to the user with the new conference ID. 默认情况下，电子邮件将发送给用户，但可以将其关闭。   
    
> [!NOTE]
> [!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。 此电子邮件将发送到主要电子邮件地址，在许多情况下，会发送到Microsoft 365或Office 365邮箱。 电子邮件包含新的会议 ID、默认拨入电话号码 (以及) 现有会议的说明。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 您可以通过在"音频会议"部分中单击"在电子邮件中为用户发送会议信息"，在包含会议 ID 和拨入电话号码的电子邮件中向用户发送 **所有会议** 信息。 它不会发送 PIN。
    
- 由服务创建一个 7-9 位数Teams ID。 不能更改其长度。
    
- 重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。
    
- [!重要信息]  创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，Microsoft 365 Office 365单点管理来管理任务或任务，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps&preserve-view=true)了解详细信息。
    
## <a name="related-topics"></a>相关主题

[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)