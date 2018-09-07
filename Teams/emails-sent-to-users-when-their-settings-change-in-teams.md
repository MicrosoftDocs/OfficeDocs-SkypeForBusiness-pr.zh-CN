---
title: 在 Microsoft 团队中更改其设置时向用户发送的电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: '了解有关哪些信息将自动发送给用户通过电子邮件时的 Microsoft 团队中更改其电话拨入式会议设置。 '
ms.openlocfilehash: a352ecb335469e1e988c625f638c6136675dc5fc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23871043"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>在 Microsoft 团队中更改其设置时向用户发送的电子邮件

电子邮件将自动发送到[启用了音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)用户使用 Microsoft 作为音频会议提供商。
  
默认情况下，有四种类型的电子邮件将发送到您的用户启用了音频会议。 但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。 Office 365 中的音频会议将向用户发送电子邮件时的电子邮件：
  
- **音频会议许可证分配给它们或您要更改为 Microsoft 的音频会议提供商。**
    
     此电子邮件包括会议 ID，会议，音频会议的用户和链接说明要用于业务在线会议更新工具，用来更新现有会议的 Skype 的 PIN 的默认会议电话号码用户。 请参阅[业务和 Microsoft 团队许可证分配 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[分配 Microsoft 作为音频会议提供商](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。
    
    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 您可以设置[您的组织中的音频会议动态 Id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。 
  
    下面是此电子邮件的一个示例：
    
     ![Skype for Business 验证许可证](media/audio-conferencing-user-enabled.png)
  
    您可以找到有关许可查看[Skype 业务和 Microsoft 团队加载项授权的](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)更多信息。
    
- **会议 ID 或用户默认会议电话号码更改。**
    
    此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。 但此电子邮件不包括用户的音频会议 PIN。 请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议信息已更改。](media/audio-conferencing-info-change.png)
  
- **音频会议用户的 PIN 重置。**
    
    此电子邮件包含组织者的音频会议 PIN、 现有会议 ID 和用户的默认会议电话号码。 请参阅[重置 PIN 的音频会议](reset-the-audio-conferencing-pin-in-teams.md)。
    
  
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议 PIN 已更改。](media/audio-conferencing-pin-has-changed.png)
  
- **删除用户的许可证或音频会议提供商更改时 microsoft 到其他提供程序或无。**
    
    **音频会议**许可证时将删除来自用户或从 Microsoft 更改用户的音频会议提供商，为第三方音频会议提供商时或设置为**无**的提供程序时，将发生这种情况。 此电子邮件包含说明和信息的用户使用的业务联机会议更新工具 Skype 删除音频会议的特定信息，例如默认会议电话号码或会议 id。
    
    请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
    
    下面是此电子邮件的一个示例：
    
     ![电话拨入式会议已关闭。](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>更改发送给用户的电子邮件

您可以对会自动向用户的电子邮件地址和*从*联系人信息中包括的显示名称包括发送的电子邮件进行更改。 默认情况下，发件人的电子邮件将从 Office 365 中，但您可以更改的电子邮件地址，并且可以显示使用 Windows PowerShell 的名称。 请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果不想向用户发送电子邮件，又该怎样做？

当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。 在此情况下，会议 ID，默认会议电话号码，以及更重要的是，将不会向用户发送其音频会议 PIN。 发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。
  
默认情况下将电子邮件发送给用户，但如果您想要阻止发送电子邮件的音频会议，则可以使用的 Microsoft 团队或 Windows PowerShell。 

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其电话拨入式设置更改**。

4. 单击" **保存**"。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
**使用 Windows PowerShell**
  
请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。
  

## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

默认情况下，发件人的电子邮件将从 Office 365 中，但您可以更改的电子邮件地址，并且可以显示使用 Windows PowerShell 的名称。 

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。
  
  
## <a name="related-topics"></a>相关主题

[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
