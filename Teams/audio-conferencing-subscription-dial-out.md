---
title: 音频会议拨出/以分钟呼叫我
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
description: 拨出和呼叫我分钟权益。 从 2019 年 12 月 1 日开始，每个音频会议订阅向区域 A 国家和地区的每个用户提供 60 分钟的时间。
ms.openlocfilehash: 8885453d2dd9a29b69a36037fd160468762e5956
ms.sourcegitcommit: 0e4e5b9933970827ea4be137ca98eab6994e2301
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2023
ms.locfileid: "69696837"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>音频会议订阅“拨出”/“呼叫我”分钟权益

## <a name="microsoft-teams-and-pstn-audio-conferencing"></a>Microsoft Teams 和 PSTN 音频会议

每个音频会议标准订阅每个用户每月提供 60 分钟，可用于拨打 A 区国家/地区任意国家/地区的非高级号码，如本文档所述。 此权益适用于音频会议 *每月订阅* 许可证，不会扩展到音频会议按分钟付费许可证。

> [!NOTE]
> 音频会议拨出到美国和加拿大订阅的拨出分钟池大小取决于 *分配给* 用户的许可证数。 例如，如果客户有 100 个许可证，其中 20 个许可证分配给用户，则音频会议拨出到美国或加拿大的订阅的拨出分钟池将为 1200 分钟 (60 个拨出分钟数 x) 分配给用户的 20 个许可证。

> [!NOTE]
> [免费拨出期](complimentary-dial-out-period.md)未于 2019 年 11 月 30 日结束，适用于提供音频会议订阅的国家和地区，但我们目前不提供设置通信点数的功能。 这些特定的国家和地区是俄罗斯、韩国和台湾。

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>音频会议“从会议拨出”&“呼叫我”详细信息

对于采用音频会议服务的客户，Microsoft 提供从分配有音频会议订阅许可证的用户组织的会议中拨出的功能。 对未包含在 [A 区域](audio-conferencing-zones.md) 国家和地区列表中的国家和地区的拨出呼叫使用通信额度按分钟收费。 对于每分钟计费的拨出呼叫 (超过租户拨出分钟池的呼叫或对不在 [区域 A 国家和地区](audio-conferencing-zones.md) 列表) 的目标的呼叫，呼叫及其关联费率基于呼叫的目标，而不是组织者所在国家或地区或发起拨出呼叫的会议参与者。 例如，如果由美国、法国或津巴布韦的会议参与者发起，则对法国（A 区国家/地区）电话号码的音频会议拨出呼叫将按相同的每分钟费率计费。

|会议组织者许可证使用位置 |已拨打目标 |是否可以使用我的拨出分钟池分钟数？|是否需要通信点数？|
|---------|---------|---------|---------|
|美国 |美国 |是 (区域 A 国家/地区)  |是 *使用* 租户分钟池后         |
|美国 |英国|是 (区域 A 国家/地区)  |  是 *使用* 租户分钟池后       |
|美国     |津巴布韦|    否     |     *是所有* 调用    |
|英国     |英国|是 (区域 A 国家/地区)  |  是 *使用* 租户分钟池后       |
|英国     |美国 |是 (区域 A 国家/地区)  |  是 *使用* 租户分钟池后       |
|英国     |津巴布韦|    否     |   *是所有* 调用      |
|津巴布韦     |津巴布韦|    不支持     |    *是所有* 调用     |
|津巴布韦     |美国 | 是 (区域 A 国家/地区)  | 是 *使用* 租户分钟池后        |
|津巴布韦     |英国 | 是 (区域 A 国家/地区)  | 是 *使用* 租户分钟池后        |
|库克群岛     |库克群岛 |   否      |    *是所有* 调用     |
|库克群岛     |美国  | 是 (区域 A 国家/地区)  |  是 *使用* 租户分钟池后       |
|库克群岛     |英国 | 是 (区域 A 国家/地区)  | 是 *使用* 租户分钟池后        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>分钟池是如何计算的？

请考虑以下示例。 一个客户购买了 115 个音频会议订阅许可证，美国有 10 个用户，英国有 100 个用户，津巴布韦有 5 个用户，所有用户都分配了音频会议订阅许可证。 所有 115 个用户共享一个池，每个日历月 (115 个用户 x 60 分钟 = 6，900 个会议拨出分钟数，) 向任何 [区域 A 区域的非](audio-conferencing-zones.md)高级号码发出出站呼叫， *而不管* 会议组织者在何处获得许可或物理位置。 例如，津巴布韦会议组织者将能够拨出到 [任何区域 A 国家和地区](audio-conferencing-zones.md) ，达到分钟池限制。

- 每个日历月超过 6，900 分钟的所有拨出呼叫均使用通信额度按我们向该目标发布的费率按分钟计费。

   > [!NOTE]
   > 客户必须设置 [通信点数](what-are-communications-credits.md) 并将通信额度许可证分配给会议组织者。

- 如果客户设置了通信额度并将通信点数许可证分配给会议组织者) ，则所有对不在 [A 区国家和地区](audio-conferencing-zones.md) 列表中的目的地的拨出呼叫均按每分钟使用通信额度按我们向该目标发布的费率计费 (。

## <a name="how-can-i-monitor-minute-my-pool-usage"></a>如何监视一分钟的池使用情况？

- 可以在 Microsoft Teams 管理中心针对拨出分钟池监视使用情况。 在左侧导航中，转到 **“分析”&报告** > **使用情况报告**，然后选择“ **PSTN 分钟池**”。 区域 A 拨出分钟池将在报表中标记为“对区域 A 国家和地区的出站呼叫”。
- 当组织的拨出分钟数池利用率达到 80% 和 100% 时，将向以下管理员发送Email通知：

  - 计费管理员
  - 全局管理员
  - 用户管理员
  - 支持管理员
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
- [音频会议的国家和地区区域](audio-conferencing-zones.md)
