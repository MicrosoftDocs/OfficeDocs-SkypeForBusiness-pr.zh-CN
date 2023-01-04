---
title: 免费拨出时段
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mikedav, OscarR
ms.topic: conceptual
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: ''
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: 了解 Microsoft Teams 中的 Microsoft 365 通话套餐和音频会议的免费拨出时段。
ms.openlocfilehash: 472482f49109932dded4594bf0381ebd93febab3
ms.sourcegitcommit: 0e4e5b9933970827ea4be137ca98eab6994e2301
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2023
ms.locfileid: "69696847"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>音频会议免费拨出期

## <a name="teams-pstn-services"></a>Teams PSTN 服务

客户可以使用 Teams PSTN 服务使用条款和客户批量许可协议中允许的 Microsoft 365 或通话套餐和 Teams 音频会议。 可以在 [许可资源和文档](https://www.microsoft.com/licensing/docs)中找到 PSTN 服务使用条款。

### <a name="end-of-complimentary-dial-out-period"></a>免费拨出期结束

免费拨出功能于 2019 年 12 月 1 日结束。 有关详细信息，请参阅 [音频会议订阅拨出和呼叫我权益](audio-conferencing-subscription-dial-out.md)。

对于提供音频会议订阅的国家和地区，未发生此更改，但我们目前不启用设置通信点数。 这些特定的国家和地区是俄罗斯、韩国和台湾。

### <a name="complimentary-dial-out-period-details"></a>免费拨出时间详细信息

对于采用 Microsoft 365 音频会议服务的客户，Microsoft 提供额外的免费权益，这些权益与在 2019 年 11 月前分配有 Microsoft 365 音频会议订阅许可证的用户组织的会议拨出相关。 在此免费期间，Microsoft 允许会议组织者或已授权与会者（如会议策略设置中定义）从会议内部拨出呼叫到 44 [个 A 区国家和地区](audio-conferencing-zones.md)的非高级电话号码。 此权益适用于音频会议每月订阅许可证，不扩展到音频会议按分钟付费许可证。

此外，免费拨出期间有 900 分钟的限制，如下所示：

具有许可证使用位置 (该位置的用户是在 _any_ _ 国家或地区Microsoft 365 管理中心) 许可区域中定义的用户国家或地区位置，可以从会议拨出到 44 [个 A 区国家和地区](audio-conferencing-zones.md)中的任何一个。 每个用户每月可接收 900 分钟的时间，用于在租户级别共用 _的任何_[区域 A 区域和区域](audio-conferencing-zones.md)。 例如，一个客户购买了 115 个音频会议订阅许可证，在美国有 10 个用户，在英国有 100 个用户，印度有 5 个用户，所有这些用户都为其用户分配了音频会议订阅许可证。

- 所有 115 个用户共享一个池 (115 个用户 X 900 分钟) = 每个日历月 103，500 个会议拨出分钟数，可用于向任何 [区域 A 国家/地区](audio-conferencing-zones.md)发出出站呼叫。

- 超过每个日历月 103，500 分钟的所有呼叫均使用通信额度按我们向该目标发布的费率按每分钟计费。  (注意：租户必须设置通信额度，并将通信额度许可证分配给会议组织者) 。

- 非区域 [A 国家和地区](audio-conferencing-zones.md) 列表中的目标的所有出站呼叫均使用通信额度按每分钟计费， (提供的租户已设置通信额度并将通信点数许可证分配给会议组织者) 。

> [!NOTE]
> 可以在 Teams 管理中心针对拨出分钟池监视使用情况。 在 Microsoft Teams 管理中心中，转到 **旧版门户** > **报表** > **PSTN 分钟池**。 此免费分钟池将在报告中标记为“对区域 A 国家和地区的出站呼叫”。

当租户的拨出分钟数池利用率达到 80% 和 100% 时，将向给定客户的所有租户管理员发送Email通知。

对于每分钟计费的拨出呼叫 (超过租户拨出分钟池的呼叫或对不在 [区域 A 区域](audio-conferencing-zones.md) 列表) 的目标的呼叫，呼叫及其关联费率主要基于呼叫目标，而不是基于发起拨出呼叫的组织者或参与者的国家或地区。 例如，如果呼叫法国的电话号码是由美国中的会议参与者发起的，则呼叫的费率将相同。

有关通信额度的详细信息，请参阅 [通信额度](what-are-communications-credits.md)。

## <a name="related-topics"></a>相关主题

- [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [音频会议的国家和地区区域](audio-conferencing-zones.md)
