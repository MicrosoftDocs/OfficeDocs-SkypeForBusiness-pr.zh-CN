---
title: 音频会议订阅"拨出"/"呼叫我 At"优点
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: '客户提供了将在 2019 年 11 月 30，结束的互补拨出功能。  每个音频会议订阅开始 2019，年 12 月 1，提供每个用户每月到任何本文档中所述的区域的国家/地区的 60 分钟。 '
ms.openlocfilehash: 890441987eb0f08d67afe8a7f231c9a534c59a7f
ms.sourcegitcommit: 7fe8daf07013d7c532f128a3ae3bbf51d1b2aac9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2019
ms.locfileid: "31809422"
---
# <a name="audio-conferencing-subscription-dial-outcall-me-at-benefit"></a>音频会议订阅"拨出"/"呼叫我 At"优点

## <a name="microsoft-teams-and-skype-for-business-pstn-audio-conferencing"></a>Microsoft 团队和 Skype 业务 PSTN 音频会议

客户提供了将在 2019 年 11 月 30，结束[互补拨出功能](complimentary-dial-out-period.md)。 每个音频会议订阅开始 2019，年 12 月 1，提供每个用户每月到任何本文档中所述的区域的国家/地区的 60 分钟。 您的租户拨出式 minute 池大小是基于*分配*许可证和尚未购买许可证。 此优点是适用于音频会议*按月订阅*许可证，并且不会扩展到音频会议付薪每分钟许可证。 

## <a name="audio-conferencing-dial-out-from-a-meeting--call-me-at-details"></a>音频会议"拨出会议从"&"呼叫我 At"详细信息

对于采用我们音频会议服务的客户，Microsoft 提供的功能从组织的用户分配音频会议订阅许可证会议拨出。 每分钟使用 Communications 字幕式收取国家/地区"区域的"国家/地区列表中不包含电话拨出式调用。 对于每分钟 （超过租户拨出式 minute 池或向不在区域的国家/地区列表的目标的呼叫的呼叫） 收取的电话拨出式呼叫，呼叫和其关联的费率基于呼叫的目标和不组织者的国家/地区的住宅或发起电话拨出式呼叫会议参与者。 例如，音频会议拨出式呼叫在法国，即区域的国家/地区的电话号码将以相同的每分钟速率收取如果它已由美国、 法国或津巴布韦中的会议参与者。 


|会议组织者许可使用位置 |拨打的目标 |我可以使用我的电话拨出式 minute 池分钟吗？|是否需要 Communications 字幕式？|
|---------|---------|---------|---------|
|美国 |美国 |是 （区域的国家/地区） |是*后*使用租户 minute 池         |
|美国 |英国|是 （区域的国家/地区） |  是*后*使用租户 minute 池       |
|美国     |津巴布韦|    否     |     是在*所有*调用    |
|英国     |英国|是 （区域的国家/地区） |  是*后*使用租户 minute 池       |
|英国     |美国 |是 （区域的国家/地区） |  是*后*使用租户 minute 池       |
|英国     |津巴布韦|    否     |   是在*所有*调用      |
|津巴布韦     |津巴布韦|    否     |    是在*所有*调用     |
|津巴布韦     |美国 | 是 （区域的国家/地区） | 是*后*使用租户 minute 池        |
|津巴布韦     |英国 | 是 （区域的国家/地区） | 是*后*使用租户 minute 池        |
|库可群岛     |库可群岛 |   否      |    是在*所有*调用     |
|库可群岛     |美国  | 是 （区域的国家/地区） |  是*后*使用租户 minute 池       |
|库可群岛     |英国 | 是 （区域的国家/地区） | 是*后*使用租户 minute 池        |
|    |         |         |         |

## <a name="how-are-minute-pools-calculated"></a>Minute 池的计算方式

请考虑下面的示例。 客户购买 115 音频会议订阅许可证，并具有在美国的 10 个用户、 100 个英国，用户和津巴布韦，所有与音频会议订阅许可证分配中的 5 个用户。 115 的所有用户都共享 （115 用户 x 60 分钟 = 6,900 会议拨出式出分钟每月） 的池进行任何国家/地区，*无论*的会议组织者授予许可其中或物理上位于区域的出站呼叫。 例如，津巴布韦会议组织者将能够拨出任何最多为 minute 池限制的区域的国家/地区。 

- 每分钟至该目标我们已发布的费用在使用 Communications 字幕式计费超出 6,900 分钟每月的所有呼叫。 (注意： 必须设置[Communications 字幕式](what-are-communications-credits.md)客户并将其分配会议组织者的通信字幕式许可证。)
- 每分钟 （提供客户已设置 Communications 字幕式和分配 Communications 字幕式许可证至该目标我们已发布速率使用 Communications 字幕式计费到目标不在区域的国家/地区列表中的所有出站呼叫会议组织者）。

## <a name="how-can-i-monitor-minute-pool-usage"></a>如何监视 minute 池使用？

- 您可以针对您拨出式 minute 池中业务管理中心的"旧"Skype 监视使用情况。 在 Microsoft 团队的管理中心中，导航到**旧门户** > **报告** > **PSTN 分钟池**。 区域的电话拨出式分钟池将被标记在报表中为"出站调用区域的国家/地区。"
- 将给定的客户的所有租户管理员都发送电子邮件通知时的租户的电话拨出式分钟池利用率已达到 80%到 100%。

通信字幕式的其他信息，请参阅[Communications 字幕式](what-are-communications-credits.md)。


|区域的国家/地区 |
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