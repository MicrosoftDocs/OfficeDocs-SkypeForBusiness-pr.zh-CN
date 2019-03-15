---
title: 为 Microsoft Teams 准备贵组织的网络
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
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
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640727"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>为 Microsoft Teams 准备贵组织的网络

> [!Tip]
> 观看下面的会话，若要了解如何团队利用您的网络和如何最好地规划最佳的网络连接：[团队网络规划](https://aka.ms/teams-networking)


团队结合使用三种形式的流量：

-   Office 365 联机环境和团队客户端 （信号、 状态、 聊天、 文件上载和下载、 OneNote 同步） 之间的数据通信。

-   对等实时通信 （音频、 视频、 桌面共享） 流量。

-   会议实时通信流量 （音频、 视频、 桌面共享）。

这会影响网络在两个级别： 通信将直接的对等方案中，在 Microsoft 团队客户端之间流动和通信将会议方案的流动的 Microsoft 团队客户端和 Office 365 环境之间。 若要确保最佳通信流，必须允许通讯以及为之间流动二者之间的内部网络段 （例如，通过 WAN 网站） 之间的网络站点和 Office 365。 不打开了正确的端口或主动阻止特定端口将导致降级体验。

> [!NOTE]
> IOS 和 Android 移动设备上支持会议。 

若要获取的 Microsoft 团队中的实时媒体与获得最佳体验，您的网络必须满足 Office 365 的网络要求。 有关详细信息，请参阅[媒体质量和业务 online Skype 的网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

两个定义网络段 （客户端到 Microsoft 边缘） 和客户边缘到 Microsoft 边缘，请考虑以下建议。


|值  |客户端到 Microsoft 边缘  |客户边缘到 Microsoft 边缘  |
|:--- |:--- |:--- |
|**延迟 （一种方法）**\*  |< 50 毫秒          |< 30ms         |
|**延迟 （RTT 或往返时间）**\* |< 为 100 毫秒   |< 为 60 毫秒 |
|**突发数据包丢失**    |任何为 200 毫秒间隔期间 <10%         |任何为 200 毫秒间隔期间 <1%         |
|**数据包丢失**     |<1%期间任何 15 秒间隔          |<0.1%期间任何 15 秒间隔         |
|**数据包间到达抖动**    |<30ms 期间任何 15 秒间隔         |<15ms 期间任何 15 秒间隔         |
|**数据包重新排序**    |<0.05%序的数据包         |<0.01%序的数据包         |

\*延迟指标目标假定您的公司网站和 Microsoft 边缘位于同一洲。

公司网站连接到 Microsoft 网络边缘包含第一个跃点网络访问，可以是 WiFi 或其他无线技术。

网络性能目标假定适当的带宽和/或[QoS 规划](QoS-in-Teams.md)。 换句话说的要求适用于团队实时的媒体流量直接峰值负载下的网络连接时。

若要测试两个网络段，您可以使用[网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799)。 此工具可以部署这两个客户端上 PC 直接并连接到客户网络边缘 PC 上。 该工具包含有限的文档，但围绕使用率的工具更深入地介绍文档可在此处找到：[网络准备情况评估](https://go.microsoft.com/fwlink/?linkid=855800)。 通过运行此网络准备情况评估，您可以验证您的网络准备运行实时的媒体的应用程序，如 Microsoft 团队。

> [!NOTE]
> 这是建议的客户希望成功部署 for Business 的 Skype 运行相同的网络准备情况评估。


## <a name="bandwidth-requirements"></a>带宽要求

Microsoft 团队的带宽计算很复杂，为了与此，具有创建一个计算器。 若要访问计算器，转到[网络规划人员](https://aka.ms/bwcalc/)MyAdvisor 中。

> [!NOTE]
> 团队带宽处理改进了业务 online Skype： 对于呼叫或会议 （与音频、 视频和共享） 的体验，高质量，团队需要仅 1.2 Mbps。 它还可以扩展最多进一步的超级高质量，如果没有足够的可用带宽。 当团队请求遇到低带宽条件时，团队可以快速重新调整带宽使用情况，以适应可用带宽。

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