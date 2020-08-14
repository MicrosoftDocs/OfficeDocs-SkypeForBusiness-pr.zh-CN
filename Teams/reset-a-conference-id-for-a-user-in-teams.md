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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 了解在 Microsoft Teams 中重置用户的会议 ID 以及获取会议更新和迁移工具链接的步骤。
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662122"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>在 Microsoft Teams 中重置用户的会议 ID

一个动态会议 ID 与呼叫者可用于拨入会议的拨入电话号码一起包含在会议邀请底部。 在用户拨打电话号码时，会议的自动助理会要求呼叫者输入此会议 ID 才能参加会议。
  
> [!NOTE]
> 会议 Id 是自动生成的，将在7-9 位之间，并且在为用户启用音频会议时设置。 **不支持静态会议 Id。** 

## <a name="resetting-the-conference-id-for-a-user"></a>重置用户的会议 ID

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 单击 " **编辑**"。

3. 在“**音频会议**”下，单击“**重置会议 ID**”。

2. 在“**重置会议 ID**”窗口中，单击“**重置**”。 将自动创建一个会议 ID，并向用户发送包含新会议 ID 的电子邮件。 默认情况下，将向用户发送电子邮件，但可以关闭此功能。   

    
> [!NOTE]
> 重置会议 ID 后，将向用户发送包含新会议 ID 的电子邮件。 此电子邮件将发送到主要电子邮件地址，在很多情况下，他们的 Microsoft 365 或 Office 365 邮箱。 该电子邮件包含新会议 ID、默认拨入电话号码以及更新现有会议的说明。 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>我还应该了解哪些信息？

- 你可以在“**音频会议**”部分针对用户单击“**通过电子邮件发送会议信息**”，通过电子邮件向用户发送所有会议信息（包括会议 ID 和拨入电话号码）。 它不会发送 PIN。
    
- 7-9 位会议 ID 由团队服务创建。 您不能更改其长度。
    
- 重置之后，你可以看到新会议 ID 列在" **会议 ID**"下方。
    
- [!重要信息]  创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365，这可以在你有多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
    
## <a name="related-topics"></a>相关主题

[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)
