---
title: 在 Microsoft Teams 中实施 QoS 和监控通话分析
author: dstrome
ms.author: dstrome
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 使用 "服务质量（QoS）" 设置，然后在 Microsoft 团队中调用分析和通话质量仪表板。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: f20b12a867c6ed248fb00bad2d3fb5e9074c2c25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138053"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>在 Microsoft 团队中实施 QoS 和监控通话质量

## <a name="get-started"></a>入门

当用户开始使用团队进行呼叫和召开会议时，他们可能会遇到呼叫或会议的呼叫者语音或 chopping。 共享视频可能冻结或像素化，或者完全失败。 这是由于表示语音和视频流量导致网络拥塞的 IP 数据包，或者根本就不在序列中。 有多种方法可在它们表面上发现这些问题并防止其返回，主要是服务质量（QoS）。

**服务质量（QoS）** 是一种允许实时网络流量（如语音或视频流）的一种方法，该功能对网络延迟非常敏感（如下载新应用程序，这种情况下，下载不太多的情况）。 QoS 使用 Windows 组策略对象和一个名为基于端口的访问控制列表的路由功能在实时流中标识和标记所有数据包，这样就可以帮助您的网络提供语音、视频和屏幕共享流其自己的专用部分网络带宽。

 现在，我们将只是说它非常喜欢通过邮件发送信件：如果你向其发送一条短信，那么，如果你将其发送到第一类，它获得的速度会更快，并且如果你发送 it 优先邮件，它将在两天内收到。 当然，网络比邮件运行速度更快，但它仍会运行，速度对某些应用程序至关重要，对其他应用不太重要。 这种主题在最初的理解中很难理解，但它在用户体验方面的差异非常大，因此需要提前投入大量时间和精力。 阅读[Microsoft 团队中的实施服务质量（QoS）](QoS-in-Teams.md) ，以便更详细地讨论。

理想情况下，你可以在你的内部网络上实现 QoS，同时设置团队，但如果你的空间足够小，则可以选择。 这允许对延迟敏感的语音和视频流量进行优先排列，使其优先于其他流量。 你将在[Microsoft 团队管理中心](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)以及你的网络中的交换机和路由器上对所有[客户端设备](QoS-in-Teams-clients.md)执行此优先顺序。

"[**呼叫分析" 和 "呼叫质量" 仪表板**](difference-between-call-analytics-and-call-quality-dashboard.md)用于查找和解决正在进行的操作中出现的问题。  

"**呼叫分析**" 显示与 Microsoft 团队或 Skype for business 帐户中每个用户的***特定呼叫和会议***相关的设备、网络和连接的详细信息。 如果你是 Office 365 管理员，则可以使用呼叫分析解决特定呼叫中遇到的通话质量和连接问题。 这可以帮助你识别和消除问题。

**通话质量仪表板（CQD）** 旨在帮助管理员和网络工程师优化***网络***，而不是分析和解决单个通话。 CQD 将焦点从特定用户转移，以查看整个组织的聚合信息。 这还可以帮助你识别和消除问题。

## <a name="related-topics"></a>相关主题

[在 Microsoft 团队中实施服务质量（QoS）](QoS-in-Teams.md)

[视频：通话质量概述](https://aka.ms/teams-quality)

[设置通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[打开并使用通话质量仪表板](turning-on-and-using-call-quality-dashboard.md)

[通话质量仪表板中可用的维度和衡量指标](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通话质量仪表板中的流分类](stream-classification-in-call-quality-dashboard.md)