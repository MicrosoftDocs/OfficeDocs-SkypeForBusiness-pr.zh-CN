---
title: 在 Microsoft 365 for Teams 中试用或购买音频会议
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d080bb8c-3465-47bb-ad2b-9428f1a3fd24
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.lync.lac.CpcGettingStarted
- seo-marvel-mar2020
description: '了解如何尝试或购买适用于 Microsoft 365 或 Office 365 的音频会议 (PSTN 会议) 许可证，以设置用户可以拨入的电话会议。 '
ms.openlocfilehash: f93ce6306dfa4ab7b5eb198363a698a352763d93
ms.sourcegitcommit: 71b9b5ec80014bd25758493bc06d633c4eac735c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2021
ms.locfileid: "50867021"
---
# <a name="try-or-purchase-audio-conferencing-in-microsoft-365-for-microsoft-teams"></a>在 Microsoft 365 for Microsoft Teams 中试用或购买音频会议

有时，组织中的人员需要使用电话拨入会议。 Microsoft Teams 包含仅针对这种情况的音频会议功能！ 用户可以使用电话（而不是在移动设备或电脑上使用 Microsoft Teams 应用）呼叫 Microsoft Teams 会议。

你只需为计划安排或引导会议的人设置音频会议。 呼入会议的与会者不需要向其分配任何许可证，也不需要其他设置。

如需了解有关定价信息，请参阅[音频会议定价](https://www.microsoft.com/microsoft-teams/audio-conferencing?rtc=3)。

## <a name="step-1-buy-and-assign-audio-conferencing-licenses"></a>步骤 1：购买和分配音频会议许可证

只有全局 [管理员或计费管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 才能执行这些步骤。

### <a name="to-buy-and-assign-user-audio-conferencing-licenses"></a>购买和分配用户音频会议许可证

1. 了解 **音频会议在你的** 国家/地区是否可用。 [音频会议和呼叫](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)计划的国家和地区可用性。

2. 获取 **音频会议** 许可证。 如果想要：

   - **在购买** 之前试用：你可以注册包括音频会议的 Office 365 企业版 E5 免费试用版。 请参阅 [Office 365 企业版 E5 试用](https://portal.office.com/Signup?OfferId=101bde18-5ffb-4d79-a47b-f5b2c62525b3)。

   - **购买：** 请参阅 [Microsoft Teams 附加许可](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。

3. [将许可证分配给组织中](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) 要安排或引导会议的用户。

4. 如果购买了音频会议外接程序许可证和通信点数许可证，也要分配它们。 有关说明，请参阅 [分配 Microsoft Teams 附加许可证](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。

### <a name="to-buy-and-assign-pay-per-minute-audio-conferencing-licenses"></a>购买和分配按分钟付费的音频会议许可证

如果你是批量许可客户，则可以获取按分钟付费的音频会议许可证。 如需了解有关按分钟付费音频会议许可证的其他信息，请参阅[按分钟付费音频会议](audio-conferencing-pay-per-minute.md)。
  
1. 了解 **音频会议在你的** 国家/地区是否可用。 [音频会议和呼叫计划的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

2. 获取 **音频会议** 许可证。 若要获取按分钟付费音频会议许可证，请联系你的客户代表。

3. [为组织设置通信](set-up-communications-credits-for-your-organization.md) 信用额度。 若要设置通信点数，请参阅[什么是通信点数？](what-are-communications-credits.md)

    > [!IMPORTANT]
    > 如果通信点数尚未设置，音频会议就不能供任何持有按每分钟付费许可证的用户使用。

4. [将许可证分配给组织中](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) 要安排或引导会议的用户。

    > [!NOTE]
    > 如果你有"音频会议每分钟付费"许可证，还必须向每个用户单独分配通信信用额度许可证。

## <a name="step-2-set-the-audio-conferencing-provider-for-people-who-lead-or-schedule-meetings"></a>第 2 步：为领导或安排会议的人员设置音频会议提供商

当你 **为组织中没有** 将 Skype for Business 与第三方音频会议提供商集成的人员分配音频会议许可证时，他们全部已设置就绪，可以开始！ （您无需设置其音频会议提供商。）

如果你的用户启用了第三方音频会议提供商，则必须将这些用户的提供商更改为 Microsoft。 若要更改用户的提供商，请参阅 [将 Microsoft 分配为音频会议提供商](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

## <a name="step-3-other-admin-tasks"></a>第 3 步：其他管理任务

以下步骤为 **可选** 步骤，但很多管理员喜欢执行这些操作：

1. [自定义会议邀请](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。 为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。 但是，你也可以添加自己的帮助和法律链接、文本消息和比较小的公司图形。

2. [设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。 这是将在用户安排的会议上显示的电话号码。

3. [设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)，音频会议自动助理将用这种语言在致电者拨入音频会议电话号码时向其发出问候。 此步骤仅在使用 Microsoft 作为音频会议提供商时适用。

4. [设置音频会议 PIN 的长度](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)。

> [!NOTE]
> 由中国世纪互联运营的 Office 365 用户暂无法使用此功能。 如需了解更多信息，请参阅[了解由世纪互联运营的 Office 365](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)。

## <a name="related-topics"></a>相关主题

[在组织中启用 Teams](office-365-set-up.md)

[音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md)

[设置在线会议和会议电话的选项](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
