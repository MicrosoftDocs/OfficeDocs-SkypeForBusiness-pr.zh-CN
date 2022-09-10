---
title: 用户设置更改时向其发送的电子邮件
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '了解当用户的电话拨入式会议设置在 Microsoft Teams 中发生更改时，通过电子邮件自动向用户发送哪些信息。 '
ms.openlocfilehash: b2ebb07562300a02058f3bfeaad103347299ba0c
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642133"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>在 Microsoft Teams 中当用户设置更改时向其发送电子邮件

电子邮件将自动发送给使用 Microsoft 作为音频会议提供商 [启用音频](set-up-audio-conferencing-in-teams.md) 会议的用户。

默认情况下，有四种类型的电子邮件将发送给已启用音频会议的用户。 但是，如果要限制向用户发送的电子邮件数，你可以将其关闭。 Microsoft 365 或 Office 365 中的音频会议将在以下情况下向用户的电子邮件发送电子邮件：

- **向他们分配音频会议许可证，或者将音频会议提供商更改为 Microsoft 时。**

     此电子邮件包括会议 ID、会议的默认会议电话号码、用户的音频会议 PIN，以及使用用于更新用户现有会议的 Teams 会议更新工具的说明和链接。 请参阅 [分配 Microsoft Teams 加载项许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

    > [!NOTE]
    > [!注释] 如果你的组织已启用动态会议 ID，用户安排的所有会议将具有唯一的会议 ID。 有关详细信息，请查看 [视图并重置在 Microsoft Teams 文章中分配给用户的会议 ID](see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams.md) 。

    下面是此电子邮件的一个示例：

     ![Teams 验证许可证。](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    若要了解有关许可的详细信息，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- **会议 ID 或用户默认会议电话号码更改。**

    此电子邮件包含会议 ID、默认会议电话号码，以及使用用于更新用户现有会议的 Teams 会议更新工具的说明和链接。 但此电子邮件不包括用户的音频会议 PIN。 请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。

    下面是此电子邮件的一个示例：

     ![电话拨入式会议信息已更改。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **重置用户的音频会议 PIN。**

    此电子邮件包含组织者的音频会议 PIN、现有会议 ID 和用户的默认会议电话号码。 请参阅 [“重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)”。

     下面是此电子邮件的一个示例：

     ![电话拨入式会议 PIN 已更改。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **当音频会议提供商从 Microsoft 更改为其他提供商或 None 时，将删除用户的许可证。**

    从用户中删除 **音频会议** 许可证或将音频会议提供商设置为 **None** 时，会发生这种情况。

    请参阅 [分配或删除 Microsoft 365 商业版许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

    下面是此电子邮件的一个示例：

     ![电话拨入式会议已关闭。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>更改发送给用户的电子邮件

可以对自动发送给用户的电子邮件进行更改。 默认情况下，电子邮件的发件人来自 Microsoft 365 或Office 365，但可以使用Windows PowerShell更改显示名称。 有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps) 。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>如果不想向用户发送电子邮件，又该怎样做？

当禁用电子邮件发送给用户时，即使用户拥有分配的许可证，也不会向其发送电子邮件。 在这种情况下，会议 ID、默认会议电话号码，更重要的是，其音频会议 PIN 不会发送给用户。 发生这种情况时，你必须通过向用户发送单独的电子邮件或呼叫他们进行通知。

默认情况下，电子邮件将发送给用户，但如果要阻止用户接收音频会议的电子邮件，可以使用 Microsoft Teams 或Windows PowerShell。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 在 **“会议桥** ”页的顶部，单击 **“桥”设置**。

3. 在 **“桥”设置** 窗格 **中，如果用户的拨入设置发生更改，则启用或禁用自动向用户发送电子邮件**。

4. 单击“**保存**”。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>使用 Windows PowerShell

还可以使用 Microsoft Teams PowerShell 模块并运行：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 管理组织的其他设置，包括电子邮件。

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps) 。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

默认情况下，电子邮件的发件人来自 Microsoft 365 或Office 365，但你可以使用Windows PowerShell更改电子邮件地址和显示名称。

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用单个管理点来管理 Microsoft 365 或 Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Office 365 的最佳方式](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。

## <a name="related-topics"></a>相关主题

[启用或禁用发送电子邮件时更改音频会议设置](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
