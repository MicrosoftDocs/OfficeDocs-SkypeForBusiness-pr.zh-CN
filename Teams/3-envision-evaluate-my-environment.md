---
title: 评估您的环境的 Microsoft 团队云语音工作负荷
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用角色和网络分析评估贵组织的准备情况，请打开了正确的 TCP 和 UDP 端口，执行的任何网络补救。
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66b86ef8789f959de9887cc1f0b3c7c1e2e8ffa3
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015570"
---
# <a name="evaluate-my-environment"></a>评估我的环境

本文概述了正确评估当前环境使用云语音服务的要求。 通过评估您的环境，您可以确定风险和将影响总体云语音部署要求。 通过预先确定这些项，您可以调整驱动器成功进行规划。

## <a name="introduction-to-evaluating-your-environment"></a>评估环境简介 

若要获得目标关键结果 (OKRs)，以前所作关键服务决策。 下一步是执行环境发现评估与您的 IT 相关的所有方面和电话基础结构、 网络和操作，以确认您的组织是否准备好实施解决方案。

环境发现必须包括网络准备情况评估，以确保您的网络可支持的音频会议或电话系统与调用 Plan services 的实现。

标识为环境评估和采用准备情况评估的一部分的技术风险和制定针对每个确定风险缓解计划。
还应该采用风险注册中的此信息。

<!--ENDOFSECTION-->

## <a name="current-environment"></a>当前环境

作为您的环境发现的一部分，包括与最终用户计算，如 Pc 准备情况评估相关的所有方面和移动设备与调用规划业务支持音频会议和电话系统使用情况下，从到的硬件要求软件要求。

是否需要对[传输给 Microsoft 的电话号码](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)，也可以发现环境发现。
了解这将有助于您的组织相应地调整其项目计划和准备号码移植所需的信息。 从 MyAdvisor[环境发现的 Microsoft 团队推出](environmental-discovery-for-microsoft-teams-rollout.md)可用于执行环境发现。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>谁将负责完成环境评估？</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档环境评估的结果。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>应用和更改管理评估功能 

部署将新技术放置在用户的当前可用，但业务成果仅实现后用户确实采用作为其自己的解决方案。 为了帮助确保持续的采用新的解决方案，您需要精力放在用户准备情况和更改管理。 为获得最佳结果，进行规划作为对您的技术准备活动并行工作流的用户准备和合并以下活动：

-   **组织和用户分析：** 组织 receptiveness 更改除了使用案例和个人分析的分析

-   **准备和资源的准备：** 创建目标和广泛的认知、 培训和支持资源，包括中心消息可加速用户购买中的值

使用以下注意事项评估解决用户更改管理您的组织准备基础。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>您已经采用用户软件或服务的以前成功？</li><li>您可以跟踪使用情况领会？</li><li>您是否要设计和管理初始的资源&mdash;和持续&mdash;采用市场活动 （认知、 培训和支持）？</li><li>您拥有一个专用的用户采用/更改管理团队，或您投资这些资源，以确保业务产出？</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>如果您对上述所有回答"是"，确定适当的用户更改管理利益干系人并开始用户准备规划。</li><li>如果您回答"no"部分或全部以上，请考虑利用外部的资源以帮助驱动更改管理和为您的组织采用相关活动。</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>网络准备

团队使用可以适应音频和视频技术 （编解码器） — 因此下更好地执行 — 最网络条件。 若要确保一致的最佳性能，应该为团队准备您的网络。

![描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有网络上焦点。](media/evaluate-my-environment-image1.png "描述质量和服务管理与全部三个组件的重叠的三个组件的关系图。具有网络上焦点。")

## <a name="key-takeaways"></a>要点

这些是从本指南的主要优点。 您必须：

-   打开 TCP 端口 80 和 443 传出来自客户端将使用团队。

-   打开 UDP 端口 3478 通过 3481 传出来自客户端将使用团队。

-   确保您有足够的带宽，通过完成[网络规划人员](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)部署团队。

-   运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)，并确保您满足从边缘段和客户端段[媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中所述的要求。

## <a name="why-should-you-prepare-your-network"></a>为什么应准备您的网络？

我们查看要采取的步骤之前，请务必了解什么会影响性能的团队从而用户幸福和满意度。
三个主要风险区域可能会影响用户如何感知网络质量：

-   可用带宽不足

-   防火墙和代理窗口阻止程序

-   如抖动和丢包的网络障碍

如下所述的步骤将帮助您确定是否部署可能受以下因素之一，将帮助您移向分辨率。
出现故障的准备您的网络可能会导致用户不满和消耗大量资金，临时修复。 通过网络准备 — 和您的组织 — 团队，您可以显著增加成功的概率。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>带宽规划

网络准备的第一步确保您的网络有足够的工作组将向用户提供形式的带宽。 规划足够的带宽为相当简单任务和非常低障碍开始以确保您的用户将具有高质量团队体验。

启动您规划旅程团队[我顾问网站](https://myadvisor.fasttrack.microsoft.com/)上使用网络计划工具的带宽。 网络计划工具提供规划团队的每个网站带宽，并提供有关优化网络性能建议。

### <a name="local-internet-egress"></a>本地 Internet 出口

许多网络设计为使用中心和辐射型拓扑。 在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。 通常，这么做事为了集中网络安全设备，目的是降低总成本。

经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。 由于 Microsoft Teams 在 Microsoft 的大型全局网络上运行，因此，用户附近通常会有网络对等位置。 用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。 对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。 在这种情况下，务必要在使用本地出口点时，将其与本地 DNS 解析配对。

优化指向 Microsoft 的全局网络的网络路径将会提高性能，并最终将为用户提供最佳体验。 有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。

### <a name="vpn"></a>VPN

VPN 为许多组织提供很有用的服务。 遗憾的是，他们正在通常不设计或配置为支持实时的媒体。 一些 VPN 可能还不支持 UDP。 Vpn 还引入了额外的已加密的媒体流量在加密。 此外，连接到团队服务可能不是有效由于字形驻留流量通过 VPN 设备。
此外，它们不一定被设计从容量角度以适应团队需要的预期的负载。

建议提供一个备用路径，以便 Teams 流量绕过 VPN。 这通常是称为*拆分隧道 VPN*。 拆分隧道 for Office 365 的流量不会遍历 VPN，但将直接转到 Office 365 的方法。 此改变不仅有利于提高质量，而且还带来额外的好处，即降低 VPN 设备和组织网络的负荷。

要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。

### <a name="wi-fi"></a>Wi-Fi

VPN，如 Wi-fi 网络不一定是设计或配置为支持实时的媒体。 规划，或优化，Wi-fi 网络支持团队是高质量部署的重要注意事项。

有派上用场优化 Wi-fi 网络的几个因素：

-   实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。

-   规划和优化 Wi-fi 区段和访问点位置。 2.4 GHz 范围可以根据接入点位置提供合乎需要的体验，但接入点通常受该范围内运行的使用者其他设备的影响。 5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。

-   如果部署双带 Wi-fi 网络，请考虑实现带控制。 带控制是由 Wi-fi 供应商以影响双带客户端使用 5 GHz 区域实现的技术。

-   访问点的同一通道太近时他们可以导致信号重叠并意外竞争，导致用户的体验不佳。 确保彼此相邻的访问点位于不相互重叠的通道。

每个无线供应商都有自己的无线解决方案部署建议。 建议你咨询你的供应商了解具体指导。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火墙和代理要求

Microsoft 团队连接到 Microsoft Online Services，并为此需要 internet 连接。 对于团队能够正常工作，您必须打开 TCP 端口 80 和 443 从客户端到 internet，以及 UDP 端口 3478 通过 3481 从客户端到 internet。 TCP 端口用于连接到基于 web 的内容，如 SharePoint Online、 Exchange Online 和团队聊天服务。
通过这些 TCP 端口还连接插件和连接器。 四个 UDP 端口用于音频和视频，如媒体以确保它们正常流。

打开这些端口对于可靠的团队部署至关重要。 阻止以下端口是不受支持，将会影响媒体质量。

如果组织要求您指定的确切的 IP 地址范围和这些端口应打开到的域，您可以限制的目标 IP 范围和这些端口的域。 有关确切的端口的列表，协议和 IP 地址范围，请参阅[Office 365 Url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。
如果您选择限制的目标 IP 地址范围和域，则必须确保您保存的端口和范围列表最新因为它们可能会更改。 您可以订阅发生更改时要更新的[此 RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)。 也很好的做法测试是否由定期运行[的业务网络评估工具的 Skype](https://www.microsoft.com/download/details.aspx?id=53885)打开所有端口。 您可以在下一步部分找出有关此工具的功能的详细信息。

发生正在部署的代理服务器，我们建议您绕过所有团队服务的代理服务器。 虽然使用代理可能起作用，就非常可能质量将由于媒体的强制使用 TCP 而 UDP 不会降低。 有关代理服务器和绕过的详细信息，请参阅[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>测试网络

在您完成规划和网络准备后 — 包括升级带宽和防火墙中打开的端口 — 您应测试您的网络性能。 此测试将结果绘制清楚地的任何网络优化或成功的您的音频会议或电话系统与调用规划实现所需的补救。

您可以下载[Skype 业务网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试您的网络是否准备好让团队。 在工具提供双功能： 它可以测试是否对已打开了正确的端口，它可以测试网络障碍。

下载并安装该工具之后，您可以找到它中 c:\\Program Files\\Microsoft Skype 业务网络评估工具。 有关如何使用 Usage.docx，工具的详细的指南包含该目录中。

### <a name="test-for-opened-ports"></a>打开的端口的测试

打开命令提示符窗口并导航到网络评估工具目录通过输入**cd c:\\Program Files\\业务网络评估工具的 Microsoft Skype**。 在命令提示符处，通过输入**networkassessmenttool.exe /connectivitycheck**开始打开端口测试

运行检查之后, 工具将显示消息"验证已成功完成"，或在已阻止的端口报告。
它还会生成一个名为 Connectivity_results.txt，其中包含从工具输出，并将其存储在 %userprofile%文件\\应用程序数据\\本地\\业务网络评估工具的 microsoft Skype\\目录。

我们建议您运行的连接检查定期以确保已打开的端口和都运行正常。

### <a name="test-for-network-impairments"></a>测试网络障碍

以提高用户满意度，您应在您的网络限制任何障碍。
最常见的网络障碍是延迟 （等待时间）、 数据包丢失和抖动：

-   **延迟：** 这是获得 IP 数据包到网络上的点 B 点 A 所花费的时间。 实际上，此网络传播延迟被限制到物理距离的两个点和轻量，包括之间执行各种路由器的额外开销的速度。
    延迟被按单向或往返时间。

-   **数据包丢失**： 通常指在给定的时间窗口中丢失数据包的百分比。 数据包丢失直接影响音频质量 — 从小，个人丢失数据包无背对背脉冲损失几乎没有任何影响原因音频，完全去掉。

-   **间数据包到达抖动或只需抖动：** 这是连续的数据包之间的延迟的平均更改。 最先进的 VoIP 软件，包括 Skype for Business，可以适应通过缓冲抖动某些级别。 则只有当抖动超过缓冲参与者会注意到的抖动效果。

[媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)介绍这些障碍的最大值。
测试这些障碍，我们区分两个独立段：

-   *边缘段*是路由器驻留在其中的线段。 这是连接到 internet 上每个位置的最接近逻辑网络段。 在大多数情况下，这是路由器或可能是外围网络 （也称为*DMZ*、*非军事区*和*屏蔽子网*） 的连接点。 影响设备路由器之外没有进一步通信应发生这一段和 internet 之间。

-   *客户端段*是客户端驻留在其中的逻辑网络段。

使用网络评估工具，您应测试两条线段。 若要测试段，定位到的目录，并输入**networkassessmenttool.exe**在命令提示符。 结果将写入名为 Results.tsv 的文件，并可以与每段的[要求](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。

请注意，两条线段必须满足高质量部署的要求。 我们建议您运行该工具为一小时多次直接要获取清楚地表明您的网络性能。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>网络修正

如果带宽规划、 测试端口，或网络要求测试的结果显示您的当前网络需要修复，部署团队之前，可以多种方式来实现这一点：

-   没有足够带宽，升级连接，以便可以流动到 Office 365 的流量而没有影响。

-   阻止端口更改防火墙规则和该包端口。

-   对于网络障碍，始终执行根源分析。

服务质量 (QoS) 可以用于通过确定优先级和分隔流量来与障碍。 某些组织选择部署 QoS 解决带宽问题或限制流的流量的数量。 这不会提高质量，并且将导致新的问题。 网络受损超过要求时，应始终执行根源分析。 QoS 可以是一个解决方案。
有关详细信息，请参阅[Microsoft 团队中的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)。

>[!NOTE]
>许多网络会由于升级、扩展或其他业务要求而逐渐发展。 请确保在你的服务管理规划中具有可操作的流程以维护这些方面。


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>谁将负责在所有网络领域和组织位置完成正确的网络评估？</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>您可以执行的详细的网络评估，以帮助确保您的网络可供您的 Microsoft 团队的部署。 有关详细信息，请参阅[网络准备情况评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)。</li><li>执行网络修正基于每个网络段网络准备情况评估结果。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->