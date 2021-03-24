---
title: '将 Skype for Business 与第三方音频会议提供商集成的生命周期计划 '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: None
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: 2021 年 7 月 31 日，结束生命周期计划，将 Skype for Business 与第三方音频会议提供商 (第三方 ACP) 。
ms.openlocfilehash: 5e48c7deb114136e0b12c2636cf562213890656d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100768"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>将 Skype for Business 与第三方音频会议提供商集成的生命周期计划 

Microsoft 已宣布将 Skype for Business 与第三方音频会议提供商和第三方音频会议提供商 (生命周期) 。 

生命周期结束于 2021 年 7 月 31 日结束。 计划结束后，Skype for Business 和第三方音频会议提供商的集成将停止工作，2021 年 7 月 31 日 (日观察到以下) ：

- 尝试通过第三方 ACP 服务提供的拨入号码加入任何 Skype for Business 会议的参与者将不再连接到 Skype for Business 会议。
 
- 为第三方 ACP 服务启用的用户将不再自动将拨入信息包含在任何新的 Skype for Business 会议邀请中。

作为生命周期结束计划开始公告的一部分，以下更改已生效，并且将继续实施，直到生命周期计划结束： 

- 没有 Skype for Business 用户配置为使用第三方 ACP 服务的客户将无法将任何用户配置为使用第三方 ACP 服务。

- 将 Skype for Business 用户配置为使用第三方 ACP 服务的现有客户能够在生命周期结束时继续添加新用户。 请注意，我们不建议将其他 Skype for Business 用户设置为使用第三方 ACP 服务，因为将于 2021 年 7 月 31 日生效的更改也适用于他们。

## <a name="preparing-for-this-change"></a>准备进行此更改

为准备进行此更改，我们鼓励受影响的组织在 2021 年 7 月 31 日之前通知其已启用此计划更新的用户。 

2021 年 7 月 31 日之后，用户可以继续使用 Skype for Business，不会中断其在线会议;但是，如果组织要求使用 Skype for Business 或 Microsoft Teams 进行电话拨入式音频会议，则需要为 Microsoft 提供的音频会议启用其用户。 若要详细了解 Microsoft 音频会议，请参阅 [音频会议](https://products.office.com/skype-for-business/audio-conferencing)。 

根据组织的所需结束状态，可以遵循三种路径：

- 迁移到 Microsoft 音频会议。 
- 继续使用第三方音频会议提供商。 
- 完全停止使用电话拨入式会议。

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>路径#1：迁移到 Microsoft 音频会议   

决定在 2021 年 7 月 31 日之前迁移到 Microsoft 音频会议并完成迁移的组织不会在此日期期间或之后遇到任何服务影响。 迁移到 Microsoft 音频会议将给组织引入以下更改： 

- 该服务将与其他所有 Microsoft 365 或 Office 365 服务一起计费。 

- 如果购买了标准订阅，则按用户每月订阅费用将包含收费拨入费用。 

- 将为每个组织及其用户提供一组新的拨入电话号码。 若要了解 Microsoft 音频会议服务的地理覆盖范围，请参阅音频会议和呼叫计划的"国家/地区["和"区域可用性"。](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
 
- 使用第三方 ACP 启用的用户已计划的会议将自动重新安排，以包括 Microsoft 音频会议拨入信息。
 
- 每个会议的会议 ID 将是动态的，这意味着每个会议都有自己的专用会议 ID。 动态会议 ID 为背对回会议提供增强的安全性和改进的体验。

- 服务的所有使用都受音频会议服务使用条款限制。 

迁移到 Microsoft 音频会议非常简单，获取服务的许可证后，只需几个步骤就可以完成。 若要了解如何迁移到 Microsoft 音频会议，请参阅：

- [在 Microsoft 365 或 Office 365 中试用或购买音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**摘要：**

- 在 2021 年 7 月 31 日之前迁移到 Microsoft 音频会议并完成迁移的组织不会看到该日期期间或之后对服务产生任何影响。

- 若要详细了解如何迁移到 Microsoft 音频会议，请参阅在 [Microsoft 365 或 Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)中试用或购买音频会议。 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>路径#2：继续单独使用第三方音频会议提供商

决定在 2021 年 7 月 31 日及之后继续使用第三方 ACP 的组织将遇到服务影响，因为第三方 ACP 拨入信息将不再能够用于加入 Skype for Business 会议的音频部分。 

为了防止某些参与者通过 VoIP 加入会议，而让另一些参与者通过第三方 ACP 加入 Skype for Business 会议中的音频碎片，建议这些组织禁止在用户的会议中使用 VoIP。 这样，所有参与者都需要使用第三方 ACP 加入会议的音频部分，并且会议的其他所有工作负荷 (例如聊天或屏幕共享) 可以通过 Skype for Business 继续受支持。 

- 若要从给定组织者的所有会议禁用 VoIP，请通过 Set-CsConferencingPolicy cmdlet 将他/她的会议策略的 AllowIPAudio 参数设置为 false。 有关其他信息，请参阅[Set-CsConferencingPolicy。](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
 
在日程安排方面，自 2021 年 7 月 31 日起，第三方 ACP 的拨入信息将不再自动包含在 Skype for Business 会议邀请中。 如果用户希望继续将此信息包括为会议的一部分，则需要手动添加其 Skype for Business 会议邀请上的拨入信息。 

请注意，2021 年 7 月 31 日，用户的现有会议不会自动重新安排，以删除任何第三方 ACP 拨入信息。 决定为用户的会议启用 VoIP 的组织应考虑禁用其用户的第三方 ACP 集成，然后使用会议迁移服务重新安排其会议，以从现有会议中删除第三方音频会议拨入信息，并防止已在计划的会议上出现音频碎片。 

- 若要为给定组织者禁用第三方音频会议集成，请使用 Remove-CsUserAcp cmdlet。 有关其他信息，请参阅[Remove-CsUserAcp。](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- 若要在禁用与第三方音频会议提供商的集成后自动重新安排用户的会议，请参阅如何为用户手动运行会议迁移？ 在 ["设置会议迁移服务 (MMS) " 中 ](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)。 

**摘要：**

- 决定在 2021 年 7 月 31 日当天和之后继续使用第三方 ACP 的组织将受到影响，因为第三方 ACP 将不能用于加入 Skype for Business 会议，并且新会议不包括第三方 ACP 拨入信息。 

- 建议在 2021 年 7 月 31 日之前禁用所有受影响用户的所有会议 VoIP，以防止音频在通过 VoIP 和第三方 ACP 加入的参与者之间分片。 

    - 若要从给定组织者的所有会议禁用 VoIP，请通过 Set-CsConferencingPolicy cmdlet 将用户会议策略的 AllowIPAudio 参数设置为 false。 有关其他信息，请参阅[Set-CsConferencingPolicy。](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
 
- 如果组织未针对所有会议禁用 VoIP，建议禁止用户使用 Skype for Business Online 和第三方 ACP 集成，并重新安排其会议以删除第三方 ACP 拨入信息以防止音频碎片。

    - 若要为给定组织者禁用第三方音频会议集成，请使用 [Remove-CsUserAcp](/powershell/module/skype/remove-csuseracp?view=skype-ps) cmdlet。 

    - 若要自动重新安排会议，请参阅如何为用户手动运行会议迁移？ 在 ["设置会议迁移服务 (MMS) " 中 ](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)。

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>路径#3：完全停止使用电话拨入式会议

决定完全停止使用电话拨入式会议的组织 (Microsoft 和第三方 ACP) 都可以完全依赖 VoIP 来支持 Skype for Business 会议的音频部分。 

这些组织需要禁止其用户使用第三方音频会议提供商，并且使用会议迁移服务自动重新安排其会议以删除其电话拨入式会议信息。 

- 若要为给定组织者禁用第三方音频会议集成，请使用 Remove-CsUserAcp cmdlet。 有关其他信息，请参阅[Remove-CsUserAcp。](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- 若要在禁用与第三方音频会议提供商的集成后自动重新安排用户的会议，请参阅如何为用户手动运行会议迁移？ 在 ["设置会议迁移服务 (MMS) " 中 ](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)。 

**摘要：** 

- 决定在 2021 年 7 月 31 日之前完全停止使用音频会议的组织不会受到影响。

- 若要为给定组织者禁用第三方音频会议集成，请使用 Remove-CsUserAcp cmdlet。 有关其他信息，请参阅[Remove-CsUserAcp。](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

- 若要在禁用与第三方音频会议提供商的集成后自动重新安排用户的会议，请参阅如何为用户手动运行会议迁移？ 在 ["设置会议迁移服务 (MMS) " 中 ](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)。