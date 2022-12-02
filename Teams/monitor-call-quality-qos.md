---
title: 监视和改进Microsoft Teams 的通话质量
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用服务质量 (QoS) 设置，然后在 Microsoft Teams 中使用呼叫分析和通话质量仪表板。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 969fc5645023bfcf4ad2bc0aadfe692f61b350f0
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245652"
---
# <a name="improve-call-quality-in-microsoft-teams"></a>提高 Microsoft Teams 中的通话质量

本文介绍三个关键工具，可用于监视、排查、管理和提高 Microsoft Teams 中的通话质量。 

- **呼叫质量仪表板 (CQD)**：若要分析组织范围的趋势或问题，请推动性能改进

- **通话分析**：分析单个用户的通话和会议质量

- **服务质量 (QoS)**：确定重要网络流量的优先级



## <a name="monitor-and-troubleshoot-call-quality"></a>监视通话质量并排查呼叫质量问题
你将使用每用户 **呼叫分析和****通话质量仪表板** 来查找和排查正在进行的操作过程中出现的通话质量问题。 这使你可以推动整个网络的性能改进。 这两个工具都位于 Teams 管理中心。

 - **通话分析** 显示与 Teams 中每个用户  **_的特定通话和会议_** 相关的设备、网络和连接的详细信息。 Teams 管理员和支持人员代理将使用此信息来排查特定呼叫中的通话质量和连接问题。 若要了解详细信息，请阅读[设置呼叫分析和](set-up-call-analytics.md)[使用呼叫分析排查通话质量不佳](use-call-analytics-to-troubleshoot-poor-call-quality.md)的问题。
 
 - **呼叫质量仪表板 (CQD)** 为你提供整个组织的通话质量 **_网络视图_** 。 使用 CQD 信息来帮助你识别和解决问题。 首先， [设置 CQD](turning-on-and-using-call-quality-dashboard.md)。 然后阅读 [在 Teams 中管理通话和会议质量](quality-of-experience-review-guide.md)。

 调用分析和 CQD 并行运行，可以单独使用或一起使用。 例如，如果通信支持专家确定他们需要更多帮助来排查用户的呼叫问题，他们会将呼叫上报给通信支持工程师，该工程师有权访问有关该呼叫的其他信息。 反过来，通信支持工程师会向网络工程师发出警报，提醒他们在通话分析中注意到的可能与站点相关的问题。 网络工程师检查 CQD，以查看与站点相关的整体问题是否可能是导致用户呼叫问题的原因。


## <a name="prioritize-important-network-traffic-using-qos"></a>使用 QoS 确定重要网络流量的优先级
当用户开始使用 Teams 进行通话和会议时，他们可能会遇到呼叫者的声音中断或切断呼叫或会议。 共享视频可能会冻结或像素化，或者完全失败。 这是由于表示语音和视频流量的 IP 数据包遇到网络拥塞并按顺序到达或不按顺序到达。 如果这种情况 (发生，或者为了防止它首先) 发生，请使用 **服务质量 (QoS)**。 

使用 QoS，可以优先考虑延迟敏感网络流量 (例如，语音或视频流) ，允许它在不太敏感 (（例如下载新应用）之前“排队”，其中多下载一秒) 不是什么大不了的事。 QoS 使用 Windows 组策略 对象和路由功能（称为基于端口的访问控制列表）识别和标记实时流中的所有数据包，该功能指示网络为语音、视频和屏幕共享提供自己的专用网络带宽。

理想情况下，你将在准备推出 Teams 的同时在内部网络上实现 QoS，但可以随时执行此操作。 如果足够小，则可能不需要 QoS。

准备就绪后，请阅读[在 Microsoft Teams 中实现服务质量 (QoS) ](QoS-in-Teams.md)。

若要使用 QoS 管理会议流量，请阅读 [设置你希望如何处理 Teams 会议的实时媒体流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。


## <a name="related-topics"></a>相关主题

[设置呼叫分析](set-up-call-analytics.md)

[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[设置 CQD](turning-on-and-using-call-quality-dashboard.md)

[在 Teams 中管理通话和会议质量](quality-of-experience-review-guide.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
