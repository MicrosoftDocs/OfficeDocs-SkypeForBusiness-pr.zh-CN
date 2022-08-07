---
title: 使用 CQD PSTN 直接路由报告
author: CarolynRowe
ms.author: crowe
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
description: 使用 Microsoft Teams 呼叫质量仪表板 (CQD) ) PSTN 直接路由报告监视和排查 Microsoft Teams 中的 PSTN 调用问题。
ms.openlocfilehash: 7b7205658358cfa3aa90824718c03731fa33a534
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270707"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>使用 CQD PSTN 直接路由报告

Microsoft Teams 通话质量仪表板 (CQD) PSTN 直接路由报表在 [CQD 的可下载 Power BI 查询模板](https://www.microsoft.com/download/details.aspx?id=102291)中可用。 


CQD PSTN 直接路由报表 (CQD PSTN 直接路由报表.pbit) 可帮助你了解 PSTN 服务的使用模式和质量。 使用此报表监视服务使用情况、会话边框控制器 (SBC) 、电话服务、网络参数和网络有效性比率详细信息。 此信息可以帮助你识别问题，包括呼叫被丢弃的原因。 例如，你将能够查看音量何时下降，或者有多少个调用受到影响，以及出于什么原因。


CQD PSTN 直接路由报告有四个部分：

  - [PSTN 概述](#pstn-overview)

  - [服务详细信息](#service-details)

  - [网络有效性比率](#network-effectiveness-ratio)

  - [网络参数](#network-parameters)

## <a name="highlights"></a>突出

1. 按呼叫类型、SBC、调用方和被调用方国家/地区进行分析

   CQD PSTN 直接路由报告聚合了租户上过去 7、30 天或 180 天的可靠性和使用情况指标， (6 个月) 。 可以按呼叫类型、SBC、调用方和被调用方国家/地区分析数据。 如果你对特定的 SBC 或国家/地区感兴趣，你将能够识别所选时间范围内趋势的变化。
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 直接路由报告中可用的筛选器的屏幕截图。":::
   
2. 跟踪趋势

    在尝试了解服务使用情况和可靠性时，趋势分析至关重要。 每小时趋势可密切了解每日性能，这有助于识别实时事件。 通过每日趋势，可以从长期角度查看服务运行状况。 在具有适当数据粒度的这两种模式之间切换非常重要。 CQD PSTN 直接路由报告提供 6 个月趋势概述、7 天和 30 天每日趋势以及每小时趋势，以便可以分析每个级别的性能。
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 直接路由报告中趋势图的屏幕截图。":::

3. 钻取到 SBC 或用户级别

   我们一直在 CQD 中针对许多数据类别构建钻取功能，这使你能够快速了解 SBC 或用户级别的使用情况或可靠性分布。 通过使用钻取，可以快速查找问题并了解实际的用户影响。 CQD PSTN 直接路由报告功能深入了解服务详细信息和网络有效性比率指标。 单击你感兴趣的数据点，深入了解 SBC 或用户级详细信息。
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="显示数据点上的钻取功能的屏幕截图。":::


## <a name="pstn-overview"></a>PSTN 概述

CQD PSTN 直接路由报告提供了与过去 180 天服务的总体运行状况相关的以下信息。
![屏幕截图：PSTN CQD 报表。](media/CQD-PSTN-report1.png)

例如，如果你对通过 SBC 进行的所有入站呼叫的总体使用情况和运行状况感兴趣，abc.bca.adatum.biz 美国作为内部国家/地区：

| **调用** | **说明**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | 可以使用顶部的筛选器向下钻取并选择 ByotIn 作为调用类型，abc.bca.contoso.com 为会话板控制器，将美国作为内部国家/地区。 |
| 2            | 过去 180 天的使用趋势。 可以在“服务详细信息”页上找到使用情况详细信息报告。                                                                     |
| 3            | 过去 180 天的拨号延迟、延迟、抖动和数据包丢失趋势。 可以在“网络参数”页上找到详细信息报表。                           |
| 4            | 过去 180 天的并发呼叫和每日活动用户趋势。 此图表可帮助你了解服务的最大卷。                            |
| 5            | 顶级呼叫结束原因影响过去 180 天的服务质量。 可以在网络有效比率 (NER) 页上找到服务运行状况详细信息。                    |

## <a name="service-details"></a>服务详细信息

此页面提供每天的服务使用趋势和按地理位置划分的用户反馈细分。

  - **尝试调用总数 –** 该时间范围内的尝试调用总数，包括成功和失败的调用

  - **已连接呼叫总数 -** 该时间范围内的已连接呼叫总数

  - **总分钟数 –** 该时间范围内的总分钟使用量

  - **每日活动用户 (DAU) -** 在当天至少拨打一次连接呼叫的每日活动用户计数

  - **并发调用 –** 一分钟内同时处于活动状态调用的最大数目

  - **用户反馈 -** “评分我的呼叫”分数来自用户。 3-5 被认为是一个很好的调用。 1-2 被视为错误调用。

![屏幕截图：PSTN CQD 报表。](media/CQD-PSTN-report2.png)

例如：

1.  如果在 2020/02/14 时看到平均呼叫持续时间降至 0，则可以首先检查呼叫量是否正常，并查看总连接调用与总尝试调用之间是否存在较大差异。 然后转到“网络有效性比率”页，针对呼叫失败原因进行投资。

2.  如果在用户反馈地图上看到越来越多的红点，可以转到“网络有效性比率”页和“网络参数”，查看是否有任何异常，并且可以使用 MS 服务台提高票证。

## <a name="network-effectiveness-ratio"></a>网络有效性比率

这是显示在“整体运行状况”仪表板上的相同指标。 可以根据每小时网络有效性比率和下面的呼叫结束原因图表检查每小时 NER 号码和受影响的呼叫详细信息，了解两个呼叫方向 (入站/出站) 。

  - **NER** - 通过测量发送的呼叫数与发送给收件人的呼叫数来 (%) 网络传送呼叫的能力。

  - **SIP 响应代码** - 三位数整数响应代码显示调用状态。

  - 从 Microsoft 组件发送的 **Microsoft 响应代码**-A 响应代码。

  - **说明** - 与 SIP 响应代码和 Microsoft 响应代码对应的原因阶段。

  - **受影响的呼叫数** – 在所选时间范围内受影响的呼叫总数。

> ![屏幕截图：PSTN CQD 报表。](media/CQD-PSTN-report3.png)
> 
例如：

![屏幕截图：PSTN CQD 报表。](media/CQD-PSTN-report4.png)

如果每日 NER 在 2020/02/02/02/025 时出现下降，则可以单击日期，其他图表将缩放到该特定日期。

![屏幕截图：PSTN CQD 报表。](media/CQD-PSTN-report5.png)

从 NER 好百分比每小时趋势，你可以发现下降发生在 21：00 左右。 然后再次单击以放大到小时 21，并检查受影响的呼叫详细信息，以查看该小时内有多少个呼叫失败，以及呼叫结束原因是什么。 可以从针对任何 SBC 问题进行自麻烦拍摄开始，或者在问题与 SBC 无关时向服务台报告。

## <a name="network-parameters"></a>网络参数

所有网络参数都从直接路由接口测量到会话边框控制器。 有关建议值的信息，请参阅 [为 Microsoft Teams 准备组织的网络](prepare-network.md)，并查看 Customer Edge 到 Microsoft Edge 的建议值。

  - **Jitter** – 使用 RTCP (RTP 控制协议) 计算两个终结点之间网络传播延迟时间变化的毫秒度量值。

  - **数据包丢失** - 是无法到达的数据包的度量值;它是在两个终结点之间计算的。

  - **延迟** - (也称为往返时间) 是发送信号所需的时间长度，以及确认接收该信号所需的时间长度。 此时间延迟由信号的两个点之间的传播时间组成。

> ![屏幕截图：PSTN CQD 报表。](media/CQD-PSTN-report6.png)

例如：

如果在延迟 (、抖动、包丢失率、拨号延迟) 特定日期（例如 2020/02/14 的延迟）的四个图表中的任何一个出现峰值，请单击日期点。 底部的每小时趋势图将刷新以显示每小时数字。 可以使用 MS 服务台检查 SBC 或提高票证。

![屏幕截图：PSTN CQD 报表。](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>相关主题

[使用 Power BI 分析 Microsoft Teams 的 CQD 数据](CQD-PSTN-report.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
