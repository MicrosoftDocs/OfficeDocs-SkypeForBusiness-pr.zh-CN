---
title: 监视和提高 Microsoft Teams 的呼叫质量
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用服务质量 (QoS) 设置，然后在 Microsoft Teams 中使用通话分析和呼叫质量仪表板。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac317ff6ac17a2b6a0e94c0fa5683979cb887b90
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66793239"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>监视和提高 Microsoft Teams 的呼叫质量

本文介绍可用于在 Microsoft Teams 中监视、排查、管理和提高呼叫质量的三个关键工具。 

- **调用质量仪表板 (CQD)**：若要分析组织范围的趋势或问题，请提高性能

- **呼叫分析**：分析单个用户的通话和会议质量

- **服务质量 (QoS)**：确定重要网络流量的优先级



## <a name="monitor-and-troubleshoot-call-quality"></a>监视和排查呼叫质量问题
你将使用每用户 **呼叫分析** 和 **呼叫质量仪表板** 来查找和排查正在进行的操作过程中出现的呼叫质量问题。 这使你可以在网络中推动性能改进。 这两个工具都在 Teams 管理中心。

 - **呼叫分析** 显示与 Teams 中每个用户的  **_特定呼叫和会议_** 相关的设备、网络和连接的详细信息。 Teams 管理员和支持人员代理将使用此信息来排查特定呼叫中的呼叫质量和连接问题。 若要了解详细信息，请阅读 [“设置呼叫分析](set-up-call-analytics.md) ”并 [使用呼叫分析来排查通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。
 
 - **调用质量仪表板 (CQD)** 提供整个组织的呼叫质量 **_网络视图_** 。 使用 CQD 信息来帮助你识别和修复问题。 首先， [设置 CQD](turning-on-and-using-call-quality-dashboard.md)。 然后在 [Teams 中读取“管理呼叫和会议质量](quality-of-experience-review-guide.md)”。

 调用分析和 CQD 并行运行，可以独立使用或一起使用。 例如，如果通信支持专家确定他们需要更多帮助来排查用户的呼叫问题，则会将呼叫上报给通信支持工程师，后者有权访问有关呼叫的其他信息。 反过来，通信支持工程师会提醒网络工程师注意他们在呼叫分析中注意到的可能与站点相关的问题。 网络工程师检查 CQD，以查看与站点相关的总体问题是否可能是导致用户呼叫问题的原因。


## <a name="prioritize-important-network-traffic-using-qos"></a>使用 QoS 确定重要网络流量的优先级
当用户开始使用 Teams 进行呼叫和会议时，他们可能会遇到呼叫者的声音中断或切断呼叫或会议。 共享视频可能会冻结或像素化，或完全失败。 这是由于表示语音和视频流量的 IP 数据包遇到网络拥塞，并且无法按顺序到达。 如果这种情况发生在 (或防止它发生在第一) ，使用 **服务质量 (QoS)**。 

借助 QoS，可以优先考虑延迟敏感的网络流量 (例如，语音或视频流) ，使其能够在不太敏感 (（如下载新应用）的流量前“换行”，其中额外的一秒下载) 不大。 QoS 使用 Windows 组策略 对象和名为“基于端口的访问控制列表”的路由功能来标识和标记实时流中的所有数据包，该功能指示网络提供语音、视频和屏幕共享其自己的专用网络带宽。

理想情况下，你将在内部网络上实现 QoS，同时准备好推出 Teams，但你可以随时执行此操作。 如果足够小，则可能不需要 QoS。

准备好后，请阅读 [Microsoft Teams 中的实现服务质量 (QoS) ](QoS-in-Teams.md)。

若要使用 QoS 管理会议流量，请阅读 [“设置要如何处理 Teams 会议的实时媒体流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)”。


## <a name="related-topics"></a>相关主题

[设置呼叫分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[设置 CQD](turning-on-and-using-call-quality-dashboard.md)

[在 Teams 中管理通话和会议质量](quality-of-experience-review-guide.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
