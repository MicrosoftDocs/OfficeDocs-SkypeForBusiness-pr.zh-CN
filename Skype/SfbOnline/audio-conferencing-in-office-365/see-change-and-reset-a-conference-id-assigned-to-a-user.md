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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解如何在 Skype for Business Online 中向用户分配会议 ID，以及会议 Id 参数应该是什么。 '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643602"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>查看和重置 Skype for Business Online​  中分配给用户的会议 ID

> [!Note]
> 有关 Microsoft 团队中的用户会议 Id 的信息，请参阅[查看和重置 Microsoft 团队中分配给用户的会议 ID](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)。

当为 Microsoft 365 或 Office 365 中的音频会议设置了会议 ID 并使用 Microsoft 作为音频会议提供商时，它会自动分配给 Skype for business 用户。在安排会议时，将在会议邀请中发送分配的会议 ID。用户安排的每个会议都将分配一个唯一的会议 ID。

Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.

An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>查看和重置会议 ID

### <a name="to-view-the-conference-id"></a>查看会议 ID

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

可以查看他们的会议 ID，并将其发送给用户。

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype For business**。

3. 在 **Skype for Business 管理中心**> **音频会议** > **用户**，选择需要会议 ID 的用户。

4. 在操作页面，查看**会议 ID** 下方。

    > [!TIP]
    > 在 "**用户**" 页面上选择用户后，通过单击 "**通过电子邮件发送会议信息**" 链接，可以在包含会议 ID 和音频电话号码的电子邮件中向用户发送所有会议信息。

**使用 Windows PowerShell**

You can use Windows PowerShell to view the conference ID for a user. To do so, run:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

请参阅[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 )以了解有关 cmdlet 的详细信息。


### <a name="to-reset-the-conference-id"></a>重置会议 ID

例如，如果用户忘记了密码，你可以为其重置会议 ID。

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype For business**。

3. 在**Skype for business 管理中心** >  **音频会议**  >  **用户**的 "操作" 窗格中的 "**会议 ID**" 下，单击 "**重置**"。

4. 在 "**重置会议 ID？** " 窗口中，单击 **"是"**。 A conference ID will be automatically created and an email sent to the user with the new conference ID.

**使用 Windows PowerShell**

可以通过使用 Windows PowerShell 重置用户的会议 ID。 若要执行此操作，请运行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

   > [!IMPORTANT]
   >  在创建新的会议 ID 或重置一个会议 ID 后，呼叫者无法使用旧的会议 id。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用 Skype for Business 会议迁移工具更新其现有会议。 若要了解如何下载、安装和运行该工具，请参阅： [skype for business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype for Business Online、会议迁移工具 (64 位) ](https://go.microsoft.com/fwlink/?LinkID=626047)和 Skype For Business [online、会议迁移工具 (32 位) ](https://www.microsoft.com/download/details.aspx?id=54079)。

- 请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。

- 会议 ID 必须满足在音频会议网桥上设置的数字长度。 您不能在会议 Id 中使用字母或特殊字符;只能使用数字。

- 默认情况下，所有音频会议用户的会议 ID 均为9个数字，并且位数不能更改。


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。 使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365 和 Skype for business Online，这样你有多个任务可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [为什么需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。 通过以下主题了解这些优势：

  - [通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题

[在 Microsoft 365 或 Office 365 中试用或购买音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

