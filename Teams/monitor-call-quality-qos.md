---
title: 在 Microsoft Teams 中实施 QoS 和监控通话分析
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jambirk
description: 使用服务质量 (QoS) 设置，然后调用分析和呼叫质量仪表板中的 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 097426e60ebcd141d1c8375343509db5607c50e2
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205768"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>在 Microsoft 团队中实现 QoS 和监视呼叫质量

## <a name="get-started"></a>入门

用户开始使用团队进行呼叫和按住会议，它们可能会遇到分解 chopping 注销呼叫或会议的呼叫者的语音。 共享视频年 5 月冻结或像素化，或完全失败。 这是由于表示语音和视频流量遇到网络拥塞和到达按顺序或者根本不 IP 数据包。 有显现和防止其返回时，主要的服务质量 (QoS) 时确定这些问题的方法。

**服务质量 (QoS)** 是一种方法，以允许 （如语音或视频流） 网络延迟"剪切行中"（如下载新应用程序，其中下载的额外的第二个不太敏感的通信之前对敏感的实时网络流量不大不了）。 QoS 标识标记中使用 Windows 组策略对象的实时流的所有数据包和名为基于端口的访问控制列表，然后帮助您为提供语音、 视频和屏幕共享的网络的路由功能流自己专用的部分网络带宽。

 现在，我们将只需说，它十分相似发送至邮件信件： 如果您将其发送它获取很快存在并且的足够了，如果您将其发送它获取大量更快、 存在的第一个类和如果优先级邮件发送的书籍速率它在两天内那里获取。 当然网络运行速度大于邮件，但它仍然运行速度是关键某些应用程序，而不是其他人如此重要，则返回 true。 本主题本质上是详细和难理解，但它使用户体验，以便它具有巨大区别值得方面投入时间和能耗提前。 读取[实现的服务质量 (QoS) 中的 Microsoft 团队](QoS-in-Teams.md)的更详细的讨论。

理想情况下将在内部网络时设置团队上实现 QoS，但如果您是小型足够它可以为可选。 这样的延迟敏感语音和视频流量以获取其他通信之前确定其优先级。 在网络中，可以实现此上的所有[客户端设备](QoS-in-Teams-clients.md)，在[Microsoft 团队管理中心](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)中，以及开关和路由器上的优先顺序。

[**调用分析和呼叫质量仪表板**](difference-between-call-analytics-and-call-quality-dashboard.md)用于查找和解决日常操作过程中遇到的问题。  

**调用分析**显示设备、 网络和连接到***特定的呼叫和会议的***每个用户的 Microsoft 团队或 Skype 中业务帐户相关的详细的信息。 如果您是 Office 365 管理员，您可以使用调用分析解决特定呼叫中有经验的呼叫质量和连接问题。 这可以帮助您确定并消除问题。

**呼叫质量仪表板 (CQD)** 旨在帮助管理员和网络工程师将优化***网络***、 不分析和疑难解答单个呼叫。 CQD 将焦点转移从特定的用户可以这样看待为整个组织的聚合信息。 这可以帮助您确定并消除问题。

## <a name="related-topics"></a>相关主题

[在 Microsoft 团队中实现服务质量 (QoS)](QoS-in-Teams.md)

[视频： 呼叫质量概述](https://aka.ms/teams-quality)

[设置通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[打开并使用通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)