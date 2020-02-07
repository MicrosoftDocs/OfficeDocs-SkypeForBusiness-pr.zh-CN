---
title: 为 Microsoft Teams 准备贵组织的网络
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
audience: admin
description: 了解如何准备和管理你的 Microsoft Teams 网络。 信息包括网络要求、带宽要求和其他考虑事项。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d331a063feacbaea5cb510c316d2b27d982eb03
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834632"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>为 Microsoft Teams 准备贵组织的网络


Teams 组合了三种形式的流量：

-   Office 365 联机环境与 Teams 客户端之间的数据流量（信号发送、联机状态、聊天、文件上载和下载、OneNote 同步）。

-   点对点实时通信流量（音频、视频、桌面共享）。

-   会议实时通信流量（音频、视频、桌面共享）。

这在两个级别上影响网络：对于点对点应用场景，流量在 Microsoft Teams 客户端之间直接传输；对于会议应用场景，流量在 Office 365 环境与 Microsoft Teams 客户端之间传输。 为了确保获得最佳通信流，必须允许在内部网络段（例如，WAN 上的站点）之间以及网络站点与 Office 365 之间传输流量。 如果未打开正确的端口或主动阻止特定端口，将会导致降低体验。


要在 Microsoft 团队内获得实时媒体的最佳体验，你的网络必须满足 Office 365 的网络要求。 有关详细信息，请参阅[Skype for Business Online 的媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

对于这两个定义网段（客户端到 Microsoft Edge 和客户边缘到 Microsoft Edge），请考虑以下建议。


|值  |客户端到 Microsoft Edge  |客户边缘到 Microsoft Edge  |
|:--- |:--- |:--- |
|**延迟（一种方法）**\*  |< 50ms          |< 30ms         |
|**延迟（RTT 或往返时间）**\* |< 100ms   |< 60ms |
|**爆发数据包丢失**    |在任何200ms 时间间隔内 <10%         |任何200ms 时间间隔内 <1%         |
|**数据包丢失**     |任何15s 时间间隔内 <1%          |任何15s 时间间隔内 <0.1%         |
|**数据包内部到达抖动**    |在任何15s 时间间隔内 <30ms         |在任何15s 时间间隔内 <15ms         |
|**数据包重新排序**    |<0.05% 的订单外数据包         |<0.01% 的订单外数据包         |

\*延迟指标目标假设您的公司网站或网站，Microsoft 边缘位于同一大陆。

您的公司网站与 Microsoft 网络 edge 的连接包括第一跃点网络访问权限，可以是 WiFi 或其他无线技术。

网络性能目标采用正确的带宽和/或[QoS 规划](QoS-in-Teams.md)。 换句话说，当网络连接处于峰值负载时，要求直接适用于团队实时媒体流量。

有关为团队准备网络的更多帮助，请查看[网络 Planner](https://docs.microsoft.com/microsoftteams/network-planner)。


## <a name="bandwidth-requirements"></a>带宽要求
无论您的网络状况如何，Microsoft 团队可为您提供最佳的音频、视频和内容共享体验。 通过可变编解码器，可以在有限的带宽环境中协商媒体，影响最小。 但是，带宽不是个问题，可以针对质量优化体验，包括最高分辨率的视频分辨率、最多30fps 视频和15fps 内容以及高保真音频。

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a>其他网络考虑事项
---------------

#### <a name="external-name-resolution"></a>外部名称解析

确保运行团队客户端的所有客户端计算机可以解析外部 DNS 查询以发现 Office 365 提供的服务，并且你的防火墙不会阻止访问。 有关配置防火墙端口的信息，请转到[Office 365 url 和 IP 范围](office-365-urls-ip-address-ranges.md)。

#### <a name="nat-pool-size"></a>NAT 池大小

当多个用户/设备使用网络地址转换（NAT）或端口地址转换（PAT）访问 Office 365 时，您需要确保隐藏在每个可访问的 IP 地址后面的设备不会超过支持的号码。

若要降低此风险，请确保为 NAT 池分配足够的公共 IP 地址以防止端口耗尽。 当连接到 Office 365 服务时，端口耗尽将导致内部最终用户和设备面临问题。 有关详细信息，请参阅[Office 365 的 NAT 支持](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)。

#### <a name="intrusion-detection-and-prevention-guidance"></a>**入侵检测和阻止指南**

如果你的环境具有针对出站连接的额外安全层而部署的入侵检测和/或防护系统（IDS/IPS），请确保将包含目标到 Office 365 Url 的任何流量列入白名单。

<a name="network-health-determination"></a>网络运行状况确定
-----------------

当规划网络中 Microsoft 团队的实现时，必须确保你拥有所需的带宽，你可以访问所有所需的 IP 地址、正确的端口，并且你可以满足实时媒体的性能要求.

如果您不能满足这些条件，最终用户将不会因在通话和会议期间出现不良质量而从团队获得最佳体验。

如果您不满足这些条件，则需要考虑暂停项目以确保满足条件，然后再继续。


|  |  |  |
|---------|---------|---------|
|![代表决策点的图标](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |决策点         |您是否对支持实时媒体的网络功能进行了评估？<br></br>如果您的网络未正确评估，或者您知道它不支持实时媒体，您是否将禁用视频和屏幕共享功能来减少网络影响和不良团队体验？         |
|![表示后续步骤的图标](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |后续步骤         |网络质量未知：执行网络准备情况评估以确定网络是否已准备好使用实时媒体。<br></br>网络质量差：执行网络修复步骤，为高质量实时媒体提供合适的环境。<br></br>网络满意：确保所有 IP 地址和端口均可正确访问。           |

## <a name="related-topics"></a>相关主题

[视频：网络规划](https://aka.ms/teams-networking)
