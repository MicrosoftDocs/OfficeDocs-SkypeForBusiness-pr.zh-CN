---
title: 音频会议订阅“拨出”/“给我打电话”的好处
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
f1keywords: None
ms.custom:
- Licensing
description: '客户已提供一项免费拨出功能，该功能将于2019年11月30日结束。  从2019年12月1日起，每个音频会议套餐将每月每个用户的60分钟数提供给本文档中所述的任何国家/地区。 '
ms.openlocfilehash: e98844a1b3d9b00d489cd32e90add357b4b85b57
ms.sourcegitcommit: b1bf37a96a8faa169d8a32b7478f1e2d1022ebbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311267"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-minutes-benefit"></a>音频会议订阅 "拨出"/"呼叫我" 分钟数的好处

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>Microsoft 团队和 Skype for business PSTN 音频会议

客户已提供一[项免费拨出功能](complimentary-dial-out-period.md)，该功能将于2019年11月30日结束。 从2019年12月1日起，每个音频会议套餐每月提供60分钟，可用于拨打本文档中所述的任何区域中的非 premium 号码。 租户拨出分钟池大小取决于*分配*的许可证和未购买的许可证。 此优势适用于*每月*套餐的音频会议许可证，并且不会延长到音频会议每分钟付费许可证。 

> [!NOTE]
> 免费拨出期的结束时间将不会在音频会议订阅的2019年11月30日进行，但目前我们不提供设置通讯信用点数的功能。 这些特定国家是俄罗斯、韩国和台湾。


## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>音频会议 "从会议拨出" & "详细信息，请致电我"

对于采用我们的音频会议服务的客户，Microsoft 提供从分配了音频会议订阅许可证的用户组织的会议中进行拨出的功能。 对于 "区域 A" 国家/地区列表中未包含的国家/地区的拨出通话使用通信信用点数每分钟收费。 对于每分钟计费的拨出呼叫（超过租户拨出分钟池的通话次数，或对不在区域 A 国家列表中的目的地的呼叫），通话及其相关费率基于呼叫目的地，而不是基于组织的国家/地区开始拨出通话的居住或会议参与者。 例如，如果由美国、法国或津巴布韦的会议参与者发起的，则在法国（国家/地区）的电话号码的音频会议拨出呼叫将按每分钟的费率计费。 


|会议组织者许可证使用位置 |已拨目标 |是否可以使用我的拨出分钟数分钟数？|我是否需要通信信用点数？|
|---------|---------|---------|---------|
|美国 |美国 |是（区域一个国家/地区） |使用租户分钟池*后*的是         |
|美国 |英国|是（区域一个国家/地区） |  使用租户分钟池*后*的是       |
|美国     |津巴布韦|    否     |     对*所有通话都*是    |
|英国     |英国|是（区域一个国家/地区） |  使用租户分钟池*后*的是       |
|英国     |美国 |是（区域一个国家/地区） |  使用租户分钟池*后*的是       |
|英国     |津巴布韦|    否     |   对*所有通话都*是      |
|津巴布韦     |津巴布韦|    否     |    对*所有通话都*是     |
|津巴布韦     |美国 | 是（区域一个国家/地区） | 使用租户分钟池*后*的是        |
|津巴布韦     |英国 | 是（区域一个国家/地区） | 使用租户分钟池*后*的是        |
|库的岛     |库的岛 |   否      |    对*所有通话都*是     |
|库的岛     |美国  | 是（区域一个国家/地区） |  使用租户分钟池*后*的是       |
|库的岛     |英国 | 是（区域一个国家/地区） | 使用租户分钟池*后*的是        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>如何计算分钟池？

请考虑以下示例。 客户已购买115音频会议套餐，在美国100、英国用户和津巴布韦的5名用户中有10名用户，并分配了 "音频会议订阅许可证"。 所有115用户共享一个（115用户 x 60 min = 6900 会议拨出分钟数分钟）将出站呼叫放入国家/地区的任何区域中的非 premium 号码，*无论*会议组织者的许可或物理位置如何。 例如，津巴布韦会议组织者将能够拨出到最大为分钟池限制的任何国家/地区的任何区域。 

- 每个日历月超过6900分钟的所有拨出通话均按分钟计费，使用通信信用点数按我们的已发布费率传输到目标。 （注意：客户必须设置[通讯信用点数](what-are-communications-credits.md)，并向会议组织者分配通讯信用许可证。）
- 对不在区域中的目的地的所有拨出通话按分钟计费，使用通讯信用点数按分钟计费到目的地（前提是客户设置了通讯信用点数并分配了 "信用点数" 许可证会议组织者）。

## <a name="how-can-i-monitor-minute-pool-usage"></a>如何监视分钟池使用情况？

- 你可以在 "旧版" Skype for business 管理中心中监控拨出分钟池的使用情况。 在 "Microsoft 团队管理中心" 中，导航到 "**旧版门户** > "**报告** > **PSTN 分钟池**。 在报告中，"拨出" 分钟池的区域将标记为 "对国家区域的出站呼叫"。
- 当租户的拨出分钟池利用率达到80% 和100% 时，将向给定客户的所有租户管理员发送电子邮件通知。

有关通讯信用点数的其他信息，请参阅[通讯信用点数](what-are-communications-credits.md)。


|区域国家/地区 |
|---------|
|澳大利亚      |
|奥地利     |
|比利时     |
|巴西     |
|保加利亚     |
|加拿大     |
|中国     |
|克罗地亚     |
|捷克共和国      |
|丹麦     |
|爱沙尼亚     |
|芬兰     |
|法国     |
|德国     |
|希腊     |
|香港特别行政区     |
|匈牙利     |
|印度     |
|爱尔兰     |
|意大利     |
|日本     |
|卢森堡      |
|马来西亚     |
|墨西哥     |
|荷兰     |
|新西兰     |
|挪威     |
|波兰     |
|葡萄牙     |
|波多黎各     |
|罗马尼亚     |
|俄罗斯     |
|新加坡     |
|斯洛伐克共和国     |
|斯洛文尼亚     |
|南非     |
|韩国     |
|西班牙     |
|瑞典     |
|瑞士     |
|台湾     |
|泰国     |
|美国     |
|英国|
||

## <a name="related-topics"></a>相关主题

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
