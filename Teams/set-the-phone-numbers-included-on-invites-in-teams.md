---
title: 设置包含在邀请中的电话号码
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 按照以下步骤为呼叫者创建默认电话号码以加入 Microsoft Teams 会议。
ms.openlocfilehash: f0956007d5df72c1fd6c6ae905433e73bd855a56
ms.sourcegitcommit: 312ff79ecab91412918793ec882bfc6e0143d30a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2022
ms.locfileid: "66884841"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>在 Microsoft Teams 中设置包含在邀请中的电话号码

Microsoft 365 和 Office 365 中的音频会议使组织中的用户能够创建 Microsoft Teams 会议，然后允许用户使用电话号码拨入这些会议。

会议桥为你的组织提供了一套拨入电话号码。 它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。

除了会议组织者的会议邀请中包含的电话号码外，还有一个链接位于每个会议邀请的底部，打开可用于加入会议的所有拨入电话号码的完整列表。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-users"></a>用户会议邀请中包含的电话号码的初始分配

为音频会议启用的用户的会议邀请中包含的电话号码在分配给用户的 *TeamsAudioConferencingPolicy* 中定义。 将 *TeamsAudioConferencingPolicy* 分配给用户时，策略中添加的所有收费和免费电话号码都包含在具有该策略的用户的会议邀请中。 如果为用户分配了 *TeamsAudioConferencingPolicy* ，并且没有向策略添加任何收费或免费电话号码，则在这种情况下，这些用户的会议邀请中显示的电话号码由默认会议收费电话号码和每个用户设置中的默认会议免费电话号码定义。

> [!NOTE]
> 添加到用户 *TeamsAudioConferencingPolicy* 的收费或免费电话号码优先于使用默认会议收费电话号码和用户设置中的默认会议免费电话号码单独设置的电话号码。

如上所述，除了电话号码外，每个会议邀请都包含一个链接，用于打开可用于加入给定会议的所有拨入电话号码的完整列表。

> [!IMPORTANT]
> 分配的电话号码最多可能需要 24 小时才能显示在会议邀请中。 如果未显示更新的数字，请等待至少 24 小时，然后再联系支持人员。

### <a name="new-users"></a>新用户

会议邀请中包含的新用户的收费和免费电话号码也由分配给这些用户的 *TeamsAudioconferencingPolicy* 定义。 默认情况下，为所有新用户分配全局 *TeamsAudioconferencingPolicy*。 除非租户管理员) 更改，否则全局策略不会添加任何电话号码 (。 在这种情况下，在为音频会议启用的用户的会议邀请中包含的电话号码由默认会议收费电话号码和在每个用户的设置中找到的默认会议免费电话号码定义。

对于新用户，默认会议收费号码是根据为音频会议服务启用用户时在用户的 Microsoft 365 管理中心中设置的使用情况位置分配的。 如果会议桥中有一个与用户所在国家/地区匹配的收费号码，则会自动将该号码分配为用户的默认收费号码。 如果没有，则会将定义为会议桥的默认收费号码的数字分配为用户的默认收费号码。  

为音频会议服务启用用户后，租户管理员可根据需要从其初始值更改用户的默认收费和免费电话号码。

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-users-in-powershell-using-the-teamsaudioconferencingpolicy-cmdlet"></a>使用 *TeamsAudioConferencingPolicy* cmdlet 设置或更改 Powershell 中用户的默认音频会议电话号码

请参阅 [有关收费和免费号码的音频会议策略设置](audio-conferencing-toll-free-numbers-policy.md)

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user-individually"></a>为会议组织者或用户单独设置或更改默认音频会议电话号码

必须是 Teams 服务管理员才能管理这些策略。 请参阅 [Teams 管理员角色管理 Teams](./using-admin-roles.md) ，了解管理员角色和权限。

1. 登录到 Microsoft Teams 管理中心。

2. 在左侧导航栏中，单击 **“用户**”。

    ![显示在 Microsoft Teams 管理中心中选择用户。](media/Admin-users.png)

3. 单击可用用户列表中的用户名。

4. 在 **音频会议** 旁边，单击 **编辑**。

    ![单击音频会议旁边的“编辑”。](media/teams-set-phone-numbers-on-invites-image3.png)

5. 使用 **“收费号码** ”或 **“免费号码** ”字段输入用户的号码。

> [!IMPORTANT]
> 更改用户的音频会议设置时，必须更新定期和将来的 Microsoft Teams 会议并将其发送给与会者。

> [!NOTE]
> 仅当分配给用户的 *TeamsAudioConferencingPolicy* 未添加任何电话号码时，才使用在此设置中输入的电话号码。

## <a name="want-to-use-windows-powershell"></a>想要使用Windows PowerShell

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 借助Windows PowerShell，可以使用单个管理点来管理 Microsoft 365 或 Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用 Windows PowerShell 管理 Microsoft 365 或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))

若要使用 [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) 设置或更改会议组织者或用户的默认音频会议电话号码，请将 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) cmdlet 的或 **`TollFreeServiceNumber`** 参数设置 **`ServiceNumber`** 为可用号码之一。

## <a name="related-topics"></a>相关主题

[尝试或购买 Microsoft 365 或 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[更改音频会议网桥中的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
