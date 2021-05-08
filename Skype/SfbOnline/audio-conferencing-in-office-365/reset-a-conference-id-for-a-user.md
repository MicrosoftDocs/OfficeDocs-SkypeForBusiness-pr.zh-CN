---
title: 在 Skype for Business Online 中重置用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解在 Skype for Business Online 中重置用户的会议 ID 的步骤，并获取会议更新和迁移工具的链接。 '
ms.openlocfilehash: 24037de3849ae54920777636e7eb745671ae2f57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237768"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>在 Skype for Business Online 中重置用户的会议 ID

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> 有关重置 Microsoft Teams 中的会议 ID 的信息，请参阅[在 Microsoft  Teams 中重置用户的会议 ID](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)。

会议邀请底部包含动态会议 ID，以及呼叫者可用于拨入会议的拨入电话号码。 当用户拨打电话号码时，会议的自动助理将要求呼叫者输入此会议 ID，以便他们可以参加会议。
  
> [!NOTE]
> 如果会议提供商是 Microsoft，则用户的会议 ID 设置为"仅动态"。 这无法更改。 仅为启用音频会议的 Skype for Business 用户自动设置会议 ID。 

## <a name="resetting-the-conference-id-for-a-user"></a>重置用户的会议 ID
   
1. 在Skype for Business管理中心中，单击"音频会议用户"，选择一个用户，然后在"会议 **ID"** 下的"操作"窗格中单击  >  "重置 **"。** 
    
2. 在"**重置会议 ID？"** 窗口中，单击"**是"。** A conference ID will be automatically created and an email sent to the user with the new conference ID. 默认情况下，电子邮件将发送给用户，但可以将其关闭。
    
> [!NOTE]
> [!注释] 重置会议 ID 后，会向用户发送包含新会议 ID 的电子邮件。 在许多情况下，此电子邮件将发送到主电子邮件地址，包括Microsoft 365 Office 365邮箱。 电子邮件中包含新的会议 ID、默认拨入电话号码以及使用 Skype for Business 会议更新工具更新现有会议的说明。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 您可以通过在"操作"窗格中单击"通过电子邮件发送会议信息"，在包含会议 ID 和拨入电话号码的电子邮件中向用户发送所有会议信息。 它不会发送 PIN。
    
- 会议 ID 将包含 7 个数字，并且不能更改其Skype for Business管理中心或Windows PowerShell。
    
- 重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。
    
- 当你在"用户"页面上选择用户时，可以在"音频会议"下的"操作"窗格底部查看音频会议 **用户的会议** ID。
    
- [!重要信息]  创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用Skype for Business工具来更新其现有会议。 若要了解如何下载、安装和运行会议Skype for Business工具，请参阅：
    
  - [Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online、会议迁移工具（64 位）](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online、会议迁移工具（32 位）](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。 使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。 通过以下主题了解这些优势：
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相关主题

[重置音频会议 PIN](reset-the-audio-conferencing-pin.md)
