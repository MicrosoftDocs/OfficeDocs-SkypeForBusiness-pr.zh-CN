---
title: 管理用户的音频会议设置
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Microsoft 365或Office 365管理员可以编辑Teams音频会议设置，包括用户的提供程序、默认收费或免费号码、会议 ID 或 PIN。
ms.openlocfilehash: 16cdc8f58ff29aff751b95e9859fdb0a04245229
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016594"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>在 Microsoft Teams 中管理用户的音频会议设置

作为Microsoft 365或Office 365管理员，可以编辑组织中单个用户的音频会议设置（例如提供程序、默认收费或免费号码、会议 ID 或 PIN）。 若要编辑组织的设置，请参阅 [“管理组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)”。

## <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在左侧导航栏中，单击 **“用户**”，然后从可用用户列表中选择用户。

2. 单击 **“编辑**”。

3. 在 **“音频会议”** 下，修改以下任一内容：

|**设置**|**说明**|
|:-----|:-----|
|**音频会议**|若要为用户打开或关闭音频会议，请单击 **音频** 会议旁边的 **“编辑**”，然后在 **“音频会议**”窗格中切换 **“音频会议** 打开或关闭”。|
|**在电子邮件中发送会议信息**  |仅当您要立即使用其会议 ID 和电话号码向用户发送电子邮件时，才单击此链接。 （此电子邮件不包括 PIN）。请参阅[使用其音频会议信息向用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。  |
|**会议 ID**  |如果需要重置用户的会议 ID，请单击 **“重置会议 ID** ”。 有关详细信息，请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。  |
|**针** |如果需要重置用户的 PIN，请单击 **“重置 PIN** ”。 有关详细信息，请参阅[重置的音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。 |
|**所需的默认会议收费电话号码** ()  |这些将是在音频会议桥上设置的数字。 设置数字的格式，因为希望它们显示在Skype for Business和Microsoft Teams会议请求中。 若要更改默认收费号码，请单击 **“音频会议**”旁边的“**编辑**”，然后在 **“音频会议”** 窗格中，选择“**收费号码**”下的数字。 还可以通过将电话号码添加到 TeamsAudioConferencingPolicy 并将策略分配给用户来设置电话号码。 添加到策略中的电话号码优先于使用 **默认会议收费电话号码设置的** 电话号码。 如果没有将电话号码添加到 TeamsAudioConferencingPolicy，则使用 **默认会议收费电话号码设置的** 电话号码将显示在会议请求Microsoft Teams中。 |
|**此用户的邀请可以包括免费号码**|只能使用 TeamsAudioconferecningPolicy 更改此设置。 |
|**未经身份验证的用户可以是会议中的第一个人**|若要更改此设置，切换 **未经身份验证的用户可以是会议中第一个** 打开或关闭的人员。
|**拨出权限**|若要更改此设置，请单击 **“音频会议**”旁边的“**编辑**”，然后在 **“音频会议**”窗格中，**从会议拨号** 下选择一个选项。|

![显示用户的音频会议设置。](media/teams-manage-audio-conferencing-settings-for-a-user-image1.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>相关主题

[管理组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[音频会议常见问题](audio-conferencing-common-questions.md)
