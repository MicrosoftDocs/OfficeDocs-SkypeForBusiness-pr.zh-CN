---
title: 规划服务管理和质量-Microsoft 团队
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 使用本指南可了解有关所需提供和维护高质量的 Microsoft 团队部署的要求。
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0050834f55568a6a747d84e8efdffb3e898d226
ms.sourcegitcommit: a20a9a7d0797e3e01afa1cf13957f10dad61cdf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "20398026"
---
![升级旅程，重点强调的技术的准备阶段的阶段](media/upgrade-banner-tech-readiness.png "升级旅程，重点强调的技术的准备阶段的阶段")

本文是您升级旅程，与用户准备阶段并行完成的活动的技术的准备阶段的一部分。 在继续之前，确认您已完成从以前的阶段的这些活动：

-   [登记项目利益干系人](upgrade-enlist-stakeholders.md)
-   [定义您的项目范围](https://aka.ms/SkypetoTeams-Scope)
-   [商业和团队理解共存和 Skype 的互操作性](https://aka.ms/SkypeToTeams-Coexist)
-   [选择您升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<!-- [!INCLUDE [envision-planning-for-service-management-and-quality-complete-guide](envision-planning-for-service-management-and-quality-complete-guide.md)]-->
# <a name="plan-for-quality"></a>规划质量

如果您正在部署音频、 视频或会议，您可以优化该功能的环境的一些额外步骤。 此内容将提供所需提供和维护高质量的 Microsoft 团队部署的要求的概述。 您可以帮助确保成功部署规划服务管理和质量，在您的第一个试验或生产部署之前。

指南分为以下几节：

-   首先是概述用户体验和支持质量的关键组件。 这将突出显示前向 Microsoft 工作组入职培训重点关注的区域。

-   其次，指南提供规划支持模型之前在首次用户试验或生产部署管理的 Microsoft 团队。 本节介绍需要定期维护高质量团队部署执行的任务。 此外，本节介绍了进一步可用于开始了解并留给这些任务的指导。

-   第三个、 特定的指导可帮助规划您的网络和您的组织中的终结点支持的 Microsoft 团队。

-   最后下, 一步步骤概括指向相关内容的引用。

## <a name="key-technical-components-that-affect-user-experience"></a>影响用户体验的重要技术组件

将在本节评审影响用户体验的关键技术组件。 查看的关键组件之前很关键，了解用户体验和实现您的组织的业务目标的重要性。 让我们查看如何我们先定义用户体验。

### <a name="user-experience-defined"></a>定义用户体验

当您部署的 Microsoft 团队和时用户采用团队作为其核心协作和通信解决方案，可以实现业务目标。 质量可以帮助确保良好的用户体验，驱动的用法和采用的关键属性。 通过提供高质量服务的富食品公司的人员，个人和团队可以信心和发现的驱动器业务好处的创新方式使用该服务。

此核心是用户的体验与团队 — 此人的情绪和服务的态度。 因此，功能可对用户体验？ 范围为从用户知道如何和为什么使用团队和并入遇到异常呼叫质量并能够可靠地，无论他们将连接到其每日工作流。 用户体验是非常广泛性质;本文仅重点介绍可以由组织控制这些技术元素。 [准备您的组织团队](https://aka.ms/SkypeToTeams-UserReadiness)中，可以找到有关用户准备情况的其他信息。

向部署非常重要，以提供美好的用户体验的特定要求 — 尤其是当使用云的语音功能中的团队。 要被视为一个一类公民与其他通信和协作的投资，相应地设置优先级的实时通信的 Microsoft 团队至关重要。 下面一节提供了概述影响用户体验的关键组件。 在进一步部分中，我们将提供指导如何启动计划部署和维护的关键组件组成质量。

### <a name="key-components-of-quality"></a>质量的关键组件

组织或支持合作伙伴应开始规划团队部署技术的准备阶段的三个主要组件： 服务管理、 网络和终结点。 所有三个方面的组合而言至关重要的用户体验质量。

![图示，说明质量和服务管理与全部三个组件的重叠的三个组件。](media/envision-planning-for-service-management-and-quality-complete-guide-image1.png "图示，说明质量和服务管理与全部三个组件的重叠的三个组件。")

#### <a name="service-management"></a>服务管理

服务管理可以分为两种不同类别的责任：

-   **Microsoft 责任**。 Microsoft 负责为 Office 365 服务均包含基础结构组件。 Microsoft 负责向客户以确保其用户连接到团队任一原样提供可靠且高质量体验。

-   **客户责任**。 您和您的组织负责管理 Office 365 服务、 本地网络和用户终结点的各个方面。 例如，新的 IP 地址添加到 Office 365 时，则必须更新相应的防火墙，以允许到新的终结点，以避免出现用户中断通信。

服务管理规划的详细指导，请参阅[规划服务管理](#plan-for-service-management)。

#### <a name="network"></a>网络 

大多数组织中网络最初旨在提供数据和驻留在他们的数据中心的应用程序的访问。 基于云的应用程序，如 Office 365 需要更改这些网络支持团队需要的新访问和数据流。 您可以让用户在组织中的团队之前，必须评估并优化您的当前网络。 利用云语音功能时，这一点非常重要。

在传统的网络中，用户将需要遍历访问团队的组织的外围网络。 许多组织会基于安全的设备，如代理服务器、 防火墙和 Vpn 可阻止限制，或网络通信提供了一个未优化的路径。

此外，核心内部网络都需要是优化和右大小，以支持团队工作负荷，包括实时媒体提供足够的容量和质量。 您可以使用带宽规划，修正，并优化以帮助确保您的网络到 Office 365 提供高质量和效率的路径。

有关网络规划的详细指南，请参阅[规划网络质量](#plan-for-network-quality)。

#### <a name="endpoints"></a>端点

Microsoft 团队支持各种终结点。 从 Pc 到电话的平板电脑，可以几乎任何设备从任何位置访问团队。

若要为用户提供最佳体验可能，您需要考虑以下重要方面： 执行您终结点符合团队硬件和软件要求？ 是否已配置和优化终结点 Wi-fi 网络支持？ 您将使用哪些设备发起和接收语音呼叫？ 针对团队优化这些设备？

有关规划的终结点的详细指南，请参阅[Plan for 终结点质量](#plan-for-endpoint-quality)。

## <a name="plan-for-service-management"></a>规划服务管理

服务管理是涵盖日常操作的 Microsoft 团队服务后已部署并为用户启用广泛主题。 团队服务包括 Microsoft Office 365 和本地部署的基础结构组件 （例如，网络）。

服务管理的概念很可能不是一个新的概念对于大多数组织。 您可能已经实现了进程和与现有服务相关联的任务。 也就是说，您可能可以增大所就地时立即以支持的 Microsoft 团队将来规划服务管理。

服务管理包括所有活动和进程涉及管理 Microsoft 团队端到端。 前面所述，某些组件服务管理-Office 365 服务本身包含基础结构组件 — 是 Microsoft 的责任，而客户负责为其用户管理团队的各个方面网络和它们提供的终结点。 文档的本部分将重点从服务管理角度客户的责任。

![图示，说明质量和服务管理与全部三个组件的重叠的三个组件。服务管理重点。](media/envision-planning-for-service-management-and-quality-complete-guide-image2.png "图示，说明质量和服务管理与全部三个组件的重叠的三个组件。服务管理重点。")

### <a name="introduction-to-the-operations-guide"></a>操作指南简介 

**哪些****人员**、 和**如何**是需要当谈到服务管理回答的三个重要问题。

[操作指南](1-drive-value-operate-my-service.md)可用于帮助您解决所有这三个这些问题。 指南提供了活动上每天、 每周、 每月和根据需要执行的列表。 这些活动和任务的维护高质量团队部署至关重要。 确定谁将负责服务管理中执行特定活动是您需要执行早期在[计划阶段](upgrade-enlist-stakeholders.md)确保成功部署进行规划的重要组成部分。 您已经确定的任务和活动后，他们需要理解和被关注的组或个人您分配给它们。 操作指南提供知识和如何执行每个任务，指南和/或外部内容的引用。

### <a name="operational-role-mapping"></a>操作的角色映射

规划服务管理早期是关键里程碑，因为操作阶段开始时启用了第一个试点用户。 项目团队必须查看并同意任务和活动需要，确定负责为每个操作任务的团队，然后获取承诺注销来自每个各自的团队。

完成注销后，负责小组然后必须启动留给这些角色和职责。 这可能包括培训并准备、 更新人员配备模型，或确保外部合作伙伴便可提供。

映射，收集您的[项目工作组](upgrade-enlist-stakeholders.md)的操作的角色使所有团队试验和掌握操作过程中启动其操作任务，并确保一切就绪后部署启动。

操作指南提供了一组映射到应在大多数情况下有效的典型角色的常见任务。 您需要进行自定义这些工作为组织的责任。

### <a name="the-quality-champion-role"></a>质量冠军角色

一组或各个需要负责在组织中所有的质量。 这是在服务管理的最重要的角色。 客户角色分配给用户或用户组属于热心有关其用户体验质量冠军。 此角色需要确定中的趋势环境和赞助 ォ オ リ モ 驱动修正工作的技能。 最适合进行质量冠军通常是客户服务所有者，人员 — 取决于组织的规模和复杂性 — 可以是任何人或团队致力于用户体验。

质量冠军利用现有的工具和记录操作过程中，如呼叫质量仪表板 (CQD) 和质量体验审阅指南要监视的用户体验，请确定质量趋势和驱动器修正在需要时。 质量冠军处理驱动器修正操作，各个团队报告给调控委员会其进度和解决问题。

任务和与角色相关联的活动记载操作指南 》。 在[计划阶段](https://aka.ms/SkypeToTeams-Plan)期间应向其分配此角色。 留给的质量冠军角色一个关键步骤获得所需的角色和确保措施来提供任务，必备组件的知识。 正则质量体验回顾运行此角色的关键任务。

### <a name="introduction-to-the-quality-experience-review-guide"></a>质量体验审阅指南简介

质量体验审阅指南有一组活动的评估，并提供对下图中所示改善用户体验的影响最大的主要区域中的补救指南。

![图表，说明在质量体验审阅过程中检查的关键区域。](media/envision-planning-for-service-management-and-quality-complete-guide-image3.png "图表，说明在质量体验审阅过程中检查的关键区域。")

通过不断地评估和补救本文所述的区域，您可以减少他们可能会产生负面影响的用户体验。 在部署中遇到的最多的用户体验问题可以分为以下类别：

-   不完整的防火墙或代理配置

-   质量欠佳 Wi-fi 覆盖范围

-   带宽不足

-   VPN

-   使用未优化或内置的音频设备

-   有问题的子网或网络设备

使用作为主要工具，呼叫质量仪表板 (CQD) 联机报告和调查所述，重点音频，以最大限度地应用和影响每个区域重点质量体验审阅指南中提供的指南。 对网络以提高音频体验任何优化还直接将翻译视频和桌面共享的改进。

我们强烈建议您在早期提名质量冠军。 正在提名之后, 他们应开始熟悉质量体验审阅指南中的内容。

可以找到质量体验审阅指南[此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)。

## <a name="plan-for-network-quality"></a>规划网络质量 

网络质量规划将下一节的焦点。

![图示，说明质量和服务管理与全部三个组件的重叠的三个组件。具有网络上焦点。](media/envision-planning-for-service-management-and-quality-complete-guide-image4.png "图示，说明质量和服务管理与全部三个组件的重叠的三个组件。具有网络上焦点。")

如前所述，规划向 Microsoft 工作组入职培训之前的网络质量非常重要。 网络就绪性的更多指南，请参阅[准备贵组织的网络中的 Microsoft 团队](prepare-network.md)。

大多数组织中网络可以包含托管和非托管网络。

托管的网络是组织拥有直接控制通过网络基础结构的组件。 因此，托管的网络具有可提供给实时通信工作负载的质量直接影响。

相反，非托管的网络是的客户具有有限的控件或没有控件，超过网络段。

Office 365 组织之间的 Internet 连接是的网络客户有限控件。 网络进行管理由 ISP，但是组织应该能够通过升级其提倡的路由优化的带宽影响网络质量或 — 如果他们都失败 — 切换 Isp。

家庭网络或网络中旅馆或咖啡馆是客户其中有无控制的网络的示例。

以下各节，我们将专注于托管网络的质量要求。

### <a name="key-network-planning-areas"></a>关键网络规划区域

以下各节重点介绍提供高质量网络的重要区域。

> [!NOTE]
> 许多网络随由于升级、 扩展或其他业务要求的时间。 确保您要维护服务管理规划的一部分这些领域有操作过程。

#### <a name="bandwidth"></a>带宽

带宽规划是网络准备活动的一个重要方面。 确保没有足够带宽的 Microsoft 团队工作负载是强制性。 为了能够右大小现有网络，您必须了解哪些当前设置，当前利用率，和 — 最终 — 剩余的可用带宽。

若要测量当前使用率，您需要监视网络。 然后，此度量可以用作的起始点带宽规划。 此外，网络应该不断监视在部署期间和之后部署以确保网络已足够设置。

> [!NOTE]
> 监视时网络利用率，务必要避免使用通过一天的平均值。 这些平均值可以包括非核心 skew 结果的时间点。 平均值可以隐藏高峰时段并屏蔽的基本问题。

[网络计划工具](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)可帮助您确定和组织中只通过几次简单步骤部署的网络要求。 通过使用该工具收集您的组织网络的详细信息和云语音用法，您可以获取您将需要为云语音部署，管理和导出的报告，这些详细信息并查看区域的网络要求近似计算对于进一步调查和后续步骤。

#### <a name="quality-of-service-qos"></a>服务质量 (QoS)

应在所有段托管网络，甚至充分设置的带宽的网络上实现 QoS。 在后一种情况，QoS 作为发生意外的网络负载应用风险缓解时。 当实现 QoS 时，以便这些无法预知的事件不会影响质量，语音通信将按优先级顺序。

QoS 实现应包括的从一直到出口点的终结点和回终结点的出口点的网络区域。 这将确保语音通信要在两个方向确定其优先级。 应在同时有线实现 QoS 和 Wi-fi 网络。

以下指南可用于实现在网络上的 QoS，帮助[中的 Microsoft 团队的服务质量](qos-in-teams.md)

#### <a name="proxy-servers"></a>代理服务器

许多组织查看为安全风险，internet 的通信和它们通过监视和评估网络中的出口点处的流量减轻此风险。 代理服务器都可以部署以满足此要求的设备的类。

执行数据包检查或修改负载时，代理服务器可能会带来问题。 这可能会导致呼叫安装失败、 丢弃的呼叫和质量欠佳的呼叫质量。 如果强制实时的媒体遍历代理服务器，则会强制团队中的媒体堆栈故障回复到 TCP，它们可以进一步减少质量。 UDP 始终是首选 tcp。

此外，代理服务器设计可能无法处理的 Office 365 和专门的 Microsoft 团队工作负载的其他负载 — 包括实时媒体。

由于潜在的问题可以引入代理服务器，以及这些额外的容量问题 Microsoft 建议绕过代理服务器并建立直接连接到 Office 365。

绕过代理服务器所需的配置随供应商，但常用的方法通常涉及更新代理服务器自动配置 (PAC) 文件。 PAC 文件是介绍哪些流量将通过代理以及哪些流量绕过其配置文件。

某些代理服务器供应商提供的自动化的过程，确保配置为最新。 如果您的供应商不提供此自动过程，您可以下载从更新的 PAC 文件<https://aka.ms/o365proxies>。

[Skype 在线业务和团队的代理服务器](/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)

#### <a name="firewalls"></a>防火墙

确保正确的端口和协议对所有 Office 365 Ip 和 Url 开放需要访问的 Microsoft 团队。 也是高质量部署至关重要。 只需进行呼叫或加入电话会议不足以确保您的防火墙配置正确。

如果只在防火墙上打开 TCP 时，将建立的会话，但未协商的首选的传输 (UDP)。 TCP 和 UDP 需要在提供最佳用户体验的防火墙上打开。

由于其状态的性质，TCP 不是首选的实时的媒体和 Microsoft 团队仅提供作为故障回复网络传输。 使用 TCP，如果没有数据包延迟或丢失，则这些数据包必须重新传输直到他们正在被应答。 这会导致不再相关与及时提供当前媒体数据包的竞争的媒体数据包。 用户的工作组客户端尝试拉伸音频，并可能会产生听见项目，具体取决于网络条件。 使用 TCP 的额外开销，通常可接受的体验可以转移到不佳的用户体验。 因此，无状态网络传输 UDP 需要。

[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)一文中提供了用于打开防火墙的 Microsoft 团队的完整指导。

打开防火墙之后，您可以使用[Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)以验证连接云语音功能。

> [!IMPORTANT]
> Microsoft Office 365 Ip 和 Url 会随时间改变。 作为服务管理规划的一部分，很重要，以确保操作过程是就地和一个组负责监视[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)，并相应地进行更新。

#### <a name="local-internet-egress"></a>本地 internet 出口

许多网络旨在使用集线器和分支拓扑。 在此拓扑中，internet 通信通常遍历 WAN 中心数据中心到之前它出现 （出口） 到 internet。 通常，这样做是为了集中网络安全设备的总成本降低的目标。

通过 WAN 后拖拉流量增加延迟具有对质量和用户体验的负面影响。 由于 Microsoft 的大型全局网络上运行的 Microsoft 团队，是通常接近用户对等网络位置。 用户很可能将通过尽快 egressing 出本地 internet 点接近其位置和到我们语音优化网络获得更好的性能。 针对某些工作负载，DNS 请求用于发送通信到最近的前端服务器。 在这种情况下，很重要，使用本地出口点，则已配对本地 DNS 解析。

优化与 Microsoft 的全局网络的网络路径将提高性能和最终用户提供最佳体验。 有关详细信息，请参阅博客文章[入门最佳的连接和 Office 365 中的性能](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)。

#### <a name="vpn"></a>VPN

Vpn 提供许多组织重要服务。 遗憾的是，他们通常不设计或配置为支持实时的媒体。 某些 Vpn 也可能不支持 UDP。 Vpn 还引入了额外的已加密的媒体流量在加密。 此外，连接到 Microsoft 团队服务可能不是有效由于字形驻留流量通过 VPN 设备。 此外，它们不一定旨在从容量角度以适应团队需要的预期的负载。

建议您是提供绕过的团队流量 VPN 备用路径。 这通常是称为拆分隧道 VPN。 拆分隧道表示的 Office 365 的流量不遍历 VPN，但将直接转到 Office 365。 此更改将产生正面影响对质量，但还提供了减少从 VPN 设备和组织的网络负载的辅助好处。

若要实现拆分隧道，请咨询您 VPN 供应商联系以获取配置详情。

#### <a name="wi-fi"></a>Wi-fi

VPN，如 Wi-fi 网络不一定设计或配置为支持实时媒体。 规划，和/或优化，Wi-fi 网络支持团队是质量部署的重要注意事项。

有派上用场优化 Wi-fi 网络的几个因素。

-   实现 QoS 或 Wi-fi 多媒体 (WMM)，以确保该媒体流量获取确定相应优先级通过 Wi-fi 网络。

-   规划和优化 W-保真区段和访问点位置。 为 2.4 GHz 范围可提供足够的体验，具体取决于接入点放置但访问点通常影响该范围内运行其他使用者设备。 5 GHz 范围更适合于实时媒体由于其密集范围，但需要更多访问点来获取足够的范围。 终结点还需要支持这一系列和配置，以便相应地利用这些分隔条。

-   如果部署双带 Wi-fi 网络，请考虑实现带控制。 带控制是由 Wi-fi 供应商以影响双带客户端使用 5 Ghz 区域实现的技术。

-   频道重叠 – 时的相同的通道访问点太近它们可能会导致信号重叠，意外竞争，导致用户的体验不佳。 确保彼此相邻的访问点位于通道比不重叠。

每个无线供应商具有自己部署其无线解决方案的建议。 我们建议您的特定指南咨询您的供应商。

### <a name="network-readiness-assessment"></a>网络就绪评估

网络准备活动的一部分包括网络评估。 在您完成您的规划和配置后，评估可以为您提供的之前板载用户网络质量比较基准了解到 Microsoft 团队。 评估结果还将帮助您确定并为用户启用团队之前确定优先级修复措施。

应在同时有线上执行网络评估和所有启用的建筑物的 Wi-fi 网络云团队中的语音功能。

可以使用的 Microsoft 合作伙伴、 第三方工具或[Microsoft 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)进行网络评估。 我们还提供进一步指导如何运行我们准备指南的一部分使用 Microsoft 网络评估工具评估[此处](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11)。

## <a name="plan-for-endpoint-quality"></a>规划终结点质量

下图从中可以看出，如终结点是中为用户提供高质量体验重要构建基块。

![图示，说明质量和服务管理与全部三个组件的重叠的三个组件。具有终结点上焦点。](media/envision-planning-for-service-management-and-quality-complete-guide-image5.png "图示，说明质量和服务管理与全部三个组件的重叠的三个组件。具有终结点上焦点。")

Microsoft 团队终结点可以在多个设备，包括 Pc、 Mac、 平板电脑和移动设备上运行。 体验的一部分而不是只包括该设备，但用户如何连接到设备 — 例如，通过使用设备的内置的麦克风扬声器、 耳机或优化的耳麦。 使用优化的耳麦可以丰富的整体用户体验。

终结点规划以下指南将帮助您确保您的组织具有与团队体验成功入职培训。

### <a name="endpoint-capability"></a>终结点功能

规划的第一部分是确保所有 Pc 和您的组织中的其他设备可以运行 Microsoft 团队。 此步骤需要而不仅仅看硬件要求，但也了解 PC 在后台执行什么操作。 许多组织运行其他软件，包括入侵检测系统和反恶意软件，这可能会影响设备的基本的性能。

Microsoft 团队具有客户端适用于网站，桌面 （Windows 和 Mac） 和移动设备 （Android、 iOS 和 Windows Mobile）。 有关每个平台的软件要求的信息，请参阅[获取 Microsoft 团队的客户端](get-clients.md)。

### <a name="endpoint-firewalls"></a>终结点防火墙

客户端防火墙可以对用户体验产生重大影响。 客户端防火墙可能会影响除了阻止的建立呼叫的呼叫质量。 基于[Office 365 Url 和 IP 地址范围](https://aka.ms/o365ips)中的信息客户端防火墙上配置了适当的排除项。 您的第三方供应商将对如何创建排除的特定指南。

> [!NOTE]
> Microsoft 团队将具有适当的防火墙配置自动更新 Windows 防火墙。

### <a name="wi-fi-recommendations-for-endpoints"></a>终结点的 Wi-fi 建议

规划和部署优化的 Wi-fi 网络支持实时工作负荷中的 Microsoft 团队需要大量的规划。 以下各节提供了一些可帮助您规划终结点时应避免一些常见错误的一般指导。

#### <a name="wi-fi-drivers"></a>Wi-fi 驱动程序

某些 Wi-fi 驱动程序可能会有问题。 例如，驱动程序可能必须访问点，导致质量欠佳的呼叫质量之间积极漫游行为。 这不是常见的事物、 但务必确保已更新和部署之前测试 PC 上的 Wi-fi 驱动程序。

#### <a name="wi-fi-bands"></a>Wi-fi 带区

有两个主要类型的用于 Wi-fi 设备今天、 2.4 GHz 和 5.0 GHz 的分隔条。 如果您的组织提供了两个带区，应配置首选 5.0 GHz 带您驱动程序设置。 此带是得多方面吞吐量高密度和小于受干扰 2.4 GHz 带中所示。 此建议假定您已正确优化 5.0 GHz 网络带。

#### <a name="wi-fi-radio-type"></a>Wi-fi 单选类型

规划支持较新 Wi-fi 单选类型的设备。 如果您利用 802.11ac，您可以获取很好的 Wi-fi 性能或更高版本上设置的设备。

#### <a name="wireless-avoidance"></a>无线避免

某些组织希望完全避免 Wi-fi。 有时本指南建议通过提供给用户直接连接到有线网络。 在某些情况下，网络绑定顺序可能具有首选的无线连接，并且可以继续使用该连接，即使 PC 连接到有线连接。 若要避免此意外的行为，请配置绑定为了避免这种情况。

#### <a name="80211-power-save-protocol"></a>802.11 节能协议

如果您的组织使用的无线访问点或不支持的 802.11 强大功能的路由器保存协议，您可能会遇到丢弃的呼叫或质量欠佳的呼叫质量在 Windows 设备上运行的 Microsoft 团队中。 如果不能升级您的无线访问点或传送器，您应更新 Windows 电源计划运行电池供电的设备上的设置。 在下列[支持文章](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)提供了进一步的详细信息和配置指导。

### <a name="devices-for-teams"></a>团队的设备

为会议或作为电话系统，则可以使用 Microsoft 团队。 时使用这些功能，用于团队接口设备中的用户体验起着重要作用。

使用内置的 PC 扬声器和麦克风听起来到已配置的用户可接受。 通常，这些设备不适合干扰取消，但任何类型的环境的噪音上可能具有下游影响其他人在调用。 利用设备优化的这些方案将有助于确保高质量体验。

每个设备需要满足您的用户。 您需要定制的不同角色如耳机设备和您的组织中使用案例。 个人到设备映射练习应完成规划过程的一部分。

选择设备后，请将它们包括在最终验证试点测试计划。 利用调查在试验阶段，收集反馈，以确保您的设备策略是最佳。

此时，我们建议使用已通过 Skype 业务认证计划认证的音频设备。 要查找此计划认证的设备，请参阅[USB 设备认证可用于 for Business 的 Skype](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)解决方案目录。

有关详细信息，请参阅[客户端和设备-准备研讨会 （英文）](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13)

## <a name="client-updates"></a>客户端更新

一个 Microsoft 团队的主要优点是，客户端保持最新自动。 PC 和 Mac 客户端是通过使用背景过程，为新的生成检查并下载新客户端应用程序空闲时进行了更新。 客户端下载大小为大约 100 MB。

组织不具有任何控件或访问策略设置来管理更新过程。 若要减轻可能较新版本中发现的问题的风险，终结点上保留上次已知的良好版本。 如果没有新生成问题，Microsoft 团队服务可以自动恢复到以前的版本的终结点。

## <a name="next-steps-and-references"></a>下一步步骤和参考

此表包含指向相关内容链接的规划活动的摘要。

| 区域 | 详细信息 | 引用 |
|-----------------------------|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 规划服务管理 | 执行操作的角色映射练习 <br/> 从无论如何团队签署 <br/> 角色准备 | [操作指南](1-drive-value-operate-my-service.md) |
| | 提名质量 Champion(s) <br/> 质量推广人准备| [了解 CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) <br/> [质量体验审阅指南](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) |
| | 安装质量体验查看模板 <br/> 构建文件上载 | [QERLite 模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-lite-templates-v-2-1.zip?raw=true) <br/> [上载构建信息](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)|
| 规划网络质量 | 运行网络计划程序 | [网络计划程序](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) |
| | 实现 QoS | [在 Microsoft 团队中的服务质量](qos-in-teams.md) |
| | 绕过代理服务器 | [代理指南](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ad=US#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies) |
| | 实现拆分隧道 VPN | [VPN 拆分隧道指南](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9) |
| | 优化实时媒体 Wi-fi 网络  | 查阅第三方供应商 |
| | 实现本地 internet 出口 | [本地 Internet 出口](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) |
| | 实现网络连接 <br/> 验证网络连接 | [Office 365 Url 和 IP 地址](https://aka.ms/o365ips) |
| | | [网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885) |
| | 执行网络评估 | [网络准备情况评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_3_0_2,4_3_0_3,4_3_0_5,4_3_0_6,4_3_0_7,4_3_0_8,4_3_0_10,4_3_0_11) |
| 规划终结点质量 | 更新终结点防火墙 | [Office 365 Url 和 IP 地址](https://aka.ms/o365ips) |
| | 验证软件要求 | [获取 Microsoft Teams 的客户端](get-clients.md) |
| | 实现终结点 Wi-fi 建议 | 查阅第三方供应商 |
| | 进行个人到映射的设备 <br/> 设置设备和试用它们 | [客户端和设备-准备研讨会 （英文）](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_13) <br/> [设备目录](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) |

规划完后，继续执行下一步：[准备环境团队](https://aka.ms/SkypeToTeams-TechnicalReadiness)。