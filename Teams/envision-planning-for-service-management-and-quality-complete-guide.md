---
title: 适用于 Microsoft Teams 的服务管理规划指南
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/16/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rowille
description: 通过管理服务、网络和终结点运行状况以及定义可操作的质量支持者角色，实现高质量的 Teams 用户体验。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b2039409d2cfb63672f1c2bb4ae5cdf68323be2
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304842"
---
# <a name="plan-for-service-management-and-quality"></a>规划服务管理和质量

本文介绍 Microsoft Teams 的展望阶段。
 
## <a name="introduction"></a>简介

此内容概述了交付和维护高质量的 Microsoft Teams 部署需要达到的要求。 在首次试点或生产部署之前，可以通过在展望阶段规划服务管理和质量来帮助确保部署得以成功。

指导由以下部分组成：

-   首先，概述用户体验和用于实现高质量的主要组成部分。 将着重介绍在上线 Microsoft Teams 之前重点关注的方面。

-   其次，指导在首次用户试点或生产部署之前如何规划用于管理 Microsoft Teams 的支持模型。 本节介绍为了维护高质量 Teams 部署需要定期执行的任务。 此外，本节还介绍你开始了解和执行这些任务时可以遵循的进一步指导。

-   再次，提供具体的指导来帮助在你的组织中规划你的网络和终结点以支持 Microsoft Teams。

-   最后，概述了后续步骤并提供相关内容参考。

## <a name="key-components-that-affect-user-experience"></a>影响用户体验的主要组成部分

本节将介绍影响用户体验的主要组成部分。 在介绍这些主要组成部分之前，务必要了解用户体验及其在实现组织业务目标中的重要性。 下面先来了解我们如何定义用户体验。

### <a name="user-experience-defined"></a>定义用户体验

在部署 Microsoft Teams 并将通信方式纳入业务流程以增强其工作流时，即可实现业务目标。 质量驱动采用和使用：如果组织提供了让大家满意的高质量服务，则个人和团队就可以获得信心，并寻求具有创新性的新型服务使用方式，用于推动业务优势。

核心在于用户使用 Teams 时的体验 - 个人对服务的感受和态度。 那么哪些方面构成了用户体验？ 其中包括从用户知道如何使用 Teams 并将其纳入自己的日常工作流，到体验出色的通话质量以及能够可靠地进行联系，无论其身在何处都是如此。 从本质上来说，用户体验非常广泛；但本文档只重点介绍组织可以控制的那些因素。

部署存在一些具体要求，这些要求对实现出色的用户体验至关重要 - 尤其是在 Teams 中使用云语音功能时。 与其他通信和协作投资相比，优先考虑 Microsoft Teams 这一点很重要，从而相应地优先处理实时流量。 下一节概述了影响用户体验的主要组成部分。 在后面各节，我们将指导如何开始规划部署和维护构成质量的主要组成部分。

### <a name="key-components-of-quality"></a>质量的主要组成部分

组织或支持合作伙伴应该在 Teams 部署的展望阶段开始规划三个主要组成部分：服务管理、网络和终结点。 这三个方面一起构成了用户体验质量的基础。

![此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。](media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。")

#### <a name="service-management"></a>服务管理

服务管理可以分为两种截然不同的职责类别：

-   **Microsoft 职责**。 Microsoft 负责构成 Office 365 服务的基础结构组件。 Microsoft 向客户负责确保为连接到 Teams 的任何用户提供可靠的高质量体验。

-   **客户职责**。 你和你的组织负责管理 Office 365 服务、本地部署网络和用户终结点的各个方面。 例如，在向 Office 365 添加新的 IP 地址时，你必须更新合适的防火墙以允许新的终结点进行通信，从而避免用户中断。

有关服务管理规划的详细指导，请参阅[规划服务管理](#plan-for-service-management)。

#### <a name="network"></a>网络 

在大多数组织中，网络最初设计为用于访问其数据中心里的数据和应用。 对于 Office 365 等基于云的应用，则需要更改这些网络以支持 Teams 所需的全新访问和数据流。 必须先评估并优化当前网络，才能在组织中为 Teams 启用用户。 在利用云语音功能时，这一点至关重要。

在传统网络中，用户需要穿越组织的外围网络才能访问 Teams。 许多组织将会有基于安全的设备（例如，代理服务器、防火墙和 VPN），这些设备可以阻止或阻碍网络流量，或者为网络流量提供未优化路径。

此外，需要优化核心内部网络以及将其调整至合适规模，以提供足够的容量和质量，从而支持 Teams 工作负荷（包括实时媒体）。 你可以使用带宽规划、修正和优化来帮助确保你的网络提供 Office 365 的高质量有效路径。

有关网络规划的详细指导，请参阅[规划服务质量](#plan-for-network-quality)。

#### <a name="endpoints"></a>终结点

Microsoft Teams 支持各种终结点。 你可以在任何地方从 PC、平板电脑和手机等几乎任何设备访问 Teams。

为了给你的用户提供可能的最佳体验，你需要在展望阶段考虑以下重要方面：你的终结点是否满足 Teams 硬件和软件要求？ 你是否已配置并优化终结点来支持 Wi-Fi 网络？ 你将使用哪些设备拨打和接听语音通话？ 是否针对 Teams 优化了这些设备？

有关终结点规划的详细指导，请参阅[规划终结点质量](#plan-for-endpoint-quality)。

## <a name="plan-for-service-management"></a>规划服务管理

服务管理是一个非常广泛的主题，涵盖了部署 Microsoft Teams 服务并为用户启用该服务后该服务的日常操作。 Teams 服务包括 Microsoft Office 365 和在本地部署的基础结构组件（例如网络）。

对于大多数组织而言，服务管理概念很可能不是一个新概念。 你可能已经实施了与现有服务关联的流程和任务。 尽管如此，当你现在规划服务管理以在将来支持 Microsoft Teams 时，你可能会扩大已实施的方面。

服务管理包含管理 Microsoft Teams 端到端时涉及的所有活动和流程。 如前文所述，服务管理的一些组件（构成 Office 365 服务自身的基础结构组件）属于 Microsoft 的职责范围，而客户负责为其用户管理自己提供的 Teams、网络和终结点的各个方面。 本文档的本节将从服务管理角度重点介绍客户的职责。

![此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。焦点在服务管理上。](media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。焦点在服务管理上。")

### <a name="introduction-to-the-operations-guide"></a>《操作指南》简介 

**什么内容**、**什么人**和**什么方式**是在讨论服务质量时需要回答的三个重要问题。

你可以使用《[操作指南](1-drive-value-operate-my-service.md)》帮助你解决所有这三个问题。 该指南提供了每天、每周、每月及按需执行的活动列表。 这些活动和任务对于维护高质量 Teams 部署至关重要。 确定谁将负责在服务管理中执行特定活动是在展望阶段早期需要执行以确保部署得以成功的规划的关键方面。 在确定了任务和活动后，需要你将其分配到的小组或个人了解并遵循这些任务和活动。 《操作指南》提供了有关如何执行每个任务的知识和指导，以及/或外部内容的参考。

### <a name="operational-role-mapping"></a>可操作的角色映射

早期规划服务管理是一个关键的里程碑，因为在启用首批试点用户时即开始操作阶段。 项目团队必须审阅并同意所需的任务和活动，确定负责每个运营任务的团队，以及得到各个团队的承诺和签字认可。

在完成签字认可后，负责团队必须开始执行这些角色和职责。 这可能包括培训和就绪工作、更新人员配置模型或确保外部合作伙伴已准备好交付。

在展望阶段早期映射可操作的角色可让所有团队在试点期间开始执行其可操作的任务，扩大操作，以及确保在部署开始后一切都已准备好。

《操作指南》提供了映射到在大多数方案中应该会有效的典型角色的常见任务列表。 你需要自定义这些职责以适用于你的组织。

### <a name="the-quality-champion-role"></a>质量支持者角色

在所有组织中，都需要小组或个人为质量负责。 这是服务管理中最重要的角色。 质量支持者是分配给关心其用户体验的个人或小组的客户角色。 此角色要求具有识别环境中的趋势的技能，以及能够支持与其他团队合作以推动修正。 质量支持者的最佳候选人通常是客户服务所有者，根据组织的规模和复杂程度，可以是关心用户体验的任何个人或小组。

质量支持者利用现有的工具和记录的流程（例如通话质量仪表板 (CQD) 和《体验质量评审指南》）来监控用户体验、识别质量趋势以及在需要的情况下推动修正。 质量支持者与各个团队合作以推动采取修正措施，并就进度和未解决的问题向指导委员会报告。

《操作指南》中记录了与该角色关联的任务和活动。 应在展望阶段早期分配此角色。 执行质量支持者角色时的一个主要步骤是获取该角色所需的知识，以及确保在执行任务时满足先决条件。 此角色的一个主要任务是运行定期质量体验评审。

### <a name="introduction-to-the-quality-experience-review-guide"></a>《体验质量评审指南》简介

《体验质量评审指南》中包含一组活动，用于评估影响最大的主要方面并提供修正指导以改进用户体验，如下图所示。

![此示意图说明了在质量体验评审期间检查的主要方面。](media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "此示意图说明了在质量体验评审期间检查的主要方面。")

通过持续评估并修正本文档中所述的方面，你可以降低其对用户体验的潜在负面影响。 在部署中遇到的大多数用户体验问题可以分为以下类别：

-   防火墙或代理配置不完整

-   Wi-Fi 覆盖范围较小

-   带宽不足

-   VPN

-   使用了未优化或内置的音频设备

-   子网或网络设备存在问题

《体验质量评审指南》主要指导如何将通话质量仪表板 (CQD) 作为主要工具进行在线使用来报告和调查所述的每个方面，且重点在音频方面，以最大限度地提高采用率和作用。 为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。

强烈建议尽早指定质量支持者。 在被指定为质量支持者后，这些人应开始了解《体验质量评审指南》中的内容。

《体验质量评审指南》位于[此处](https://aka.ms/qerguide)。

## <a name="plan-for-network-quality"></a>规划网络质量 

下面主要介绍如何规划网络质量。

![此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。焦点在网络上。](media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。焦点在网络上。")

如前文所述，在上线 Microsoft Teams 之前进行网络质量规划至关重要。 有关网络就绪的进一步指导，请参阅[为 Microsoft Teams 准备组织的网络](prepare-network.md)。

在大多数组织中，网络可能包含托管网络和非托管网络。

托管网络是组织可以直接控制的网络基础结构组成部分。 因此，托管网络直接影响可以向实时流量工作负荷提供的质量。

相反，非托管网络是客户只能进行有限控制或无法控制的网络部分。

组织与 Office 365 之间的 Internet 连接是客户只能进行有限控制的网络。 这些网络由 ISP 管理，但组织应该能够通过升级其带宽、支持路由优化或（如果所有其他方法都无效）改换 ISP 来提高网络质量。

家庭网络或者酒店或咖啡店的网络属于客户无法控制的网络。

在以下各节中，将重点介绍托管网络的质量要求。

### <a name="key-network-planning-areas"></a>主要网络规划方面

以下各节将重点介绍用于实现高质量网络的重要方面。

> [!NOTE]
> 许多网络会由于升级、扩展或其他业务要求而逐渐发展。 请确保在你的服务管理规划中具有可操作的流程以维护这些方面。

#### <a name="bandwidth"></a>带宽

带宽规划是网络就绪活动的一个关键方面。 务必要确保有足够的带宽用于 Microsoft Teams 工作负荷。 为了能够调整现有网络的规模，必须了解当前预配的内容、当前利用率，最后是剩余的可用带宽。

要度量当前利用率，需要监控网络。 之后，可以将此度量结果用作带宽规划的基础。 此外，还应该在部署期间和之后持续监控网络，以确保充分预配了网络。

> [!NOTE]
> 监控网络利用率时，务必要避免使用每天的平均值。 这些平均值可能包含影响结果准确性的非核心时段数据。 平均值可能无法体现高峰时段的数据，并掩盖了基本问题。

[Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) 帮助你通过几个简单的步骤即可确定和整理你的部署的网络要求。 通过使用该工具收集组织的网络详细信息和云语音使用情况，可以获取你的云语音部署所需的网络要求的近似计算结果，管理并导出这些详细信息进行报告，以及查看相关方面以便进行进一步调查和后续步骤。

#### <a name="quality-of-service-qos"></a>服务质量 (QoS)

应对托管网络的所有部分实施 QoS，即使是在带宽方面充分预配的网络也是如此。 在后一种情况下，当出现意外网络负荷时，QoS 可以缓解风险。 实施 QoS 时，将优先处理语音流量，以避免这些意外事件影响质量。

QoS 实施应包括网络的多个方面，从终结点一直到出口点，以及从出口点回到终结点。 这将确保在两个方向上都优先处理语音流量。 应对有线网络和 Wi-Fi 网络实施 QoS。

要对网络实施 QoS，以下指导有助于提高 [Microsoft Teams 中的服务质量](qos-in-teams.md)

#### <a name="proxy-servers"></a>代理服务器

许多组织都将传输到 Internet 的流量视为安全风险，并通过监控和评估网络中出口点处的流量来缓解此风险。 可以部署代理服务器这类设备来满足此要求。

在对负载执行数据包检查或修改时，代理服务器可能会引入问题。 这可能会导致通话设置失败、通话中断以及通话质量较差。 如果强制实时媒体穿过代理服务器，则 Teams 中的媒体堆栈将会被强制故障回复到 TCP，从而可能进一步导致质量降低。 UDP 始终优先于 TCP。

此外，代理服务器可能未设计为处理额外的 Office 365 负荷，尤其是 Microsoft Teams 工作负荷（包括实时媒体）。

由于代理服务器可能会引入潜在的问题，以及这些额外的容量顾虑，Microsoft 建议绕过代理服务器并直接连接到 Office 365。

绕过代理服务器所需的配置因供应商而异，但常见方法通常是更新代理自动配置 (PAC) 文件。 PAC 文件是一个配置文件，记录哪些流量通过代理以及哪些流量绕过代理。

一些代理服务器供应商会提供一个自动流程以确保配置是最新的。 如果你的供应商未提供此自动流程，你可以从 <https://aka.ms/o365proxies> 下载更新的 PAC 文件。

[Teams 或 Skype for Business Online 的代理服务器](proxy-servers-for-skype-for-business-online.md)

#### <a name="firewalls"></a>防火墙

需要确保向所有 Office 365 IP 和 URL 打开正确的端口和协议，才能访问 Microsoft Teams。 此外，这对实现高质量部署也很关键。 只是拨打电话或加入电话会议不足以确保正确配置了防火墙。

如果在防火墙上只打开 TCP，则将会建立会话，但不会协商首选传输 (UDP)。 需要在防火墙上同时打开 TCP 和 UDP，才能提供最佳用户体验。

由于其有状态性质，TCP 不适用于实时媒体，仅作为 Microsoft Teams 的故障回复网络传输提供。 在使用 TCP 的情况下，如果发生数据包延迟或丢失，则必须重新传输这些数据包，直到其得到确认。 这可能会导致不再相关的媒体数据包与当前媒体数据包竞争及时传递。 用户的 Teams 客户端尝试拉伸音频，根据网络状况，可能会生成非自然音频信号。 由于 TCP 的额外开销，普遍接受的体验可能会变为较差的用户体验。 因此，需要使用无状态网络传输 UDP。

[Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)一文提供了为 Microsoft Teams 打开防火墙的完整指导。

打开防火墙后，可以使用  [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885)  验证云语音功能的连接性。

> [!IMPORTANT]
> Microsoft Office 365 IP 和 URL 将随时间变化。 在服务管理规划中，务必要确保具有可操作的流程，以及一个小组负责监控 [Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)以及相应地进行更新。

#### <a name="local-internet-egress"></a>本地 Internet 出口

许多网络设计为使用中心和辐射型拓扑。 在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。 通常，这么做事为了集中网络安全设备，目的是降低总成本。

经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。 由于 Microsoft Teams 在 Microsoft 的大型全局网络上运行，因此，用户附近通常会有网络对等位置。 用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。 对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。 在这种情况下，务必要在使用本地出口点时，将其与本地 DNS 解析配对。

优化指向 Microsoft 的全局网络的网络路径将会提高性能，并最终将为用户提供最佳体验。 有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。

#### <a name="vpn"></a>VPN

VPN 为许多组织提供很有用的服务。 遗憾的是，它们通常未设计或配置为支持实时媒体。 一些 VPN 可能还不支持 UDP。 VPN 还会在已加密的媒体流量之上引入额外一层加密。 此外，由于通过 VPN 设备的发夹流量，与 Microsoft Teams 服务的连接可能无效。 而且，从容量角度来看，它们不一定设计为容纳 Teams 所需的预计负荷。

建议提供一个备用路径，以便 Teams 流量绕过 VPN。 这就是通常所谓的拆分通道 VPN。 拆分通道意味着流向 Office 365 的流量不穿过 VPN，而是直接传输到 Office 365。 此改变不仅有利于提高质量，而且还带来额外的好处，即降低 VPN 设备和组织网络的负荷。

要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。

#### <a name="wi-fi"></a>Wi-Fi

与 VPN 一样，Wi-Fi 网络不一定设计或配置为支持实时媒体。 规划和/或优化 Wi-Fi 网络以支持 Teams 是实现高质量部署的一个重要考虑事项。

可从几个因素来优化 Wi-Fi 网络。

-   实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。

-   规划和优化 Wi-Fi 频带和接入点位置。 2.4 GHz 范围可以根据接入点位置提供合乎需要的体验，但接入点通常受该范围内运行的使用者其他设备的影响。 5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。

-   如果部署了双频 Wi-Fi 网络，请考虑实施频带切换。 频带切换技术由 Wi-Fi 供应商实施，以促使双频客户端使用 5 GHz 范围。

-   频道重叠 - 同一频道的多个接入点太靠近时，它们可能会导致信号重叠并无意地竞争，从而导致用户体验很差。 请确保频道上相邻的接入点不会重叠。

每个无线供应商都有自己的无线解决方案部署建议。 建议你咨询你的供应商了解具体指导。

### <a name="network-readiness-assessment"></a>网络就绪评估

网络就绪活动中包括网络评估。 完成规划和配置后，在为用户上线 Microsoft Teams 之前，可以通过评估对你网络的质量有基本的了解。 此外，评估结果也可以帮助你在支持用户使用 Teams 之前确定并优先处理修正工作。

应该对所有建筑物中要用于支持 Teams 中云语音功能的有线和 Wi-Fi 网络进行网络评估。

可以通过 Microsoft 合作伙伴、第三方工具或 [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) 进行网络评估。 我们还在[此处](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11)的就绪指导中提供了有关如何使用 Microsoft Network Assessment Tool 运行评估的进一步指导。

## <a name="plan-for-endpoint-quality"></a>规划终结点质量

如下图所示，终结点是为用户提供高质量体验的一个重要构建基块。

![此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。焦点在终结点上。](media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。焦点在终结点上。")

Microsoft Teams 终结点可以在多种设备（包括 PC、Mac、平板电脑和移动设备）上运行。 不仅设备本身影响体验，而且用户连接设备的方式（例如，使用设备的内置麦克风/扬声器、耳塞式耳机或优化耳机）也影响体验。 使用优化耳机可以丰富整体用户体验。

以下有关终结点规划的指导将帮助你确保你的组织成功上线 Teams。

### <a name="endpoint-capability"></a>终结点功能

规划的第一部分是确保组织中的所有 PC 和其他设备都可以运行 Microsoft Teams。 这不仅要查看硬件要求，而且还要了解 PC 在后台执行的其他操作。 许多组织会运行其他软件，包括入侵检测系统和反恶意软件，这些软件会影响设备的基础性能。

Microsoft Teams 的客户端适用于 Web、桌面（Windows 和 Mac）和移动（Android、iOS 和 Windows Mobile）。 有关每个平台的软件要求信息，请参阅[获取 Microsoft Teams 客户端](get-clients.md)。

### <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙会对用户体验产生很大影响。 客户端防火墙会影响通话质量，以及阻止建立通话。 应根据 [Office 365 URL 和 IP 地址范围](https://aka.ms/o365ips)中的信息在客户端防火墙上配置适当的排除项。 你的第三方供应商会提供有关如何创建排除项的具体指导。

> [!NOTE]
> Microsoft Teams 会自动为 Windows 防火墙更新适当的防火墙配置。

### <a name="wi-fi-recommendations-for-endpoints"></a>针对终结点的 Wi-Fi 建议

规划和部署优化的 Wi-Fi 网络以支持 Microsoft Teams 中的实时工作负荷需要进行重要的规划。 以下各节提供了一些常规指导，可以帮助你在规划端点时避免一些常见困难。

#### <a name="wi-fi-drivers"></a>Wi-Fi 驱动程序

一些 Wi-Fi 驱动程序可能存在问题。 例如，某个驱动程序可能存在在接入点之间进行非常积极的漫游行为，从而导致通话质量较差。 这并不常见，但务必要确保在部署之前更新并测试 PC 上的 Wi-Fi 驱动程序。

#### <a name="wi-fi-bands"></a>Wi-Fi 频带

当前，Wi-Fi 设备中主要使用两种类型的频带：2.4 GHz 和 5.0 GHz。 如果你的组织提供这两种频带，你应将驱动程序设置配置为首选 5.0 GHz 频带。 在吞吐量方面，此频带的密度远高于 2.4 GHz 频带，且受干扰影响低于 2.4 GHz 频带。 此建议的前提是你已正确优化 5.0 GHz 网络频带。

#### <a name="wi-fi-radio-type"></a>Wi-Fi 无线电类型

规划支持较新 Wi-Fi 无线电类型的设备 如果你在你预配的设备上利用 802.11ac 或更高版本，则会获得非常好的 Wi-Fi 性能。

#### <a name="wireless-avoidance"></a>避免使用无线

一些组织倾向于完全避免使用 Wi-Fi。 有时，此指导以建议用户直接连接有线网络来体现。 在某些情况下，网络绑定顺序中无线连接可能处于优先使用位置，即使 PC 已连接到有线连接，仍会继续使用该连接。 为了避免出现此意外行为，应配置绑定顺序以避免出现此情况。

#### <a name="80211-power-save-protocol"></a>802.11 节能协议

如果你的组织使用不支持 802.11 节能协议的无线接入点或路由器，则你在使用 Windows 设备上运行的 Microsoft Teams 时可能会遇到通话中断或通话质量较差的情况。 如果无法升级你的无线接入点或路由器，则应在使用电池的设备上更新 Windows 电源计划设置。 以下[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了进一步的详细信息和配置指导。

### <a name="devices-for-teams"></a>支持 Teams 的设备

Microsoft Teams 可以用于会议或用作电话系统。 在使用这些功能时，用于 Teams 的接口设备在用户体验中起到重要作用。

使用内置 PC 扬声器和麦克风对具有该配置的用户而言可能会正常接受。 但通常情况下，这些设备没有针对噪声消除进行优化，因此任何类型的环境噪声都可能会对通话中的其他人造成下游影响。 利用针对这些情况优化的设备有助于确保获得高质量体验。

每个设备都需要满足用户的需求。 你需要为你组织中的不同角色和用例定制设备（例如耳机）。 应在规划流程中完成角色-设备映射操作。

选择了设备后，将其包含在试点测试计划中以便进行最终验证。 应在试点期间利用调查来收集反馈，以确保你的设备策略是最佳的。

目前，建议使用通过 Skype for Business 认证计划认证的音频设备。 要查找此计划认证的设备，请参阅[经过认证适用于 Skype for Business 的 USB 设备](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)解决方案目录。

有关更多详细信息，请参阅 [Client and Devices - Readiness Workshop](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)（客户端和设备 - 就绪研讨会）

## <a name="client-updates"></a>客户端更新

Microsoft Teams 的主要优势之一是客户端会自动保持最新。 PC 和 Mac 上的客户端是通过使用一个后台进程进行更新，该进程在该应用处于空闲状态时检查是否有新的内部版本并下载新客户端。 客户端下载大小大概为 100 MB。

组织无法控制或访问策略设置来管理更新过程。 为了缓解可能在更高内部版本中发现的问题的风险，会在终结点上保留上一个已知完好的版本。 如果新的内部版本存在问题，Microsoft Teams 服务可以自动将终结点恢复到上一个版本。

## <a name="next-steps-and-references"></a>后续步骤和参考

下表概述了规划活动，并提供相关内容链接。

| 区域 | 详细信息 | References |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 规划服务管理 | 进行可操作的角色映射操作 <br/> 负责团队的签字认可 <br/> 角色就绪 | [《操作指南》](1-drive-value-operate-my-service.md) |
| | 指定质量支持者 <br/> 质量支持者就绪| [了解 CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [《体验质量评审指南》](https://aka.ms/qerguide) |
| | 安装质量体验评审模板 <br/> 上载构建文件 | [QERLite 模板](https://aka.ms/qertemplates) <br/> [上载构建信息](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)|
| 规划网络质量 | 运行 Network Planner | [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | 实施 QoS | [Microsoft Teams 中的服务质量](qos-in-teams.md) |
| | 绕过代理服务器 | [代理指导](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) |
| | 实施拆分通道 VPN | [VPN 拆分通道指导](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | 为实时媒体优化 Wi-Fi 网络  | 咨询第三方供应商 |
| | 实施本地 Internet 出口 | [本地 Internet 出口](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | 实施网络连接 <br/> 验证网络连接 | [Office 365 URL 和 IP 地址](https://aka.ms/o365ips) |
| | | [Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) |
| | 执行网络评估 | [网络就绪评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| 规划终结点质量 | 更新终结点防火墙 | [Office 365 URL 和 IP 地址](https://aka.ms/o365ips) |
| | 验证软件要求 | [获取 Microsoft Teams 客户端](get-clients.md) |
| | 实施终结点 Wi-Fi 建议 | 咨询第三方供应商 |
| | 进行角色-设备映射 <br/> 预配设备并对其进行试点 | [Client and Devices - Readiness Workshop（客户端和设备 - 就绪研讨会）](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [设备目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |