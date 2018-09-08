---
title: 准备升级团队的 Microsoft 团队到您的网络
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 使用本指南团队部署和推出准备您的网络
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 465112aa154620f4cabf59aa1e6d4c70aa74eb16
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887802"
---
![升级旅程，重点强调的技术的准备阶段的阶段](media/upgrade-banner-tech-readiness.png "升级旅程，重点强调的技术的准备阶段的阶段")

本文是您升级旅程，与用户准备阶段并行完成的活动的技术的准备阶段的一部分。 在继续之前，确认您已完成从以前的阶段的这些活动：

-   [登记项目利益干系人](upgrade-enlist-stakeholders.md)
-   [定义您的项目范围](https://aka.ms/SkypetoTeams-Scope)
-   [商业和团队理解共存和 Skype 的互操作性](https://aka.ms/SkypeToTeams-Coexist)
-   [选择您升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>准备您的网络升级到团队

如果您正在部署音频、 视频或会议，可以执行一些额外的步骤，以优化您的网络的功能。 团队使用可以适应音频和视频技术 （编解码器） — 因此下更好地执行 — 最网络条件。 若要确保一致的最佳性能，应该为团队准备您的网络。

![描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有网络上焦点。](media/evaluate-my-environment-image1.png "描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有网络上焦点。")

## <a name="why-should-you-prepare-your-network"></a>为什么应准备您的网络？

我们查看要采取的步骤之前，请务必了解什么会影响性能的团队从而用户幸福和满意度。 三个主要风险区域可能会影响用户如何感知网络质量：

-   可用带宽不足

-   防火墙和代理窗口阻止程序

-   如抖动和丢包的网络障碍

如下所述的步骤将帮助您确定是否部署可能受以下因素之一，将帮助您移向分辨率。 出现故障的准备您的网络可能会导致用户不满和消耗大量资金，临时修复。 通过网络准备 — 和您的组织 — 团队，您可以显著增加成功的概率。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>带宽规划

网络准备的第一步确保您的网络有足够的工作组将向用户提供形式的带宽。 规划足够的带宽为相当简单任务和非常低障碍开始以帮助确保您的用户将具有高质量团队体验。

启动您规划旅程团队[我顾问网站](https://myadvisor.fasttrack.microsoft.com/)上使用网络计划工具的带宽。 网络计划工具提供规划团队的每个网站带宽，并提供有关优化网络性能建议。

> [!IMPORTANT]
> 如果所需的带宽不可用，媒体堆栈内部团队降低的质量的音频/视频会话以适应该低影响呼叫或会议的质量的可用带宽量。 团队客户端尝试优先于视频的质量的音频的质量。 因此，它是非常重要，具有预期的可用带宽。


|活动  |下载带宽  |上载带宽  |通信流 |
|---------|---------|---------|---------|
|**对等音频呼叫**     |0.1 Mbps         |0.1 Mbps        |客户端 <> 客户端         |
|**对等视频呼叫 （全屏）**     |4 Mbps         |4 Mbps         |客户端 <> 客户端          |
|**对等桌面共享 (1920年 & #215; 1080年解决方案)**     |4 Mbps         |4 Mbps         |客户端 <> 客户端          |
|**两个参与者的会议**     |4 Mbps         |4 Mbps         |客户端 <> Office 365         |
|**三个参与者的会议**     |8 Mbps         |6.5 Mbps         |客户端 <> Office 365           |
|**四个参与者的会议**     |5.5 Mbps         |4 Mbps         |客户端 <> Office 365           |
|**五个或更多 – 参与者会议**     |6 Mbps         |1.5 Mbps         |客户端 <> Office 365           |

### <a name="local-internet-egress"></a>本地 Internet 出口

许多网络设计为使用中心和辐射型拓扑。 在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。 通常，这么做事为了集中网络安全设备，目的是降低总成本。

经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。 由于 Microsoft Teams 在 Microsoft 的大型全局网络上运行，因此，用户附近通常会有网络对等位置。 用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。 对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。 在这种情况下，务必要在使用本地出口点时，将其与本地 DNS 解析配对。

优化指向 Microsoft 的全局网络的网络路径将会提高性能，并最终将为用户提供最佳体验。 有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。


若要获取使用中的 Microsoft 团队的实时媒体获得最佳体验，必须满足 Office 365 的网络要求。 有关详细信息，请参阅 [Skype for Business Online 中的媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

两个定义网络段（客户端到 Microsoft Edge 和客户边缘到 Microsoft Edge）必须满足以下要求：


|**值**  |**客户端到 Microsoft Edge**  |**客户边缘到 Microsoft Edge**  |
|---------|---------|---------|
|**延迟（单向）**     |< 50 ms          |< 30 ms          |
|**延迟 （往返时间或 RTT）** |< 100 毫秒         |< 60 毫秒         |
|**突发数据包丢失**    |< 任何 200 毫秒间隔期间的 10%         |< 任何 200 毫秒间隔期间 1%         |
|**数据包丢失**     |< 任何 15 秒间隔期间 1%          |< 任何 15 秒间隔期间 0.1%         |
|**数据包间到达抖动**    |< 任何 15 秒间隔期间 30 ms         |< 在任何 15 秒时间间隔 15 ms         |
|**数据包重新排序**    |< 0.05% 无序数据包         |< 0.01% 无序数据包         |

要测试两个网段，你可以使用[网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799)。 此工具可以直接部署在客户端 PC 上，也可以部署在连接到客户网络边缘的 PC 上。 此工具附带内容有限的文档，有关此工具用法的深度文档，请参阅此处：[网络就绪评估](https://go.microsoft.com/fwlink/?linkid=855800)。 通过进行此网络就绪评估，你可以验证你的网络是否为运行实时媒体应用（例如 Microsoft Teams）做好准备。

> [!NOTE]
> 这是相同的客户来说成功部署 for Business 的 Skype 由运行建议的网络准备情况评估。


### <a name="vpn"></a>VPN

VPN 为许多组织提供很有用的服务。 遗憾的是，他们正在通常不设计或配置为支持实时的媒体。 一些 VPN 可能还不支持 UDP。 Vpn 还引入了额外的已加密的媒体流量在加密。 此外，连接到团队服务可能不是有效由于字形驻留流量通过 VPN 设备。 此外，它们不一定被设计从容量角度以适应团队需要的预期的负载。

建议提供一个备用路径，以便 Teams 流量绕过 VPN。 这通常是称为*拆分隧道 VPN*。 拆分隧道 for Office 365 的流量不会遍历 VPN，但将直接转到 Office 365 的方法。 此改变不仅有利于提高质量，而且还带来额外的好处，即降低 VPN 设备和组织网络的负荷。

要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。

### <a name="wi-fi"></a>Wi-Fi

VPN，如 Wi-fi 网络不一定是设计或配置为支持实时的媒体。 规划，或优化，Wi-fi 网络支持团队是高质量部署的重要注意事项。

有派上用场优化 Wi-fi 网络的几个因素：

-   实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。

-   规划和优化 Wi-fi 区段和访问点位置。 2.4 GHz 区域可能提供足够具体取决于接入点放置体验，但该范围内运行其他使用者设备通常会影响访问点。 5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。

-   如果部署双带 Wi-fi 网络，请考虑实现带控制。 _带控制_是由 Wi-fi 供应商以影响双带客户端使用 5 GHz 区域实现的技术。

-   访问点的同一通道太近时他们可以导致信号重叠并意外竞争，导致用户的体验不佳。 确保彼此相邻的访问点位于不相互重叠的通道。

每个无线供应商都有自己的无线解决方案部署建议。 建议你咨询你的供应商了解具体指导。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火墙和代理要求

Microsoft 团队连接到 Microsoft Online Services，并为此需要 internet 连接。 对于团队能够正常工作，您必须打开 TCP 端口 80 和 443 从客户端到 internet，以及 UDP 端口 3478 通过 3481 从客户端到 internet。 TCP 端口用于连接到基于 web 的内容，如 SharePoint Online、 Exchange Online 和团队聊天服务。 通过这些 TCP 端口还连接插件和连接器。 四个 UDP 端口用于音频和视频，如媒体以确保它们正常流。

打开这些端口对于可靠的团队部署至关重要。 阻止以下端口不受支持，并将影响媒体质量。

如果组织要求您指定的确切的 IP 地址范围和这些端口应打开到的域，您可以限制的目标 IP 范围和这些端口的域。 有关确切的端口的列表，协议和 IP 地址范围，请参阅[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 如果您选择限制的目标 IP 地址范围和域，则必须确保您保存的端口和范围列表最新因为它们可能会更改。 您可以订阅发生更改时要更新的[此 RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)。 也很好的做法测试是否由定期运行[的业务网络评估工具的 Skype](https://www.microsoft.com/download/details.aspx?id=53885)打开所有端口。 您可以在下一步部分找出有关此工具的功能的详细信息。

发生正在部署的代理服务器，我们建议您绕过所有团队服务的代理服务器。 虽然使用代理可能起作用，就非常可能质量将由于媒体的强制使用 TCP 而 UDP 不会降低。 有关代理服务器和绕过的详细信息，请参阅[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>其他网络考虑事项
### <a name="external-name-resolution"></a>外部名称解析

确保运行团队客户端的所有客户端计算机可以解析发现 Office 365 提供的服务的外部 DNS 查询。

### <a name="nat-pool-size"></a>NAT 池大小

当多个用户和设备访问 Office 365 使用网络地址转换 (NAT) 或端口地址转换 (PAT)，您需要确保隐藏在每个公共可路由的 IP 地址的设备不超过支持的数目。

若要减轻此风险，请确保足够公共 IP 地址将分配给 NAT 池以防止端口耗尽。 端口耗尽会导致内部最终用户和设备在连接到 Office 365 服务时遇到问题。 有关详细信息，请参阅 [Office 365 的 NAT 支持](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365)。

### <a name="intrusion-detection-and-prevention-guidance"></a>入侵检测和防护指南

如果您的环境包含的入侵检测系统和/或部署额外的安全的出站连接的入侵防御系统，确保具有 Office 365 Url 作为其目标是白名单任何通信。

## <a name="test-the-network"></a>测试网络

在您完成规划和网络准备后 — 包括升级带宽和防火墙中打开的端口 — 您应测试您的网络性能。 此测试将结果绘制清楚地的任何网络优化或团队实现成功所需的补救。

您可以下载[Skype 业务网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试您的网络是否准备好让团队。 在工具提供双功能： 它可以测试是否对已打开了正确的端口，它可以测试网络障碍。

下载并安装该工具之后，您可以找到它中 c:\\Program Files\\Microsoft Skype 业务网络评估工具。 有关如何使用 Usage.docx，工具的详细的指南包含该目录中。

### <a name="test-for-opened-ports"></a>打开的端口的测试

打开命令提示符窗口并导航到网络评估工具目录通过输入**cd c:\\Program Files\\业务网络评估工具的 Microsoft Skype**。 在命令提示符处，通过输入**networkassessmenttool.exe /connectivitycheck**开始打开端口测试

运行检查之后, 工具将显示消息"验证已成功完成"，或在已阻止的端口报告。 它还会生成一个名为 Connectivity_results.txt，其中包含从工具输出，并将其存储在 %userprofile%文件\\应用程序数据\\本地\\业务网络评估工具的 microsoft Skype\\目录。

我们建议您运行的连接检查定期以确保已打开的端口和都运行正常。

### <a name="test-for-network-impairments"></a>测试网络障碍

以提高用户满意度，您应在您的网络限制任何障碍。 最常见的网络障碍是延迟 （等待时间）、 数据包丢失和抖动：

-   **延迟：** 这是获得 IP 数据包到网络上的点 B 点 A 所花费的时间。 实际上，此网络传播延迟被限制到物理距离的两个点和轻量，包括之间执行各种路由器的额外开销的速度。 延迟被按单向或往返时间。

-   **数据包丢失**： 通常指在给定的时间窗口中丢失数据包的百分比。 数据包丢失直接影响音频质量 — 从小，个人丢失数据包无背对背脉冲损失几乎没有任何影响原因音频，完全去掉。

-   **间数据包到达抖动或只需抖动：** 这是连续的数据包之间的延迟的平均更改。 最先进的 VoIP 软件，包括 Skype for Business，可以适应通过缓冲抖动某些级别。 则只有当抖动超过缓冲参与者会注意到的抖动效果。

[媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)介绍这些障碍的最大值。 测试这些障碍，我们区分两个独立段：

-   *边缘段*是路由器驻留在其中的线段。 这是连接到 internet 上每个位置的最接近逻辑网络段。 在大多数情况下，这是路由器或可能是外围网络 （也称为*DMZ*、*非军事区*和*屏蔽子网*） 的连接点。 影响设备路由器之外没有进一步通信应发生这一段和 internet 之间。

-   *客户端段*是客户端驻留在其中的逻辑网络段。

使用网络评估工具，您应测试两条线段。 若要测试段，定位到的目录，并输入**networkassessmenttool.exe**在命令提示符。 结果将写入名为 Results.tsv 的文件，并可以与每段的[要求](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

请注意，两条线段必须满足高质量部署的要求。 我们建议您运行该工具为一小时多次直接要获取清楚地表明您的网络性能。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>网络修正

如果带宽规划、 测试端口，或网络要求测试的结果显示您的当前网络需要修复，部署团队之前，可以多种方式来实现这一点： 

-   没有足够带宽，升级连接，以便可以流动到 Office 365 的流量而没有影响。

-   阻止端口更改防火墙规则和该包端口。

-   对于网络障碍，始终执行根源分析。

服务质量 (QoS) 可以用于通过确定优先级和分隔流量来与障碍。 某些组织选择部署 QoS 解决带宽问题或限制流的流量的数量。 这不会提高质量，并且将导致新的问题。 网络受损超过要求时，应始终执行根源分析。 QoS 可以是一个解决方案。 有关详细信息，请参阅[Microsoft 团队中的服务质量](qos-in-teams.md)。

>[!NOTE]
>许多网络会由于升级、扩展或其他业务要求而逐渐发展。 请确保在你的服务管理规划中具有可操作的流程以维护这些方面。


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>谁将负责在所有网络领域和组织位置完成正确的网络评估？</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>您可以执行的详细的网络评估，以帮助确保您的网络可供您的 Microsoft 团队的部署。 有关详细信息，请参阅[网络准备情况评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)。</li><li>执行网络修正基于每个网络段网络准备情况评估结果。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>要点

这些是从本指南的主要优点。 您必须：

-   打开 TCP 端口 80 和 443 传出来自客户端将使用团队。

-   打开 UDP 端口 3478 通过 3481 传出来自客户端将使用团队。

-   确保您有足够的带宽，通过完成[网络规划人员](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)部署团队。

-   运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)，并确保您满足从边缘段和客户端段[媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中所述的要求。
