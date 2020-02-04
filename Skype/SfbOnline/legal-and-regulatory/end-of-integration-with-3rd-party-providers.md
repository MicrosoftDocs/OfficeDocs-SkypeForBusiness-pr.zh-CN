---
title: '将 Skype for Business 与第三方音频会议提供商集成的生命周期结束 '
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
description: 2021年7月31日，生命期结束计划将结束与第三方音频会议提供商（第三方 ACP）的 Skype for Business 的集成。
ms.openlocfilehash: b9bd1640d615babab29a073aeeee2b1beb92fc02
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706687"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>将 Skype for Business 与第三方音频会议提供商集成的生命周期结束 

Microsoft 已宣布开始使用第三方音频会议提供商（ACPs）与 Skype for Business 集成的生命周期结束。 

生命周期结束计划将于2021年7月31日结束。 当程序结束时，与第三方音频会议提供商的 Skype for Business 集成将停止工作，并且将在该日期（2021年7月31日）看到以下更改：

- 尝试通过第三方 ACP 服务提供的拨入号码加入任何 Skype for Business 会议的参与者将不再连接到 Skype for Business 会议。
 
- 为第三方 ACP 服务启用的用户将不再自动包含任何新的 Skype for business 会议邀请中的电话拨入信息。

作为开始使用计划结束的一部分，以下更改已生效，并且将在生命周期结束之前继续保持不动的状态： 

- 没有配置为使用第三方 ACP 服务的 Skype for business 用户的客户将无法将任何用户配置为使用第三方 ACP 服务。

- 已配置为使用第三方 ACP 服务的 Skype for business 用户的现有客户将继续能够在生命周期结束期间添加新用户。 请注意，我们不建议将其他 Skype for Business 用户设置为使用第三方 ACP 服务，因为将在2021年7月31日生效的更改也将应用于这些更改。

## <a name="preparing-for-this-change"></a>准备进行此更改

为准备此更改，我们鼓励受影响的组织在2021年7月31日之前通知已启用的此计划更新用户。 

2021年7月31日之后，用户可以继续使用 Skype for Business，而不中断其在线会议;但是，如果组织需要电话拨入音频会议和 Skype for business 或 Microsoft 团队，则组织需要为 Microsoft 提供的音频会议启用用户。 若要了解有关 Microsoft 音频会议的详细信息，请参阅[音频会议](https://products.office.com/en-us/skype-for-business/audio-conferencing)。 

根据所需的组织结束状态，可以遵循以下三个路径：

- 迁移到 Microsoft 音频会议。 
- 继续单独使用第三方音频会议提供商。 
- 完全停止使用电话拨入式会议。

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>路径 #1：迁移到 Microsoft 音频会议   

如果组织决定迁移到 Microsoft 音频会议并在2021年7月31日之前完成迁移，将不会在该日期期间或之后遇到任何服务影响。 迁移到 Microsoft 音频会议将对组织引入以下更改： 

- 将向所有其他 Office 365 服务收取服务费用。 

- 如果购买了标准套餐，则按每个用户的每月订阅费用包括收费电话拨入费。 

- 将为每个组织及其用户提供一组新的拨入电话号码。 若要查看 Microsoft 音频会议服务的地理覆盖范围，请参阅[音频会议和通话计划的国家和地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)。
 
- 已由使用第三方 ACP 启用的用户安排的会议将自动重新安排为包括 Microsoft 音频会议拨入信息。
 
- 每个会议的会议 Id 都是动态的，这意味着每个会议都将拥有自己的专用会议 ID。 动态会议 Id 提供了更高的安全性和更好的后端到后会议体验。

- 该服务的所有使用均受音频会议服务使用条款的制约。 

迁移到 Microsoft 音频会议非常简单，只需在为服务获取许可证后的几个步骤中完成迁移即可。 若要了解如何迁移到 Microsoft 音频会议，请参阅：

- [试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**摘要：**

- 迁移到 Microsoft 音频会议并在2021年7月31日之前完成迁移的组织将不会在该日期期间或之后看到对其服务的任何影响。

- 若要了解有关迁移到 Microsoft 音频会议的详细信息，请参阅[在 Office 365 中试用或购买音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)。 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>路径 #2：继续单独使用第三方音频会议提供商

如果组织决定继续使用2021年7月31日的第三方 ACP，将会受到服务影响，因为第三方 ACP 的拨入信息将不再能够用于加入 Skype for business 会议的音频部分。 

为了防止某些参与者通过 VoIP 和其他参与者通过 VoIP 和其他参与者加入 Skype for Business 会议中的音频碎片，我们建议这些组织在其用户的会议中禁用 VoIP ACP。 这样，所有参与者都需要使用第三方 ACP 和会议的所有其他工作负荷（如聊天或屏幕共享）通过 Skype for business 继续支持会议的音频部分。 

- 若要从给定组织者的所有会议中禁用 VoIP，请通过 CsConferencingPolicy cmdlet 将其会议策略的 AllowIPAudio 参数设置为 false。 有关详细信息，请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
 
根据日程安排和2021年7月31日起，第三方 ACP 的拨入信息将不再自动包含在 Skype for Business 会议邀请中。 如果用户希望继续将此信息包含在会议的一部分中，用户将需要手动在其 Skype for Business 会议邀请上添加拨入信息。 

请注意，在2021年7月31日，将不会自动重新安排用户的现有会议以删除任何第三方 ACP 的拨入信息。 决定为用户的会议启用 VoIP 的组织应考虑禁用其用户的第三方 ACP 的集成，并使用会议迁移服务重新安排其会议以删除第三方音频从现有会议中会议拨入信息，并在已计划的会议上阻止音频碎片。 

- 若要禁用给定组织者的第三方音频会议的集成，请使用 CsUserAcp cmdlet。 有关其他信息，请参阅[Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)。 

- 若要在禁用与第三方音频会议提供商的集成后，自动重新安排用户的会议，请参阅 "如何为用户手动运行会议迁移？" 在[设置会议迁移服务（MMS）](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)时。 

**摘要：**

- 决定继续使用2021的第三方 ACP 的组织将受到影响，因为第三方 ACP 无法用于加入 Skype for Business 会议，新会议不会包含第三方 ACP 的拨入信息。 

- 建议在2021年7月31日之前对所有受影响用户的所有会议禁用 VoIP，以防止音频在通过 VoIP 和第三方 ACP 加入的参与者之间分段。 

    - 若要从给定组织者的所有会议中禁用 VoIP，请通过 CsConferencingPolicy cmdlet 将用户的会议策略的 AllowIPAudio 参数设置为 false。 有关详细信息，请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
 
- 如果组织没有为所有会议禁用 VoIP，则建议禁用用户使用 Skype for Business Online 与第三方 ACP 集成，并重新安排其会议以删除第三方 ACP 拨入信息，以阻止音频碎片。

    - 若要禁用给定组织者的第三方音频会议的集成，请使用[CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) cmdlet。 

    - 若要自动重新安排会议，请参阅 "如何为用户手动运行会议迁移？" 在[设置会议迁移服务（MMS）](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)时。

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>路径 #3：完全停止使用拨入式会议

决定完全停止使用电话拨入式会议的组织（不是由 Microsoft 和第三方 ACP 提供）都可以完全依赖 VoIP 来支持 Skype for business 会议的音频部分。 

这些组织将需要禁用其用户使用第三方音频会议提供商，并使用会议迁移服务自动重新安排其会议以删除其电话拨入式会议信息。 

- 若要禁用给定组织者的第三方音频会议的集成，请使用 CsUserAcp cmdlet。 有关其他信息，请参阅[Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)。 

- 若要在禁用与第三方音频会议提供商的集成后，自动重新安排用户的会议，请参阅 "如何为用户手动运行会议迁移？" 在[设置会议迁移服务（MMS）](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)时。 

**摘要：** 

- 决定在 2021 7 月31日之前停止使用音频会议的组织不会受到影响。

- 若要禁用给定组织者的第三方音频会议的集成，请使用 CsUserAcp cmdlet。 有关其他信息，请参阅[Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps)。 

- 若要在禁用与第三方音频会议提供商的集成后自动重新安排用户的会议，请参阅 "如何为用户手动运行会议迁移？" 在[设置会议迁移服务（MMS）](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)时。
