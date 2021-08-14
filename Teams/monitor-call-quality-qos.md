---
title: 监视和改进呼叫质量Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用"服务质量" (QoS) 设置，然后在"呼叫分析"和"呼叫质量仪表板"Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0b7458c18b25acc1e4d501a1f41da01a5dc3b963
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58243569"
---
# <a name="microsoft-teams-monitor-and-improve-call-quality"></a>Microsoft Teams：监视和改进呼叫质量

本文介绍可用于监视、排查、管理和提高呼叫质量的三种关键Microsoft Teams。 

- **调用质量仪表板 (CQD) ：** 要分析组织范围内的趋势或问题，请推动性能改进

- **呼叫分析**：分析单个用户的呼叫和会议质量

- **QoS (服务质量) ：** 确定重要网络流量的优先级



## <a name="monitor-and-troubleshoot-call-quality"></a>监视和排查呼叫质量问题
你将使用按用户的呼叫分析和呼叫质量 **仪表板** 来查找和排查正在进行的操作期间出现呼叫质量问题。 这样，可以在整个网络中推动性能改进。 这两个工具都位于Teams中心。

 - **呼叫分析** 显示与特定呼叫和会议相关的设备、网络和连接的详细信息，这些呼叫 **** 和会议适用于 Teams。 Teams管理员和技术支持代理将使用此信息来排查特定呼叫中的呼叫质量和连接问题。 有关详细信息，请阅读[设置呼叫分析和](set-up-call-analytics.md)[使用呼叫分析来排查通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **使用 CQD (** 呼叫质量) 可让你在整个网络中查看呼叫质量 ****。 使用 CQD 信息来帮助识别和修复问题。 首先 [，设置 CQD](turning-on-and-using-call-quality-dashboard.md)。 然后阅读[在 中管理呼叫和会议Teams。](quality-of-experience-review-guide.md)

 调用分析和 CQD 并行运行，可以独立或一起使用。 例如，如果通信支持专家确定他们需要更多帮助来排查用户的呼叫问题，他们会将呼叫上报给通信支持工程师，该工程师有权访问有关呼叫的其他信息。 反过来，通信支持工程师会向网络工程师发出警报，提醒他们注意呼叫分析中可能发现的网站相关问题。 网络工程师会检查 CQD，以查看与网站相关的整体问题是否可能是用户呼叫问题的促成原因。


## <a name="prioritize-important-network-traffic-using-qos"></a>使用 QoS 确定重要网络流量的优先级
随着用户开始使用 Teams呼叫和会议，他们可能会遇到呼叫者语音中断或呼叫或会议中断。 共享视频可能会冻结或像素化，或完全失败。 这是因为表示语音和视频流量遇到网络拥塞并按顺序到达或完全无法到达的 IP 数据包。 如果发生这种情况 (或防止它最初) ，请使用服务质量 (**QoS) 。** 

使用 QoS，可以优先处理延迟敏感的网络流量 (例如语音或视频流) ，从而允许它在不太敏感的流量前"切线" (例如下载新应用，其中额外下载秒数不是一个大问题) 。 QoS 使用 Windows 组策略对象和名为基于端口的访问控制列表的路由功能来识别并标记实时流中的所有数据包，该功能指示网络提供语音、视频和屏幕共享其自己的专用网络带宽。

理想情况下，你将在内部网络上实现 QoS，同时准备推出Teams，但你可以随时实现。 如果足够小，可能不需要 QoS。

准备就绪后，请阅读在 (中实现服务质量[) QoS Microsoft Teams。](QoS-in-Teams.md)

若要使用 QoS 管理会议流量，请阅读设置如何处理会议实时[媒体Teams流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>相关主题

[设置呼叫分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[设置 CQD](turning-on-and-using-call-quality-dashboard.md)

[管理呼叫和会议质量Teams](quality-of-experience-review-guide.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
