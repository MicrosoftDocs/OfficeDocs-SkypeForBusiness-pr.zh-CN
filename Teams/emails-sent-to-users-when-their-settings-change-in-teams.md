---
title: 在 Microsoft Teams 中当用户设置更改时向其发送的电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解在 Microsoft Teams 中当用户的电话拨入式会议设置更改时自动通过电子邮件向其发送的信息。 '
ms.openlocfilehash: 67e4945095b9ed7e69632741e04b4ac384741feb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245095"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>在 Microsoft Teams 中当用户设置更改时向其发送的电子邮件

当使用 Microsoft 作为音频会议提供商时，会自动向[启用了音频会议](set-up-audio-conferencing-in-teams.md)的用户发送电子邮件。

默认情况下，对于启用了音频会议的用户，向其发送的电子邮件共有四种类型。 但是，如果你要限制向用户发送的电子邮件数，你可以将其关闭。 在下列情况下，Office 365 中的音频会议将向用户发送电子邮件：

- **为用户分配了音频会议许可证时，或者你将音频会议提供商更改为 Microsoft 时。**

     此电子邮件包括会议 ID、默认的会议电话号码、用户的音频会议 PIN 以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。 请参阅[分配的 Microsoft 团队许可证](assign-teams-licenses.md)或[分配 Microsoft 作为音频会议提供商](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

    > [!NOTE]
    > 如果贵组织已启用动态会议 ID，则用户安排的所有会议都将具有唯一的会议 ID。 你可以[在贵组织中设置音频会议动态 ID](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。 

    下面是此电子邮件示例：

     ![Skype for Business 验证许可证](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    若要了解有关授权的详细信息，请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- **更改了用户的会议 ID 或默认会议电话号码。**

    此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。 但此电子邮件不包括用户的音频会议 PIN。 请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。

    下面是此电子邮件示例：

     ![电话拨入式会议信息已更改。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **重置了用户的音频会议 PIN。**

    此电子邮件包含组织者的音频会议 PIN、用户的现有会议 ID 和默认会议电话号码。 请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
    
     下面是此电子邮件示例：
    
     ![电话拨入式会议 PIN 已更改。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **用户的许可证被删除，或者音频会议提供商从 Microsoft 更改为其他提供商或“无”。**

    在删除了用户的**音频会议**许可证，或者将用户的音频会议提供商从 Microsoft 更改为第三方音频会议提供商，或将提供商设置为“**无**”时，会发生这种情况。 此电子邮件包含用户使用 Skype for Business Online 会议更新工具删除音频会议特定信息（例如默认会议电话号码或会议 ID）的说明和信息。

    请参阅[分配或删除 Office 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

    下面是此电子邮件示例：

     ![电话拨入式会议已关闭。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>更改向用户发送的电子邮件

您可以对会自动向用户发送的电子邮件进行更改。 默认情况下的电子邮件发件人将从 Office 365，但您可以更改使用 Windows PowerShell 的显示名称。 有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果不希望向用户发送电子邮件该怎么办？

禁用向用户发送电子邮件时，即使为用户分配了许可证，也不会发送电子邮件。 在此情况下，不会向用户发送会议 ID、默认会议电话号码，以及更重要的是，他们的音频会议 PIN。 发生这种情况时，你必须通过向用户发送单独的电子邮件或给他们打电话进行通知。

默认情况下，将向你的用户发送电子邮件，但如果你不希望他们收到音频会议的电子邮件，可使用 Microsoft Teams 或 Windows PowerShell。 

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。

4. 单击“**保存**”。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。


## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

默认情况下，这些电子邮件的发件人将显示为来自 Office 365，但你可以使用 Windows PowerShell 更改电子邮件地址和显示名称。 

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：

  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。


## <a name="related-topics"></a>相关主题

[启用或禁用在音频会议设置更改时发送电子邮件](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
