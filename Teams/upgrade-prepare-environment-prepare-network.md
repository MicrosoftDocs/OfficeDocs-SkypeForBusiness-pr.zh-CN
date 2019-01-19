---
title: 准备您的网络的 Microsoft 团队 | 端口防火墙要求
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 使用此指导来准备网络以便进行 Teams 部署和推出
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3eb4317954e619f58236c96a2cee035f2df75e0
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349510"
---
![升级过程的各个阶段，重点在技术就绪阶段](media/upgrade-banner-tech-readiness.png "升级过程的各个阶段，重点在技术就绪阶段")

本文属于升级过程的技术就绪阶段，此阶段的活动与用户就绪阶段并行完成。 在继续操作之前，请确认你已完成前面各阶段的活动。

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和 Teams 的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [已选择升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>准备网络以便升级到 Teams

如果你要部署音频、视频或会议，可以采取一些额外的步骤来针对相应功能优化你的网络。 Teams 使用音频和视频技术（编解码器），该技术可以适应大多数网络条件，并且在这些条件下效果有所提高。 为了确保获得最优的一致性能，应为 Teams 准备你的网络。

![此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。焦点在网络上。](media/evaluate-my-environment-image1.png "此示意图说明了质量的三个组成部分以及服务管理如何贯穿于这三个组成部分。焦点在网络上。")

## <a name="why-should-you-prepare-your-network"></a>为什么应该准备网络？

在讨论要采取的步骤之前，务必要了解会影响 Teams 性能从而影响用户高兴度和满意度的因素。 以下三个主要风险方面会影响用户对网络质量的感受：

- 可用带宽不足

- 防火墙和代理阻止程序

- 网络损伤，例如抖动和数据包丢失

下面所述步骤将帮助你确定你的部署是否可能受其中任何因素的影响，以及帮助你找到解决方案。 如果无法准备网络，很可能会导致用户不满意以及代价高昂的临时修复。 通过为 Teams 准备你的网络以及让贵组织做好相应准备，你可以动态提高成功率。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>带宽规划

网络就绪的第一步是确保你的网络具有足够的带宽可用于 Teams 将为用户提供的各种功能形式。 规划足够的带宽非常简单，通过此方式来帮助确保你的用户拥有高质量的 Teams 体验的起点很低。

你可以使用 [MyAdvisor 网站上](https://myadvisor.fasttrack.microsoft.com/)的 Network Planner 开始为 Teams 规划带宽。 Network Planner 提供针对 Teams 的每个站点带宽规划，并提供网络性能优化建议。

> [!IMPORTANT]
> 如果未提供所需的带宽，Teams 中的媒体堆栈将降低音频/视频会话的质量以适应较低的可用带宽，因而会影响通话或会议的质量。 Teams 客户端在处理音频质量和视频质量时将尝试优先考虑音频质量。 因此，提供所需带宽非常重要。

|活动 |下载带宽 |上载带宽 |通信流 |
|---|---|---|---|
|**对等音频呼叫** |0.1 Mbps |0.1 Mbps |客户端 <> 客户端 |
|**对等视频呼叫（全屏）** |4 Mbps |4 Mbps |客户端 <> 客户端 |
|**对等桌面共享（1920&#215;1080 分辨率）** |4 Mbps |4 Mbps |客户端 <> 客户端 |
|**两方会议** |4 Mbps |4 Mbps |客户端 <> Office 365 |
|**三方会议** |8 Mbps |6.5 Mbps |客户端 <> Office 365 |
|**四方会议** |5.5 Mbps |4 Mbps |客户端 <> Office 365 |
|**五方或更多方会议** |6 Mbps |1.5 Mbps |客户端 <> Office 365 |

### <a name="local-internet-egress"></a>本地 Internet 出口

许多网络设计为使用中心和辐射型拓扑。 在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。 通常，这么做事为了集中网络安全设备，目的是降低总成本。

经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。 由于 Microsoft Teams 在 Microsoft 的大型全局网络上运行，因此，用户附近通常会有网络对等位置。 用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。 对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。 在这种情况下，务必要在使用本地出口点时，将其与本地 DNS 解析配对。

优化指向 Microsoft 的全局网络的网络路径将会提高性能，并最终将为用户提供最佳体验。 有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。

为了在 Microsoft Teams 中获得实时媒体方面的最佳体验，必须满足 Office 365 的网络连接要求。 有关详细信息，请参阅 [Skype for Business Online 的媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

两个定义网络段（客户端到 Microsoft Edge 和客户边缘到 Microsoft Edge）必须满足以下要求：

|**值** |**客户端到 Microsoft Edge** |**客户边缘到 Microsoft Edge** |
|---|---|---|
|**延迟（单向）** |< 50 ms |< 30 ms |
|**延迟（往返时间或 RTT）** |< 100 ms |< 60 ms |
|**突发数据包丢失** |< 10%，在任何 200 ms 时间间隔内 |< 1%，在任何 200 ms 时间间隔内 |
|**数据包丢失** |< 1%，在任何 15 s 时间间隔内 |< 0.1%，在任何 15 s 时间间隔内 |
|**数据包中间间隔抖动** |< 30 ms，在任何 15 s 时间间隔内 |< 15 ms，在任何 15 s 时间间隔内 |
|**数据包重新排序** |< 0.05% 无序数据包 |< 0.01% 无序数据包 |

要测试两个网段，你可以使用[网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799)。 此工具可以直接部署在客户端 PC 上，也可以部署在连接到客户网络边缘的 PC 上。 此工具附带内容有限的文档，有关此工具用法的深度文档，请参阅此处：[网络就绪评估](https://go.microsoft.com/fwlink/?linkid=855800)。 通过进行此网络就绪评估，你可以验证你的网络是否为运行实时媒体应用（例如 Microsoft Teams）做好准备。

> [!NOTE]
> 对于希望成功部署 Skype for Business 的客户，同样建议进行此网络就绪评估。

### <a name="vpn"></a>VPN

VPN 为许多组织提供很有用的服务。 遗憾的是，它们通常未设计或配置为支持实时媒体。 一些 VPN 可能还不支持 UDP。 VPN 还会在已加密的媒体流量之上引入额外一层加密。 此外，由于通过 VPN 设备的发夹流量，与 Teams 服务的连接可能无效。 而且，从容量角度来看，它们不一定设计为容纳 Teams 所需的预计负荷。

建议提供一个备用路径，以便 Teams 流量绕过 VPN。 这就是通常所谓的*拆分通道 VPN*。 拆分通道意味着流向 Office 365 的流量不穿过 VPN，而是直接传输到 Office 365。 此改变不仅有利于提高质量，而且还带来额外的好处，即降低 VPN 设备和组织网络的负荷。

要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。

### <a name="wi-fi"></a>Wi-Fi

与 VPN 一样，Wi-Fi 网络不一定设计或配置为支持实时媒体。 规划和/或优化 Wi-Fi 网络以支持 Teams 是实现高质量部署的一个重要考虑事项。

可从几个因素来优化 Wi-Fi 网络：

- 实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。

- 规划和优化 Wi-Fi 频带和接入点位置。 2.4 GHz 范围可以根据接入点位置提供合乎需要的体验，但接入点通常受该范围内运行的使用者其他设备的影响。 5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。

- 如果部署了双频 Wi-Fi 网络，请考虑实施频带切换。 _频带切换_技术由 Wi-Fi 供应商实施，以促使双频客户端使用 5 GHz 范围。

- 同一频道的多个接入点太靠近时，它们可能会导致信号重叠并无意地竞争，从而导致用户体验很差。 请确保频道上相邻的接入点不会重叠。

每个无线供应商都有自己的无线解决方案部署建议。 建议你咨询你的供应商了解具体指导。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火墙和代理要求

Microsoft Teams 会连接到 Microsoft Online Services，因此需要 Internet 连接来实现。 为了 Teams 正常运行，必须打开客户端上用于连接 Internet 的 TCP 端口 80 和 443 以及 UDP 端口 3478 到 3481。 TCP 端口用于连接到基于 Web 的内容，例如 SharePoint Online、Exchange Online 和 Teams 聊天服务。 插件和连接器也通过这些 TCP 端口进行连接。 四个 UDP 端口用于音频和视频等媒体以确保其正确传输。

为了实现可靠的 Teams 部署，必须打开这些端口。 不可阻止这些端口，否则会影响媒体质量。

如果贵组织要求你指定应打开这些端口的确切 IP 地址范围和域，你可以限制这些端口的目标 IP 范围和域。 有关确切的端口、协议和 IP 范围列表，请参阅 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 如果你选择限制目标 IP 范围和域，则必须确保使端口和范围列表保持最新，因为它们可能会发生变化。 你可以订阅[此 RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)以在发生变化时收到更新。 此外，通过定期运行 [Skype for Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试是否已打开所有端口也是一个很好的方法。 下一节提供了有关此工具的功能的详细信息。

如果要部署代理服务器，建议对所有 Teams 服务不使用代理服务器。 尽管使用代理可能有用，但媒体被强制使用 TCP 而不是 UDP，因此，质量很可能会降低。 有关代理服务器和不使用代理服务器的详细信息，请参阅 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>其他网络考虑事项

### <a name="external-name-resolution"></a>外部名称解析

确保运行 Teams 客户端的所有客户端计算机都可以解析外部 DNS 查询以发现 Office 365 提供的服务。

### <a name="nat-pool-size"></a>NAT 池大小

多个用户/设备使用网络地址转换 (NAT) 或端口地址转换 (PAT) 访问 Office 365 时，你需要确保每个公开可路由 IP 地址后面隐藏的设备不超过支持的数量。

为了缓解此风险，请确保为 NAT 池分配足够的公用 IP 地址以防止端口耗尽。 端口耗尽会导致内部最终用户和设备在连接到 Office 365 服务时遇到问题。 有关详细信息，请参阅 [Office 365 的 NAT 支持](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365)。

### <a name="intrusion-detection-and-prevention-guidance"></a>入侵检测和防护指导

如果你的环境部署了入侵检测系统和/或入侵防护系统，从而为出站连接附加了一层安全性，请确保目标为 Office 365 URL 的任何流量都列入白名单。

## <a name="test-the-network"></a>测试网络

在完成规划和网络准备（包括升级带宽和在防火墙中打开端口）后，你应测试你的网络的性能。 此测试的结果将更加清晰地提供有关成功实施 Teams 所需的任何网络优化或补救的信息。

你可以下载 [Skype for Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试你的网络是否已为 Teams 做好准备。 该工具具有两种功能：可以测试是否已打开所有正确端口，测试网络损伤情况。

下载并安装该工具后，可以在 C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool 中找到。 该目录中包含有关该工具使用方法的详细指南 Usage.docx。

### <a name="test-for-opened-ports"></a>测试打开的端口

打开命令提示窗口，然后输入 **cd C:\\Program Files\\Microsoft Skype for Business Network Assessment Tool** 以导航到 Network Assessment Tool 目录。 在命令提示符中，输入 **networkassessmenttool.exe /connectivitycheck** 以开始测试打开的端口。

运行检查后，该工具将显示消息“Verifications Completed Successfully”，或报告被阻止的端口。 此外，还会生成包含该工具输出的文件 Connectivity_results.txt，并将其存储在 %userprofile%\\appdata\\local\\microsoft skype for business network assessment tool\\ 目录中。

建议定期运行连接检查以确保端口已打开且正常工作。

### <a name="test-for-network-impairments"></a>测试网络损伤

为了提供用户满意度，应尽量减少你网络上的任何损伤。 最常见的网络损伤时延迟、数据包丢失和抖动：

- **延迟**：这是 IP 数据包从网络上的 A 点传输到 B 点所用时间。 此网络传播延迟实际上与两点之间的物理距离和光速（包括中间各种路由器承担的额外开销）相关。 延迟以单向或往返时间度量。

- **数据包丢失**：通常定义为在给定时间范围内丢失的数据包百分比。 数据包丢失直接影响音频质量 - 从几乎没有影响的丢失的小型单个数据包到导致音频完全切断的接连式突发丢失。

- **数据包中间间隔抖动或简单抖动**：这是连续数据包之间的延迟平均变化量。 大多数新式 VoIP 软件（包括 Skype for Business）可以通过缓冲适应某些程度的抖动。 仅当抖动超过缓冲量时，参与者才会注意到抖动效果。

[媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中介绍了这些损伤的最大值。 测试这些损伤时，我们会区分两种单独的段：

- *边缘段*是路由器所在的段。 这是你的每个地点与 Internet 连接的最近逻辑网络段。 大多数情况下，这是路由器的连接点，也可能是外围网络（也称为 *DMZ*、*隔离区域*和*外围子网*）。 此段与 Internet 之间应没有影响路由器以外的设备的其他流量。

- *客户端段*是客户端所在的逻辑网络段。

应使用网络评估工具测试这两种段。 要测试段，请导航到相应目录，然后在命令提示符中输入 **networkassessmenttool.exe**。 结果将写入名为 Results.tsv 的文件，你可以针对每个段将其与 [要求](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)进行比较。

请注意，两种段都必须满足高质量部署的要求。 建议在一小时内连续多次运行该工具，以便清楚了解网络性能。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>网络补救

如果带宽规划、端口测试或网络要求测试的结果表明你的当前网络需要先补救才能部署 Teams，你可以通过以下几种方式来完成：

- 如果带宽不足，请升级连接，以便与 Office 365 的流量可以顺利传输。

- 如果端口被阻止，请更改防火墙规则并重新测试端口。

- 如果存在网络损伤，请始终进行根本原因分析。

可以使用服务质量 (QoS) 通过划分流量优先级与分隔流量来尽量消除损伤。 有些组织选择部署 QoS 来克服带宽问题或限制流量传输量。 这不会提高质量，并会带来新的问题。 当网络损伤超过要求时，应始终进行根本原因分析。 可以采用 QoS 进行解决。 有关详细信息，请参阅 [Microsoft Teams 中的服务质量](qos-in-teams.md)。

>[!NOTE]
>许多网络会由于升级、扩展或其他业务要求而逐渐发展。 请确保在你的服务管理规划中具有可操作的流程以维护这些方面。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>决策点</td><td><ul><li>由谁负责完成所有网络段和组织地点的正确网络评估？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>后续步骤</td><td><ul><li>你可以执行详细的网络评估来帮助确保你的网络为 Microsoft Teams 部署做好准备。 有关详细信息，请参阅<a href="https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness" data-raw-source="[Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)">网络就绪评估</a>。</li><li>根据针对每个网络段的网络就绪评估结果进行网络补救。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>关键结论

下面是本指导的主要结论。 你必须：

- 打开将使用 Teams 的客户端上用于传出连接的 TCP 端口 80 和 443。

- 打开将使用 Teams 的客户端上用于传出连接的 UDP 端口 3478 到 3481。

- 通过完成 [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner).来确保你有足够的带宽用于部署 Teams。

- 从边缘段和客户段运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)并确保满足[媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中所述的要求。
