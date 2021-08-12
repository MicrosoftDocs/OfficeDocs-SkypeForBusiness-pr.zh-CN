---
title: 监视和改进 Microsoft Teams 的通话质量
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用服务质量 (QoS) 设置，然后在 Microsoft Teams 中使用呼叫分析和呼叫质量Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed9bab3ad0cde91bc8faa4298956b07f73438e823e3e3c110ce09610fee5e7c0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286261"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>监视和改进 Microsoft Teams 的通话质量

本文介绍可用于监视、故障排除、管理和提高呼叫质量的三种关键Microsoft Teams。 

- **呼叫质量仪表板 (CQD) ：** 若要分析组织范围内的趋势或问题，请推动性能改进

- **通话分析**：分析单个用户的通话和会议质量

- **QoS (服务质量) ：** 确定重要网络流量的优先级



## <a name="monitor-and-troubleshoot-call-quality"></a>监视呼叫质量并排除其故障
你将使用每用户通话分析和通话质量仪表板来查找和排查正在进行的操作过程中出现呼叫质量问题。 这使你可以驱动整个网络的性能改进。 这两个工具均位于Teams中心。

 - **通话分析** 显示有关设备上每个用户的特定通话和会议相关的设备、网络和Teams。 **** Teams管理员和技术支持代理将使用此信息来排查特定呼叫中的通话质量和连接问题。 若要了解更多信息，请阅读设置 [通话分析](set-up-call-analytics.md) 和使用通话分析 [解决通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **呼叫质量仪表板 (CQD)** 可为你提供整个组织的呼叫质量 **** 网络视图。 使用 CQD 信息来帮助你识别和修复问题。 首先， [设置 CQD](turning-on-and-using-call-quality-dashboard.md)。 然后，[阅读管理呼叫和会议质量Teams。](quality-of-experience-review-guide.md)

 通话分析和 CQD 并行运行，可以单独使用，也可以一起使用。 例如，如果通信支持专家确定他们需要更多帮助来排查用户的呼叫问题，他们会将呼叫上报给通信支持工程师，该工程师可以访问有关呼叫的其他信息。 反过来，通信支持工程师会向网络工程师发出警报，提醒他们在通话分析中发现了一个可能的网站相关问题。 网络工程师检查 CQD，以查看与站点相关的整体问题是否可能导致用户的呼叫问题。


## <a name="prioritize-important-network-traffic-using-qos"></a>使用 QoS 确定重要网络流量的优先级
当用户开始将 Teams 用于呼叫和会议时，他们可能遇到呼叫者的语音中断或中断呼叫或会议。 共享视频可能会冻结或像素化，或者完全失败。 这是因为表示遇到网络拥塞和按顺序到达或不按顺序到达的语音和视频流量的 IP 数据包。 如果发生这种情况 (或阻止它首先) ，请使用 **QoS (服务质量) 。** 

使用 QoS，可优先处理延迟敏感的网络流量 (例如语音流或视频流) ，从而允许它在不太敏感的 (流量（如下载新应用）前"直接排队") 。 QoS 使用 Windows 组策略对象和称为基于端口的访问控制列表的路由功能识别和标记实时流中所有数据包，这将指示网络提供语音、视频和屏幕共享自己的专用网络带宽。

理想情况下，您将在内部网络上实施 QoS，同时准备好Teams，但可以随时执行。 如果足够小，可能不需要 QoS。

准备好后，请阅读在 ([中) QoS](QoS-in-Teams.md)Microsoft Teams。

若要使用 QoS 管理会议流量，请阅读设置如何处理会议实时[Teams流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>相关主题

[设置通话分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[设置 CQD](turning-on-and-using-call-quality-dashboard.md)

[管理呼叫和会议质量Teams](quality-of-experience-review-guide.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)