---
title: 音频会议拨出/呼叫我几分钟
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mikedav, oscarr
ms.topic: conceptual
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
- Licensing
- seo-marvel-mar2020
description: 拨出和呼叫我几分钟的好处。 从 2019 年 12 月 1 日起，每个音频会议订阅每月为 A 区国家/地区提供 60 分钟的每个用户。
ms.openlocfilehash: 6df0b6f2157f16da6e992d465b524a5b582e0a12
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642143"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>音频会议订阅“拨出”/“呼叫我”分钟权益

## <a name="microsoft-teams-and-pstn-audio-conferencing"></a>Microsoft Teams 和 PSTN 音频会议

每个音频会议标准订阅每月为每个用户提供 60 分钟，可用于在任何区域 A 国家/地区中拨出非高级号码，如本文档中所述。 此权益适用于音频会议 *每月订阅* 许可证，并且不扩展到音频会议每分钟付费许可证。

> [!NOTE]
> 音频会议拨出到美国和加拿大订阅的拨出分钟池大小基于 *分配* 给用户的许可证数。 例如，如果客户有 100 个许可证，并且向用户分配了其中 20 个许可证，则分配给美国或加拿大订阅的音频会议拨号分钟池将为 1200 分钟 (分配给用户的订阅 x 20 许可证的 60 分钟拨号分钟) 。

> [!NOTE]
> 2019 年 11 月 30 日，音频会议订阅可用的国家没有结束 [免费拨出期](complimentary-dial-out-period.md) ，但我们目前没有提供设置通信额度的能力。 这些特定国家是俄罗斯、韩国和台湾。

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>音频会议“从会议中拨出”&“呼叫我”详细信息

对于采用音频会议服务的客户，Microsoft 提供从分配了音频会议订阅许可证的用户组织的会议中进行拨号的功能。 对未包含在 [区域 A 国家和地区](audio-conferencing-zones.md) 列表中的国家/地区的拨号呼叫使用通信额度每分钟收费。 对于每分钟计费的拨号呼叫 (超过租户拨出分钟池的呼叫或未在 [A 区国家和地区](audio-conferencing-zones.md) 列表) 的呼叫，呼叫及其关联费率基于呼叫的目标，而不是组织者的居住国或发起拨号呼叫的会议参与者。 例如，如果由美国、法国或津巴布韦的会议参与者发起，则法国（一个A区国家/地区）的电话号码的音频会议拨号呼叫将按每分钟相同的费率计费。

|会议组织者许可证使用位置 |已拨入目标 |是否可以使用拨出分钟池分钟数？|是否需要通信额度？|
|---------|---------|---------|---------|
|美国 |美国 |是 (区域 A 国家/地区)  |使用租户分钟池 *后* 是         |
|美国 |英国|是 (区域 A 国家/地区)  |  使用租户分钟池 *后* 是       |
|美国     |津巴布韦|    否     |     所有 *呼叫均* 为“是”    |
|英国     |英国|是 (区域 A 国家/地区)  |  使用租户分钟池 *后* 是       |
|英国     |美国 |是 (区域 A 国家/地区)  |  使用租户分钟池 *后* 是       |
|英国     |津巴布韦|    否     |   所有 *呼叫均* 为“是”      |
|津巴布韦     |津巴布韦|    否     |    所有 *呼叫均* 为“是”     |
|津巴布韦     |美国 | 是 (区域 A 国家/地区)  | 使用租户分钟池 *后* 是        |
|津巴布韦     |英国 | 是 (区域 A 国家/地区)  | 使用租户分钟池 *后* 是        |
|库克群岛     |库克群岛 |   否      |    所有 *呼叫均* 为“是”     |
|库克群岛     |美国  | 是 (区域 A 国家/地区)  |  使用租户分钟池 *后* 是       |
|库克群岛     |英国 | 是 (区域 A 国家/地区)  | 使用租户分钟池 *后* 是        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>如何计算分钟池？

请考虑以下示例。 一位客户购买了 115 个音频会议订阅许可证，美国有 10 个用户，英国有 100 个用户，津巴布韦有 5 个用户，所有用户都分配了音频会议订阅许可证。 所有 115 个用户共享一个包含 (115 个用户的池 x 60 分钟 = 每个日历月 6，900 个会议拨出分钟数) 在任何 [A 区国家和地区](audio-conferencing-zones.md)对非高级号码进行出站呼叫， *无论* 会议组织者是许可的还是实际位置。 例如，津巴布韦会议组织者将能够拨打到任何 [A 区国家和地区](audio-conferencing-zones.md) ，直至达到分钟池限制。

- 每个日历月超过 6，900 分钟的所有拨出呼叫均按我们发布到该目标的费率使用通信额度按每分钟计费。

   > [!NOTE]
   > 客户必须设置 [通信额度](what-are-communications-credits.md) 并将通信信用额度许可证分配给会议组织者。

- 在客户设置了通信信用额度并向会议组织者分配了通信额度许可证) 时，每分钟使用通信额度向该目标 (对不在 [A 区](audio-conferencing-zones.md) 国家和地区列表中的目标进行所有拨出呼叫。

## <a name="how-can-i-monitor-minute-my-pool-usage"></a>如何监视池使用情况的分钟数？

- 可以针对 Microsoft Teams 管理中心内的拨出分钟池监视使用情况。 在左侧导航栏中，转到 **分析&报告** > **使用情况报告**，然后选择 **PSTN 分钟池**。 区域 A 拨出分钟池将在报表中标记为“对区域 A 国家/地区的出站呼叫”。
- 当组织拨出分钟池的使用率达到 80% 和 100% 时，将向以下管理员发送Email通知：

  - 计费管理员
  - 全局管理员
  - 用户管理员
  - 支持人员管理员
  - 服务支持管理员
  - 已加入 Azure AD 的设备本地管理员
  - 应用程序管理员
  - 许可证管理员
  - 云设备管理员
  - 身份验证管理员
  - 特权身份验证管理员
  - Teams 通信管理员
  - Teams 通信支持工程师
  - Teams 通信支持专家
  - Teams 管理员

有关通信额度的其他信息，请参阅 [通信额度](what-are-communications-credits.md)。

## <a name="related-topics"></a>相关主题

- [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [音频会议的国家/地区区域](audio-conferencing-zones.md)
