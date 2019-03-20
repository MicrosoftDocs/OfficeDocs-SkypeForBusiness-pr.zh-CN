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
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7e6e46ca534a821d4697714448bcc5e4e20888f
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "30684061"
---
![升级过程的各个阶段，重点在技术就绪阶段](media/upgrade-banner-tech-readiness.png "升级过程的各个阶段，重点在技术就绪阶段")

本文属于升级过程的技术就绪阶段，此阶段的活动与用户就绪阶段并行完成。 在继续操作之前，请确认你已完成前面各阶段的活动。

- [已登记项目利益干系人](upgrade-enlist-stakeholders.md)
- [已定义项目范围](https://aka.ms/SkypetoTeams-Scope)
- [了解 Skype for Business 和 Teams 的共存和互操作性](https://aka.ms/SkypeToTeams-Coexist)
- [已选择升级过程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

> [!Tip]
> 观看下面的会话，若要了解如何团队利用您的网络和如何最好地规划最佳的网络连接：[团队网络规划](https://aka.ms/teams-networking)

# <a name="prepare-your-network-for-upgrading-to-teams"></a>准备您的网络升级到团队

如果您正在部署音频、 视频或会议，可以执行一些额外的步骤，以优化您的网络的功能。 团队使用可以适应音频和视频技术 （编解码器） — 因此下更好地执行 — 最网络条件。 若要确保一致的最佳性能，应该为团队准备您的网络。

![描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有网络上焦点。](media/evaluate-my-environment-image1.png "描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有网络上焦点。")

## <a name="why-should-you-prepare-your-network"></a>为什么应准备您的网络？

我们查看要采取的步骤之前，请务必了解什么会影响性能的团队从而用户幸福和满意度。 三个主要风险区域可能会影响用户如何感知网络质量：

- 可用带宽不足

- 防火墙和代理窗口阻止程序

- 如抖动和丢包的网络障碍

如下所述的步骤将帮助您确定是否部署可能受以下因素之一，将帮助您移向分辨率。 出现故障的准备您的网络可能会导致用户不满和消耗大量资金，临时修复。 通过网络准备 — 和您的组织 — 团队，您可以显著增加成功的概率。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>带宽规划

Microsoft 团队为您提供最佳音频、 视频和共享体验，而不管您的网络状况的内容。 使用变量编解码器，可以具有的影响最小带宽有限的环境中协商媒体。 但是，其中带宽不是关键因素，可以为质量，包括 1080p 视频分辨率，最多 30 fps 的视频和内容和高保真音频优化体验。

本文介绍团队实时音频、 视频和桌面共享形式在各种使用情况下如何使用带宽的准确地描述版本。 团队始终对带宽使用率保守且可以提供 HD 视频质量以在 1.2 mb 为单位。 每个音频/视频呼叫或会议中的实际带宽使用将有所不同，根据多种因素，例如视频布局、 视频分辨率和视频帧速率。更多的带宽有质量和使用情况将会增加为了提供最佳体验。

|Bandwidth(up/down) |方案 |
|---|---|
|30 kbps |对等音频呼叫 |
|130 kbps |对等音频呼叫和屏幕共享 |
|500 kbps |对等质量视频 30 fps 时调用 360 p |
|1.2 Mbps |调用不带 HD 720 p 30 fps 时的解决方案的对等 HD 质量视频 |
|1.5 Mbps |调用不带分辨率为高清 1080p 以 30 fps 的对等 HD 质量视频 |
|500 kbps/1Mbps |组视频呼叫 |
|为 2Mbps 1Mps / |HD 组视频呼叫 （1080p 屏幕上的 540 p 视频） |

### <a name="local-internet-egress"></a>本地 Internet 出口

许多网络设计为使用中心和辐射型拓扑。 在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。 通常，这么做事为了集中网络安全设备，目的是降低总成本。

经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。 由于 Microsoft Teams 在 Microsoft 的大型全局网络上运行，因此，用户附近通常会有网络对等位置。 用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。 对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。 在这种情况下，务必要在使用本地出口点时，将其与本地 DNS 解析配对。

优化指向 Microsoft 的全局网络的网络路径将会提高性能，并最终将为用户提供最佳体验。 有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。

若要获取使用中的 Microsoft 团队的实时媒体获得最佳体验，必须满足 Office 365 的网络要求。 有关详细信息，请参阅[媒体质量和业务 online Skype 的网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

两个定义网络段 （客户端到 Microsoft 边缘） 和客户边缘到 Microsoft 边缘必须满足以下要求：

|**值** |**客户端到 Microsoft 边缘** |**客户边缘到 Microsoft 边缘** |
|---|---|---|
|**延迟 （一种方法）** |< 50 ms |< 30 ms |
|**延迟 （往返时间或 RTT）** |< 100 毫秒 |< 60 毫秒 |
|**突发数据包丢失** |任何 200 毫秒间隔期间 <10% |任何 200 毫秒间隔期间 <1% |
|**数据包丢失** |任何 15 秒间隔期间 <1% |任何 15 秒间隔期间 <0.1% |
|**数据包间到达抖动** |任何 15 秒间隔期间 <30 ms |任何 15 秒间隔期间 <15 ms |
|**数据包重新排序** |<0.05%序的数据包 |<0.01%序的数据包 |

若要测试两个网络段，您可以使用[网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799)。 此工具可以部署这两个客户端上 PC 直接并连接到客户网络边缘 PC 上。 该工具包含有限的文档，但围绕使用率的工具更深入地介绍文档可在此处找到：[网络准备情况评估](https://go.microsoft.com/fwlink/?linkid=855800)。 通过运行此网络准备情况评估，您可以验证您的网络准备运行实时的媒体的应用程序，如 Microsoft 团队。

> [!NOTE]
> 这是相同的客户来说成功部署 for Business 的 Skype 由运行建议的网络准备情况评估。

### <a name="vpn"></a>VPN

VPN 为许多组织提供很有用的服务。 遗憾的是，他们正在通常不设计或配置为支持实时的媒体。 一些 VPN 可能还不支持 UDP。 Vpn 还引入了额外的已加密的媒体流量在加密。 此外，连接到团队服务可能不是有效由于字形驻留流量通过 VPN 设备。 此外，它们不一定被设计从容量角度以适应团队需要的预期的负载。

建议提供一个备用路径，以便 Teams 流量绕过 VPN。 这通常是称为*拆分隧道 VPN*。 拆分隧道 for Office 365 的流量不会遍历 VPN，但将直接转到 Office 365 的方法。 此改变不仅有利于提高质量，而且还带来额外的好处，即降低 VPN 设备和组织网络的负荷。

要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。

### <a name="wi-fi"></a>Wi-Fi

VPN，如 Wi-fi 网络不一定是设计或配置为支持实时的媒体。 规划，或优化，Wi-fi 网络支持团队是高质量部署的重要注意事项。

有派上用场优化 Wi-fi 网络的几个因素：

- 实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。

- 规划和优化 Wi-fi 区段和访问点位置。 2.4 GHz 区域可能提供足够具体取决于接入点放置体验，但该范围内运行其他使用者设备通常会影响访问点。 5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。

- 如果部署双带 Wi-fi 网络，请考虑实现带控制。 _带控制_是由 Wi-fi 供应商以影响双带客户端使用 5 GHz 区域实现的技术。

- 访问点的同一通道太近时他们可以导致信号重叠并意外竞争，导致用户的体验不佳。 确保彼此相邻的访问点位于不相互重叠的通道。

每个无线供应商都有自己的无线解决方案部署建议。 建议你咨询你的供应商了解具体指导。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火墙和代理要求

Microsoft 团队连接到 Microsoft Online Services，并为此需要 internet 连接。 对于团队能够正常工作，您必须打开 TCP 端口 80 和 443 从客户端到 internet，以及 UDP 端口 3478 通过 3481 从客户端到 internet。 TCP 端口用于连接到基于 web 的内容，如 SharePoint Online、 Exchange Online 和团队聊天服务。 通过这些 TCP 端口还连接插件和连接器。 四个 UDP 端口用于音频和视频，如媒体以确保它们正常流。

打开这些端口对于可靠的团队部署至关重要。 阻止以下端口不受支持，并将影响媒体质量。

如果组织要求您指定的确切的 IP 地址范围和这些端口应打开到的域，您可以限制的目标 IP 范围和这些端口的域。 有关确切的端口的列表，协议和 IP 地址范围，请参阅[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 如果您选择限制的目标 IP 地址范围和域，则必须确保您保存的端口和范围列表最新因为它们可能会更改。 您可以订阅发生更改时要更新的[此 RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)。 也很好的做法测试是否由定期运行[的业务网络评估工具的 Skype](https://www.microsoft.com/download/details.aspx?id=53885)打开所有端口。 您可以在下一步部分找出有关此工具的功能的详细信息。

发生正在部署的代理服务器，我们建议您绕过所有团队服务的代理服务器。 虽然使用代理可能起作用，就非常可能质量将由于媒体的强制使用 TCP 而 UDP 不会降低。 有关代理服务器和绕过的详细信息，请参阅[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。

<!--ENDOFSECTION-->

## <a name="additional-network-considerations"></a>其他网络注意事项

### <a name="external-name-resolution"></a>外部名称解析

确保运行团队客户端的所有客户端计算机可以解析发现 Office 365 提供的服务的外部 DNS 查询。

### <a name="nat-pool-size"></a>NAT 池大小

当多个用户和设备访问 Office 365 使用网络地址转换 (NAT) 或端口地址转换 (PAT)，您需要确保隐藏在每个公共可路由的 IP 地址的设备不超过支持的数目。

若要减轻此风险，请确保足够公共 IP 地址将分配给 NAT 池以防止端口耗尽。 端口耗尽会导致内部最终用户和设备连接到 Office 365 服务时面临的问题。 有关详细信息，请参阅[Office 365 的 NAT 支持](https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365)。

### <a name="intrusion-detection-and-prevention-guidance"></a>入侵检测和防护指南

如果您的环境包含的入侵检测系统和/或部署额外的安全的出站连接的入侵防御系统，确保具有 Office 365 Url 作为其目标是白名单任何通信。

## <a name="test-the-network"></a>测试网络

在您完成规划和网络准备后 — 包括升级带宽和防火墙中打开的端口 — 您应测试您的网络性能。 此测试将结果绘制清楚地的任何网络优化或团队实现成功所需的补救。

您可以下载[Skype 业务网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试您的网络是否准备好让团队。 在工具提供双功能： 它可以测试是否对已打开了正确的端口，它可以测试网络障碍。

下载并安装该工具之后，您可以为业务网络评估工具 (x86) 为 C:\Program Files \Microsoft Skype 中找到它。 有关如何使用 Usage.docx，工具的详细的指南包含该目录中。

### <a name="test-for-opened-ports"></a>打开的端口的测试

打开命令提示符窗口并导航到网络评估工具目录通过输入**cd C:\Program Files (x86) \Microsoft Skype 业务网络评估工具**。 在命令提示符处，通过输入**networkassessmenttool.exe /connectivitycheck**开始打开端口测试

运行检查之后, 工具将显示消息"验证已成功完成"，或在已阻止的端口报告。 它还会生成一个名为 Connectivity_results.txt，其中包含从工具输出，并将其存储在 %userprofile%文件\\应用程序数据\\本地\\业务网络评估工具的 microsoft Skype\\目录。

我们建议您运行的连接检查定期以确保已打开的端口和都运行正常。

### <a name="test-for-network-impairments"></a>测试网络障碍

以提高用户满意度，您应在您的网络限制任何障碍。 最常见的网络障碍是延迟 （等待时间）、 数据包丢失和抖动：

- **延迟：** 这是获得 IP 数据包到网络上的点 B 点 A 所花费的时间。 实际上，此网络传播延迟被限制到物理距离的两个点和轻量，包括之间执行各种路由器的额外开销的速度。 延迟被按单向或往返时间。

- **数据包丢失**： 通常指在给定的时间窗口中丢失数据包的百分比。 数据包丢失直接影响音频质量 — 从小，个人丢失数据包无背对背脉冲损失几乎没有任何影响原因音频，完全去掉。

- **间数据包到达抖动或只需抖动：** 这是连续的数据包之间的延迟的平均更改。 最先进的 VoIP 软件，包括 Skype for Business，可以适应通过缓冲抖动某些级别。 则只有当抖动超过缓冲参与者会注意到的抖动效果。

[媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)介绍这些障碍的最大值。 测试这些障碍，我们区分两个独立段：

- *边缘段*是路由器驻留在其中的线段。 这是连接到 internet 上每个位置的最接近逻辑网络段。 在大多数情况下，这是路由器或可能是外围网络 （也称为*DMZ*、*非军事区*和*屏蔽子网*） 的连接点。 影响设备路由器之外没有进一步通信应发生这一段和 internet 之间。

- *客户端段*是客户端驻留在其中的逻辑网络段。

使用网络评估工具，您应测试两条线段。 若要测试段，定位到的目录，并输入**networkassessmenttool.exe**在命令提示符。 结果将写入名为 Results.tsv 的文件，并可以与每段的[要求](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

请注意，两条线段必须满足高质量部署的要求。 我们建议您运行该工具为一小时多次直接要获取清楚地表明您的网络性能。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>网络修正

如果带宽规划、 测试端口，或网络要求测试的结果显示您的当前网络需要修复，部署团队之前，可以多种方式来实现这一点：

- 没有足够带宽，升级连接，以便可以流动到 Office 365 的流量而没有影响。

- 阻止端口更改防火墙规则和该包端口。

- 对于网络障碍，始终执行根源分析。

服务质量 (QoS) 可以用于通过确定优先级和分隔流量来与障碍。 某些组织选择部署 QoS 解决带宽问题或限制流的流量的数量。 这不会提高质量，并且将导致新的问题。 网络受损超过要求时，应始终执行根源分析。 QoS 可以是一个解决方案。 有关详细信息，请参阅[Microsoft 团队中的服务质量](qos-in-teams.md)。

>[!NOTE]
>许多网络会由于升级、扩展或其他业务要求而逐渐发展。 请确保在你的服务管理规划中具有可操作的流程以维护这些方面。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>决策点</td><td><ul><li>谁将负责在所有网络领域和组织位置完成正确的网络评估？</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>后续步骤</td><td><ul><li>您可以执行的详细的网络评估，以帮助确保您的网络可供您的 Microsoft 团队的部署。 有关详细信息，请参阅<a href="https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness" data-raw-source="[Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)">网络准备情况评估</a>。</li><li>执行网络修正基于每个网络段网络准备情况评估结果。</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="key-takeaways"></a>要点

这些是从本指南的主要优点。 您必须：

- 打开 TCP 端口 80 和 443 传出来自客户端将使用团队。

- 打开 UDP 端口 3478 通过 3481 传出来自客户端将使用团队。

- 确保您有足够的带宽，通过完成[网络规划人员](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)部署团队。

- 运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)，并确保您满足从边缘段和客户端段[媒体质量和网络连接性能](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中所述的要求。

## <a name="related-topics"></a>相关主题

[视频： 网络规划](https://aka.ms/teams-networking)
