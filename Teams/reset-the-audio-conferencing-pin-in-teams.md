---
title: 在 Microsoft Teams 中重置音频会议 PIN
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: 了解如何在 Microsoft Teams 中重置用户的音频会议 PIN，并了解有关 PIN 的重要事实。
ms.openlocfilehash: 51c936580010899355db539a45477afd932fb53d
ms.sourcegitcommit: d3eb876e58c9e4a0a11a21b9292d3a6177508d81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2022
ms.locfileid: "68329026"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>在 Microsoft Teams 中重置音频会议 PIN

PIN 是由为为音频会议启用的每个 Microsoft Teams 用户创建的数字组成的代码。 会议组织者使用音频会议 PIN 来确定他们是会议组织者，并允许他们通过电话开始会议。 如果他们使用 Microsoft Teams 应用启动会议，则不需要 PIN。 如果用户忘记了 PIN，并且在启用音频会议时发送给他们的电子邮件中找不到它，管理员可以重置其 PIN，或者可以重置自己的 PIN。
  
当经过身份验证的用户使用 Microsoft Teams 应用加入或组织者通过手机加入其 PIN 时，可以开始会议。 当会议需要 PIN 启动时，通过电话加入的用户将被放置在大厅中，并会在组织者承认之前按住收听音乐。 如果会议组织者不需要 PIN 来通过电话启动会议，则当呼叫者加入会议时，系统不会要求他们提供 PIN。

## <a name="reset-a-users-pin"></a>重置用户的 PIN

使用 Microsoft Teams 管理中心：

1. 在左侧导航栏中，单击 **“用户**”，然后从可用用户列表中选择用户。

2. 单击 **“编辑**”。

3. 在 **“音频会议”** 下，单击 **“重置 PIN**”。

4. 单击 **“重置**”。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="have-a-user-reset-their-own-pin"></a>让用户重置自己的 PIN

1. 让用户转到 [https://dialin.teams.microsoft.com/usp](https://dialin.teams.microsoft.com/usp)。
2. 单击 **“重置 PIN**”。

> [!NOTE]
> 对于 GCCH，请转到： [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp).
> 对于 DoD，请转到： [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp).

> [!NOTE]
> 如果使用此方法，则不会向用户发送 PIN 重置电子邮件。

## <a name="what-else-should-you-know-about-pins"></a>你还应该知道有关 PIN 的哪些信息？

- 出于安全目的，在重置 PIN 时，PIN 仅向管理员显示一次。 管理员重置 PIN 后，PIN 将列为 *******。

- 默认情况下会启用自动向用户发送电子邮件，当用户启用音频会议或重置 PIN 时，用户将收到带有其 PIN 的电子邮件。 但是，如果已禁用自动发送电子邮件，则不会向用户发送 PIN 重置电子邮件，必须手动将 PIN 信息发送给用户。

- 会议开始时，组织者需要允许大厅中的所有 PSTN 用户加入会议。 例如，如果两名 PSTN 参与者在会议开始前尝试加入会议，他们将被放在大厅中，并会在会议组织者通过电话使用 PIN 加入时，会议将开始，组织者可以使用会议内命令 (按 *21) 允许大厅中的所有 PSTN 用户。

- 默认设置是不允许匿名呼叫者启动会议。

- 为用户启用音频会议时，默认情况下会发送包含会议信息及其 PIN 的电子邮件。 用户必须具有 Microsoft 365 或Office 365邮箱，因为当重置 PIN 时，将在电子邮件中向用户发送新的 PIN，以发送到其主要 SMTP 地址 (为用户设置的别名) 。

- 设置音频会议时，设置组织中 PIN 所需的数字。 PIN 可以包含 4 至 12 个数字，默认情况下为 5 个。 如果更改 PIN 长度设置，则该设置仅应用于新生成的 PIN，并且不会应用于为音频会议启用的现有用户的 PIN 设置。 请参阅 [设置音频会议 PIN 的长度](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。

- 默认情况下，电子邮件将设置为用户的 Microsoft 365 或Office 365主 SMTP 地址。 可以向非 Microsoft 365 或非Office 365地址（例如 Hotmail 或 MSN 电子邮件地址）发送电子邮件。 可以使用Windows PowerShell替代默认电子邮件地址。 如果用户在 Microsoft 365 或 Office 365 中没有 Exchange 邮箱，这很有用。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 借助Windows PowerShell，可以使用单个管理点来管理 Microsoft 365 或 Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。
  
## <a name="related-topics"></a>相关主题

[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)
