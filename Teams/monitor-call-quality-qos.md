---
title: 监控和提高 Microsoft 团队的通话质量
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用 "服务质量（QoS）" 设置，然后在 Microsoft 团队中调用分析和通话质量仪表板。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085930"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>监控和提高 Microsoft 团队的通话质量

本文介绍了可用于在 Microsoft 团队中监控、解决、管理和改进通话质量的三个关键工具。 

- **通话质量仪表板（CQD）**：分析组织范围内的趋势或问题，提高性能

- **调用分析**：分析单个用户的通话和会议质量

- **服务质量（QoS）**：确定重要网络流量的优先级



## <a name="monitor-and-troubleshoot-call-quality"></a>监控通话质量并解决问题
您将使用每用户**呼叫分析**和**通话质量仪表板**查找并解决正在进行的操作中出现的通话质量问题。 这可让你在网络上推动性能改进。 这两个工具均位于团队管理中心。

 - "**呼叫分析**" 显示与团队中每个用户的***特定呼叫和会议***相关的设备、网络和连接的详细信息。 团队管理员和帮助台工程师将使用此信息来解决特定呼叫中的通话质量和连接问题。 若要了解详细信息，请参阅[设置呼叫分析](set-up-call-analytics.md)和[使用呼叫分析解决较差的通话质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **通话质量仪表板（CQD）** 在整个组织内为您提供通话质量的***网络视图***。 使用 CQD 信息帮助您识别并解决问题。 首先，[设置 CQD](turning-on-and-using-call-quality-dashboard.md)。 然后阅读[团队中的 "管理通话和会议质量"](quality-of-experience-review-guide.md)。

 调用分析和 CQD 并行运行，并且可以独立使用，也可以一起使用。 例如，如果通信支持专家确定他们需要更多的帮助来解决用户的呼叫问题，他们将呼叫提升到通信支持工程师，该工程师有权访问有关呼叫的其他信息。 然后，通信支持工程师将向网络工程师发出警报，通知他们可能会在通话分析中注意到的与网站相关的问题。 网络工程师检查 CQD 以了解网站的总体相关问题是否可能是导致用户呼叫问题的原因。


## <a name="prioritize-important-network-traffic-using-qos"></a>使用 QoS 确定重要网络流量的优先级
当用户开始使用团队进行呼叫和会议时，他们可能会遇到呼叫者的语音或通话或会议。 共享视频可能冻结或像素化，或者完全失败。 这是由于表示语音和视频流量导致网络拥塞的 IP 数据包，或者根本就不在序列中。 如果发生这种情况（或阻止其在第一个位置发生），请使用 "**服务质量（QoS）**"。 

使用 QoS，你可以为延迟敏感的网络流量（例如，语音或视频流）设置优先级，从而允许它 "在不太敏感的通信（如下载新应用，要下载的额外第二秒）" 之前 "在行中剪切"。 QoS 使用 Windows 组策略对象和一个名为基于端口的访问控制列表的路由功能在实时流中标识和标记所有数据包，这将指示你的网络为语音、视频和屏幕共享自己的专用网络带宽。

理想情况下，你将在你的内部网络上实施 QoS，同时准备好部署团队，但你可以随时执行此操作。 如果您非常小，则可能不需要 QoS。

准备就绪后，请阅读[Microsoft 团队中的实施服务质量（QoS）](QoS-in-Teams.md)。

若要使用 QoS 管理会议流量，请参阅[设置你希望如何处理团队会议的实时媒体流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>相关主题

[设置呼叫分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[设置 CQD](turning-on-and-using-call-quality-dashboard.md)

[在团队中管理通话和会议质量](quality-of-experience-review-guide.md)

[Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

