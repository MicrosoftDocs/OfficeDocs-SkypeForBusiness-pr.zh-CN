---
title: 在 Microsoft Teams 中实施服务质量
author: LolaJacobsen
ms.author: lolaj
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何为 Microsoft 团队中的服务质量（QoS）准备组织的网络。
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
ms.openlocfilehash: ef2fca810a7125c4150ff4de2c3eea8fd7970d2e
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085278"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>在 Microsoft 团队中实施服务质量（QoS）

Microsoft 团队中的服务质量（QoS）是一种使实时网络流量对网络延迟（例如，语音或视频流）敏感的方式，以便在不太敏感的通信（如下载新应用，要下载的额外第二秒）之前 "在行中剪切"。 QoS 在实时流中标识和标记所有数据包（使用 Windows 组策略对象和名为基于端口的访问控制列表的路由功能，有关这些列表的详细信息），然后可帮助你的网络提供语音、视频和屏幕共享流，以流出专用的网络带宽部分。

如果你支持一组大型用户，并且遇到下面所述的任何问题，则可能需要实现 QoS。 用户数较少的小型企业可能不需要 QoS，但甚至应该有帮助。

如果没有某种形式的 QoS，您可能会在语音和视频中看到以下质量问题：

- 抖动-媒体数据包以不同的费率收取，这可能会导致通话中缺少单词或音节
- 数据包丢失-丢弃的数据包，还可能导致更低的语音质量，并且难以理解语音
- 延迟的往返时间（RTT）-媒体数据包在到达其目标时花费很长时间，从而导致对话中两方之间出现明显延迟，从而导致用户相互通话

解决这些问题的最简单的方法是在内部和 internet 上增加数据连接的大小。 由于这通常是成本不受影响的，因此 QoS 提供了一种更高效地管理您所拥有的资源（而不是增加带宽）的方法。 若要解决质量问题，我们建议你首先使用 QoS，然后仅在必要时才添加带宽。

为了使 QoS 有效，你将在整个组织中应用一致的 QoS 设置，因为无法支持 QoS 优先级的路径的任何部分可能会降低呼叫、视频和屏幕共享的质量。 这包括将设置应用到所有用户电脑或设备、网络交换机、互联网路由器以及团队服务。

_图1。组织的网络与 Microsoft 365 或 Office 365 服务之间的关系_

![网络和服务之间的关系的插图](media/Qos-in-Teams-Image1.png "组织的网络和 Microsoft 365 或 Office 365 服务之间的关系：本地网络和设备与互连网络连接，后者又与 Microsoft 365 或 Office 365 云语音和音频会议服务连接。")

## <a name="qos-implementation-checklist"></a>QoS 实施清单

在高级别上，执行以下操作来实现 QoS：

1. [请确保您的网络已准备就绪](#make-sure-your-network-is-ready)

1. [选择 QoS 实现方法](#select-a-qos-implementation-method)

1. [为每种媒体类型选择初始端口范围](#choose-initial-port-ranges-for-each-media-type)

1. 实施 QoS 设置：
   1. 在使用 GPO[设置客户端设备端口范围和标记](QoS-in-Teams-clients.md)的客户端上
   2. 在路由器上（请参阅制造商文档）或其他网络设备。 这可能包括基于端口的 Acl，或者仅定义 QoS 队列和 DSCP 标记，或者所有这些操作。

      > [!IMPORTANT]
      > 我们建议使用客户端源端口和来源和目标 IP 地址 "any" 实现这些 QoS 策略。 这将在内部网络上捕获传入和传出媒体流量。  

   3. [设置你希望如何处理团队会议的媒体流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. 通过分析网络上的团队通信来[验证你的 QoS 实施](#validate-your-qos-implementation)情况。

准备实施 QoS 时，请牢记以下准则：

- 最短的 Microsoft 365 路径最短
- 关闭端口仅会导致质量下降
- 不建议在任何情况下（如代理）中的任何障碍
- 限制跃点的数量：
  - 客户端到网络边缘-3 到5个跃点
  - ISP 到 Microsoft network edge –3个跃点
  - Microsoft 网络边缘到最终目标-不相关

有关配置防火墙端口的信息，请转到[Office 365 url 和 IP 范围](office-365-urls-ip-address-ranges.md)。


## <a name="make-sure-your-network-is-ready"></a>请确保您的网络已准备就绪

如果你正在考虑 QoS 实施，你应该已确定带宽要求和其他[网络要求](prepare-network.md)。 
  
网络上的流量拥塞将显著影响媒体质量。 缺少带宽会导致性能下降和用户体验较差。 当团队采纳和使用增加时，请使用 "报告"、"[每用户呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)" 和 "[呼叫质量" 仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md)来识别问题，然后使用 QoS 和选择性带宽增加进行调整。

### <a name="vpn-considerations"></a>VPN 注意事项

仅当在调用方之间的所有链接上实现时，QoS 才按预期工作。 如果在内部网络上使用 QoS，并且用户从远程位置登录，则只能在内部托管网络中设置优先级。 虽然远程位置可以通过实施虚拟专用网络（VPN）接收托管连接，但 VPN 本身会增加数据包开销并在实时流量中产生延迟。 我们建议你避免通过 VPN 运行实时通信流量。

在具有跨大洲的托管链接的全球组织中，我们强烈建议使用 QoS，因为与 LAN 相比，这些链接的带宽受到限制。

## <a name="introduction-to-qos-queues"></a>QoS 队列简介

为了提供 QoS，网络设备必须能够对流量进行分类，并且必须能够将语音或视频与其他网络流量区分开。

当网络流量进入路由器时，流量将放入队列中。 如果未配置 QoS 策略，则仅有一个队列，所有数据将按具有相同优先级的第一项处理。 这意味着语音流量（对延迟非常敏感）可能会陷入通信量不足的情况下，延迟几个额外的毫秒不会出现问题。

当你实现 QoS 时，你可以使用以下几个拥塞管理功能之一定义多个队列（如 Cisco 的优先级队列和[基于类的加权公平队列（CBWFQ）](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)）和拥塞避免功能（如[加权随机检测（WRED）](https://en.wikipedia.org/wiki/Weighted_random_early_detection)）。

_图2。QoS 队列的示例_

![QoS 队列和带宽划分的插图](media/Qos-in-Teams-Image2.png "可用带宽的总可用带宽分为多个队列：音频、视频和其他流量，这些队列已被分配不同的优先级。")

简单的类比是 QoS 在数据网络中创建虚拟的 "carpool 车道"，因此某些类型的数据从不或几乎不会遇到延迟。 创建这些泳道后，您可以调整其相对大小，并更有效地管理您拥有的连接带宽，同时还可以为您的组织的用户提供业务级体验。

## <a name="select-a-qos-implementation-method"></a>选择 QoS 实现方法

你可以使用网络路由器上的访问控制列表（Acl），通过基于端口的标记实现 QoS。 基于端口的标记是最可靠的方法，因为它在混合的 Windows、Mac 和 Linux 环境中工作，并且最容易实现。 移动客户端不提供使用 DSCP 值标记流量的机制，因此它们将需要此方法。  

使用基于端口的标记，你的网络路由器将检查传入的数据包，如果该数据包使用特定的端口或端口范围接收，则它将其标识为特定媒体类型，并将其放入该类型的队列中，将预定义的[DSCP](https://tools.ietf.org/html/rfc2474)标记添加到 IP 数据包标头，以便其他设备可以识别其流量类型，并在其队列中授予其优先级

尽管这在多个平台上有效，但它仅将流量标记为 WAN edge （而不是客户端计算机的任何方式），并创建管理开销。 您应该参考路由器制造商提供的文档，获取有关实施此方法的说明。

### <a name="insert-dscp-markers"></a>插入 DSCP 标记

你还可以通过使用组策略对象（GPO）直接在 IP 数据包标题中插入 DSCP 标记以将 DSCP 标记插入标识为特定类型的流量（例如，语音）来实现 QoS。 路由器和其他网络设备可以配置为识别此项，并将流量放在一个单独的、优先级较高的队列中。

虽然此方案完全有效，但它仅适用于加入域的 Windows 客户端。 任何不是加入域的 Windows 客户端的设备都不会启用 DSCP 标记。 客户端（如 Mac OS）具有硬编码的标记，并且将始终标记流量。

在加号，通过 GPO 控制 DSCP 标记可确保所有加入域的计算机接收相同的设置，并且只有管理员可以管理它们。 可以使用 GPO 的客户端将在原始设备上进行标记，然后配置的网络设备可以通过 DSCP 代码识别实时流并为其提供相应优先级。

### <a name="best-practice"></a>最佳做法

我们建议在路由器上的终结点和基于端口的 Acl 中使用 DSCP 标记组合（如有可能）。 使用组策略对象捕获大多数客户端，同时使用基于端口的 DSCP 标记，可确保移动、Mac 和其他客户端仍会获得 QoS 处理（至少部分）。

DSCP 标记可以是 likened 到邮票，用于向邮政标志指明邮政的重要程度，以及如何对其进行排序以实现快速交付。 将您的网络配置为为实时媒体流提供优先级后，丢失数据包和后期数据包应该会显著降低。

一旦网络中的所有设备使用相同的分类、标记和优先级，就可以通过更改分配给每个流量类型使用的队列的端口范围的大小来减少或消除延迟、丢弃的数据包和抖动。 从 "团队" 角度来看，最重要的配置步骤是对数据包进行分类和标记，但要使端到端 QoS 成功，还需要将应用程序的配置与基础网络配置仔细对齐。 当 QoS 完全实施后，持续管理是根据组织的需求和实际使用情况调整分配给每个流量类型的端口范围的问题。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>为每种媒体类型选择初始端口范围

DSCP 值会将相应的配置的网络通知到相应配置的网络，提供数据包或流的优先级，无论是由客户还是基于 ACL 设置为网络本身分配了 DSCP 标记。 每个媒体工作负荷获取自己的唯一 DSCP 值（其他服务可能允许工作负荷共享 DSCP 标记、团队不支持）以及用于每种媒体类型的定义的和单独的端口范围。 其他环境可能具有现有的 QoS 策略，这将帮助你确定网络工作负荷的优先级。

不同实时流工作负荷的端口范围的相对大小设置专用于该工作负荷的总可用带宽的比例。 若要返回到我们以前的邮政编码，请执行以下操作：带有 "Air Mail" 图章的信函可能会在一个小时内进入最接近的机场，而标记为 "大宗邮件" 的小程序包可以在一天前等待一天。

_推荐的初始端口范围_

|媒体流量类型| 客户端源端口范围 |协议|DSCP 值|DSCP 类|
|:--- |:--- |:--- |:--- |:--- |
|音频| 50,000–50,019|TCP/UDP|46|加速转发 (EF)|
|视频| 50,020–50,039|TCP/UDP|34|保证转发 (AF41)|
|应用程序/屏幕共享| 50,040–50,059|TCP/UDP|18|保证转发 (AF21)|
||||||

使用这些设置时，请注意以下事项：

- 如果你计划在将来实施 ExpressRoute，但尚未实现 QoS，我们建议你按照指南进行操作，以便从发送方到接收方的 DSCP 值相同。
- 所有客户（包括移动客户端和团队设备）将使用这些端口范围，并且将受到你使用这些源端口范围实现的任何 DSCP 策略的影响。 只有基于浏览器的客户端（即允许参与者使用其浏览器加入会议的客户端）才会继续使用动态端口。
- 虽然 Mac 客户端使用相同的端口范围，但它还会将硬编码的值用于音频（EF）和视频（AF41）。 这些值不可配置。
- 如果稍后需要调整端口范围以提高用户体验，则端口范围不会重叠，并且应彼此相邻。

## <a name="migrate-qos-to-teams"></a>将 QoS 迁移到团队

如果你以前已部署 Skype for business Online，包括 QoS 标记和端口范围，并且现在部署团队，团队将考虑现有配置，并将使用相同的端口范围和标记作为 Skype for Business 客户端。 在大多数情况下，不需要额外的配置。

> [!NOTE]
> 如果你通过组策略使用应用程序名称 QoS 标记，则必须添加 Teams.exe 作为应用程序名称。


## <a name="managing-source-ports-in-the-teams-admin-center"></a>管理团队管理中心中的源端口

在团队中，不同工作负荷使用的 QoS 源端口应处于主动管理状态，并根据需要进行调整。 在[选择每个媒体类型的初始端口范围](#choose-initial-port-ranges-for-each-media-type)中引用表，可调整端口范围，但无法配置 DSCP 标记。 实现这些设置后，你可能会发现给定媒体类型需要更多或更少的端口。 [每用户呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)和[通话质量仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md)应该用于决定在团队实施后调整端口范围，以及根据需要定期进行更改。

> [!NOTE]
> 如果你已基于 Skype for business Online 的源端口范围和 DSCP 标记配置了 QoS，则同一配置将应用到团队，并且不需要进一步的客户端或网络更改，但你可能需要[将团队中使用的区域](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)与 skype For business Online 配置相匹配。

如果以前已部署了本地 Skype for business 服务器，你可能需要重新检查 QoS 策略并对其进行调整，以匹配已验证的端口范围设置为团队提供了高质量的用户体验。

## <a name="validate-your-qos-implementation"></a>验证你的 QoS 实施

为了使 QoS 有效，组策略对象设置的 DSCP 值需要存在于调用的两端。 通过分析由团队客户端生成的流量，可以验证当团队工作负载流量通过网络移动时，DSCP 值不会更改或去除。

最好是在网络出口点处捕获流量。 可以在交换机或路由器上使用端口镜像来帮助解决此情况。


## <a name="related-topics"></a>相关主题

[视频：网络规划](https://aka.ms/teams-networking)

[为 Microsoft Teams 准备组织的网络](prepare-network.md)

[在团队客户端中实施 QoS](QoS-in-Teams-clients.md)
