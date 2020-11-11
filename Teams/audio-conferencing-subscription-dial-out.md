---
title: 音频会议拨出/呼叫我的分钟数
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
description: 拨出并以分钟为单位给我打电话。 从2019年12月1日起，每个音频会议套餐为每个月的用户提供60分钟数以对国家/地区进行分区。
ms.openlocfilehash: 0f5b4ea3dd59e4a6a9c957f4ec397c9ceb5cc660
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993458"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>音频会议订阅 "拨出"/"呼叫我" 分钟数的好处

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>Microsoft 团队和 Skype for business PSTN 音频会议

客户已提供一 [项免费拨出功能](complimentary-dial-out-period.md) ，该功能将于2019年11月30日结束。 从2019年12月1日起，每个音频会议套餐每月提供60分钟，可用于拨出到任何区域中任何 [国家和地区](audio-conferencing-zones.md)的非 premium 号码。 租户拨出分钟池大小取决于 *分配* 的许可证和未购买的许可证。 此优势适用于 *每月* 套餐的音频会议许可证，并且不会延长到音频会议每分钟付费许可证。 

> [!NOTE]
> 免费拨出期的结束时间不会在2019年11月30日（对于可用音频会议订阅的国家/地区）进行，但目前我们不提供设置通讯信用点数的功能。 这些特定国家是俄罗斯、韩国和台湾。


## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>音频会议 "从会议拨出" & "详细信息，请致电我"

对于采用我们的音频会议服务的客户，Microsoft 提供从分配了音频会议订阅许可证的用户组织的会议中进行拨出的功能。 对区域中未包含的国家/地区 [的](audio-conferencing-zones.md) 拨出通话使用通信信用点数每分钟收费。 对于按分钟计费的拨出呼叫 (呼叫超过租户拨出分钟池或不在 [区域的 "国家和地区](audio-conferencing-zones.md) " 列表中的目标通话时，呼叫和其相关费率基于呼叫目的地，而不是基于组织所在的居住国家/地区或发起拨出呼叫的会议参与者。 例如，如果由美国、法国或津巴布韦的会议参与者发起的，则在法国（国家/地区）的电话号码的音频会议拨出呼叫将按每分钟的费率计费。 


|会议组织者许可证使用位置 |已拨目标 |是否可以使用我的拨出分钟数分钟数？|我是否需要通信信用点数？|
|---------|---------|---------|---------|
|美国 |美国 |是 (区域一个国家)  |使用租户分钟池 *后* 的是         |
|美国 |英国|是 (区域一个国家)  |  使用租户分钟池 *后* 的是       |
|美国     |津巴布韦|    否     |     对 *所有通话都* 是    |
|英国     |英国|是 (区域一个国家)  |  使用租户分钟池 *后* 的是       |
|英国     |美国 |是 (区域一个国家)  |  使用租户分钟池 *后* 的是       |
|英国     |津巴布韦|    否     |   对 *所有通话都* 是      |
|津巴布韦     |津巴布韦|    否     |    对 *所有通话都* 是     |
|津巴布韦     |美国 | 是 (区域一个国家)  | 使用租户分钟池 *后* 的是        |
|津巴布韦     |英国 | 是 (区域一个国家)  | 使用租户分钟池 *后* 的是        |
|库的岛     |库的岛 |   否      |    对 *所有通话都* 是     |
|库的岛     |美国  | 是 (区域一个国家)  |  使用租户分钟池 *后* 的是       |
|库的岛     |英国 | 是 (区域一个国家)  | 使用租户分钟池 *后* 的是        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>如何计算分钟池？

请考虑以下示例。 客户已购买115音频会议套餐，在美国100、英国用户和津巴布韦的5名用户中有10名用户，并分配了 "音频会议订阅许可证"。 所有115用户共享一个 (115 用户的池 x 60 min = 6900 会议每个月的拨出分钟数) 将出站呼叫放入 [国家和地区](audio-conferencing-zones.md)的任何区域中的非 premium 号码， *无论* 会议组织者的许可或物理位置如何。 例如，津巴布韦会议组织者将能够拨打最高至分钟池限制的任何 [国家/](audio-conferencing-zones.md) 地区的区域。

- 每个日历月超过6900分钟的所有拨出通话均按分钟计费，使用通信信用点数按我们的已发布费率传输到目标。  (注意：客户必须设置 [通讯信用点数](what-are-communications-credits.md) ，并向会议组织者分配通讯信用许可证。 ) 
- 对不在 [区域](audio-conferencing-zones.md) 中的目的地的所有拨出呼叫均按分钟计费，使用通讯信用点数在我们的发布费率和目标 (，前提是客户已经设置了通讯信用点数，并为会议组织者分配了通讯信用许可证) 。

## <a name="how-can-i-monitor-minute-my-pool-usage"></a>如何监控我的池使用情况？

- 你可以使用 Microsoft 团队管理中心中的拨出分钟池监视使用情况。 在左侧导航中，转到 " **分析" & 报告**  >  **使用情况报表** ，然后选择 " **PSTN 分钟池** "。 在报告中，"拨出" 分钟池的区域将标记为 "对国家区域的出站呼叫"。
- 当组织的拨出分钟池利用率达到80% 和100% 时，将向以下管理员发送电子邮件通知：

  - 帐单管理员
  - Skype for Business 管理员
  - 公司管理员
  - 用户帐户管理员
  - 帮助台管理员
  - 服务支持管理员
  - 设备管理员
  - 应用程序管理员
  - 许可证管理员
  - 云设备管理员
  - 身份验证管理员
  - 特权身份验证管理员
  - Teams 通信管理员
  - Teams 通信支持工程师
  - 团队沟通支持专家
  - Teams 服务管理员

有关通讯信用点数的其他信息，请参阅 [通讯信用点数](what-are-communications-credits.md)。

## <a name="related-topics"></a>相关主题

- [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [音频会议的国家和地区区域](audio-conferencing-zones.md)
