---
title: 为 Microsoft Teams 准备贵组织的网络
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: 了解如何准备和管理你的 Microsoft Teams 网络。 信息包括网络要求、带宽要求和其他考虑事项。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f8b3105889021408983c8e3ae249c74833e65ced
ms.sourcegitcommit: 8e5fc1d8c19a7f26f53e40b23dd6476a8c6d805f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800070"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>为 Microsoft Teams 准备贵组织的网络


Teams 组合了三种形式的流量：

-   Office 365 联机环境与 Teams 客户端之间的数据流量（信号发送、联机状态、聊天、文件上载和下载、OneNote 同步）。

-   点对点实时通信流量（音频、视频、桌面共享）。

-   会议实时通信流量（音频、视频、桌面共享）。

这在两个级别上影响网络：对于点对点应用场景，流量在 Microsoft Teams 客户端之间直接传输；对于会议应用场景，流量在 Office 365 环境与 Microsoft Teams 客户端之间传输。 为了确保获得最佳通信流，必须允许在内部网络段（例如，WAN 上的站点）之间以及网络站点与 Office 365 之间传输流量。 如果未打开正确的端口或主动阻止特定端口，将会导致降低体验。

> [!NOTE]
> IOS 和 Android 移动设备上支持会议。 

若要获取的 Microsoft 团队中的实时媒体与获得最佳体验，您的网络必须满足 Office 365 的网络要求。 有关详细信息，请参阅 [Skype for Business Online 的媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

对于两个定义网络段（客户端到 Microsoft Edge 和客户边缘到 Microsoft Edge），请考虑以下建议：


|值  |客户端到 Microsoft Edge  |客户边缘到 Microsoft Edge  |
|:--- |:--- |:--- |
|**延迟 （一种方法）**\*  |< 50 ms          |< 30 ms         |
|**延迟 （RTT 或往返时间）**\* |< 100 ms   |< 60 ms |
|**突发数据包丢失**    |< 10%，在任何 200 ms 时间间隔内         |< 1%，在任何 200 ms 时间间隔内         |
|**数据包丢失**     |< 1%，在任何 15 s 时间间隔内          |< 0.1%，在任何 15 s 时间间隔内         |
|**数据包中间间隔抖动**    |< 30 ms，在任何 15 s 时间间隔内         |< 15 ms，在任何 15 s 时间间隔内         |
|**数据包重新排序**    |< 0.05% 无序数据包         |< 0.01% 无序数据包         |

\*延迟指标目标假定您的公司网站和 Microsoft 边缘位于同一洲。

公司网站连接到 Microsoft 网络边缘包含第一个跃点网络访问，可以是 WiFi 或其他无线技术。

网络性能目标假定适当的带宽和/或[QoS 规划](QoS-in-Teams.md)。 换句话说的要求适用于团队实时的媒体流量直接峰值负载下的网络连接时。

若要测试两个网络段，您可以使用[网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799)。 此工具可以部署这两个客户端上 PC 直接并连接到客户网络边缘 PC 上。 该工具包含有限的文档，但围绕使用率的工具更深入地介绍文档可在此处找到：[网络准备情况评估](https://go.microsoft.com/fwlink/?linkid=855800)。 通过运行此网络准备情况评估，您可以验证您的网络准备运行实时的媒体的应用程序，如 Microsoft 团队。

> [!NOTE]
> 这是建议的客户希望成功部署 for Business 的 Skype 运行相同的网络准备情况评估。


## <a name="bandwidth-requirements"></a>带宽要求


本文介绍简洁版的 Microsoft 团队实时音频、 视频和桌面共享形式在各种使用情况下如何使用带宽。 工作组始终是保守对带宽使用率和下 1.2Mbps 中可以提供 HD 视频质量。  每个音频/视频呼叫或会议中的实际带宽使用将有所不同，根据多种因素，例如视频布局、 视频分辨率和视频帧速率。 更多的带宽有质量和使用情况将会增加为了提供最佳体验。


|Bandwidth(up/down) |方案 |
|---|---|
|30 kbps |对等音频呼叫 |
|130 kbps |对等音频呼叫和屏幕共享 |
|500 kbps |对等质量视频 30 fps 时调用 360 p |
|1.2 Mbps |调用不带 HD 720 p 30 fps 时的解决方案的对等 HD 质量视频 |
|1.5 Mbps |调用不带分辨率为高清 1080p 以 30 fps 的对等 HD 质量视频 |
|500 kbps/1Mbps |组视频呼叫 |
|为 2Mbps 1Mbps / |HD 组视频呼叫 （1080p 屏幕上的 540 p 视频） |

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

<a name="additional-network-considerations"></a>其他网络注意事项
---------------

#### <a name="external-name-resolution"></a>外部名称解析

确保运行团队客户端的所有客户端计算机可以解析发现 Office 365 提供的服务的外部 DNS 查询，并且，您的防火墙不会阻止访问。 有关配置防火墙端口的信息，请转到[Office 365 Url 和 IP 范围](office-365-urls-ip-address-ranges.md)。

#### <a name="nat-pool-size"></a>NAT 池大小

当多个用户/设备访问 Office 365 使用网络地址转换 (NAT) 或端口地址转换 (PAT) 时，您需要确保隐藏在每个公共可路由的 IP 地址的设备不能超过支持的数目。

若要减轻此风险，请确保足够公共 IP 地址将分配给 NAT 池以防止端口耗尽。 端口耗尽会导致内部最终用户和设备连接到 Office 365 服务时面临的问题。 有关详细信息，请参阅[Office 365 的 NAT 支持](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)。

#### <a name="intrusion-detection-and-prevention-guidance"></a>**入侵检测和防护指南**

如果您的环境的入侵检测和/或防护系统 (ID/IP) 部署额外的安全的出站连接，请确保目标为 Office 365 Url 与任何通信白名单。

<a name="network-health-determination"></a>网络运行状况确定
-----------------

在您的网络内的 Microsoft 团队实现规划时，您必须确保您具有所需的带宽、 您有权访问所有必需 IP 地址，打开了正确的端口和您会议实时的媒体的性能要求.

如果您知道您将不符合这些条件，您的最终用户将不获得最佳体验团队由于错误质量呼叫和会议过程中。

您应不满足这些条件，这是要考虑暂停项目来确保在继续之前满足条件的时间。


|  |  |  |
|---------|---------|---------|
|![决策点图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |决策点         |您已经评估支持实时媒体您网络功能？<br></br>如果您的网络未正确评估，或您知道它将不支持实时媒体，您将禁用视频和屏幕共享功能，以减少网络影响和差团队体验？         |
|![后续步骤图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |后续步骤         |网络质量未知： 按照[网络准备情况评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)指导来确定您的网络是否准备好让实时媒体。<br></br>网络质量差： 执行网络补救步骤，以提供高质量实时媒体的适当环境。<br></br>网络满意： 确保所有 IP 地址和端口都都正确可访问。           |

## <a name="related-topics"></a>相关主题

[视频： 网络规划](https://aka.ms/teams-networking)
