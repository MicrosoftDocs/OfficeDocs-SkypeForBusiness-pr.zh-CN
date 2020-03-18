---
title: 为 Microsoft 团队准备网络 | 端口防火墙要求
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: 使用此指导来准备网络以便进行 Teams 部署和推出
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d58613bc3455d5467e9e6c6589f73d498c6e1e3b
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706902"
---
# <a name="prepare-your-network-for-upgrading-to-teams"></a>准备要升级到团队的网络

![升级旅行图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级旅程的阶段，重点介绍技术准备阶段")

本文是您的升级过程的技术准备阶段的一部分，与用户准备阶段并行完成的活动。 在继续之前，请确认您已完成以前阶段中的这些活动：

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和团队的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [已选择升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> 观看以下会话，了解如何让团队利用你的网络以及如何实现最佳网络连接的最佳计划：[团队网络规划](https://aka.ms/teams-networking)

如果你要部署音频、视频或会议，你可以执行一些额外的步骤来为该功能优化你的网络。 团队使用音频和视频技术（编解码器），它可以在大多数网络条件下适应，从而性能更好。 为确保最佳性能，应为团队准备网络。

![描述三个质量组件的图表](media/evaluate-my-environment-image1.png "描述三种质量组件以及服务管理如何与所有三个组件重叠的图表。将焦点放在网络上。")

## <a name="why-should-you-prepare-your-network"></a>为什么要准备网络？

在查看要采取的步骤之前，请务必了解哪些内容会影响团队的性能，从而提高用户的幸福和满意度。 三个主要风险领域会影响用户对网络质量的理解：

- 可用带宽不足

- 防火墙和代理阻止程序

- 网络障碍，如抖动和数据包丢失

下面介绍的步骤将帮助你确定你的部署是否受这些因素的影响，并将帮助你转向解决方案。 无法准备网络可能会导致不满意的用户和非常昂贵的临时修补程序。 通过为团队准备网络和你的组织，你可以大大增加成功的可能性。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>带宽规划

无论您的网络状况如何，Microsoft 团队可为您提供最佳的音频、视频和内容共享体验。 通过可变编解码器，可以在有限的带宽环境中协商媒体，影响最小。 但是，带宽不是个问题，可以针对质量优化体验，包括最高分辨率的视频分辨率、最多30fps 视频和15fps 内容以及高保真音频。

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]

### <a name="local-internet-egress"></a>本地 Internet 出口

许多网络设计为使用中心和辐射型拓扑。 在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。 通常，这么做事为了集中网络安全设备，目的是降低总成本。

经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。 由于 Microsoft 团队在 Microsoft 的大型全球网络上运行，因此通常会向用户靠近网络对等位置。 用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。 对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。 在这种情况下，在使用本地出口点时，它与本地 DNS 解析相配对非常重要。

优化 Microsoft 全球网络的网络路径将提高性能，并最终为用户提供最佳体验。 有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。

若要使用 Microsoft 团队中的实时媒体获取最佳体验，必须满足 Office 365 的网络要求。 有关详细信息，请参阅[Skype for Business Online 的媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

定义网络段（客户端到 Microsoft Edge 和客户边缘到 Microsoft Edge）的两个网络段必须满足以下要求：

|**Value** |**客户端到 Microsoft Edge** |**客户边缘到 Microsoft Edge** |
|---|---|---|
|**延迟（一种方法）** |< 50 ms |< 30 ms |
|**延迟（往返行程时间或 RTT）** |< 100 ms |< 60 ms |
|**爆发数据包丢失** |在任何200毫秒的时间间隔内 <10% |在任何200毫秒的时间间隔内 <1% |
|**数据包丢失** |在任何15秒的时间间隔内 <1% |在任何15秒的时间间隔内 <0.1% |
|**数据包内部到达抖动** |在任何15秒的时间间隔内 <30 ms |在任何15秒的时间间隔内 <15 毫秒 |
|**数据包重新排序** |<0.05% 的订单外数据包 |<0.01% 的订单外数据包 |

若要测试这两个网络段，可以使用 "[网络评估" 工具](https://go.microsoft.com/fwlink/?linkid=855799)。 此工具可直接在客户端 PC 上和连接到客户网络边缘的 PC 上部署。 该工具包含有限的文档，但有关该工具用法的更深入的文档可在此处找到：[网络准备情况评估](https://go.microsoft.com/fwlink/?linkid=855800)。 通过运行此网络准备情况评估，你可以验证你的网络是否已准备好运行实时媒体应用程序，例如 Microsoft 团队。

> [!NOTE]
> 这是相同的网络准备情况评估，我们建议由希望成功部署 Skype for Business 的客户运行。

### <a name="vpn"></a>VPN

VPN 为许多组织提供很有用的服务。 很遗憾，它们通常不是为支持实时媒体而设计或配置的。 一些 VPN 可能还不支持 UDP。 Vpn 还会在已加密的媒体流量顶部引入额外的加密层。 此外，由于通过 VPN 设备有头发的流量，到团队服务的连接可能不会有效。 此外，它们不一定从容量角度进行设计，以适应团队需要的预期负载。

建议提供一个备用路径，以便 Teams 流量绕过 VPN。 这通常称为*拆分隧道 VPN*。 拆分隧道意味着 Office 365 的流量不会遍历 VPN，但会直接转到 Office 365。 此更改将对质量产生积极影响，但也会提供从 VPN 设备和组织网络减少负载的辅助优点。

要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。

### <a name="wi-fi"></a>Wi-Fi

与 VPN 类似，Wlan 网络不一定设计或配置为支持实时媒体。 在高质量部署中，为支持团队规划或优化 Wi-fi 网络是重要的考虑因素。

优化 Wlan 网络有以下几个因素：

- 实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。

- 规划和优化 Wi-fi 频带和接入点放置。 2.4 GHz 范围可能会提供足够的体验，具体取决于接入点的位置，但访问点通常受在该范围内运行的其他消费者设备的影响。 5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。

- 如果已部署了双频带 Wi-fi 网络，请考虑实施频带筹划。 _波段_控制是由 wi-fi 供应商实施的一项技术，可影响双层客户使用 5 GHz 范围。

- 当同一频道的接入点太靠近时，它们可能会导致信号重叠并无意间竞争，从而导致用户体验不良。 确保彼此相邻的接入点位于不重叠的频道上。

每个无线供应商都有自己的无线解决方案部署建议。 建议你咨询你的供应商了解具体指导。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火墙和代理要求

Microsoft 团队连接到 Microsoft Online 服务，并且需要 internet 连接才能实现此操作。 要使团队正常运行，必须从客户端打开 TCP 端口80和443，并从客户端到网络的 UDP 端口3478到3481。 TCP 端口用于连接到基于 web 的内容，如 SharePoint Online、Exchange Online 和团队聊天服务。 插件和连接器也通过这些 TCP 端口进行连接。 四个 UDP 端口用于音频和视频等媒体，以确保它们正常流动。

打开这些端口对于可靠的团队部署非常重要。 阻止这些端口不受支持，这些端口将影响媒体质量。

如果你的组织要求你指定应在其中打开这些端口的确切 IP 地址范围和域，则可以限制这些端口的目标 IP 范围和域。 有关确切的端口、协议和 IP 范围的列表，请参阅[Office 365 url 和 ip 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 如果你选择限制目标 IP 地址范围和域，则必须确保将端口和范围的列表保持为最新，因为它们可能会发生更改。 你可以订阅[此 RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)，以便在发生更改时进行更新。 这也是一种很好的做法，通过定期运行[Skype For Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试所有端口是否已打开。 可在下一节中了解有关此工具的功能的详细信息。

在正在部署的代理服务器事件中，我们建议您绕过所有团队服务的代理服务器。 虽然使用代理可能有效，但由于媒体被迫使用 TCP 而不是 UDP，因此很可能会降低质量。 有关代理服务器和绕过的详细信息，请参阅[Office 365 url 和 IP 地址范围](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>其他网络注意事项

### <a name="external-name-resolution"></a>外部名称解析

确保运行团队客户端的所有客户端计算机可以解析外部 DNS 查询以发现 Office 365 提供的服务。

### <a name="nat-pool-size"></a>NAT 池大小

当多个用户和设备通过使用网络地址转换（NAT）或端口地址转换（PAT）访问 Office 365 时，你需要确保隐藏在每个可访问的 IP 地址后面的设备不会超过支持的号码。

若要降低此风险，请确保为 NAT 池分配足够的公共 IP 地址以防止端口耗尽。 当连接到 Office 365 服务时，端口耗尽将导致内部最终用户和设备面临问题。 有关详细信息，请参阅[Office 365 的 NAT 支持](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365)。

### <a name="intrusion-detection-and-prevention-guidance"></a>入侵检测和阻止指南

如果你的环境有一个入侵检测系统和/或入侵防护系统为出站连接的额外安全层而部署，请确保将 Office 365 Url 作为其目标的任何流量均为白名单。

## <a name="test-the-network"></a>测试网络

完成规划和网络准备（包括升级带宽和打开防火墙中的端口）后，应测试网络的性能。 此测试的结果将使你更清楚地了解团队实施成功所需的任何网络优化或补救措施。

你可以下载[Skype For Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试你的网络是否已准备好进行团队。 此工具提供双重功能：它可以测试是否已打开所有正确的端口，并且它可以测试网络是否有障碍。

下载并安装该工具后，您可以在 C:\Program 文件（x86） \Microsoft Skype for Business 网络评估工具中找到它。 有关如何使用该工具的详细指南（如 .docx）包含在该目录中。

### <a name="test-for-opened-ports"></a>测试打开的端口

打开命令提示符窗口，然后导航到网络评估工具目录，方法是输入**cd C:\Program Files （x86） \Microsoft Skype For Business 网络评估工具**。 在命令提示符处，通过输入**networkassessmenttool/connectivitycheck**开始测试已打开的端口

运行检查后，该工具将显示消息 "验证已成功完成" 或报告已阻止的端口。 它还会生成一个名为 Connectivity_results .txt 的文件，其中包含该工具的输出，并将其存储在%\\userprofile\\%\\appdata 本地 microsoft skype for business 网络\\评估工具目录中。

我们建议你定期运行连接检查，以确保端口已打开并正常运行。

### <a name="test-for-network-impairments"></a>测试网络是否有障碍

为提高用户满意度，您应该限制网络的任何障碍。 最常见的网络障碍是延迟（延迟）、数据包丢失和抖动：

- **延迟：** 这是将 IP 数据包从点 A 转到网络上的点 B 所需的时间。 此网络传播延迟实质上与两个点之间的物理距离和光之间的距离保持联系，包括不同路由器所用的额外开销。 延迟是指单向或往返时间。

- **数据包丢失**：这通常定义为在给定时间段内丢失的数据包的百分比。 数据包丢失直接影响音频质量-从较小的单个丢失的数据包中，几乎不会影响对导致音频完全减少的后端到后突发损失的影响。

- **数据包间到达抖动或简单抖动：** 这是连续数据包之间的延迟的平均变化。 大多数现代 VoIP 软件（包括 Skype for Business）可以通过缓冲来适应某些级别的抖动。 仅当抖动超过的是参与者将注意到抖动效果的缓冲时才会如此。

在[媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中介绍了这些障碍的最大值。 测试这些障碍时，请区分两个不同的段：

- *边缘段*是你的路由器所在的段。 这是您的每个位置上连接到互联网的最接近的逻辑网络段。 在大多数情况下，这是路由器的连接点，或者是外围网络（也称为*DMZ*、*隔离区*和*屏蔽子网*）。 除了路由器之外的设备之外，任何其他通信量都不应出现在此网段和 internet 之间。

- *客户端段*是客户端所在的逻辑网络段。

你应该使用网络评估工具测试这两个段。 若要测试段，请导航到目录并在命令提示符处输入**networkassessmenttool** 。 结果将写入一个名为 tsv 的文件中，您可以将其与每个段的[要求](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)进行比较。

请注意，两个段必须满足高质量部署的要求。 我们建议你在一小时内多次运行该工具，以获得更好的网络性能指示。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>网络修正

如果带宽规划、端口测试或网络要求测试的结果显示您当前的网络需要补救措施才能部署团队，则可以通过以下几种方式实现此目的：

- 如果带宽不足，请升级连接，以便到 Office 365 的通信流 unhindered。

- 对于已阻止的端口，请更改防火墙规则并重新测试端口。

- 对于网络障碍，请始终执行根本原因分析。

服务质量（QoS）可用于对流量进行排序和分隔，从而使障碍更有障碍。 某些组织选择部署 QoS 来克服带宽问题或限制流量的流量。 这不会提高质量，并将导致新问题。 当网络障碍超过要求时，应始终执行根本原因分析。 QoS 可以是一个解决方案。 有关详细信息，请参阅[Microsoft 团队中的服务质量](qos-in-teams.md)。

>[!NOTE]
>许多网络会由于升级、扩展或其他业务要求而逐渐发展。 请确保在你的服务管理规划中具有可操作的流程以维护这些方面。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>决策点</td><td><ul><li>谁将负责在所有网段和组织位置完成正确的网络评估？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>你可以执行详细的网络评估，以帮助确保你的网络为你的 Microsoft 团队部署做好准备。 </li><li>基于每个网络段的网络准备情况评估的结果执行网络修正。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>关键优势

这是本指南的主要优点。 您必须：

- 打开从将使用团队的客户端传出的 TCP 端口80和443。

- 打开从将使用团队的客户端传出的 UDP 端口3478到3481。

- 确保您有足够的带宽来部署团队。

- 运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)，确保满足从边缘段和客户端段的[媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中所述的要求。

## <a name="related-topics"></a>相关主题

[视频：网络规划](https://aka.ms/teams-networking)
