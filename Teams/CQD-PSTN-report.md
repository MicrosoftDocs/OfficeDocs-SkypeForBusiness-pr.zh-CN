---
title: 使用 CQD PSTN 直接路由报告
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: 使用 CQD Microsoft Teams呼叫质量仪表板 (PSTN) ) 路由报告来监视和排查 PSTN 呼叫Microsoft Teams。
ms.openlocfilehash: ae36ff214de2142b74b8493e925e25f32572709c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726421"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>使用 CQD PSTN 直接路由报告

我们于 2020 年 3 月新增了一个 Microsoft Teams 呼叫质量仪表板 (CQD) PSTN 直接路由报告，该报表已添加到[CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)的可下载 Power BI 查询模板中。 


CQD PSTN 直接路由报告 (CQD PSTN 直接路由报告.pbit) 可帮助你了解 PSTN 服务的使用模式和质量。 使用此报告可以监视服务使用情况、有关会话边界控制器 (SBC) 、电话服务、网络参数和网络有效性比详细信息。 此信息可帮助你识别问题，包括通话中断的原因。 例如，你将能够查看音量下降时间、受影响的调用数量以及原因。


CQD PSTN 直接路由报告包含四个部分：

  - [PSTN 概述](#pstn-overview)

  - [服务详细信息](#service-details)

  - [网络有效性比](#network-effectiveness-ratio)

  - [网络参数](#network-parameters)

## <a name="highlights"></a>突出显示

1. 按呼叫类型、SBC、呼叫方和被叫方国家/地区进行分析

   CQD PSTN 直接路由报告聚合了过去 7、30 或 180 天内租户中所有 SDC 的可靠性与使用情况指标， (6 个月) 。 可以按呼叫类型、SBC、呼叫方和被调用方国家/地区分析数据。 如果对特定 SBC 或国家/地区感兴趣，将能够识别所选时间范围内的趋势变化。
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 直接路由报告中提供的筛选器的屏幕截图。":::
   
2. 跟踪趋势

    在尝试了解服务使用情况和可靠性时，趋势分析至关重要。 每小时趋势提供每日性能的仔细查看，帮助识别实时事件。 通过每日趋势，可长期查看服务运行状况。 必须能够在具有适当数据粒度的这两种模式之间切换。 CQD PSTN 直接路由报告提供 6 个月趋势概述、7 天和 30 天每日趋势以及每小时趋势，以便分析每个级别的性能。
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 直接路由报告中的趋势图的屏幕截图。":::

3. 钻取到 SBC 或用户级别

   我们一直在 CQD 中的许多数据类别上构建钻取功能，让你快速了解 SBC 或用户级别的使用情况或可靠性分布。 通过使用钻取，可以快速发现问题并了解实际用户的影响。 CQD PSTN 直接路由报告功能钻取服务详细信息和网络有效性比指标。 单击感兴趣的数据点，钻取 SBC 或用户级详细信息。
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="屏幕截图，显示一个数据点上的钻取功能。":::


## <a name="pstn-overview"></a>PSTN 概述

CQD PSTN 直接路由报告提供与过去 180 天服务总体运行状况相关的以下信息。
![屏幕截图：PSTN CQD 报告。](media/CQD-PSTN-report1.png)

例如，如果对通过 SBC 的所有入站呼叫的总体使用情况和运行状况感兴趣，abc.bca.adatum.biz 美国作为内部国家/地区：

| **呼叫** | **说明**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | 可以使用顶部的筛选器向下钻取并选择"ByotIn"作为呼叫类型，abc.bca.contoso.com"会话板控制器"和"美国"作为内部国家/地区。 |
| 2            | 过去 180 天的使用趋势。 可以在"服务详细信息"页上找到使用情况详细信息报表。                                                                     |
| 3            | 过去 180 天的后拨号延迟、延迟、抖动和数据包丢失趋势。 可以在"网络参数"页上找到详细报告。                           |
| 4            | 过去 180 天的并发呼叫和每日活动用户趋势。 此图表可帮助你了解服务的最大容量。                            |
| 5            | 呼叫结束原因影响过去 180 天的服务质量。 可以在网络有效比率和 NER (上) 运行状况详细信息。                    |

## <a name="service-details"></a>服务详细信息

此页面提供每天的服务使用趋势和按地理划分的用户反馈。

  - **总尝试次数 –** 该时间范围内尝试调用总数，包括成功和失败的调用

  - **已连接呼叫总数 -** 该时间范围内已连接呼叫总数

  - **总分钟数 –** 该时间范围内分钟使用量总计

  - **每日活动用户 (DAU) –** 当天至少进行了一次已连接呼叫的每日活动用户的计数

  - **并发调用 –** 一分钟内同时进行的活动呼叫的最大数量

  - **用户反馈 –** "评价我的通话"分数来自用户。 3-5 被认为是一个很好的调用。 1-2 被视为错误调用。

![屏幕截图：PSTN CQD 报告。](media/CQD-PSTN-report2.png)

例如：

1.  如果看到平均呼叫持续时间在 2020 年 2 月 14 日下降到 0，可以首先检查呼叫量是否正常，并查看总连接呼叫和总尝试呼叫之间是否存在很大差异。 然后转到"网络有效性比"页，对呼叫失败原因进行投资。

2.  如果在用户反馈地图上看到红点不断增加，可以转到"网络有效性比"页和网络参数，查看是否有异常，并且可以使用 MS 服务台提出票证。

## <a name="network-effectiveness-ratio"></a>网络有效性比

这是"总体运行状况"仪表板上显示的指标。 可以在下面的"每小时网络有效率"和"呼叫结束原因"图表上查看具有受影响呼叫详细信息的每小时 NER (入站/出站) 。

  - **NER** - (%) 通过测量已发送的呼叫数与发送给收件人的呼叫数来传送呼叫。

  - **SIP 响应代码**- 三位数整数响应代码显示呼叫状态。

  - **Microsoft 响应代码**- 从 Microsoft 组件发送的响应代码。

  - **说明** - 对应于 SIP 响应代码和 Microsoft 响应代码的原因阶段。

  - **受影响的呼叫数** - 所选时间范围内受影响的呼叫总数。

> ![屏幕截图：PSTN CQD 报告。](media/CQD-PSTN-report3.png)
> 
例如：

![屏幕截图：PSTN CQD 报告。](media/CQD-PSTN-report4.png)

如果"每日 NER"在 2020 年 2 月 5 日下降，可以单击日期，其他图表将缩放到该特定日期。

![屏幕截图：PSTN CQD 报告。](media/CQD-PSTN-report5.png)

从"NER 良好百分比每小时趋势"中，可发现低值发生在大约 21：00。 然后再次单击以缩放到第 21 小时，并选中"影响呼叫详细信息"以查看该小时内失败的呼叫数以及呼叫结束原因。 如果问题与 SBC 不相关，可以从解决任何 SBC 问题开始自行解决问题，或者向服务台报告。

## <a name="network-parameters"></a>网络参数

从直接路由接口到会话边界控制器测量所有网络参数。 有关建议值的信息，请参阅[准备](prepare-network.md)组织的网络Microsoft Teams，并查看 Customer Edge Microsoft Edge值。

  - **抖动** - 是使用 RTCP 和 RTP 控制协议在两个终结点之间计算的网络传播延迟 (毫秒) 。

  - **数据包丢失** – 是未能到达的数据包的度量值;它是在两个终结点之间计算的。

  - 延迟 **-** (也称为往返时间) 是发送信号所花的时间长度加上接收该信号的确认所花的时间长度。 此时间延迟由信号的两个点之间的传播时间组成。

> ![屏幕截图：PSTN CQD 报告。](media/CQD-PSTN-report6.png)

例如：

如果看到特定日期的四个图表（例如，2020/02/14 的延迟）中的任意一个图表出现峰值 (延迟、抖动、程序包丢失率、后拨号延迟) ，请单击日期点。 底部的每小时趋势图表将刷新以显示每小时数字。 可以通过 MS 服务台检查 SDC 或提出票证。

![屏幕截图：PSTN CQD 报告。](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>相关主题

[使用Power BI分析用于存储的 CQD Microsoft Teams](CQD-PSTN-report.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)