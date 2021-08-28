---
title: 在 Skype for Business Online 中查看、更改和重置分配给用户的会议 ID
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解如何在 Skype for Business Online 中向用户分配会议 ID，以及会议 ID 参数应是什么。 '
ms.openlocfilehash: c8c3abcf515a0a60046cd2438833467b8be78231
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607669"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>查看和重置 Skype for Business Online​  中分配给用户的会议 ID

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有关用户在 Microsoft Teams 会议 ID 的信息，请参阅在 Microsoft Teams 中查看[和重置分配给Microsoft Teams。](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

在 Microsoft 365 或 Office 365 中为音频会议设置会议并将 Microsoft 用作音频会议提供商时，会议 Skype for Business ID 将自动分配给Office 365用户。 安排会议时，将在会议邀请中发送分配的会议 ID。 用户安排的每次会议将分配到一个唯一的会议 id。

尽管会议 ID 将自动创建并分配给用户，但有时用户可能不想使用此 ID，而你想要将其设置为特定号码，或者用户记不起来或已丢失其会议 ID。 可以使用 **Skype for Business 管理中心** 和 Windows PowerShell 来查看、更改和重置其会议 ID。

电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。 有关重置会议组织者 PIN 的详细信息，请[转到此处](reset-a-conference-id-for-a-user.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>查看和重置会议 ID

### <a name="to-view-the-conference-id"></a>查看会议 ID

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

可以查看他们的会议 ID，并将其发送给用户。

1. 使用工作或学校帐户登录。

2. 转到管理中心 **> Skype for Business。**

3. 在 **Skype for Business 管理中心**> **音频会议** > **用户**，选择需要会议 ID 的用户。

4. 在操作页面，查看 **会议 ID** 下方。

    > [!TIP]
    > 在"用户"页面上选择用户后，您可以通过单击"通过电子邮件发送会议信息"链接，在包含会议 ID 和音频电话号码的电子邮件中向用户发送所有 **会议信息。**

**使用Windows PowerShell**

可以使用 Windows PowerShell 来查看用户的会议 ID。 为此，请运行：

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

若要详细了解 cmdlet，请参阅[Get-CsOnlineDialInConferencingUser。](/powershell/module/skype/Get-CsOnlineDialInConferencingUser)


### <a name="to-reset-the-conference-id"></a>重置会议 ID

例如，如果用户忘记了密码，你可以为其重置会议 ID。

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

1. 使用工作或学校帐户登录。

2. 转到管理中心 **> Skype for Business。**

3. 在Skype for Business **管理** 中心"音频会议用户"中，在"会议 ID"下的"操作"窗格中 >    >  ，单击"重置 **"。** 

4. 在"**重置会议 ID？"** 窗口中，单击"**是"。** A conference ID will be automatically created and an email sent to the user with the new conference ID.

**使用Windows PowerShell**

可以通过使用 Windows PowerShell 重置用户的会议 ID。 为此，请运行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

   > [!IMPORTANT]
   >  新建会议 ID 或重置会议 ID 后，呼叫者将不能使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用会议Skype for Business工具来更新其现有会议。 若要了解如何下载、安装和运行该工具，请参阅：适用于 Skype for Business 和[Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)的会议更新工具、Skype for Business Online、会议迁移工具[ (64](https://go.microsoft.com/fwlink/?LinkID=626047)位) 和 Skype for Business Online 会议迁移工具[ (32](https://www.microsoft.com/download/details.aspx?id=54079)位) 。

- 请参阅 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 以了解有关 cmdlet 的更多信息。

- 会议 ID 必须符合音频会议网桥上设置的位数长度。 不能对会议 ID 使用字母或特殊字符;只能使用数字。

- 默认情况下，所有音频会议用户的会议 ID 将为 9 位，不能更改位数。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。 使用 Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365 Skype for Business Online，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell比仅使用 Microsoft 365 管理中心（例如，一次对许多用户进行设置更改时）在速度、简单性和工作效率方面具有许多优势。 通过以下主题了解这些优势：

  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
