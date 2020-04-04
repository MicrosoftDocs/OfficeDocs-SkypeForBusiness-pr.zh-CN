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
description: 使用角色和网络分析来评估组织的准备情况，打开正确的 TCP 和 UDP 端口，然后执行任何网络修正。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 17843b886fc334d7b02907882a82dffdf302e9f5
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137982"
---
# <a name="evaluate-my-environment"></a>评估环境

本文概述了正确评估当前环境使用云语音服务的要求。 通过评估你的环境，确定将影响你的整体云语音部署的风险和要求。 通过预先确定这些项目，您可以调整计划以推动成功。

## <a name="introduction-to-evaluating-your-environment"></a>评估环境简介 

为了实现客观的关键结果（OKRs），您以前已做出关键服务决策。 下一步是执行环境发现以评估与你的 IT 和电话基础结构、网络和操作相关的所有方面，以确认你的组织已准备好实施解决方案。

环境发现必须包含网络准备情况评估，以确保你的网络能够支持通过呼叫计划服务实现音频会议或电话系统。

你可以将技术风险标识为环境评估和采纳准备情况评估的一部分，并针对每个确定的风险制定一个缓解计划。
您应将此信息合并到风险注册中。

<!--ENDOFSECTION-->

## <a name="current-environment"></a>当前环境

作为环境发现的一部分，请包括与最终用户计算相关的所有事宜，如电脑和移动设备的准备情况评估，以支持音频会议和手机系统，支持使用呼叫计划的业务使用案例（从硬件要求到软件要求）。

环境发现还可以揭示是否需要将[电话号码转移到 Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。
了解此操作将帮助你的组织相应调整其项目计划，并为数字移植准备必要的信息。 你可以使用[Microsoft 团队推出的环境发现](environmental-discovery-for-microsoft-teams-rollout.md)来执行环境发现。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>谁将负责完成环境评估？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>记录环境评估的结果。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>采纳和更改管理评估功能 

部署为用户提供了一种新的技术，但仅在用户真正将该解决方案视为自己的情况后才会实现业务结果。 为了帮助确保持续接受新的解决方案，你需要将精力集中在用户准备工作和更改管理上。 为获得最佳结果，请将用户准备工作计划作为并行工作流提供给你的技术准备活动，并合并以下活动：

-   **组织和用户分析：** 对组织 receptiveness 的分析，以在使用案例和角色分析之外进行更改

-   **准备情况和资源准备：** 创建目标范围和广泛关注的感知、培训和支持资源，包括专注的价值消息传递以加速用户购买

使用以下注意事项评估组织的准备情况以解决用户更改管理问题。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>您是否曾对使用软件或服务的用户进行了以前的成功？</li><li>是否可以跟踪使用 uptake？</li><li>您是否有用于设计和管理初始&mdash;和正在进行&mdash;的采纳活动（意识、培训和支持）的资源？</li><li>您是否有专门的用户采纳/更改管理团队，是否可以购买这些资源以确保业务成果？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>如果对上述&quot;全部&quot;项回答 "是"，请确定合适的用户变更管理利益干系人并开始准备用户规划。</li><li>如果您回答&quot;的&quot;不是上述部分或全部，请考虑向外部资源提供帮助，帮助您组织的变更管理和与采纳相关的活动。</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>网络准备情况

团队使用音频和视频技术（编解码器），它可以在大多数网络条件下适应，从而性能更好。 为确保最佳性能，应为团队准备网络。

![描述三个质量组件的图表](media/evaluate-my-environment-image1.png "描述三种质量组件以及服务管理如何与所有三个组件重叠的图表。将焦点放在网络上。")

## <a name="key-takeaways"></a>关键优势

这是本指南的主要优点。 您必须：

-   打开从将使用团队的客户端传出的 TCP 端口80和443。

-   打开从将使用团队的客户端传出的 UDP 端口3478到3481。

-   确保您有足够的带宽来部署团队。

-   运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)，确保满足从边缘段和客户端段的[媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中所述的要求。

## <a name="why-should-you-prepare-your-network"></a>为什么要准备网络？

在查看要采取的步骤之前，请务必了解哪些内容会影响团队的性能，从而提高用户的幸福和满意度。
三个主要风险领域会影响用户对网络质量的理解：

-   可用带宽不足

-   防火墙和代理阻止程序

-   网络障碍，如抖动和数据包丢失

下面介绍的步骤将帮助你确定你的部署是否受这些因素的影响，并将帮助你转向解决方案。
无法准备网络可能会导致不满意的用户和非常昂贵的临时修补程序。 通过为团队准备网络和你的组织，你可以大大增加成功的可能性。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>带宽规划

网络准备情况的第一步是确保你的网络有足够的带宽可供形式团队提供给用户。 规划足够的带宽是一个非常简单的任务和一个非常低廉的起点，可确保你的用户具有高质量的团队体验。

### <a name="local-internet-egress"></a>本地 Internet 出口

许多网络设计为使用中心和辐射型拓扑。 在此拓扑中，Internet 流量通常先穿过 WAN 到达中心数据库，然后再向外传输（流出）到 Internet。 通常，这么做事为了集中网络安全设备，目的是降低总成本。

经过 WAN 的回程流量会造成延迟增加，并对质量和用户体验产生负面影响。 由于 Microsoft 团队在 Microsoft 的大型全球网络上运行，因此通常会向用户靠近网络对等位置。 用户通过从其所在位置附近的本地 Internet 点流出并尽快进入我们的语言优化网络，很可能会获得更佳的性能。 对于某些工作负荷，使用 DNS 请求向最近的前端服务器发送流量。 在这种情况下，在使用本地出口点时，它与本地 DNS 解析相配对非常重要。

优化 Microsoft 全球网络的网络路径将提高性能，并最终为用户提供最佳体验。 有关更多详细信息，请参阅博客文章 [Getting the best connectivity and performance in Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)（在 Office 365 中获取最佳连接性和性能）。

### <a name="vpn"></a>VPN

VPN 为许多组织提供很有用的服务。 很遗憾，它们通常不是为支持实时媒体而设计或配置的。 一些 VPN 可能还不支持 UDP。 Vpn 还会在已加密的媒体流量顶部引入额外的加密层。 此外，由于通过 VPN 设备有头发的流量，到团队服务的连接可能不会有效。
此外，它们不一定从容量角度进行设计，以适应团队需要的预期负载。

建议提供一个备用路径，以便 Teams 流量绕过 VPN。 这通常称为*拆分隧道 VPN*。 拆分隧道意味着 Office 365 的流量不会遍历 VPN，但会直接转到 Office 365。 此更改将对质量产生积极影响，但也会提供从 VPN 设备和组织网络减少负载的辅助优点。

要实施拆分通道，请咨询 VPN 供应商了解配置详细信息。

### <a name="wi-fi"></a>Wi-Fi

与 VPN 类似，Wlan 网络不一定设计或配置为支持实时媒体。 在高质量部署中，为支持团队规划或优化 Wi-fi 网络是重要的考虑因素。

优化 Wlan 网络有以下几个因素：

-   实施 QoS 或 Wi-Fi 多媒体 (WMM) 以确保通过 Wi-Fi 网络的媒体流量相应地得到优先处理。

-   规划和优化 Wi-fi 频带和接入点放置。 2.4 GHz 范围可以根据接入点位置提供合乎需要的体验，但接入点通常受该范围内运行的使用者其他设备的影响。 5 GHz 范围因其密度范围更适合实时媒体，但需要更多接入点以获取足够的覆盖范围。 此外，终结点还需要相应地支持该范围并配置为利用这些频带。

-   如果已部署了双频带 Wi-fi 网络，请考虑实施频带筹划。 波段控制是由 Wi-fi 供应商实施的一项技术，可影响双层客户使用 5 GHz 范围。

-   当同一频道的接入点太靠近时，它们可能会导致信号重叠并无意间竞争，从而导致用户体验不良。 确保彼此相邻的接入点位于不重叠的频道上。

每个无线供应商都有自己的无线解决方案部署建议。 建议你咨询你的供应商了解具体指导。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火墙和代理要求

Microsoft 团队连接到 Microsoft Online 服务，并且需要 internet 连接才能实现此操作。 要使团队正常运行，必须从客户端打开 TCP 端口80和443，并从客户端到网络的 UDP 端口3478到3481。 TCP 端口用于连接到基于 web 的内容，如 SharePoint Online、Exchange Online 和团队聊天服务。
插件和连接器也通过这些 TCP 端口进行连接。 四个 UDP 端口用于音频和视频等媒体，以确保它们正常流动。

打开这些端口对于可靠的团队部署非常重要。 阻止这些端口不受支持，并且将对媒体质量产生影响。

如果你的组织要求你指定应在其中打开这些端口的确切 IP 地址范围和域，则可以限制这些端口的目标 IP 范围和域。 有关确切的端口、协议和 IP 范围的列表，请参阅[Office 365 url 和 ip 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。
如果你选择限制目标 IP 地址范围和域，则必须确保将端口和范围的列表保持为最新，因为它们可能会发生更改。 你可以订阅[此 RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)，以便在发生更改时进行更新。 这也是一种很好的做法，通过定期运行[Skype For Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试所有端口是否已打开。 可在下一节中了解有关此工具的功能的详细信息。

在正在部署的代理服务器事件中，我们建议您绕过所有团队服务的代理服务器。 虽然使用代理可能有效，但由于媒体被强制使用 TCP 而不是 UDP，因此很可能会降低质量。 有关代理服务器和绕过的详细信息，请参阅[Office 365 url 和 IP 地址范围](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>测试网络

完成规划和网络准备（包括升级带宽和打开防火墙中的端口）后，应测试网络的性能。 此测试的结果将绘制一个更清晰的图片，让你的音频会议或电话系统成功完成所需的任何网络优化或补救措施。

你可以下载[Skype For Business 网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试你的网络是否已准备好进行团队。 此工具提供双重功能：它可以测试是否已打开所有正确的端口，并且它可以测试网络是否有障碍。

下载并安装该工具后，您可以在 C：\\Program Files\\Microsoft Skype For business 网络评估工具中找到它。 有关如何使用该工具的详细指南（如 .docx）包含在该目录中。

### <a name="test-for-opened-ports"></a>测试打开的端口

打开命令提示符窗口，然后导航到 "网络评估" 工具目录，方法是输入**Cd\\C\\： Program Files Microsoft Skype for business 网络评估工具**。 在命令提示符处，通过输入**networkassessmenttool/connectivitycheck**开始测试已打开的端口

运行检查后，该工具将显示消息 "验证已成功完成" 或报告已阻止的端口。
它还会生成一个名为 Connectivity_results .txt 的文件，其中包含该工具的输出，并将其存储在%\\userprofile\\%\\appdata 本地 microsoft skype for business 网络\\评估工具目录中。

我们建议你定期运行连接检查，以确保端口已打开并正常运行。

### <a name="test-for-network-impairments"></a>测试网络是否有障碍

为提高用户满意度，您应该限制网络的任何障碍。
最常见的网络障碍是延迟（延迟）、数据包丢失和抖动：

-   **延迟：** 这是将 IP 数据包从点 A 转到网络上的点 B 所需的时间。 此网络传播延迟实质上与两个点之间的物理距离和光之间的距离保持联系，包括不同路由器所用的额外开销。
    延迟是指单向或往返时间。

-   **数据包丢失**：这通常定义为在给定时间段内丢失的数据包的百分比。 数据包丢失直接影响音频质量-从较小的单个丢失的数据包中，几乎不会影响对导致音频完全减少的后端到后突发损失的影响。

-   **数据包间到达抖动或简单抖动：** 这是连续数据包之间的延迟的平均变化。 大多数现代 VoIP 软件（包括 Skype for Business）可以通过缓冲来适应某些级别的抖动。 仅当抖动超过的是参与者将注意到抖动效果的缓冲时才会如此。

在[媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中介绍了这些障碍的最大值。
测试这些障碍时，请区分两个不同的段：

-   *边缘段*是你的路由器所在的段。 这是您的每个位置上连接到互联网的最接近的逻辑网络段。 在大多数情况下，这是路由器的连接点，或者是外围网络（也称为*DMZ*、*隔离区*和*屏蔽子网*）。 除了路由器之外的设备之外，任何其他通信量都不应出现在此网段和 internet 之间。

-   *客户端段*是客户端所在的逻辑网络段。

你应该使用网络评估工具测试这两个段。 若要测试段，请导航到目录并在命令提示符处输入**networkassessmenttool** 。 结果将写入一个名为 tsv 的文件中，您可以将其与每个段的[要求](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)进行比较。

请注意，两个段必须满足高质量部署的要求。 我们建议你在一小时内多次运行该工具，以获得更好的网络性能指示。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>网络修正

如果带宽规划、端口测试或网络要求测试的结果显示您当前的网络需要补救措施才能部署团队，则可以通过以下几种方式实现此目的：

-   如果带宽不足，请升级连接，以便到 Office 365 的通信流 unhindered。

-   对于已阻止的端口，请更改防火墙规则并重新测试端口。

-   对于网络障碍，请始终执行根本原因分析。

服务质量（QoS）可用于对流量进行排序和分隔，从而使障碍更有障碍。 某些组织选择部署 QoS 来克服带宽问题或限制流量的流量。 这不会提高质量，并将导致新问题。 当网络障碍超过要求时，应始终执行根本原因分析。 QoS 可以是一个解决方案。
有关详细信息，请参阅[Microsoft 团队中的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)。

>[!NOTE]
>许多网络会由于升级、扩展或其他业务要求而逐渐发展。 请确保在你的服务管理规划中具有可操作的流程以维护这些方面。


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>决策点</td><td><ul><li>谁将负责在所有网段和组织位置完成正确的网络评估？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>后续步骤</td><td><ul><li>你可以执行详细的网络评估，以帮助确保你的网络为你的 Microsoft 团队部署做好准备。</li><li>基于针对每个网络段的评估结果执行网络修正。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->
