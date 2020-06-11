---
title: 用户设置更改时向其发送的电子邮件
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
description: '了解在 Microsoft Teams 中当用户的电话拨入式会议设置更改时自动通过电子邮件向其发送的信息。 '
ms.openlocfilehash: 15c35570d509ae69a41e4c6d9522a5a62d32dd59
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691478"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>在 Microsoft Teams 中当用户设置更改时向其发送的电子邮件

当使用 Microsoft 作为音频会议提供商时，会自动向[启用了音频会议](set-up-audio-conferencing-in-teams.md)的用户发送电子邮件。

默认情况下，对于启用了音频会议的用户，向其发送的电子邮件共有四种类型。 但是，如果你要限制向用户发送的电子邮件数，你可以将其关闭。 在以下情况中，Microsoft 365 或 Office 365 中的音频会议将向用户的电子邮件发送电子邮件：

- **为用户分配了音频会议许可证时，或者你将音频会议提供商更改为 Microsoft 时。**

     此电子邮件包括会议 ID、默认的会议电话号码、用户的音频会议 PIN 以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。 请参阅[分配 Microsoft 团队附加许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)或[指定 microsoft 作为音频会议提供商](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

    > [!NOTE]
    > 如果贵组织已启用动态会议 ID，则用户安排的所有会议都将具有唯一的会议 ID。 你可以[在贵组织中设置音频会议动态 ID](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。 

    下面是此电子邮件示例：

     ![Skype for Business 验证许可证](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    若要了解有关许可的详细信息，请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- **更改了用户的会议 ID 或默认会议电话号码。**

    此电子邮件包括会议 ID、默认会议电话号码以及使用 Skype for Business Online 会议更新工具为用户更新现有会议的说明和链接。 但此电子邮件不包括用户的音频会议 PIN。 请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。

    下面是此电子邮件示例：

     ![电话拨入式会议信息已更改。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **重置了用户的音频会议 PIN。**

    此电子邮件包含组织者的音频会议 PIN、用户的现有会议 ID 和默认会议电话号码。 请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
    
     下面是此电子邮件示例：
    
     ![电话拨入式会议 PIN 已更改。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **用户的许可证被删除，或者音频会议提供商从 Microsoft 更改为其他提供商或“无”。**

    当从用户删除**音频会议**许可证或将音频会议提供商设置为 "**无**" 时，会发生这种情况。

    请参阅[分配或删除 Microsoft 365 for business 的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

    下面是此电子邮件的一个示例：

     ![电话拨入式会议已关闭。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>更改发送给用户的电子邮件

您可以对自动发送给用户的电子邮件进行更改。 默认情况下，电子邮件的发件人将来自 Microsoft 365 或 Office 365，但你可以使用 Windows PowerShell 更改显示名称。 有关详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果不想向用户发送电子邮件，又该怎样做？

当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。 在此情况下，会议 ID、默认会议电话号码和更重要的是，其音频会议 PIN 不会发送给用户。 发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。

默认情况下，将向你的用户发送电子邮件，但如果你希望阻止他们接收用于音频会议的电子邮件，则可以使用 Microsoft 团队或 Windows PowerShell。 

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在 "**会议桥**" 页面顶部，单击 "**桥接设置**"。 

3. 在**桥设置**窗格中，启用或禁用**如果其拨入设置发生更改，则自动向用户发送电子邮件**。

4. 单击“**保存**”。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**

有关详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。


## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

默认情况下，电子邮件的发件人将来自 Microsoft 365 或 Office 365，但你可以使用 Windows PowerShell 更改电子邮件地址和显示名称。 

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365，这可以在你有多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。


## <a name="related-topics"></a>相关主题

[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
