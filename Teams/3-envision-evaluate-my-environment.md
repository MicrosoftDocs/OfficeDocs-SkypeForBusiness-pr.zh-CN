---
title: 评估您的 Microsoft 小组云语音工作负载环境
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 使用角色和网络分析来评估您的组织准备情况，请打开正确的 TCP 和 UDP 端口，执行网络的任何补救。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b97a588a55eb1b7183315751a9483d69eeb0b6b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="evaluate-my-environment"></a>评估环境

这篇文章概括介绍了使用云语音服务的当前环境进行正确评估的要求。 通过评估您的环境，您可以确定风险和将会影响整体云语音部署的要求。 通过预先确定这些项，可以调整您的驱动器成功的规划。

## <a name="introduction-to-evaluating-your-environment"></a>评估您的环境简介 

为了实现目标搜索结果 (OKRs)，以前做关键服务的决策。 下一步是执行环境研究，以评估与您的 IT 的所有方面和电话基础架构、 网络和操作，以确认您的组织已准备好实施解决方案。

环境的发现过程必须包括网络就绪性评估，以确保您的网络可以支持音频会议或电话系统调用计划服务的实现。

作为一个环境评估和采用准备情况评估，识别技术风险并制定每个确定的风险的缓解计划。
应该采用风险登记簿中的此信息。

<!--ENDOFSECTION-->

## <a name="current-environment"></a>当前环境

作为您环境的发现，包括最终用户计算，如 Pc 和移动设备与调用计划的业务用例，从硬件要求支持音频会议和电话系统准备情况评估相关的所有事宜软件要求。

是否需要[传送到 Microsoft 的电话号码](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)，还可以揭示环境的发现。
了解这将有助于您的组织，其项目计划进行相应的调整和准备的数字移植所需的信息。 可以使用[Microsoft 小组范围内部署环境发现](https://docs.microsoft.com/MicrosoftTeams/environmental-discovery-for-microsoft-teams-rollout)从 MyAdvisor 执行环境的发现。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>谁将负责完成环境评估？</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>文档环境评估的结果。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>采用和更改管理评估功能 

部署用户的指尖，在将一种新技术，但之后用户真正采用该解决方案作为自己只实现业务成效。 为了帮助确保持续的采用新的解决方案，您需要精力放在用户准备和更改管理。 为获得最佳结果，进行规划与技术准备活动并行工作流为用户准备并将纳入以下活动：

-   **组织和用户分析：**除了使用用例和角色分析更改的组织 receptiveness 的分析

-   **准备情况和资源准备：**创建目标和广泛的意识、 培训和支持资源，包括专注于消息传递来加速用户购买中的值

使用下列事项评估解决用户更改管理您的组织的应急能力。

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>您是否遇到以前成功的软件或服务的用户采用率？</li><li>您可以跟踪使用率倡导？</li><li>您是否有资源来设计和管理一个初始&mdash;及以后的例行&mdash;采用市场 （意识、 培训和支持）？</li><li>您是否有一个专用的用户采用/更改管理团队，还是可以投资这些资源，以确保业务成果？</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>如果您对上述所有回答"是"，确定适当的用户更改管理利益干系人并开始用户准备工作规划。</li><li>如果您回答"否"的部分或所有上述，考虑利用外部资源来协助推动变更管理和采用相关的活动，为您的组织。</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>网络就绪

团队使用可适应于音频和视频技术 （编码解码器） — — 因此下更好地执行 — — 大多数的网络条件。 为了确保一致的最佳性能，应为团队准备您的网络。

![描述的质量和服务管理与所有三个组件的重叠的三个组件的关系图。与网络上的焦点。](media/evaluate-my-environment-image1.png "描述的质量和服务管理与所有三个组件的重叠的三个组件的关系图。与网络上的焦点。")

## <a name="key-takeaways"></a>记住的要点

这些都是从本指南的主要优点。 您必须：

-   打开 TCP 端口 80 和 443 将使用团队的客户端的传出。

-   打开 UDP 端口 3478 通过从客户端将使用团队 3481 传出。

-   确保您有足够的带宽，通过完成[网络规划人员](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)部署团队。

-   运行[网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)，并确保您满足从边段和客户端网段中[媒体质量和网络连接的性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)描述的要求。

## <a name="why-should-you-prepare-your-network"></a>为什么您应该准备您的网络？

我们看一看所采取的步骤之前，请务必了解什么可以影响性能的团队，从而用户幸福和满意度。
三个主要风险方面会影响用户如何感知网络质量：

-   没有足够的可用带宽

-   防火墙和代理服务器的阻止程序

-   如抖动和数据包丢失的网络障碍

下面介绍的步骤将帮助您确定您是否您的部署的所有这些因素可能会影响并有助于移向分辨率。
未能准备您的网络可能会导致用户不满，成本高昂，临时解决了。 准备您的网络，和您的组织 — — 团队，可以极大地提高成功的机会。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>带宽规划

网络准备工作的第一步确保您的网络有足够的带宽供团队将提供给用户的情态。 规划足够的带宽是一个相当简单的任务，门槛非常低开始，以确保您的用户将获得高质量的团队体验。

您开始您的带宽规划旅行团队[我审查网站](https://myadvisor.fasttrack.microsoft.com/)上通过网络规划人员。 网络规划人员提供每网站带宽规划团队，并提供了优化网络性能的建议。

### <a name="local-internet-egress"></a>本地互联网出口

在设计许多网络使用一个集线器和分支拓扑。 在此拓扑中，互联网通信量通常通过 WAN 到中央数据中心之前它出现 （出口） 到互联网。 通常情况下，这样做是为了集中网络安全设备，以降低整体成本的目标。

跨广域网后拖拉流量增加延迟，对质量和用户体验的负面影响。 因为 Microsoft 的大型全球网络上运行 Microsoft 小组，是通常接近用户的网络对等位置。 用户通过尽快 egressing 出本地 internet 点靠近它们的位置和我们的声音进行了优化的网络到最有可能获得更好的性能。 对于某些工作负载，使用 DNS 请求以便向发送通讯最近的前端服务器。 在这种情况下，非常重要，当使用本地出口点，则已配对使用本地 DNS 解析。

优化网络路径与 Microsoft 的全球网络将提高性能，并最终为用户提供最好的体验。 有关详细信息，请参阅博客文章[获得最佳的连接和 Office 365 中的性能](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)。

### <a name="vpn"></a>VPN

Vpn 将提供许多组织有价值服务。 遗憾的是，通常不设计或配置为支持实时媒体。 某些 Vpn 可能也不支持 UDP。 Vpn 还引入了额外的顶部已被加密的介质流量加密。 另外，为团队服务的连接可能不是由于头发固定通过 VPN 设备的通信效率高。
此外，他们不一定能够从产能角度来看适应团队将需要的预期的负载。

建议是提供备选路径绕过团队通信 VPN。 这通常被称为*拆分隧道 VPN*。 分拆隧道 Office 365 的通讯不通过 VPN，但将直接转到 Office 365 的手段。 此更改对质量，将产生积极影响，而且还提供辅助福利减少从 VPN 设备和组织的网络负载。

实现拆分隧道，请咨询您的 VPN 供应商的配置的详细信息。

### <a name="wi-fi"></a>Wi-Fi

如 VPN、 Wi-Fi 网络并不一定能设计或配置为支持实时媒体。 规划，或优化，Wi-Fi 网络来支持团队，是优质部署的一个重要考虑。

榜上有名的 Wi-Fi 网络优化的若干因素有：

-   实现 QoS 或 Wi-fi 多媒体 (WMM)，以确保该媒体通信获取相应地优先顺序通过 Wi-fi 网络。

-   规划和优化的 Wi-Fi 区段和访问点的位置。 2.4 GHz 范围可能会提供足够的经验，根据接入点放置，但接入点通常受到运行在该范围内其他消费型设备。 5 GHz 范围更适合于实时媒体由于其密集的范围，但是需要更多的接入点以获得足够的覆盖范围。 终结点还需要支持该范围和配置，以便相应地利用这些频带。

-   如果部署双模 Wi-fi 网络，考虑实现带控制。 带控制是影响双波段客户端使用 5 GHz 范围的 Wi-Fi 供应商实现的技术。

-   当接入点的相同的通道太近时他们可以引起信号重叠并无意中竞争，从而导致糟糕的用户体验。 确保在不重叠的通道上彼此相邻的接入点。

每个无线供应商已部署其无线解决方案的建议。 我们建议您咨询您的供应商进行具体指导。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火墙和代理服务器要求

Microsoft 小组连接到 Microsoft Online Services，并为此需要互联网连接。 为团队才能正常工作，您必须打开 TCP 端口 80 和 443 从客户端到互联网，并通过从客户端到 internet 3481 3478 的 UDP 端口。 TCP 端口用于连接到基于 web 的内容，如 SharePoint Online，Exchange 在线学习，以及团队聊天服务。
通过这些 TCP 端口还连接的插件和连接器。 四个 UDP 端口用于介质，例如，音频和视频，以确保它们正确流动。

打开这些端口对于可靠的团队部署至关重要。 封堵这些端口不支持和媒体质量的影响。

如果您的组织要求您指定确切的 IP 地址范围和域都应该向其打开这些端口，您可以限制的目标 IP 地址范围和域为这些端口。 确切的端口的列表，协议和 IP 地址范围，请参阅[Office 365 的 Url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。
如果您选择限制的目标 IP 地址范围和域，您必须确保您保留的端口和范围列表最新因为它们可能会更改。 您可以订阅[该 RSS 源](https://go.microsoft.com/fwlink/p/?linkid=236301)发生更改时进行更新。 它也是很好的做法，以测试是否通过定期运行[Skype 业务网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)打开所有端口。 您可以了解有关此工具的功能的详细信息在下一节中。

在要部署的代理服务器，我们建议您绕过代理服务器的所有团队服务。 虽然使用代理可能起作用，就极有可能的质量将会降低由于强制媒体的使用而不是 UDP TCP。 代理服务器，绕过有关的详细信息，请参阅[Office 365 的 Url 和 IP 地址范围](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>测试网络

已经完成规划和网络准备之后 — — 包括升级的带宽和在防火墙中的打开端口 — 您应测试您的网络性能。 该测试将结果绘制清楚任何网络优化或补救所需的音频会议或电话系统调用计划实施的成功。

您可以下载[Skype 业务网络评估工具](https://www.microsoft.com/download/details.aspx?id=53885)来测试您的网络是否准备好团队。 该工具提供了双重的功能： 它可以测试是否已打开正确的端口，并且它可以测试网络障碍。

下载并安装该工具之后，您可以找到它在 c:\\程序文件\\Microsoft Skype 业务网络评估工具。 该目录中包含有关如何使用该工具，Usage.docx 的详细的指导。

### <a name="test-for-opened-ports"></a>打开端口的测试

打开一个命令提示符窗口并定位到网络评估工具目录输入**cd c:\\程序文件\\Microsoft Skype 业务网络评估工具**。 在命令提示符下，输入**networkassessmenttool.exe /connectivitycheck**开始打开端口测试

运行后检查，该工具将显示消息"验证成功完成"或报告已阻止的端口上。
它还生成一个文件，该文件命名为 Connectivity_results.txt，其中包含该工具的输出并将其存储在 %userprofile%\\应用程序数据\\本地\\microsoft Skype 业务网络评估工具\\目录。

我们建议您运行定期以确保端口已打开，并且可以正常连接检查。

### <a name="test-for-network-impairments"></a>测试网络障碍

为了提高用户满意度，应该限制网络上任何障碍。
最常见的网络障碍被延迟 （等待时间）、 数据包丢失，并且抖动：

-   **延迟时间：**这是获得点 A 到点 B 网络 IP 数据包所需的时间。 这种网络传播延迟实质上限制到两个点光源，包括额外的系统开销之间采取的各种路由器的速度之间的物理距离。
    单向或往返时间延迟的衡量标准。

-   **数据包丢失**： 这通常指在给定的时间窗口中丢失的数据包的百分比。 数据包丢失率直接影响语音质量 — — 小，从单个丢失几乎没有影响到背对背突发包丢失的数据包导致音频来完全切除。

-   **间数据包到达时抖动或只是抖动：**这是连续数据包之间的延迟的平均变化。 大多数现代 VoIP 软件，包括 Skype 业务，可以适应抖动缓冲通过某些级别。 它是抖动的只有当抖动超过缓冲参与者会注意到的影响。

这些障碍中的最大值所述[介质质量和网络连接的性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。
当测试有这些障碍，我们来区分两个独立的网段：

-   *边缘线段*是路由器居住在其中的段。 这是最接近的逻辑网络段连接到互联网在每个位置。 在大多数情况下，这是路由器，或可能是一个外围网络 （也称为*DMZ*、*非军事区*和*屏蔽子网*） 的连接点。 这一段和 internet 之间发生影响路由器的设备没有进一步通信。

-   *客户端网段*是客户机驻留在其中的逻辑网络段。

应通过网络评估工具来测试这两个领域。 若要测试此段，定位到的目录并输入**networkassessmenttool.exe**命令提示符处。 结果写入一个名为 Results.tsv，文件，则可以为每个段的[要求](https://docs.microsoft.com/en-us/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance?ui=en-US&rs=en-US&ad=US)进行比较。

请注意这两个领域，必须满足高质量部署的要求。 我们建议您运行该工具的一个小时内多次直才能清楚地表明您的网络性能。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>网络更新

如果带宽规划、 端口测试或网络要求测试的结果显示您当前的网络部署团队之前，需要对其进行修正，可以通过多种方法完成此操作：

-   没有足够的带宽，升级连接以便可以排到 Office 365 的通信而没有影响。

-   有关被阻止的端口更改防火墙规则并重新测试端口。

-   对于网络障碍始终执行根本原因分析。

服务质量 (QoS) 可用于通过的优先排序和分隔的通信来战役障碍。 有些组织选择部署 QoS 来克服带宽问题或限制流的流量的量。 这将不会提高质量，并将导致新的问题。 网络障碍超过要求时，应始终执行根本原因分析。 QoS 是解决方案。
有关详细信息，请参阅[Microsoft 小组中的服务质量](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)。

>[!NOTE]
>很多网络随由于升级、 扩展或其他业务要求的时间。 确保让您的操作过程来维护这些区域作为服务管理计划的一部分。


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>决策点</td><td><ul><li>谁将负责完成正确的网络评估跨所有网络段和组织位置？</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>后续步骤</td><td><ul><li>您可以执行详细的网络评估，以帮助确保您的网络是 Microsoft 小组部署准备工作就绪。 有关详细信息，请参阅[网络就绪性评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)。</li><li>执行网络修正根据每个网段的网络就绪状态评估的结果。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->