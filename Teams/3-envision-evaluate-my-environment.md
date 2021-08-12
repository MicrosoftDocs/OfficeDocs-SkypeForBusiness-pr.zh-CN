---
title: 评估云语音工作负荷的环境
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用角色和网络分析来评估组织的准备情况，打开正确的 TCP 和 UDP 端口，执行任何网络修正。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2498d634bda4760d34b6d76762312e56ae51efe4ea08a9b42b875ac250759403
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302086"
---
# <a name="evaluate-my-environment"></a>评估环境

本文概述了正确评估当前环境以使用云语音服务的要求。 通过评估环境，可以识别影响整体云语音部署的风险和要求。 通过事先确定这些项目，可以调整规划以推动成功。

## <a name="introduction-to-evaluating-your-environment"></a>环境评估简介

为了在 OKR (目标) ，你之前做出过关键服务决策。 下一步是执行环境发现，评估与 IT 和电话基础结构、网络和操作相关的所有方面，以确认组织已准备好实施解决方案。

环境发现必须包含网络就绪性评估，以确保你的网络可以支持音频会议或电话系统呼叫计划服务的实现。

在环境评估和采用就绪性评估中识别技术风险，并针对每个已识别的风险制定缓解计划。
应该将此信息合并到风险寄存器中。

<!--ENDOFSECTION-->

## <a name="current-environment"></a>当前环境

作为环境发现的一部分，包括与最终用户计算相关的所有事项，例如电脑和移动设备的准备情况评估，以支持音频会议和 电话系统 与呼叫计划业务用例（从硬件要求到软件要求）。

环境发现还可以发现是否需要将[电话号码转移到 Microsoft。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
了解此信息有助于组织相应地调整其项目计划，并为号码移植准备必要的信息。 可以使用环境[发现来Microsoft Teams环境](environmental-discovery-for-microsoft-teams-rollout.md)发现。

<table>
<tr><td>标题</td><td>描述</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>Who将负责完成环境评估？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>下一步</td><td><ul><li>记录环境评估的结果。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>采用和更改管理评估功能

部署使一项新技术触手可及，但只有在用户真正将该解决方案采用为其自己的解决方案之后，才能实现业务成果。 若要帮助确保持续采用新解决方案，需要将工作重心放在用户就绪状态和更改管理上。 为获得最佳结果，请作为技术准备活动的并行工作流进行用户准备情况规划，并整合以下活动：

-   **组织和用户分析：** 除了用例和人员分析外，还分析要更改的组织不活动性

-   **准备和资源准备：** 创建针对性和广泛宣传的认知、培训和支持资源，包括重点价值消息传送以加速用户购买

使用以下注意事项评估组织解决用户更改管理问题的准备情况。

<table>
<tr><td>标题</td><td>描述</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>用户以前是否成功采用软件或服务？</li><li>能否跟踪使用情况上升？</li><li>你是否拥有资源来设计和管理初始和持续采用活动， (认知、培训和 &mdash; &mdash; 支持) ？</li><li>您是否有专门的用户采用/更改管理团队，或者您是否可以投资这些资源以确保业务成果？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>下一步</td><td><ul><li>如果上述所有人员都回答了"是"，请确定适当的用户变更管理利益干系人 &quot; &quot; 并开始用户准备情况规划。</li><li>如果你对上述部分或所有内容都回答了"否"，请考虑利用外部资源来帮助推动组织变更管理和采用 &quot; &quot; 相关的活动。</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>网络就绪性

Teams音频和视频技术 (编解码器) 能够适应大多数网络条件，因此在大部分网络条件下性能更佳。 为了确保最佳性能和一致性能，应为网络准备Teams。

![描述质量的三个要素的示意图](media/evaluate-my-environment-image1.png "描述质量的三个组件以及服务管理如何与这三个组件重叠的示意图。将焦点放在网络上。")

## <a name="key-takeaways"></a>要点

这些是本指南的主要要点。 必须：

-   打开 TCP 端口 80 和 443，从将使用 Teams 的客户端传出。

-   打开 UDP 端口 3478 到 3481，从将使用 Teams 的客户端传出。

-   确保有足够的带宽来部署Teams。

-   运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)，确保满足边缘段和客户端段中媒体质量和[](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)网络连接性能中所述的要求。

## <a name="why-should-you-prepare-your-network"></a>为什么要准备网络？

在查看要执行的步骤之前，必须了解哪些因素可能会影响用户的性能，从而Teams和满意度。
三个主要风险领域可能会影响用户对网络质量的看法：

-   可用带宽不足

-   防火墙和代理阻止程序

-   网络障碍，例如抖动和数据包丢失

下面的步骤可帮助确定部署是否可能受上述任何因素影响，并有助于解决问题。
无法准备网络可能会导致用户不满意，并需要临时修复费用。 通过为网络和组织准备Teams，可以大幅提高成功的可能性。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>带宽规划

网络就绪性的第一步是确保网络有足够的带宽，Teams为用户提供的方式。 规划足够的带宽是一项相当简单的任务，也是一个低屏障的开始，可确保用户获得高质量的Teams体验。

### <a name="local-internet-egress"></a>本地 Internet 出口

许多网络设计为使用中心和辐射型拓扑。 在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。 通常，这么做事为了集中网络安全设备，目的是降低总成本。

经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。 由于Microsoft Teams在 Microsoft 的大型全球网络上运行，因此通常存在靠近用户的网络对等位置。 用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。 对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。 在这种情况下，使用本地出口点时，必须搭配使用本地 DNS 解析。

优化 Microsoft 全球网络的网络路径将提高性能，并最终为用户提供最佳体验。 有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。

### <a name="vpn"></a>VPN

VPN 为许多组织提供很有用的服务。 遗憾的是，它们通常未设计为或配置为支持实时媒体。 一些 VPN 可能还不支持 UDP。 VPN 还会在已加密的媒体流量之上额外引入一层加密。 此外，由于通过 VPN 设备Teams发固定流量，连接到 Teams 服务可能没有效率。
此外，它们不一定从容量角度设计，以适应预期负载，Teams需求。

建议提供一个备用路径，以便 Teams 流量绕过 VPN。 这通常称为 *拆分隧道 VPN。* 拆分隧道意味着 Microsoft 365 或 Office 365 的流量不会遍历 VPN，而是直接Microsoft 365或Office 365。 此更改将对质量产生积极的影响，但也提供从 VPN 设备和组织网络减少负载的次要优势。

要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。

### <a name="wi-fi"></a>Wi-Fi

与 VPN 一样，Wi-Fi网络不一定设计为或配置为支持实时媒体。 规划或优化Wi-Fi网络以支持Teams是高质量部署的一个重要考虑因素。

优化网络网络有几个因素Wi-Fi因素：

-   实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。

-   规划和优化Wi-Fi和接入点位置。 2.4 GHz 范围可以根据接入点位置提供合乎需要的体验，但接入点通常受该范围内运行的使用者其他设备的影响。 5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。

-   如果部署了双Wi-Fi网络，请考虑实施带引导。 带引导是一种由 Wi-Fi 实现的技术，用于影响双带客户端以使用 5 GHz 范围。

-   当同一通道的访问点过于靠近时，它们可能会导致信号重叠和意外竞争，从而导致用户体验不佳。 请确保相邻接入点的信道不会重叠。

每个无线供应商都有自己的无线解决方案部署建议。 建议你咨询你的供应商了解具体指导。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火墙和代理要求

Microsoft Teams连接到 Microsoft Online Services并且需要 Internet 连接。 若要Teams正常运行，必须打开从客户端到 Internet 的 TCP 端口 80 和 443，以及从客户端到 Internet 的 UDP 端口 3478 到 3481。 TCP 端口用于连接到基于 Web 的内容，例如 SharePoint Online、Exchange Online 和 Teams 聊天服务。
插件和连接器还通过这些 TCP 端口进行连接。 四个 UDP 端口用于音频和视频等媒体，以确保它们正常运行。

打开这些端口对于可靠的部署Teams至关重要。 阻止这些端口不受支持，并且将影响媒体质量。

如果组织要求指定要打开这些端口的确切 IP 地址范围和域，可以限制这些端口的目标 IP 范围和域。 有关确切端口、协议和 IP 范围的列表，请参阅 Microsoft 365 或 Office 365 URL 和[IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。
如果选择限制目标 IP 地址范围和域，必须确保端口和范围列表保持最新，因为它们可能会更改。 您可以订阅此 [RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301) ，以在发生更改时进行更新。 此外，通过定期运行 Skype for Business 评估工具来测试[是否](https://www.microsoft.com/download/details.aspx?id=53885)打开所有端口也是一个不错的做法。 可以在下一部分中详细了解此工具的功能。

部署代理服务器时，建议针对所有服务绕过Teams服务器。 尽管使用代理可能正常工作，但由于媒体被强制使用 TCP 而不是 UDP，质量很可能降低。 有关代理服务器和绕过功能的信息，请参阅Microsoft 365或Office 365 [URL 和 IP 地址范围](./office-365-urls-ip-address-ranges.md)。

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>测试网络

完成规划和网络准备（包括升级带宽和在防火墙中打开端口）后，应测试网络的性能。 此测试的结果将更清晰地显示音频会议或通话计划实现成功电话系统修正所需的任何网络优化或修正。

可以下载Skype for Business[评估工具](https://www.microsoft.com/download/details.aspx?id=53885)，以测试网络是否已准备好Teams。 该工具提供双重功能：它可以测试是否已打开所有正确的端口，并且可以测试网络障碍。

下载并安装该工具后，可以在 C： Program Files Microsoft Skype for Business Network Assessment Tool（程序文件 Microsoft 网络 \\ \\ 评估工具）找到它。 该目录中包含有关如何使用该工具的详细Usage.docx，例如，

### <a name="test-for-opened-ports"></a>测试打开的端口

打开命令提示符窗口，并输入 cd C： Program Files Microsoft Skype for Business Network Assessment Tool 导航 **\\ \\ 到网络评估工具目录**。 在命令提示符下，输入 **/connectivitychecknetworkassessmenttool.exe打开的端口**

运行检查后，该工具会显示消息"验证已成功完成"或报告已阻止的端口。
它还生成名为 Connectivity_results.txt 的文件，其中包含该工具的输出，并存储在 %userprofile% appdata 本地 \\ Microsoft skype for business \\ \\ 网络评估工具 \\ 目录中。

建议定期运行连接检查，确保端口已打开且正常运行。

### <a name="test-for-network-impairments"></a>网络障碍测试

若要提高用户满意度，应限制网络的任何障碍。
最常见的网络障碍是延迟 (延迟) 丢包和抖动：

-   **延迟：** 这是从网络上的点 A 到点 B 获取 IP 数据包所花的时间。 此网络传播延迟实质上与两个点之间的物理距离和光速有关，包括介于两者之间的各种路由器所增加的开销。
    延迟以单向或往返时间度量。

-   **数据包** 丢失：这通常定义为给定时间窗口中丢失的数据包的百分比。 数据包丢失直接影响音频质量 - 从小型、单个丢失的数据包到导致音频完全中断的背对回突发丢失几乎没有任何影响。

-   **数据包间到达抖动，或只是抖动：** 这是连续数据包之间的延迟的平均变化。 大多数现代 VoIP 软件（Skype for Business）可以通过缓冲来适应某些级别的抖动。 只有当抖动超过缓冲时，参与者才能注意到抖动的影响。

媒体质量和网络连接性能中介绍了这些障碍 [的最大值](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。
在测试这些障碍时，我们会区分两个单独的段：

-   *边缘段* 是路由器所位于的网段。 这是连接到每个位置的 Internet 的最近逻辑网络段。 在大多数情况下，这是路由器的连接点，也可能是外围网络 (外围网络，也称为 *外围* 网络、外围安全区域以及屏蔽) 。   此网段和 Internet 之间不应出现影响路由器外的其他设备的流量。

-   *客户端段* 是客户端所在的逻辑网络段。

应该使用网络评估工具测试这两个段。 若要测试段，请导航到目录，并在命令 **networkassessmenttool.exe** 输入命令。 结果将写入名为 Results.tsv 的文件，你可以将它们与 [每个段的要求](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 进行比较。

请注意，这两个段必须满足高质量部署的要求。 建议直接在一小时内多次运行该工具，以良好地指示网络性能。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>网络修正

如果带宽规划、端口测试或网络要求测试结果显示，在部署网络之前，当前网络需要Teams修正，则可通过多种方式实现此目的：

-   如果带宽不足，请升级连接，以便Microsoft 365或Office 365流量不受阻碍。

-   对于阻止的端口，请更改防火墙规则，然后重新测试端口。

-   对于网络障碍，请始终执行根本原因分析。

QoS (服务质量) 优先和分隔流量，从而解决障碍。 某些组织选择部署 QoS 来克服带宽问题或限制流量流动量。 这不会提高质量，也会导致新问题。 当网络障碍超过要求时，应始终执行根本原因分析。 QoS 可以是一种解决方案。
有关详细信息，请参阅服务[中的服务质量Microsoft Teams。](./qos-in-teams.md)

>[!NOTE]
>许多网络会由于升级、扩展或其他业务要求而逐渐发展。 请确保在你的服务管理规划中具有可操作的流程以维护这些方面。


<table>
<tr><td>标题</td><td>描述</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>Who负责在所有网段和组织位置完成适当的网络评估？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>下一步</td><td><ul><li>可以执行详细的网络评估，帮助确保网络已准备好进行Microsoft Teams部署。</li><li>根据每个网络段的评估结果执行网络修正。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->