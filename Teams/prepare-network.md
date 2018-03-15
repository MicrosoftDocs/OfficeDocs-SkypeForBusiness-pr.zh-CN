---
title: "为 Microsoft Teams 准备贵组织的网络"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 02/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: "了解如何准备和管理你的 Microsoft Teams 网络。 信息包括网络要求、带宽要求和其他考虑事项。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e734014ff72c8b7eb6ba0e9f27cce7489ec3daf9
ms.sourcegitcommit: 50446359cd7c359eb2536176545291c723392e47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>为 Microsoft Teams 准备贵组织的网络
=================================================

Teams 组合了三种形式的流量：

-   Office 365 联机环境与 Teams 客户端之间的数据流量（信号发送、联机状态、聊天、文件上载和下载、OneNote 同步）。

-   点对点实时通信流量（音频、视频、桌面共享）。

-   会议实时通信流量（音频、视频、桌面共享）。

这在两个级别上影响网络：对于点对点应用场景，流量在 Microsoft Teams 客户端之间直接传输；对于会议应用场景，流量在 Office 365 环境与 Microsoft Teams 客户端之间传输。 为了确保获得最佳通信流，必须允许在内部网络段（例如，WAN 上的站点）之间以及网络站点与 Office 365 之间传输流量。 如果未打开正确的端口或主动阻止特定端口，将会导致降低体验。

> [!IMPORTANT]
> 当前，在 iOS 和 Android 移动设备上支持会议，但在 Windows Phone 上不支持。

为了在 Microsoft Teams 中获得实时媒体方面的最佳体验，需要满足 Office 365 的网络连接要求。 有关详细信息，请参阅 [Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US)。

两个定义网络段（客户端到 Microsoft Edge 和客户边缘到 Microsoft Edge）必须满足以下要求：


|值  |客户端到 Microsoft Edge  |客户边缘到 Microsoft Edge  |
|---------|---------|---------|
|**延迟（单向）**     |< 50 ms          |< 30 ms          |
|**延迟（RTT 或往返时间）** |< 100 ms         |< 60 ms         |
|**突发数据包丢失**    |< 10%，在任何 200 ms 时间间隔内         |< 1%，在任何 200 ms 时间间隔内         |
|**数据包丢失**     |< 1%，在任何 15 s 时间间隔内          |< 0.1%，在任何 15 s 时间间隔内         |
|**数据包中间间隔抖动**    |< 30 ms，在任何 15 s 时间间隔内         |< 15 ms，在任何 15 s 时间间隔内         |
|**数据包重新排序**    |< 0.05% 无序数据包         |< 0.01% 无序数据包         |

要测试两个网段，你可以使用[网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799)。 此工具可以直接部署在客户端 PC 上，也可以部署在连接到客户网络边缘的 PC 上。 此工具附带内容有限的文档，有关此工具用法的深度文档，请参阅此处：[网络就绪评估](https://go.microsoft.com/fwlink/?linkid=855800)。 通过进行此网络就绪评估，你可以验证你的网络是否为运行实时媒体应用（例如 Microsoft Teams）做好准备。

> [!NOTE]
> 对于希望成功部署 Skype for Business 的客户，同样建议进行此网络就绪评估。

<a name="bandwidth-requirements"></a>带宽要求
----------

Microsoft Teams 的带宽计算很复杂，因此为了帮助进行此计算，创建了一个计算器。 要访问计算器，请转到 [MyAdvisor 中的网络规划器](http://aka.ms/bwcalc/)。

下文内容可以用作补充背景信息，但建议客户使用[网络规划器](https://aka.ms/bwcalc)来跟踪其需求。

> [!IMPORTANT]
>如果未提供所需的带宽，Teams 中的媒体堆栈将降低音频/视频会话的质量以适应较低的可用带宽，因而会影响通话/会议的质量。 Teams 客户端在处理音频质量和视频质量时将尝试优先考虑音频质量。 因此，提供所需带宽非常重要。


|活动  |下载带宽  |上载带宽  |通信流 |
|---------|---------|---------|---------|
|**点对点音频通话**     |0.1 Mb         |0.1 Mb         |客户端 <> 客户端         |
|**点对点视频通话（全屏幕）**     |4 Mb         |4 Mb         |客户端 <> 客户端          |
|**点对点桌面共享（1920*1080 分辨率）**     |4 Mb         |4 Mb         |客户端 <> 客户端          |
|**2 个参与者的会议**     |4 Mb         |4 Mb         |客户端 <> Office 365         |
|**3 个参与者的会议**     |8 Mb         |6.5 Mb         |客户端 <> Office 365           |
|**4 个参与者的会议**     |5.5 Mb         |4 Mb         |客户端 <> Office 365           |
|**5 个以上参与者的会议**     |6 Mb         |1.5 Mb         |客户端 <> Office 365           |


<a name="additional-network-considerations"></a>其他网络考虑事项
---------------

#### <a name="external-name-resolution"></a>**外部名称解析**

确保运行 Teams 客户端的所有客户端计算机都可以解析外部 DNS 查询以发现 Office 365 提供的服务。

#### <a name="nat-pool-size"></a>**NAT 池大小**

多个用户/设备使用网络地址转换 (NAT) 或端口地址转换 (PAT) 访问 Office 365 时，你需要确保每个公开可路由 IP 地址后面隐藏的设备不超过支持的数量。

为了缓解此风险，请确保为 NAT 池分配足够的公用 IP 地址以防止端口耗尽。 端口耗尽会导致内部最终用户和设备在连接到 Office 365 服务时遇到问题。 有关详细信息，请参阅 [Office 365 的 NAT 支持](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)。

#### <a name="intrusion-detection-and-prevention-guidance"></a>**入侵检测和防护指导**

如果你的环境部署了入侵检测和/或防护系统 (IDS/IPS)，从而为出站连接附加了一层安全性，请确保目标为 Office 365 URL 的任何流量都列入白名单。

<a name="network-health-determination"></a>网络运行状况确定
-----------------

规划在你的网络中实施 Microsoft Teams 时，你必须确保有所需的带宽、有权访问所有所需的 IP 地址、打开了正确的端口且满足实时媒体的性能要求。

你应清楚，如果你无法满足这些条件，那么你的最终用户在使用 Teams 时由于在通话和会议过程中质量较差而无法获得最优体验。

如果你未满足这些条件，现在应考虑暂停项目，以确保先满足条件，然后再继续。


|  |  |  |
|---------|---------|---------|
|![决策点图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |决策点         |你是否评估了用于支持实时媒体的网络功能？<br></br>如果未正确评估你的网络，或者你知道它将无法支持实时媒体，你是否将禁用视频和屏幕共享功能以降低网络影响和糟糕的 Teams 体验？         |
|![后续步骤图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |后续步骤         |网络质量未知：按照[网络就绪评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)指导来确定你的网络是否可以支持实时媒体。<br></br>网络质量较差：执行网络补救步骤以提供合适的环境来支持高质量的实时媒体。<br></br>网络满意：确保可以正确访问所有 IP 地址和端口。           |

