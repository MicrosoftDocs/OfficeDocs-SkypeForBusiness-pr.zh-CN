---
title: 对特定 Teams 用户禁用免费电话号码
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
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
- seo-marvel-mar2020
description: 了解如何控制组织者如何使用免费号码参加音频会议桥会议。
ms.openlocfilehash: 6d841a48381609a019a1749095aac4a95901a7c4
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016624"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>对特定 Teams 用户禁用免费电话号码

如果组织在其 Microsoft 音频会议网桥中拥有免费电话号码，可以在特定的组织者的会议中允许或阻止其使用免费电话号码。  

默认方式，组织中的所有用户均启用免费电话号码，这意味着，这些号码，如果可用，参会者可使用它们参加会议。 如果不希望组织中的某些用户可以这样参会，可以通过免费电话号码启用控件限制特定用户在其会议中使用这些号码。

当针对某设定组织者禁用免费电话号码时：

- 免费电话号码将不再包含在他或她的会议邀请中。
- 免费电话号码将不再在"查找本地号码"页上列出，该页面在他或她的会议邀请中被引用。
- 参会者如果拨组织的任何免费电话号码，都将无法参加该设定组织者的会议。
- 参会者可以继续使用收费电话号码参加该组织者的会议。

## <a name="disabling-toll-free-numbers-for-specific-users"></a>禁用特定用户的免费电话号码

可以通过在分配给这些用户的 *TeamsAudioConferencingPolicy* 中将 *AllowTollFreeDialIn* 的设置更改为 **Off**，为特定用户禁用免费号码。 关闭此类用户创建的任何新会议后，将不包括任何免费号码。 [用于收费和免费号码的音频会议策略设置](audio-conferencing-toll-free-numbers-policy.md) 包含更多信息。

> [!IMPORTANT]
> 旧式和以前安排的定期会议可能仍显示免费号码，参与者将无法使用免费号码参加此类会议。 可以为这些用户重新安排所有旧会议和定期会议，并使用 MMS 从他们中删除免费号码。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
