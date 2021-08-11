---
title: 音频会议拨出/呼叫我（分钟）
ms.author: tonysmit
author: tonysmit
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
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-mar2020
description: "\"拨出\"和\"以分钟呼叫我\"权益。 截至 2019 年 12 月 1 日，每个音频会议订阅向区域 A 国家/地区提供每个用户每月 60 分钟的会议时间。"
ms.openlocfilehash: d532664abee611fe9ced2e744415edb91e3dae03b8aaea36e705d8bed59b10e6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278230"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>音频会议订阅"拨出"/"呼叫我"分钟权益

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>Microsoft Teams和Skype for Business PSTN 音频会议

每个音频会议订阅每月为每个用户提供 60 分钟，可用于拨打任何区域 A 国家/地区中的非高级号码，如本文档中所述。 租户拨出分钟数池大小 *取决于购买的许可证* 。 此权益适用于音频会议 *月度订阅* 许可证，不适用于音频会议按分钟付费许可证。

> [!NOTE]
> 从 2020 年 10 月 22 日起，租户的拨出分钟数池大小取决于购买的音频会议订阅许可证数。 以前，拨出分钟数池大小基于分配给用户的 *许可证* 数。


> [!NOTE]
> 对于提供音频会议[](complimentary-dial-out-period.md)订阅的国家/地区，2019 年 11 月 30 日未结束免费拨出期，但我们目前不提供设置通信信用额度的能力。 这些特定国家/地区包括俄罗斯、韩国和台湾。

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>音频会议"从会议拨出"&"呼叫我"详细信息

对于采用音频会议服务的客户，Microsoft 提供从分配有音频会议订阅许可证的用户组织的会议中拨出功能。 对未包含在区域 [A](audio-conferencing-zones.md) 国家和地区列表中的国家/地区的拨出呼叫使用通信信用额度每分钟收费。 对于每分钟拨出呼叫数超过租户拨出分钟数池的 (呼叫或对不在区域 [A](audio-conferencing-zones.md) 国家和地区列表) 中的目标的呼叫，呼叫及其关联的费率基于呼叫的目标，而不是组织者的居住地或发起拨出呼叫的会议参与者。 例如，如果音频会议拨出呼叫是由美国、法国或阿拉伯联合酋长国的会议参与者发起的，则拨打法国（即区域 A 国家/地区）的电话号码时，将按相同的每分钟费率计费。 


|会议组织者许可证使用位置 |已拨号的目标 |可以使用拨出分钟数池分钟数吗？|是否需要通信积分？|
|---------|---------|---------|---------|
|美国 |美国 |是 (国家/地区)  |使用 *租户* 分钟池后是         |
|美国 |英国|是 (国家/地区)  |  使用 *租户* 分钟池后是       |
|美国     |津巴布韦|    弱     |     所有通话 *均支持*    |
|英国     |英国|是 (国家/地区)  |  使用 *租户* 分钟池后是       |
|英国     |美国 |是 (国家/地区)  |  使用 *租户* 分钟池后是       |
|英国     |津巴布韦|    弱     |   所有通话 *均支持*      |
|津巴布韦     |津巴布韦|    弱     |    所有通话 *均支持*     |
|津巴布韦     |美国 | 是 (国家/地区)  | 使用 *租户* 分钟池后是        |
|津巴布韦     |英国 | 是 (国家/地区)  | 使用 *租户* 分钟池后是        |
|维尔京群岛     |维尔京群岛 |   弱      |    所有通话 *均支持*     |
|维尔京群岛     |美国  | 是 (国家/地区)  |  使用 *租户* 分钟池后是       |
|维尔京群岛     |英国 | 是 (国家/地区)  | 使用 *租户* 分钟池后是        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>如何计算分钟池？

请考虑以下示例。 客户已购买 115 个音频会议订阅许可证，在美国有 10 个用户，英国有 100 个用户，在安哥拉有 5 个用户，所有这些用户都分配有音频会议订阅许可证。 所有 115 个用户共享一个 (池，该池的 115 个用户 x 60 分钟 = 每个日历月) 的 6，900 个会议拨出分钟数，以便向任何区域[A](audio-conferencing-zones.md)国家和地区的非高级号码进行出站呼叫，无论会议组织者是获得许可还是实际位于何处。 例如，在达到分钟池限制之前，一个安哥拉会议组织者能够拨出到任何区域 [A](audio-conferencing-zones.md) 国家和地区。

- 每个日历月超过 6，900 分钟的所有拨出呼叫均使用通信积分以我们发布到该目的地的费率每分钟计费。 

   > [!NOTE]
   > 客户必须设置 [通信信用额度](what-are-communications-credits.md) ，并将通信信用额度许可证分配给会议组织者。

- 对于不在" [区域 A](audio-conferencing-zones.md) 国家和地区"列表中的目标的所有拨出呼叫，使用通信信用额度按我们发布到该目的地的费率每分钟计费 (但客户已设置通信信用额度并将通信信用额度许可证分配给会议组织者) 。

## <a name="how-can-i-monitor-minute-my-pool-usage"></a>如何监视池使用情况的分钟数？

- 可以在管理中心内针对拨出分钟数池监视Microsoft Teams使用情况。 在左侧导航中，转到"分析&报告  >  **使用情况报告**"，然后选择 **"PSTN 分钟池"。** 区域 A 拨出分钟数池将在报告中标记为"对区域 A 国家/地区进行出站呼叫"。
- 当组织的拨出分钟数池利用率达到 80% 和 100% 时，电子邮件通知将发送给以下管理员：

  - 计费管理员
  - Skype for Business管理员
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
  - Teams通信支持专家
  - Teams 管理员

有关通信信用额度的其他信息，请参阅 [通信信用额度](what-are-communications-credits.md)。

## <a name="related-topics"></a>相关主题

- [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [音频会议的国家/地区与区域](audio-conferencing-zones.md)
