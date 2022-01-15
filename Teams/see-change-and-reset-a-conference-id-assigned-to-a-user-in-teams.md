---
title: 查看、更改和重置用户的会议 ID
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
- seo-marvel-apr2020
description: 了解如何向用户分配会议 ID Microsoft Teams会议 ID 参数应是什么。
ms.openlocfilehash: 89b74dc97206f064cd88c30e69ed4b3752c19e08
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055128"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>查看和重置分配给用户的会议 ID Microsoft Teams

在 Microsoft 365 或 Office 365 中为音频会议设置 Microsoft Teams 并且使用 Microsoft 作为音频会议提供商时，会议 ID 会自动分配给他们。 安排会议时，将在会议邀请中发送分配的会议 ID。 用户安排的每次会议将分配到一个唯一的会议 id。
  
尽管会议 ID 将自动创建并分配给用户，但有时用户可能不想使用此 ID，而你想要将其设置为特定号码，或者用户记不起来或已丢失其会议 ID。 您可以使用Microsoft Teams中心或Windows PowerShell查看、更改和重置其会议 ID。
  
电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。 若要[详细了解如何重置会议组织者的 PIN，请参阅](reset-a-conference-id-for-a-user-in-teams.md)重置 Microsoft Teams 中的用户的会议 ID。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>查看和重置会议 ID

### <a name="to-view-the-conference-id"></a>查看会议 ID

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>使用管理中心查看Microsoft Teams ID

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 在页面的顶部，单击 **编辑**。

3. 在 **"音频会议"下**，查看"会议 **ID"下**。

    > [!TIP]
    > 您可以通过单击"在电子邮件中发送会议信息"链接，在包含会议 ID 和音频电话号码的电子邮件中向用户 **发送所有会议** 信息。
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>使用会议 ID Windows PowerShell

有关详细信息[，Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)参考。

### <a name="to-reset-the-conference-id"></a>重置会议 ID

例如，如果用户忘记了密码，你可以为其重置会议 ID。
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>使用管理中心重置Microsoft Teams ID

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 在页面的顶部，单击 **编辑**。

3. 在 **"音频会议"下**，单击"**重置会议 ID"。**

4. 在"**重置会议 ID"窗口中**，单击"重置 **"。** A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>使用"会议 ID"重置Windows PowerShell

有关详细信息[，Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)参考。

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

> [!IMPORTANT]
> 新建会议 ID 或重置会议 ID 后，呼叫者将不能使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。

- 会议 ID 必须符合音频会议网桥上设置的位数长度。 不能对会议 ID 使用字母或特殊字符;只能使用数字。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，Microsoft 365 Office 365单点管理来管理任务或任务，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。

## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
