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
description: 了解 Microsoft Teams 中 Microsoft 365 通话计划和音频会议的免费拨出期。
ms.openlocfilehash: 72ec36eb99a4a0eb2358195a52db00b26bb591e5
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641893"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>音频会议免费拨出期

## <a name="teams-pstn-services"></a>Teams PSTN 服务

客户可以根据 Teams PSTN 服务使用条款和客户的批量许可协议中允许使用 Microsoft 365 或通话计划和 Teams 音频会议。 可在 [许可资源和文档](https://www.microsoft.com/licensing/docs)中找到 PSTN 服务使用条款。

### <a name="end-of-complimentary-dial-out-period"></a>免费拨出期结束

免费拨出功能于 2019 年 12 月 1 日结束。 有关详细信息，请参阅 [音频会议订阅拨出并致电我](audio-conferencing-subscription-dial-out.md)。

对于音频会议订阅可用的国家/地区，此更改并未发生，但我们目前不启用设置通信额度。 这些特定国家是俄罗斯、韩国和台湾。

### <a name="complimentary-dial-out-period-details"></a>免费拨出时间段详细信息

对于采用 Microsoft 365 音频会议服务的客户，Microsoft 将提供额外的免费权益，与从由分配 Microsoft 365 音频会议订阅许可证的用户组织的会议中拨出到 2019 年 11 月相关的额外免费权益。 在此免费时间段内，Microsoft 允许会议组织者或授权与会者（如会议策略设置中定义）从会议内部拨打非高级电话号码（在 A 区域 44 [个国家和地区](audio-conferencing-zones.md)）。 此权益适用于音频会议每月订阅许可证，并且不扩展到音频会议每分钟付费许可证。

此外，免费拨出期间有 900 分钟的限制，如下所示：

拥有许可证使用位置 (位置的用户是 _任何_ _ 国家/地区Microsoft 365 管理中心) 的许可区域中定义的用户国家/地区位置，可以从会议拨出到 44 [个区域 A 国家和地区](audio-conferencing-zones.md)中的任何一个。 每个用户每月向 _任何_ [A 区域国家和地区](audio-conferencing-zones.md)接收 900 分钟，这些国家和地区在租户级别共用。 例如，客户已购买 115 个音频会议订阅许可证，在美国有 10 个用户、100 个英国用户和 5 个印度用户，所有这些用户都分配有音频会议订阅许可证。

- 所有 115 个用户共享一个 (115 个用户的池 X 900 分钟) = 每个日历月 103，500 个会议拨出分钟数，可用于向任何 [A 区域国家和地区](audio-conferencing-zones.md)发出出站呼叫。

- 每个日历月超过 103，500 分钟的所有呼叫均使用通信额度按我们发布到该目标的费率按每分钟计费。  (注意：租户必须设置通信额度并将通信信用额度许可证分配给会议组织者) 。

- 对不在 [A 区国家和地区](audio-conferencing-zones.md) 列表中的目标的所有出站呼叫均按每分钟使用通信额度计费，我们已发布到该目标的费率 (前提是租户已设置通信信用额度并向会议组织者分配通信额度许可证) 。

> [!NOTE]
> 可以针对 Teams 管理中心内的拨出分钟池监视使用情况。 在 Microsoft Teams 管理中心，转到 **旧版门户** > **报告** > **PSTN 分钟池**。 报表中将此免费分钟池标记为“对 A 区域国家和地区的出站呼叫”。

当租户的拨出分钟池的使用率达到 80% 和 100% 时，将向给定客户的所有租户管理员发送Email通知。

对于每分钟计费的拨号呼叫 (超过租户拨出分钟池的呼叫或未在 [A 区国家和地区](audio-conferencing-zones.md) 列表) 的呼叫，呼叫及其关联费率主要基于呼叫的目标，而不是组织者或发起拨号呼叫的参与者的国家或地区。 例如，如果呼叫法国的电话号码是由美国或法国的会议参与者发起的，则其收费费率相同。

有关通信额度的详细信息，请参阅 [通信额度](what-are-communications-credits.md)。

## <a name="related-topics"></a>相关主题

- [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [音频会议的国家/地区区域](audio-conferencing-zones.md)
