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
description: 了解如何向 Microsoft Teams 中的用户分配会议 ID，以及会议 ID 参数应是什么。
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642113"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>在 Microsoft Teams 中查看和重置分配给用户的会议 ID

在 Microsoft 365 或 Office 365中为音频会议设置会议并使用 Microsoft 作为音频会议提供商时，会自动将会议 ID 分配给 Microsoft Teams 用户。 安排会议时，会在会议邀请中发送分配的会议 ID。 用户安排的每次会议将分配到一个唯一的会议 id。
  
尽管会自动创建会议 ID 并将其分配给用户，但有时用户可能不想使用此 ID，而你想要将其设置为特定数字，或者用户无法记住或丢失其会议 ID。 可以使用 Microsoft Teams 管理中心或Windows PowerShell查看、更改和重置其会议 ID。
  
电子邮件将发送到有会议 ID 的用户和默认音频会议电话号码，或者，如果重置的会议 ID，将发送一封不同的电子邮件，其将包括会议 ID，但没有 PIN。 有关如何重置会议组织者 PIN 的详细信息，请参阅 [Microsoft Teams 中用户的“重置会议 ID](reset-a-conference-id-for-a-user-in-teams.md) ”。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>查看和重置会议 ID

### <a name="to-view-the-conference-id"></a>查看会议 ID

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心查看会议 ID

1. 在左侧导航栏中，单击 **“用户**”，然后从可用用户列表中选择用户。

2. 在页面的顶部，单击 **编辑**。

3. 在 **“音频会议”** 下，查看 **“会议 ID**”。

    > [!TIP]
    > 可以通过单击电子邮件链接中的“ **发送会议信息** ”，在包含会议 ID 和音频电话号码的电子邮件中向用户发送所有会议信息。
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>使用Windows PowerShell查看会议 ID

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps) 。

### <a name="to-reset-the-conference-id"></a>重置会议 ID

例如，如果用户忘记了密码，你可以为其重置会议 ID。
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心重置会议 ID

1. 在左侧导航栏中，单击 **“用户**”，然后从可用用户列表中选择用户。

2. 在页面的顶部，单击 **编辑**。

3. 在 **“音频会议”** 下，单击 **“重置会议 ID**”。

4. 在 **“重置会议 ID** ”窗口中，单击 **“重置**”。 A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>使用Windows PowerShell重置会议 ID

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps) 。

## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

> [!IMPORTANT]
> 创建新的会议 ID 或重置会议 ID 后，呼叫者无法使用旧的会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。

- 会议 ID 必须满足音频会议网桥上设置的长度（以数字为单位）。 不能在会议 ID 中使用字母或特殊字符;只能使用数字。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 借助Windows PowerShell，可以使用单个管理点来管理 Microsoft 365 或 Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。

## <a name="related-topics"></a>相关主题

[尝试或购买 Microsoft 365 for Microsoft Teams 中的音频会议](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
