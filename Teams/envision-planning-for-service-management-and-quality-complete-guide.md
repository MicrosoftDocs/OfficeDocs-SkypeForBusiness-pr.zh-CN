---
title: 规划对于 Microsoft 小组服务管理指南
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 提供高质量的用户体验团队管理服务、 网络和端点的健康并定义操作和质量拥护者的角色。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cccd06cd9bd5ee458497fbb41db56955bb9a5ee9
ms.sourcegitcommit: d70e5a5e7d05a2226c1d011895fb12187d73fad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2018
---
# <a name="plan-for-service-management-and-quality"></a>服务管理和质量计划

本文是关于 Microsoft 小组的构想阶段。
 
## <a name="introduction"></a>简介

此内容将提供概述所提供和维护高质量的 Microsoft 小组部署所需的要求。 您可以帮助通过在构想阶段，第一试验或生产部署之前规划服务管理功能和质量，确保成功的部署。

本指南分为以下各节：

-   首先是用户体验和支持质量的关键组件的概述。 这将突出显示的区域重点在 Microsoft 小组到服务之前。

-   第二，指南给出规划支持模型在第一个用户试验或生产部署之前管理 Microsoft 小组。 本部分介绍需要定期维护质量团队部署执行的任务。 此外，本部分向您介绍进一步的指导，您可以使用它来开始了解，留给这些任务。

-   第三，具体指导帮助规划您的网络和组织中的终结点以支持 Microsoft 小组。

-   最后，对相关内容的引用与总结了下一步行动。

## <a name="key-components-that-affect-user-experience"></a>影响用户体验的关键组件

在本节中，将审查影响用户体验的关键组件。 之前查看的关键组件，这一点至关重要，了解用户体验，并实现组织的业务目标的重要性。 让我们回顾一下如何我们首先定义了用户体验。

### <a name="user-experience-defined"></a>定义的用户体验

当您部署 Microsoft 小组并将通信纳入到您的业务流程，以提高其工作流，可以实现业务目标。 质量促进采用和使用： 如果您的组织提供了一种高质量服务，带来快乐的人，那么个人和团队可以信心并查找新的和创新的方式使用服务推动业务方面的好处。

此核心都是用户体验团队 — — 人的情感和服务的态度。 所以什么作用于用户体验？ 其范围从用户了解如何使用团队，并将其纳入遇到异常呼叫质量和能够连接可靠，不管他们在哪里他们日常工作流程。 用户体验是非常广泛的性质;本文档只侧重于可由您的组织中控制这些元素。

还有太重要，提供最佳的用户体验到部署的具体要求 — — 特别是当使用云的语音功能在团队中。 它是 Microsoft 小组视为一类公民，与其他的通信和协作的投资，相应地确定优先级的实时通信的关键。 下面一节概述了影响用户体验的关键组件。 在进一步章节中，我们将提供您指导如何开始规划来部署并维护组成质量的关键组件。

### <a name="key-components-of-quality"></a>关键组件的质量

组织或支持合作伙伴应开始在构想阶段的团队部署规划三个主要组件： 管理、 网络和终结点提供服务。 所有三个方面的结合是用户体验的质量基础。

![关系图描述 3 组件的质量和服务管理与 3 的所有组件的都重叠。](media/envision-planning-for-service-management-and-quality-complete-guide-image1.png)

#### <a name="service-management"></a>服务管理

服务管理可以分为两个不同类别的责任：

-   **Microsoft 的责任**。 Microsoft 将负责包括 Office 365 提供服务的基础结构组件。 Microsoft 将对其负责的客户，以确保任何用户连接到的团队提供可靠和高质量的体验。

-   **客户负责**。 您和您的组织负责管理 Office 365 提供服务、 内部网络和终结点用户的各个方面。 例如，新的 IP 地址添加到 Office 365，必须更新相应的防火墙，以允许新的终结点，以避免用户中断的通信。

服务管理计划的详细指导，请参阅[服务管理规划](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-service-management)。

#### <a name="network"></a>网络 

在大多数组织中，网络最初旨在提供对数据和应用程序驻留在其数据中心的访问。 Office 365 等基于云的应用程序需要更改这些网络，以支持团队需要新访问和数据流程。 您可以使用户在组织中为团队之前，您必须评估和优化您的当前网络。 当利用云语音功能，这是至关重要的。

在传统网络中，用户将需要遍历访问团队在组织的外围网络。 许多组织都基于安全的设备，如代理服务器、 防火墙和 Vpn，可以阻止、 妨碍，或网络通信提供了一个未优化的路径。

此外，核心内部网络需要优化和适中的支持团队的工作负载，包括实时媒体提供足够的容量和质量。 您可以使用带宽规划、 补救措施，和优化，以帮助确保您的网络到 Office 365 提供高质量和有效路径。

有关网络规划的详细指导，请参阅[规划网络质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-network-quality)。

#### <a name="endpoints"></a>端点

Microsoft 小组支持不同的终结点。 从 Pc 到手机到平板电脑，可以从几乎任何设备任意位置访问团队。

若要为用户提供最好的体验，需要构想阶段考虑这些重要的方面： 不完终结点满足团队的硬件和软件要求吗？ 已配置和优化支持 Wi-Fi 网络终结点？ 您将使用哪些设备要拨打和接听语音电话？ 这些设备经过优化的团队？

有关计划的终结点的详细指导，请参阅[规划终结点质量](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#Plan-for-endpoint-quality)。

## <a name="plan-for-service-management"></a>服务管理计划

服务管理是一个宽泛的话题，涵盖日常操作 Microsoft 小组服务部署并为用户启用之后。 团队服务包括 Microsoft Office 365 和基础结构的组件部署内部 （如连网）。

The notion of service management is most likely not a new concept for most organizations. You probably have already implemented processes and tasks that are associated with existing services. 话虽如此，但可能可以增加什么您有的今天以支持 Microsoft 小组将来计划服务管理。

服务管理包括的所有活动和进程所涉及的管理端到端的 Microsoft 小组。 As described earlier, some components of service management—the infrastructure components that the Office 365 service itself comprises—are Microsoft’s responsibility, whereas the customer is accountable to its users to manage the various aspects of Teams, the network, and endpoints they provide. 文档的本节将重点从服务管理的角度看，客户有责任。

![描述 3 qualilty，和服务管理与 3 的所有组件的都重叠组件的关系图。 服务管理为重点。](media/envision-planning-for-service-management-and-quality-complete-guide-image2.png)

### <a name="introduction-to-the-operations-guide"></a>操作指南简介 

**什么**，**谁**，以及**如何**将需要服务管理时回答的三个重要问题。

您可以使用操作指南 [链接到操作指南] 来帮助您解决所有这三个问题。 指南 》 列出了要在每日、 每周、 每月和按需要的基础上进行的活动。 These activities and tasks are critical for maintaining a high-quality Teams deployment. Determining who will be responsible for performing specific activities in service management is a critical aspect of your planning that you need to do early in the Envision phase to ensure a successful deployment. After you’ve figured out the tasks and activities, they need to be understood and followed by the groups or individuals that you assign to them. The Operations Guide provides knowledge and guidance for how to perform each of the tasks, and/or references to outside content.

### <a name="operational-role-mapping"></a>操作角色映射

早期规划服务管理是一个重要的里程碑，因为操作阶段开始时启用了第一个试验用户。 The project team must review and agree on the tasks and activities required, identify the team that’s responsible for each operational task, and then get a commitment and sign-off from each respective team.

签字完毕后，负责小组必须启动留给这些角色和职责。 This might include training and readiness, updating the staffing model, or ensuring that external partners are ready to deliver.

Mapping operational roles early in the Envision phase enables all teams to start their operational tasks during the pilot, and ramp up operations and make sure that everything is ready after the deployment starts.

The Operations Guide provides a list of common tasks mapped to typical roles that should be valid in most scenarios. You need to customize these responsibilities to work for your organization.

### <a name="the-quality-champion-role"></a>The Quality Champion role

一组或个别需要负责在所有组织中的质量。 这是服务管理中最重要的角色。 The Quality Champion is a customer role that's assigned to a person or group who is passionate about their users' experience. This role requires the skills to identify trends in the environment and the sponsorship to work with other teams to drive remediation. The best candidate for the Quality Champion is typically the customer service owner, who—depending on the organization’s size and complexity—could be any person or group who is passionate about user experience.

The Quality Champion leverages existing tools and documented processes, such as the Call Quality Dashboard (CQD) and the Quality Experience Review Guide, to monitor user experience, identify quality trends, and drive remediation where needed. The Quality Champion works with the respective teams to drive remediation actions, reporting to a steering committee on their progress and open issues.

The tasks and activities associated with the role have been documented in the Operations Guide. This role should be assigned early in the Envision phase. A key step in operationalizing the role of Quality Champion is gaining the knowledge required for the role and ensuring the prerequisites are in place to deliver on the tasks. A key task for this role is running a regular Quality Experience Review.

### <a name="introduction-to-the-quality-experience-review-guide"></a>Introduction to the Quality Experience Review Guide

The Quality Experience Review Guide has a set of activities that assess and provide remediation guidance in key areas that have the greatest impact for improving user experience as shown in the figure below.

![A diagram that indicates the key areas that are examined during a quality experience review.](media/envision-planning-for-service-management-and-quality-complete-guide-image3.png)

By continually assessing and remediating the areas described in this document, you can reduce their potential to negatively affect user experience. Most user-experience problems encountered in a deployment can be grouped into the following categories:

-   Incomplete firewall or proxy configuration

-   Poor Wi-Fi coverage

-   Insufficient bandwidth

-   VPN

-   使用优化的还是内置的音频设备

-   有问题的子网或网络设备

The guidance provided in the Quality Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact. Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.

We highly recommend that you nominate the Quality Champion early on. After being nominated, they should start to familiarize themselves with the content in the Quality Experience Review Guide.

The Quality Experience Review Guide can be found [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true).

## <a name="plan-for-network-quality"></a>Plan for network quality 

Planning for network quality will be the focus for the following section.

![Diagram describing the 3 components of quality, and how service management overlaps all 3 components. With a focus on Network.](media/envision-planning-for-service-management-and-quality-complete-guide-image4.png)

As previously mentioned, planning for network quality prior to onboarding to Microsoft Teams is critical. For further guidance for network readiness, see [Prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network).

In most organizations, networks can comprise both managed and unmanaged networks.

Managed networks are components of the network infrastructure that an organization has direct control over. As a result, managed networks have a direct influence on the quality that can be provided to real-time traffic workloads.

Conversely, unmanaged networks are segments of the network that a customer has limited control, or no control, over.

Internet connections between the organization and Office 365 are networks where a customer has limited control. The networks are managed by an ISP, but organizations should be able to influence the quality of the network by upgrading their bandwidth, advocating for route optimizations, or—if all else fails—switching ISPs.

Home networks or networks in hotels or coffee shops are examples of networks where a customer has no control.

In the following sections, we will focus on the quality requirements of managed networks.

### <a name="key-network-planning-areas"></a>关键的网络规划区域

The following sections focus on the important areas for delivering a high-quality network.

> [!NOTE]
> Many networks evolve over time due to upgrades, expansion, or other business requirements. Ensure that you have operational processes in place to maintain these areas as part of your service management planning.

#### <a name="bandwidth"></a>Bandwidth

Bandwidth planning is a critical aspect of the network readiness activity. Ensuring that there's enough bandwidth for the Microsoft Teams workloads is imperative. To be able to right-size an existing network, you must understand what’s currently provisioned, the current utilization, and—ultimately—the remaining available bandwidth.

To measure current utilization, you need to monitor the network. This measurement can then be used as the starting point for bandwidth planning. 此外，网络应该不断地监视在部署期间和之后的部署，以确保网络足够资源调配。

> [!NOTE]
> When monitoring network utilization, it’s important to avoid using averages over the day. These averages can include non-core hours that skew the result. Averages can hide peak periods and mask an underlying problem.

The [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) helps you determine and organize network requirements for your deployment in just a few simple steps. By using the tool to gather your organization's networking details and Cloud Voice usage, you can get an approximate calculation of the network requirements you’ll need for your Cloud Voice deployment, manage and export these details for reporting, and view areas for further investigation and next steps.

#### <a name="quality-of-service-qos"></a>服务质量 (QoS)

QoS should be implemented on all segments of the managed network, even networks that have been adequately provisioned for bandwidth. In the latter case, QoS acts as a risk mitigation in the event of unanticipated network load. 当实现 QoS 时，语音通信将优先安排，以便这些意外的事件不会影响质量。

A QoS implementation should include areas of the network, from the endpoint all the way up to the egress points and from the egress points back to the endpoint. This will ensure that voice traffic is being prioritized in both directions. QoS should be implemented on both wired and Wi-Fi networks.

在您的网络上实现 QoS，以下指南可以帮助[Microsoft 小组中的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)

#### <a name="proxy-servers"></a>代理服务器

Many organizations view traffic destined for the internet as a security risk, and they mitigate this risk by monitoring and evaluating traffic at the egress points in the network. 代理服务器是一种可以部署以满足这一要求的设备。

A proxy server can introduce problems when performing packet inspection or modification to the payload. 这可能会导致调用安装程序失败、 通话中断和较差的呼叫质量。 如果实时媒体不得不遍历一个代理服务器，将被迫在团队中的媒体堆栈故障回复到 TCP，可以进一步降低质量。 UDP is always preferred over TCP.

此外，不可能设计一个代理服务器来处理额外负载的 Office 365 和特别是 Microsoft 小组工作负载 — — 包括实时媒体。

由于潜在的问题可能会引入一个代理服务器，并且这些额外的容量问题，Microsoft 建议绕过代理服务器，并使 Office 365 的直接连接。

不使用代理服务器所需的配置随供应商，但常用的方法一般包括更新代理自动配置 (PAC) 文件。 PAC 文件是配置文件描述的通信都要通过代理服务器和哪些通信量将绕过它。

某些代理服务器供应商提供的自动化的过程，确保配置为最新。 如果您的供应商没有提供此自动过程，则可以下载更新的 PAC 文件从<https://aka.ms/o365proxies>。

[Skype 的在线业务和团队的代理服务器](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>防火墙

访问 Microsoft 小组，要求确保所有 Office 365 IPs 和 Url 打开正确的端口和协议。 它也是部署高质量的关键。 只需拨打电话，或加入会议呼叫不足以确保您的防火墙配置正确。

如果只在防火墙上打开 TCP 时，将建立的会话，但没有协商的首选的传输 (UDP)。 TCP 和 UDP 要求打开防火墙以提供最佳用户体验上。

由于其状态的性质，TCP 不是首选的实时媒体和 Microsoft 小组只提供作为故障回复网络传输协议。 使用 TCP，如果数据包延迟或丢失，这些数据包必须重新传输直到它们正在确认。 这可能会导致不再及时提供的当前媒体数据包与竞争相关的媒体包。 用户的团队客户端尝试伸展音频，并可能产生听见根据网络状况的项目。 与 TCP 的额外开销，通常可接受的体验可以转移到差的用户体验。 鉴于此，无状态的网络传输 UDP 是必需的。

[Office 365 的 Url 和 IP 地址范围](https://aka.ms/o365ips)的文章提供了对于 Microsoft 小组打开防火墙的完整指南。

打开防火墙后，可以使用[Microsoft 网络评估工具](https://www.microsoft.com/en-us/download/details.aspx?id=53885)来验证连接云语音功能。

> [!IMPORTANT]
> Microsoft Office 365 IPs 和 Url 会随时间改变。 服务管理计划的一部分，它是一定要确保操作过程是在地方，一个组负责监视[Office 365 的 Url 和 IP 地址范围](https://aka.ms/o365ips)，并相应地进行更新。

#### <a name="local-internet-egress"></a>本地互联网出口

在设计许多网络使用一个集线器和分支拓扑。 在此拓扑中，互联网通信量通常通过 WAN 到中央数据中心之前它出现 （出口） 到互联网。 通常情况下，这样做是为了集中网络安全设备，以降低整体成本的目标。

跨广域网后拖拉流量增加延迟，对质量和用户体验的负面影响。 因为 Microsoft 的大型全球网络上运行 Microsoft 小组，是通常接近用户的网络对等位置。 用户通过尽快 egressing 出本地 internet 点靠近它们的位置和我们的声音进行了优化的网络到最有可能获得更好的性能。 对于某些工作负载，使用 DNS 请求以便向发送通讯最近的前端服务器。 在这种情况下，非常重要，当使用本地出口点，则已配对使用本地 DNS 解析。

优化网络路径与 Microsoft 的全球网络将提高性能，并最终为用户提供最好的体验。 有关详细信息，请参阅博客文章[获得最佳的连接和 Office 365 中的性能](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)。

#### <a name="vpn"></a>VPN

Vpn 将提供许多组织有价值服务。 遗憾的是，他们通常不设计或配置为支持实时媒体。 某些 Vpn 可能也不支持 UDP。 Vpn 还引入了额外的加密的通信已加密的介质上。 此外，连接到 Microsoft 小组服务可能不是由于头发固定通过 VPN 设备的通信效率。 此外，它们不一定被旨在从产能角度来看以适应团队将需要的预期的负载。

建议是提供备选路径绕过团队通信 VPN。 这通常被称为拆分隧道 VPN。 拆分隧道意味着 Office 365 的通讯不通过 VPN，但将直接转到 Office 365。 此更改对质量，将产生积极影响，而且还提供辅助福利减少从 VPN 设备和组织的网络负载。

实现拆分隧道，请咨询您的 VPN 供应商的配置的详细信息。

#### <a name="wi-fi"></a>Wi-Fi

如 VPN、 Wi-Fi 网络不一定而设计或配置为支持实时媒体。 规划，和/或优化，Wi-Fi 网络以支持团队是一个重要考虑事项质量部署。

有几个榜上有名的 Wi-Fi 网络优化的因素。

-   实现 QoS 或 Wi-fi 多媒体 (WMM)，以确保该媒体通信获取相应地优先顺序通过 Wi-fi 网络。

-   规划和优化的 W-Fi 区段和访问点的位置。 2.4 GHz 范围可能会提供足够的经验，根据接入点放置，但接入点通常受到运行在该范围内其他消费型设备。 5 GHz 范围更适合于实时媒体由于其密集的范围，但是需要更多的接入点以获得足够的覆盖范围。 终结点还需要支持该范围和配置，以便相应地利用这些频带。

-   双频 Wi-Fi 网络在部署时，如果考虑实现带控制。 带控制是影响双波段客户端使用 5 Ghz 范围的 Wi-Fi 供应商实现的技术。

-   信道重叠 – 当接入点的相同的通道太紧靠在一起，则会导致信号重叠，无意中参与竞争，从而导致糟糕的用户体验。 确保接入点的相邻频道比不重叠。

每个无线供应商已部署其无线解决方案的建议。 我们建议您咨询您的供应商进行具体指导。

### <a name="network-readiness-assessment"></a>网络就绪评估

部分网络准备工作活动包括网络评估。 规划和配置完成后，评估服务可以使您之前板载用户网络质量的一个基本了解 Microsoft 小组。 评估结果还将帮助您识别并针对性为用户启用团队之前的补救措施。

应在既有线上执行网络评估和正在进行的所有建筑物的 Wi-Fi 网络云在团队中的语音功能。

可以通过使用 Microsoft 合作伙伴、 第三方工具或[Microsoft 网络评估工具](https://www.microsoft.com/en-us/download/details.aspx?id=53885)进行网络评估。 我们还提供进一步指导如何运行作为我们准备指南的一部分使用 Microsoft 网络评估工具的评估[这里](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11).

## <a name="plan-for-endpoint-quality"></a>终结点质量的计划

从下图可以看出，终结点都是在为最终用户提供品质体验的重要组成部分。

![关系图描述 3 组件的质量和服务管理与 3 的所有组件的都重叠。 终结点为重点。](media/envision-planning-for-service-management-and-quality-complete-guide-image5.png)

Microsoft 小组终结点可以在很多设备，包括 Pc、 Mac、 平板电脑和移动设备上运行。 体验的一部分不仅涵盖了该设备，但如何在用户连接到设备 — — 例如，使用该设备的内置的麦克风扬声器、 耳机或优化的头戴式耳机。 使用优化的耳机可以丰富用户的总体体验。

终结点计划的以下指南将帮助您确保您的组织有经验的团队成功服务。

### <a name="endpoint-capability"></a>终结点功能

计划的第一部分是为了确保所有 Pc 和您的组织中的其他设备可以运行 Microsoft 小组。 这涉及到不只看一看的硬件要求，但也知道电脑在后台干些什么。 许多组织运行的其他软件，包括入侵检测系统和反恶意软件可能影响到设备的基本性能。

Microsoft 的小组都有客户机可用于 web、 桌面 （Windows 和 Mac） 和手机 （Android、 iOS 和 Windows Mobile）。 有关每个平台的软件要求的信息，请参阅[获取有关 Microsoft 小组的客户机](https://docs.microsoft.com/microsoftteams/get-clients)。

### <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙可以对用户体验有很大的影响。 客户端防火墙可以影响以及防止在建立呼叫的呼叫质量。 在[Office 365 的 Url 和 IP 地址范围](https://aka.ms/o365ips)中的信息基于客户端防火墙上配置相应的排除。 第三方供应商将对如何创建排除特定的指导。

> [!NOTE]
> Microsoft 的小组使用适当的防火墙配置中将自动更新 Windows 防火墙。

### <a name="wi-fi-recommendations-for-endpoints"></a>终结点的的 Wi-Fi 建议

规划和部署优化的 Wi-fi 网络，以在 Microsoft 小组支持实时的工作负载，需要大量的规划。 以下各节提供了可以帮助您避免一些常见的陷阱，规划为终结点时某些一般性指导。

#### <a name="wi-fi-drivers"></a>Wi-fi 驱动程序

一些 Wi-fi 驱动程序可能有问题。 例如，驱动程序可能必须接入点，从而导致较差的呼叫质量之间的极具挑战性漫游行为。 这不是常见的事，但一定要确保已更新并在部署之前测试 Wi-fi 驱动程序在计算机上。

#### <a name="wi-fi-bands"></a>Wi-Fi 带区

有两个主要类型的区段采用 Wi-fi 设备今天、 2.4 g h z 和 5.0 g h z。 如果您的组织提供了这两个区段，应配置驱动程序设置表示希望 5.0 g h z 频段。 该带是在吞吐量方面更高密度，更少受到干扰，在 2.4 GHz 频带中看到。 这一建议假定您已经正确地优化 5.0 g h z 网络带。

#### <a name="wi-fi-radio-type"></a>Wi-fi 无线电类型

支持较新的 Wi-fi 无线电类型的设备的计划。 如果利用 802.11ac，可以获得很好的 Wi-fi 性能或更高版本在您配置的设备。

#### <a name="wireless-avoidance"></a>无线回避

一些组织倾向于完全避免 Wi-fi。 有时本指南建议通过提供给用户直接连接到有线网络。 在某些情况下，网络绑定顺序可能具有首选的无线连接并继续使用该连接，即使将此电脑连接到有线连接。 若要避免此意外的现象，请配置绑定顺序，以避免这种情况。

#### <a name="80211-power-save-protocol"></a>802.11 节能协议

如果您的组织使用无线访问点或路由器不支持 802.11 节能的保存协议时，可能出现通话中断或在 Windows 设备上运行的 Microsoft 小组在较差的呼叫质量。 如果不能升级您的无线访问点或路由器，则应更新设备上，使用电池电源运行 Windows 电源计划的设置。 以下[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)中提供了进一步的详细信息和配置指南。

### <a name="devices-for-teams"></a>团队的的设备

会议或电话系统，则可以使用 Microsoft 小组。 在使用这些功能时的接口设备，用于团队将用户体验中起着重要作用。

使用内置的 PC 扬声器和麦克风听起来可接受该配置的用户。 但通常这些设备不适合噪音取消和任何类型的环境噪音会对下游的影响其他人待命。 利用设备适合这些方案将有助于确保高质量的体验。

每个设备都需要以满足用户的需要。 您需要定制不同的角色如耳机的设备和您的组织中使用用例。 角色到设备的映射练习应作为规划过程的一部分来完成。

选择设备后，则将它们包括在最终验证的试验性测试计划。 在试验阶段，若要收集反馈信息以确保您的设备战略利用调查是最佳的。

到目前为止，我们建议使用 Skype 业务认证计划通过认证的音频设备。 若要查找在此计划下认证的设备，请到[USB 设备认证，Skype 业务](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)解决方案目录。

有关详细信息，请参阅[客户端和设备的准备工作研讨会](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)

## <a name="client-updates"></a>客户端更新

Microsoft 的小组的主要优点之一是，客户端将保持为最新自动。 在 PC 和 Mac 上的客户端使用一个后台进程，检查新生成并下载新的客户端，当应用程序处于空闲状态更新。 客户端下载大小大约为 100 MB。

组织没有任何控件或访问策略设置来管理更新过程。 要缓解的风险可能较新版本中发现的问题，该终结点上保留上次已知的正确版本。 如果没有新的生成问题，Microsoft 小组服务可以自动还原为早期版本的终结点。

## <a name="next-steps-and-references"></a>下一步步骤和参考

此表包含链接到相关内容的规划活动的摘要。

| 区域 | 详细信息 | References |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Plan for service management | 执行的操作角色映射练习 <br/> 负责小组的签收 <br/> 角色的准备工作 | [操作指南](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service) |
| | 提名质量 Champion(s) <br/> 质量冠军准备工作| [了解 CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [质量的经验审查指南](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) |
| | 安装质量的经验审查模板 <br/> 构建文件上载 | [QERLite 的模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-1-2.zip?raw=true) <br/> [上载的构建信息](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard?ui=en-US&rs=en-US&ad=US#upload-building-information)|
| 网络质量的计划 | 运行网络规划器 | [网络规划器](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | QoS 的实施 | [在 Microsoft 团队的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| | 跳过代理服务器 | [代理指南](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ad=US#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies) |
| | Implement split-tunnel VPN | [VPN Split Tunnel Guidance](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | Optimize Wi-Fi networks for real-time media  | 请参考第三方供应商 |
| | 实现本地互联网出口 | [本地互联网出口](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | 实现网络连接 <br/> 验证网络连接 | [Office 365 的 Url 和 IP 地址](https://aka.ms/o365ips) |
| | | [网络评估工具](https://www.microsoft.com/en-us/download/details.aspx?id=53885) |
| | Perform network assessment | [网络就绪性评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| 终结点质量的计划 | 更新终结点防火墙 | [Office 365 URLs and IP addresses](https://aka.ms/o365ips) |
| | Validate software requirements | [Get Clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients) |
| | Implement endpoint Wi-Fi recommendations | Consult 3rd Party Vendors |
| | 开展设备映射的角色 <br/> 供应设备和试验它们 | [客户端和设备的准备工作研讨会](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [设备目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |