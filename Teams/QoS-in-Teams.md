---
title: 在 Microsoft Teams 中实施服务质量
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何在 Microsoft Teams 中为组织的服务质量和 QoS () 网络。
localization_priority: Normal
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
ms.openlocfilehash: 87f3577d34df6d2b0665a45b60b441d29cd0265b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092610"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>在 Microsoft Teams 中 (QoS) 服务质量

Microsoft Teams 中的服务质量 (QoS) 允许对网络延迟敏感的实时网络流量 (例如，语音或视频流) 在不太敏感的 (例如下载新应用（其中额外下载秒数不是大型) ）的流量前"直接排队"。 QoS 使用 Windows 组策略对象和基于端口的访问控制列表来识别并标记实时流中的所有数据包。 这有助于网络为语音、视频和屏幕共享流提供专用的网络带宽部分。

如果你支持大量遇到本文所述任何问题的用户，则你可能需要实现 QoS。 用户数很少的小型企业可能不需要 QoS，但即使存在，它也应该很有用。

如果没有某种形式的 QoS，你可能会在语音和视频中看到以下质量问题：

- 抖动 - 媒体数据包以不同的速率到达，这可能会导致通话中缺少字词或音节
- 数据包丢失 - 丢弃数据包，这还可能导致语音质量降低且难以理解语音
- RTT (延迟的往返) – 媒体数据包到达其目的地需要很长时间，这导致对话中双方之间的明显延迟，并且导致人们相互交谈

解决这些问题最不复杂的方法就是增加内部和外部到 Internet 的数据连接的大小。 由于这通常成本过高，QoS 提供了一种更有效地管理资源的方法，而不是增加带宽。 若要解决质量问题，建议首先使用 QoS，然后仅在必要时添加带宽。

若要使 QoS 生效，必须在整个组织中应用一致的 QoS 设置。 路径中无法支持 QoS 优先级的任何部分都可能会降低通话、视频和屏幕共享的质量。 这包括将设置应用到每个用户电脑或设备、网络交换机、路由器到 Internet 和 Teams 服务。

_图 1.组织网络与 Microsoft 365 或 Office 365 服务之间的关系_

![网络与服务之间的关系图示](media/Qos-in-Teams-Image1.png "组织网络与 Microsoft 365 或 Office 365 服务之间的关系：本地网络和设备通过互连网络进行连接，而互连网络又与 Microsoft 365 或 Office 365 云语音和音频会议服务连接。")

## <a name="qos-implementation-checklist"></a>QoS 实现清单

在高级别上，执行以下操作来实现 QoS：

1. [确保你的网络已准备就绪](#make-sure-your-network-is-ready)。

1. [选择 QoS 实现方法](#select-a-qos-implementation-method)。

1. [选择每个媒体类型的初始端口范围](#choose-initial-port-ranges-for-each-media-type)。

1. 实现 QoS 设置：
   1. 在使用组策略对象的客户端上 (GPO) [设置客户端设备端口范围和标记](QoS-in-Teams-clients.md)。
   2. 在路由器 (请参阅制造商文档) 或其他网络设备。 这可能包括基于端口的访问控制列表 (ACL) 只需定义 QoS 队列和 DSCP 标记，或者所有这些。

      > [!IMPORTANT]
      > 我们建议使用客户端源端口以及"任意"的源和目标 IP 地址实施这些 QoS 策略。 这会捕获内部网络上传入和传出的媒体流量。  

   3. [设置如何处理 Teams 会议的媒体流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。

5. [通过分析网络上 Teams](#validate-your-qos-implementation) 流量来验证 QoS 实现。

准备实施 QoS 时，请记住以下准则：

- 最好是最短的 Microsoft 365 路径。
- 关闭端口只会导致质量下降。
- 不建议在两者之间设置任何障碍，例如代理。
- 限制跃点数：
  - 客户端到网络边缘 – 3 到 5 个跃点
  - ISP 到 Microsoft 网络边缘 – 3 个跃点
  - Microsoft 网络边缘到最终目标 – 不相关

有关配置防火墙端口的信息，请转到 Office [365 URL 和 IP 范围](office-365-urls-ip-address-ranges.md)。

## <a name="make-sure-your-network-is-ready"></a>确保网络已准备就绪

如果你正在考虑 QoS 实现，你应该已经确定了你的带宽要求和其他 [网络要求](prepare-network.md)。
  
网络的流量拥塞将极大地影响媒体质量。 带宽不足会导致性能下降和用户体验不佳。 随着 Teams 采用和使用情况的增长，使用报告[](use-call-analytics-to-troubleshoot-poor-call-quality.md)、每个用户的呼叫分析和呼叫质量仪表板[ (CQD) ](turning-on-and-using-call-quality-dashboard.md)来识别问题，然后使用 QoS 和选择性带宽添加进行调整。

### <a name="vpn-considerations"></a>VPN 注意事项

QoS 仅在呼叫方之间的所有链接上实现时，才能正常使用。 如果在内部网络上使用 QoS，并且用户从远程位置登录，则只能在内部托管网络中设置优先级。 尽管远程位置可以通过实现虚拟专用网络 (VPN) 来接收托管连接，但 VPN 本身会增加数据包开销，并造成实时流量的延迟。 建议避免通过 VPN 运行实时通信流量。

在具有跨大洲的托管链接的全球组织中，我们强烈建议使用 QoS，因为这些链接的带宽与 LAN 相比受到限制。

## <a name="introduction-to-qos-queues"></a>QoS 队列简介

若要提供 QoS，网络设备必须具有一种对流量进行分类的方法，并且必须能够将语音或视频与其他网络流量相区分。

当网络流量进入路由器时，流量将放入队列。 如果未配置 QoS 策略，则只有一个队列，所有数据都被视为优先级相同的"先入先出"。 这意味着语音流量 (对延迟非常敏感) 可能会卡在流量后面，因为延迟数毫秒不会是问题。

实现 QoS 时，可以使用多种拥塞管理功能之一来定义多个队列，例如 Cisco 的优先级队列和基于类的加权公平队列[ (CBWFQ) ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)和拥塞规避功能，例如加权随机早期检测[ (WRED) 。 ](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_图 2.QoS 队列示例_

![QoS 队列和带宽划分的图示](media/Qos-in-Teams-Image2.png "总可用带宽在分配了不同优先级的多个队列（音频、视频和其他流量）之间划分。")

一个简单的类比是 QoS 在数据网络中创建虚拟"拼车通道"，以便某些类型的数据永远不会或很少遇到延迟。 创建这些通道后，可以调整其相对大小并更有效地管理你拥有的连接带宽，同时仍为组织的用户提供企业级体验。

## <a name="select-a-qos-implementation-method"></a>选择 QoS 实现方法

可以通过基于端口的标记实现 QoS，使用访问控制列表 (网络路由器) ACL。 基于端口的标记是最可靠的方法，因为它适用于混合 Windows、Mac 和 Linux 环境，并且最容易实现。 移动客户端不提供使用 DSCP 值标记流量的机制，因此需要此方法。  

使用基于端口的标记，网络的路由器会检查传入的数据包，如果数据包使用特定端口或端口范围到达，它将它标识为特定媒体类型，并放在该类型的队列中，将预先确定的 [DSCP](https://tools.ietf.org/html/rfc2474) 标记添加到 IP 数据包标头，以便其他设备可以识别其流量类型，并在其队列中赋予其优先级。

尽管基于端口的标记可以跨平台工作，但它仅标记 WAN 边缘 (到客户端计算机的流量，) 产生管理开销。 有关实现此方法的说明，请参阅路由器制造商提供的文档。

### <a name="insert-dscp-markers"></a>插入 DSCP 标记

您还可以通过使用组策略对象 (GPO) 来指示客户端设备在标识为特定流量类型的 IP 数据包标头中插入 DSCP 标记 (例如语音) 。 可以将路由器和其他网络设备配置为识别这一点，将流量放在一个单独的、优先级更高的队列中。

尽管此方案完全有效，但它仅适用于已加入域的 Windows 客户端。 任何未加入域的 Windows 客户端的设备将不会启用 DSCP 标记。 其他客户端（例如运行 macOS 的客户端）具有硬编码的标记，并且始终标记流量。

从另一方面来说，通过 GPO 控制 DSCP 标记可确保所有已加入域的计算机接收相同的设置，并且只有管理员可以管理这些设置。 可以使用 GPO 的客户端将在原始设备上进行标记，然后配置的网络设备可以通过 DSCP 代码识别实时流，并赋予其适当的优先级。

### <a name="best-practice"></a>最佳做法

我们建议结合使用终结点上的 DSCP 标记和路由器上基于端口的 ACL（如果可能）。 使用 GPO 捕获大多数客户端，同时使用基于端口的 DSCP 标记将确保移动、Mac 和其他客户端仍将获得 QoS 处理 (至少部分) 。

DSCP 标记可以比作邮政戳记，它向邮政工作人员指示交付的紧急性，以及如何以最佳方式对它进行排序以加快交付。 将网络配置为优先处理实时媒体流后，丢失的数据包和延迟的数据包应大大减少。

一旦网络内的所有设备使用相同的分类、标记和优先级，则通过更改分配给每个流量类型的队列的端口范围的大小，可以减少或消除延迟、丢弃数据包和抖动。 从 Teams 的角度来看，最重要的配置步骤是数据包的分类和标记。 但是，若要使端到端 QoS 成功，还需要仔细将应用程序的配置与基础网络配置保持一致。 完全实施 QoS 后，持续管理就是根据组织的需求和实际使用情况调整分配给每种流量类型的端口范围的问题。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>选择每种媒体类型的初始端口范围

DSCP 值告知相应配置的网络为数据包或流提供什么优先级，无论 DSCP 标记是由客户端分配还是网络本身基于 ACL 设置分配。 每个媒体工作负荷获取其自己的唯一 DSCP 值 (其他服务可能允许工作负荷共享 DSCP 标记，Teams 不会) 以及用于每种媒体类型的已定义和单独端口范围。 其他环境可能有现有的 QoS 策略，可帮助确定网络工作负荷的优先级。

不同实时流式处理工作负荷的端口范围的相对大小设置专用于该工作负荷的总可用带宽的比例。 要返回到我们之前的邮政类比：带"Air Mail"戳记的信函可能在一小时内到达最近的机场，而标有"批量邮件"标记的小包裹可以等待一天，然后再在一系列卡车上着陆。

_建议的初始端口范围_

|媒体流量类型| 客户端源端口范围 |协议|DSCP 值|DSCP 类|
|:--- |:--- |:--- |:--- |:--- |
|音频| 50,000–50,019|TCP/UDP|46|加速转发 (EF)|
|视频| 50,020–50,039|TCP/UDP|34|保证转发 (AF41)|
|应用程序/屏幕共享| 50,040–50,059|TCP/UDP|18|保证转发 (AF21)|
||||||

使用这些设置时请注意以下事项：

- 如果计划在将来实现 ExpressRoute，但尚未实现 QoS，我们建议遵循指导，以便从发送方到接收方的 DSCP 值相同。

- 所有客户端（包括移动客户端和 Teams 设备）都将使用这些端口范围，并且将受你实施的任何使用这些源端口范围的 DSCP 策略的影响。 将继续使用动态端口的唯一客户端是基于浏览器的客户端 (允许参与者使用其浏览器) 。

- 虽然 Mac 客户端使用相同的端口范围，但它也使用音频的硬编码值 (EF) 和视频 (AF41) 。 这些值不可配置。

- 如果以后需要调整端口范围以改善用户体验，则端口范围不能重叠，并且应该彼此相邻。

## <a name="migrate-qos-to-teams"></a>将 QoS 迁移到 Teams

如果你之前部署了 Skype for Business Online（包括 QoS 标记和端口范围），并且现在正在部署。 Teams、Teams 将尊重现有配置，并使用与 Skype for Business 客户端相同的端口范围和标记。 在大多数情况下，不需要其他配置。

> [!NOTE]
> 如果通过组策略使用应用程序名称 QoS 标记，则必须Teams.exe作为应用程序名称。

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>使用 PowerShell 在 Windows 上的 Teams 中实现 QoS

**为音频设置 QoS**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**为视频设置 QoS**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**设置 QoS 进行共享**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>在 Teams 管理中心管理源端口

在 Teams 中，应主动管理不同工作负荷使用的 QoS 源端口，并根据需要进行调整。 引用为 [每种媒体类型](#choose-initial-port-ranges-for-each-media-type)选择初始端口范围中的表，端口范围是可调整的，但 DSCP 标记不可配置。 实现这些设置后，你可能会发现给定媒体类型需要更多或更少的端口。 [应该使用](use-call-analytics-to-troubleshoot-poor-call-quality.md) 基于用户的呼叫分析和呼叫质量仪表板 [ (CQD) ](turning-on-and-using-call-quality-dashboard.md) 来做出在 Teams 实施后调整端口范围的决策，并定期根据需求变化进行调整。

> [!NOTE]
> 如果已基于 Skype for Business Online 的源端口范围和 DSCP 标记配置 QoS，则相同的配置将应用于 Teams，并且无需进一步对映射进行客户端或网络更改，不过，您可能需要设置 [Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 中使用的范围，以匹配为 Skype for Business Online 配置的范围。

如果以前在本地部署了 Skype for Business Server，可能需要重新检查 QoS 策略。 调整策略以匹配已验证的端口范围设置，为 Teams 提供高质量的用户体验。

## <a name="validate-your-qos-implementation"></a>验证 QoS 实现

若要使 QoS 生效，GPO 设置的 DSCP 值需要在呼叫的两端显示。 通过分析 Teams 客户端生成的流量，可以验证当 Teams 工作负荷流量在网络中移动时，是否未更改或去除 DSCP 值。

最好是捕获网络出口点的流量。 可以使用交换机或路由器上的端口镜像来帮助实现此要求。

## <a name="implement-qos-for-other-devices"></a>为其他设备实现 QoS

阅读这些主题，了解实现适用于 Intune、Surface、iOS、Android 和 Mac 的 QoS 的信息

- [Surface Hub 2S 的 QoS](/surface-hub/surface-hub-2s-manage-intune)

- [Surface Hub 的 QoS](/surface-hub/surface-hub-qos)

- [适用于 iOS、Android 和 Mac 的 QoS](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>相关主题

- [视频：网络规划](https://aka.ms/teams-networking)

- [为 Microsoft Teams 准备组织的网络](prepare-network.md)

- [在 Teams 客户端中实现 QoS](QoS-in-Teams-clients.md)