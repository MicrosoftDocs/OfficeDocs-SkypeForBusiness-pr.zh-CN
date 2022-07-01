---
title: 在 Microsoft Teams 中实施服务质量
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何在 Microsoft Teams 中为组织的服务质量 (QoS) 准备网络。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6015c7b7cf1e7be5bc6b9b3e1fe0577a7f707377
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564140"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>在 Microsoft Teams 中实现服务质量 (QoS) 

Microsoft Teams 中的服务质量 (QoS) 允许对网络延迟敏感的实时网络流量 (例如，语音或视频流) 在不太敏感 (（如下载新应用）的流量前“排成一排”，因为下载新应用时需要多下载一秒并不大) 。 QoS 使用 Windows 组策略 对象和基于端口的访问控制列表来识别和标记实时流中的所有数据包。 这有助于网络为语音、视频和屏幕共享流提供网络带宽的专用部分。

如果支持遇到本文中所述任何问题的大量用户，则可能需要实现 QoS。 用户很少的小型企业可能不需要 QoS，但即使存在，也应有所帮助。

如果没有某种形式的 QoS，你可能会在语音和视频中看到以下质量问题：

- 抖动 - 以不同速率到达的媒体数据包，这可能会导致调用中缺少单词或音节
- 数据包丢失 – 数据包被丢弃，这还可能导致语音质量较低且难以理解语音
- 延迟往返时间 (RTT) - 媒体数据包需要很长时间才能到达目的地，这会导致双方在对话中出现明显的延迟，并导致人们互相交谈

解决这些问题的最不复杂的方法是增加数据连接的大小，无论是内部连接还是 Internet 连接。 由于这通常成本过高，因此 QoS 提供了一种更有效地管理资源的方法，而不是添加带宽。 若要解决质量问题，建议先使用 QoS，然后仅在必要时添加带宽。

若要使 QoS 有效，必须在整个组织中应用一致的 QoS 设置。 无法支持 QoS 优先级的路径的任何部分都可能会降低通话、视频和屏幕共享的质量。 这包括将设置应用到所有用户电脑或设备、网络交换机、Internet 路由器和 Teams 服务。

_图 1.组织网络与 Microsoft 365 或Office 365服务之间的关系_

![网络和服务之间的关系图示。](media/Qos-in-Teams-Image1.png "组织网络与 Microsoft 365 或Office 365服务之间的关系：本地网络和设备与互连网络连接，而互连网络又与 Microsoft 365 或Office 365云语音和音频会议服务连接。")

## <a name="qos-implementation-checklist"></a>QoS 实现清单

在高级别上，请执行以下操作来实现 QoS：

1. [确保网络已准备就绪](#make-sure-your-network-is-ready)。

1. [选择 QoS 实现方法](#select-a-qos-implementation-method)。

1. [为每个媒体类型选择初始端口范围](#choose-initial-port-ranges-for-each-media-type)。

1. 实现 QoS 设置：
   1. 在客户端上，使用组策略对象 (GPO) [设置客户端设备端口范围和标记](QoS-in-Teams-clients.md)。
   2. 在路由器 (请参阅制造商文档) 或其他网络设备。 这可能包括基于端口的访问控制列表 (ACL) 或只是定义 QoS 队列和 DSCP 标记，或所有这些。

      > [!IMPORTANT]
      > 建议使用客户端源端口以及“any”的源和目标 IP 地址来实现这些 QoS 策略。 这将捕获内部网络上的传入和传出媒体流量。  

   3. [设置要如何处理 Teams 会议的媒体流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。

5. 通过分析网络上的 Teams 流量[来验证 QoS 实现](#validate-your-qos-implementation)。

在准备实施 QoS 时，请记住以下准则：

- Microsoft 365 的最短路径最好。
- 关闭端口只会导致质量下降。
- 不建议在代理之间设置任何障碍。
- 限制跃点数：
  - 客户端到网络边缘 - 3 到 5 个跃点
  - ISP 到 Microsoft 网络边缘 – 3 跃点
  - Microsoft 网络边缘到最终目标 - 无关紧要

有关配置防火墙端口的信息，请转到[Office 365 URL 和 IP 范围](office-365-urls-ip-address-ranges.md)。

## <a name="make-sure-your-network-is-ready"></a>确保网络已准备就绪

如果正在考虑 QoS 实现，则应已确定带宽要求和其他 [网络要求](prepare-network.md)。
  
整个网络的交通拥堵将极大地影响媒体质量。 缺乏带宽会导致性能下降和用户体验不佳。 随着 Teams 采用率和使用率的增长，使用报告、 [每用户呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)和 [呼叫质量仪表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md) 来识别问题，然后使用 QoS 和选择性带宽添加进行调整。

### <a name="vpn-considerations"></a>VPN 注意事项

QoS 仅在调用方之间的所有链接上实现时才按预期工作。 如果在内部网络上使用 QoS，并且用户从远程位置登录，则只能在内部托管网络中确定优先级。 尽管远程位置可以通过实现虚拟专用网络 (VPN) 来接收托管连接，但 VPN 本质上会增加数据包开销，并导致实时流量延迟。 建议避免通过 VPN 运行实时通信流量。

在具有跨大洲的托管链接的全局组织中，我们强烈建议使用 QoS，因为与 LAN 相比，这些链接的带宽有限。

## <a name="introduction-to-qos-queues"></a>QoS 队列简介

若要提供 QoS，网络设备必须具有对流量进行分类的方法，并且必须能够将语音或视频与其他网络流量区分开来。

当网络流量进入路由器时，流量将放置在队列中。 如果未配置 QoS 策略，则只有一个队列，并且所有数据都被视为具有相同优先级的先入先出。 这意味着语音流量 (非常敏感的延迟) 可能会卡在流量后面，其中延迟几毫秒不会成为问题。

实现 QoS 时，将使用多个拥塞管理功能之一定义多个队列，例如 Cisco 的优先队列和 [基于类的加权公平队列 (CBWFQ) ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 和避免拥塞功能，例如 [加权随机早期检测 (WRED) ](https://en.wikipedia.org/wiki/Weighted_random_early_detection)。

_图 2.QoS 队列示例_

![QoS 队列和带宽划分的插图。](media/Qos-in-Teams-Image2.png "可用带宽总数除以已分配了不同优先级的多个队列（音频、视频和其他流量）。")

一个简单的类比是，QoS 在数据网络中创建虚拟“拼车通道”，因此某些类型的数据永远不会或很少遇到延迟。 创建这些通道后，可以调整其相对大小并更有效地管理拥有的连接带宽，同时仍为组织的用户提供业务级体验。

## <a name="select-a-qos-implementation-method"></a>选择 QoS 实现方法

可以通过基于端口的标记实现 QoS，在网络路由器上使用访问控制列表 (ACL) 。 基于端口的标记是最可靠的方法，因为它适用于混合 Windows、Mac 和 Linux 环境，并且是最容易实现的方法。 移动客户端不提供使用 DSCP 值标记流量的机制，因此需要此方法。  

使用基于端口的标记，网络的路由器会检查传入数据包，如果数据包是使用特定端口或端口范围到达的，它会将其标识为特定媒体类型，并将其置于该类型的队列中，并向 IP 数据包标头添加预先确定的 [DSCP](https://tools.ietf.org/html/rfc2474) 标记，以便其他设备可以识别其流量类型，并将其放在队列中的优先级。

尽管基于端口的标记可跨平台工作，但它只会将 WAN 边缘的流量标记为 (不会一直指向客户端计算机) 并产生管理开销。 有关实现此方法的说明，请参阅路由器制造商提供的文档。

### <a name="insert-dscp-markers"></a>插入 DSCP 标记

还可以使用组策略对象 (GPO) 来实现 QoS，以指示客户端设备在 IP 数据包标头中插入 DSCP 标记，将其标识为特定类型的流量 (例如语音) 。 路由器和其他网络设备可以配置为识别此值，并将流量置于单独的、优先级较高的队列中。

尽管此方案完全有效，但它仅适用于已加入域的 Windows 客户端。 任何不是已加入域的 Windows 客户端的设备都不会启用 DSCP 标记。 其他客户端（例如运行 macOS 的客户端）具有硬编码标记，并且始终会标记流量。

有利的一面是，通过 GPO 控制 DSCP 标记可确保所有已加入域的计算机都收到相同的设置，并且只有管理员才能管理它们。 可以使用 GPO 的客户端将在源设备上标记，然后配置的网络设备可以识别 DSCP 代码的实时流，并为其提供适当的优先级。

### <a name="best-practice"></a>最佳做法

如果可能，建议在终结点结合使用 DSCP 标记，并在路由器上结合使用基于端口的 ACL。 使用 GPO 捕获大多数客户端，以及使用基于端口的 DSCP 标记将确保移动、Mac 和其他客户端仍可获得至少部分)  (QoS 处理。

DSCP 标记可以比作邮寄邮票，这些邮票向邮政工作人员指示传送是多么紧迫，以及如何最好地对它进行排序以快速交付。 将网络配置为优先处理实时媒体流后，丢失的数据包和延迟数据包应会大大减少。

网络中的所有设备都使用相同的分类、标记和优先级后，可以通过更改分配给用于每个流量类型的队列的端口范围的大小来减少或消除延迟、丢弃的数据包和抖动。 从 Teams 的角度来看，最重要的配置步骤是数据包的分类和标记。 但是，要使端到端 QoS 成功，还需要将应用程序的配置与基础网络配置进行仔细的对齐。 完全实现 QoS 后，持续管理是根据组织的需求和实际使用情况调整分配给每个流量类型的端口范围的问题。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>为每个媒体类型选择初始端口范围

DSCP 值告诉相应配置的网络提供数据包或流的优先级，是客户端分配的 DSCP 标记，还是根据 ACL 设置分配网络本身。 每个媒体工作负载都获取自己的唯一 DSCP 值 (其他服务可能允许工作负载共享 DSCP 标记、Teams 不) 以及用于每个媒体类型的已定义和单独的端口范围。 其他环境可能已制定现有的 QoS 策略，这将有助于确定网络工作负荷的优先级。

不同实时流式处理工作负荷的端口范围的相对大小设置专用于该工作负荷的总可用带宽的比例。 要返回我们之前的邮政类比：一封带有“航空邮件”邮票的信可能会在一小时内到达最近的机场，而一个标有“大容量邮件”标记的小包裹可以等待一天，然后乘坐一系列卡车在陆地上旅行。

_建议的初始端口范围_

|媒体流量类型| 客户端源端口范围 |协议|DSCP 值|DSCP 类|
|:--- |:--- |:--- |:--- |:--- |
|音频| 50,000–50,019|TCP/UDP|46|加速转发 (EF)|
|视频| 50,020–50,039|TCP/UDP|34|保证转发 (AF41)|
|应用程序/屏幕共享| 50,040–50,059|TCP/UDP|18|保证转发 (AF21)|
||||||

使用以下设置时，请注意以下事项：

- 如果计划将来实现 ExpressRoute，但尚未实现 QoS，建议遵循指南，使 DSCP 值在发件人到接收方时相同。

- 所有客户端（包括移动客户端和 Teams 设备）都将使用这些端口范围，并且会受到你实施的任何使用这些源端口范围的 DSCP 策略的影响。 唯一将继续使用动态端口的客户端是基于浏览器的客户端 (客户端，这些客户端允许参与者使用浏览器) 加入会议。

- 尽管 Mac 客户端使用相同的端口范围，但它也对音频 (EF) 和视频使用硬编码值 (AF41) 。 这些值不可配置。

- 如果以后需要调整端口范围以提高用户体验，则端口范围不能重叠，并且应该彼此相邻。

## <a name="migrate-qos-to-teams"></a>将 QoS 迁移到 Teams

如果之前已部署 Skype for Business Online，包括 QoS 标记和端口范围，现在正在部署。 Teams、Teams 将尊重现有配置，并将使用与Skype for Business客户端相同的端口范围和标记。 在大多数情况下，不需要其他配置。

> [!NOTE]
> 如果通过组策略使用应用程序名称 QoS 标记，则必须将Teams.exe添加为应用程序名称。

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>使用 PowerShell 在 Windows 上的 Teams 中实现 QoS

**为音频设置 QoS**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**为视频设置 QoS**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**设置用于共享的 QoS**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>在 Teams 管理中心管理源端口

在 Teams 中，应主动管理不同工作负荷使用的 QoS 源端口，并根据需要进行调整。 引用 [每个媒体类型的“选择初始端口范围](#choose-initial-port-ranges-for-each-media-type)”中的表，端口范围是可调整的，但 DSCP 标记不可配置。 实现这些设置后，可能会发现给定媒体类型需要的端口或多或少。 [每个用户呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md) 和 [呼叫质量仪表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md) 应用于在 Teams 实施后做出调整端口范围的决定，并根据需求变化定期进行。

> [!NOTE]
> 如果已基于源端口范围和 Skype for Business Online 的 DSCP 标记配置了 QoS，则相同的配置将应用于 Teams，并且无需对映射进行进一步的客户端或网络更改，但可能需要[设置 Teams 中使用的区域](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)，以匹配为 Skype for Business Online 配置的内容。

如果之前已在本地部署Skype for Business Server，则可能需要重新检查 QoS 策略。 调整策略以匹配已验证的端口范围设置，为 Teams 提供高质量的用户体验。

## <a name="validate-your-qos-implementation"></a>验证 QoS 实现

若要使 QoS 有效，GPO 设置的 DSCP 值需要出现在调用的两端。 通过分析 Teams 客户端生成的流量，可以验证当 Teams 工作负荷流量通过网络移动时 DSCP 值是否未更改或被剥离。

最好是在网络出口点捕获流量。 可以在交换机或路由器上使用端口镜像来帮助解决此问题。

## <a name="implement-qos-for-other-devices"></a>为其他设备实现 QoS

阅读这些主题，了解如何实现适用于 Intune、Surface、iOS、Android 和 Mac 的 QoS

- [适用于 Surface Hub 2S 的 QoS](/surface-hub/surface-hub-2s-manage-intune)

- [适用于 Surface Hub 的 QoS](/surface-hub/surface-hub-qos)

- [适用于 iOS、Android 和 Mac 的 QoS](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>相关主题

- [视频：网络规划](https://aka.ms/teams-networking)

- [为 Microsoft Teams 准备组织的网络](prepare-network.md)

- [在 Teams 客户端中实现 QoS](QoS-in-Teams-clients.md)