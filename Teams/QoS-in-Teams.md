---
title: 在 Microsoft Teams 中实施服务质量
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 针对 Microsoft Teams 的服务质量 (QoS) 准备贵组织的网络。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef01b9c62fe65a04d09592ca49531e12ac6d4325
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459009"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>在 Microsoft 团队中实现服务质量 (QoS)

本文将帮助您的服务质量 (QoS) 中的 Microsoft 团队准备贵组织的网络。 如果要支持一大组用户，并且它们遇到的任何下述问题，您可能需要实现 QoS。 小型企业几个用户可能不需要 QoS，但即使存在应非常有用。

QoS 是一种方法，以允许 （如语音或视频流） 网络延迟"剪切行中"（如下载新应用程序，其中下载的额外的第二个不大不了） 不太敏感的通信之前对敏感的实时网络流量。 QoS 标识和标记 （使用 Windows 组策略对象和调用基于端口的访问控制列表，再详细那些低于路由功能） 的实时流中的所有数据包的 then 可帮助您的网络语音、 视频和屏幕共享流授予网络带宽专用的部分。

如果没有 QoS 某种形式，您可能会看到以下语音和视频质量问题：

- 抖动 – 到达不同的比率，这可能会导致缺少单词或音节呼叫中的媒体数据包。
- 数据包丢失 – 数据包而丢弃，其中也可能导致在较低的语音质量和硬了解语音。
- 延迟往返时间 (RTT) – 媒体数据包需要很长时间才能到达其目的地，这将导致导致讨论通过每个其他人对话中的两方之间的显著延迟。

为了解决这些问题的复杂程度最小方法是增加的数据连接，大小同时内部和 internet。 由于通常是成本上不可行，因此 QoS 使您能够更有效地管理您而不是添加新的资源的资源。 完全解决质量问题，您需要使用 QoS 跨实现，然后仅当绝对需要时添加连接。

QoS 可以取得高效率，您将需要应用一致 QoS 设置 （包括所有用户的 Pc、 网络交换机和到 internet 的路由器） 在组织中端到端，因为无法支持 QoS 优先级路径的任何部分会降低呼叫、 视频和屏幕共享的质量。

_图 1。组织的网络和 Office 365 服务之间的关系_

![组织的网络和 Office 365 服务之间的关系： 本地网络和设备将与反过来连接和 Office 365 云语音和音频会议服务互连网络连接。](media/Qos-in-Teams-Image1.png)

在大多数情况下，将您不是能够可靠地设置 QoS 选项非托管的网络连接到云企业的网络。 一个选项可用于解决端到端 QoS [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)，但我们仍建议您实现您的本地网络上的 QoS。 这将提高整个部署的实时通信工作负载的质量，并解决阻塞点。

## <a name="verify-your-network-is-ready"></a>验证您的网络准备好

如果您正在考虑 QoS 实现，您应已确定您的带宽要求和其他[网络要求](prepare-network.md)。 Microsoft Teams 的带宽计算很复杂，因此为了帮助进行此计算，创建了一个计算器。 若要访问计算器，转到[网络规划人员](https://aka.ms/bwcalc/)MyAdvisor 中。
  
  通过网络流量拥塞将会显著影响媒体质量。 带宽不足导致性能下降和很差的用户体验。 随着团队应用和使用情况，使用报告功能，[呼叫分析和呼叫质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)以确定问题，然后进行使用 QoS 和选择性带宽的新增功能的调整。

### <a name="vpn-considerations"></a>VPN 注意事项

按预期方式实现呼叫者之间的所有链接上时，仅适用于 QoS。 如果您使用内部网络上的 QoS，一个用户登录从远程位置，您可以仅设置优先级内部、 托管网络中。 虽然远程位置可以收到托管的连接，通过实现虚拟专用网络 (VPN)，VPN 本质上是添加数据包开销然后延迟在创建实时通信。 我们建议您避免 VPN 上运行实时通信流量。

> [!NOTE]
> VPN 连接的远程用户应实现拆分隧道最大限度地的用户体验质量。 [部署指南 VPN 拆分隧道](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 )的文档可从 MyAdvisor，并提供了详细信息。

在全局组织中使用托管跨洲的链接，强烈建议 QoS 因为这些链接的带宽有限 LAN 进行对比。

## <a name="introduction-to-qos-queues"></a>QoS 队列简介

若要提供 QoS，网络设备必须具有分类通信的方式，并且必须能够与其他网络流量区分语音或视频。

当网络流量进入路由器时，流量放入队列。 如果不配置 QoS 策略，没有为只有一个队列，并且所有数据都视为为第一项，先出具有相同优先级。 这意味着语音通信 （这是非常对延迟敏感） 可能有疑问后面流量其中的一些额外毫秒延迟不会出现问题。

实现 QoS 时，您定义使用多个拥塞管理功能 （如 Cisco 的优先级队列和基于类的加权公平队列[CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)） 和拥塞避免功能之一 （如加权随机早期的多个队列检测[WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)）。

_图 2。QoS 队列的示例_

![全部可用带宽分为多个队列 — 音频、 视频和其他通信 — 的已分配不同的优先级。](media/Qos-in-Teams-Image2.png "全部可用带宽分为多个队列 — 音频、 视频和其他通信 — 的已分配不同的优先级。")

简单葡萄形状是 QoS 创建虚拟数据中的"乘泳道"网络使某些类型的数据从不或很少遇到延迟。 一旦创建这些道，可以其相对大小调整和更有效地管理连接的带宽有，同时仍提供对您的组织用户的企业级体验。

## <a name="select-a-qos-implementation-method"></a>选择 QoS 实现方法

您可以实施 QoS 通过基于端口的标记，使用您的网络路由器上的访问控制列表 (Acl)。 基于端口的标签是最可靠的方法，因为它混合 Windows 和 Mac 环境中正常工作，容易实现。 移动客户端不提供一种机制，因此他们将需要此方法使用 DSCP 值标记流量。  

使用此方法，您的网络路由器检查传入的数据包，并使用特定端口或的端口范围，已到达数据包，如果其标识为特定媒体类型，并将其放在队列中的该类型，将一个预先确定的[DSCP](https://tools.ietf.org/html/rfc2474)标记添加到 IP数据包标头，以便其他设备可以识别其通信类型，并为其提供其队列中的优先级。

虽然这可以工作跨平台，仅标记在 WAN 边缘 （不一直到客户端计算机中） 的通信，并创建管理开销。 您应参考路由器制造商提供的说明实现此方法的文档。

* * *

您还可以执行 QoS 通过使用组策略对象 (GPO) 定向客户端设备来实现，以确定它作为特定类型的通信 （例如，语音） 的 IP 数据包标头中插入的 DSCP 标记。 路由器和其他网络设备可以配置以识别此和流量置于单独的、 更高优先级的队列。

尽管这种情况下完全无效，但它仅适用于加入域的 Windows 客户端。 未加入域的 Windows 客户端的任何设备不启用 DSCP 标记。 客户端 Mac OS 如具有硬编码标记，并且将始终标记流量。

加号控制 DSCP 标记通过 GPO 一侧，确保所有加入域的计算机接收相同的设置，并且只有管理员可以管理其。 将在发起设备上，标记客户端可以使用 GPO，然后配置的网络设备可以识别由 DSCP 代码的实时流并为其提供相应的优先级。

* * *

建议终结点和基于端口的路由器上的 Acl 的 DSCP 标记的组合如果可能。 使用组策略对象来捕获大多数客户端，以及使用基于端口的 DSCP 标记将确保该 mobile、 Mac 和其他客户端将仍获取 QoS 诊 （至少部分）。

DSCP 标记可以比作邮票邮政工作者如何紧急交付是以及如何最好地对它进行排序的快速发送到指示。 一旦您已配置网络以授予实时的媒体流的优先级，丢失的数据包和后期数据包应会显著降低。

一旦网络中的所有设备都使用相同的分类、 标记、 和优先级，可以减少甚至完全消除推迟，被丢弃的数据包，率和抖动通过更改分配给队列的每种通信类型使用的端口范围的大小。 从工作组角度来看，最重要的配置步骤的分类和标记的数据包，但在进行端到端 QoS 成功您还需要仔细对齐的基础的网络配置的应用程序的配置。 一旦完全实现 QoS，持续管理是调整分配给基于组织的需求和实际使用每种通信类型的端口范围的问题。

## <a name="choose-initial-port-ranges-for-each-media-type"></a>选择每种媒体类型的初始端口范围

是否由客户端或网络本身基于 ACL 设置指派 DSCP 标记的 DSCP 值将告知相应地配置的网络授予数据包或流，哪些优先级。 每个媒体工作负荷获取自己独特的 DSCP 值 （其他服务可能允许工作负荷共享 DSCP 标记，团队不） 和每种媒体类型的定义和单独的端口范围。 其他环境可能具有现有的 QoS 策略就地，这将帮助您确定网络工作负荷的优先级。

针对不同的实时流工作负载的端口范围的相对大小设置的总的可用带宽的比例到该工作负荷专用。 返回到我们之前的邮政葡萄形状： 与"空气 Mail"戳字母可能获取所需在一个小时内到最接近机场时小型包标记"批量邮件"标记可以等待的卡车一系列上通过园地传输前一天。

下表显示与 ExpressRoute，团队所需的 DSCP 标记和关联的工作负荷队列端口。 这些范围可能用作不能确定要在其自己的环境中使用的客户的良好的起始点。 要了解详细信息，请阅读 [ExpressRoute QoS 要求](https://docs.microsoft.com/azure/expressroute/expressroute-qos)。

_建议初始端口范围_

|媒体通信类型| 客户端源端口范围 |协议|DSCP 值|DSCP 类|
|:--- |:--- |:--- |:--- |:--- |
|音频| 50000 – 50,019|TCP/UDP|46|加速转发 (EF)|
|视频| 50,020 – 50,039|TCP/UDP|34|保证转发 (AF41)|
|应用程序/屏幕共享| 50,040 – 50,059|TCP/UDP|18|保证转发 (AF21)|
||||||

使用这些设置时要注意以下事项：

- 如果您计划将来实现 ExpressRoute 并没有尚未实施 QoS，我们建议您遵循的指南，以便是来自到接收方的发件人相同的 DSCP 值。
- 所有客户端，其中包括移动客户端和团队设备，将使用这些端口范围，并将受您实现任何 DSCP 策略使用这些源端口范围。 将继续使用动态端口的唯一客户端是基于浏览器的客户端 （即，这些客户端，允许使用其浏览器加入会议的参与者）。
- 尽管 Mac 客户端使用相同的端口范围，但它还使用硬编码为值 （ef） 级别音频和视频 (AF41)。 这些值是不可配置。
- 如果您稍后需要调整以改善用户体验的端口范围，端口范围不能重叠，并且应彼此相邻。

## <a name="migrate-qos-to-teams"></a>迁移到团队的 QoS

如果您之前已部署 Skype 业务 Online，包括 QoS 标记和端口范围，并且现在部署团队，团队将尊重现有配置，并将使用相同的端口范围和标记为业务客户端 Skype。 在大多数情况下，将不需要任何其他配置。

> [!NOTE]
> 如果您使用的应用程序名称 QoS 标记通过组策略，您必须添加 Teams.exe 作为应用程序的名称。

## <a name="qos-implementation-steps"></a>QoS 实现步骤

在非常高级别，实现 QoS 需要以下步骤：

1. [验证您的网络准备好](#verify-your-network-is-ready)
2. [选择 QoS 实现方法](#select-a-qos-implementation-method)
3. [选择每种媒体类型的初始端口范围](#choose-initial-port-ranges-for-each-media-type)
4. 实现 QoS 设置：
   1. 在客户端上使用 GPO 为[客户端设备端口范围和标记](QoS-in-Teams-clients.md)的设置
   2. （请参阅制造商的文档） 的路由器或其他网络设备。 这可能包括基于端口的 Acl 或仅 QoS 队列或所有这些和 DSCP 标记中定义。

      > [!IMPORTANT]
      > 我们建议实现使用客户端源端口和源和目标 IP 地址的任意。 这些 QoS 策略 这将在内部网络中捕获这两个传入和传出的媒体流量。  

   3. 在[工作组管理中心](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)
5. 通过分析团队流量网络上的[的 QoS 实现验证](#validate-the-qos-implementation)。

准备实现 QoS 时，请记住以下准则：

- Office 365 的最短路径是最佳。
- 关闭端口仅将导致质量下降。
- 任何障碍中间，如代理，不建议使用。
- 限制跃距数：
  - 客户端到网络边缘 – 3 到 5 跃点数。
  - Microsoft 网络边缘 – 3 个跳跃 ISP
  - Microsoft 网络边缘到最终目的地 – 无关

有关配置防火墙端口的信息，请转到[Office 365 Url 和 IP 范围](office-365-urls-ip-address-ranges.md)。

## <a name="managing-source-ports-in-the-teams-admin-center"></a>管理团队管理中心中的源端口

团队中使用的不同的工作负载的 QoS 源端口应主动管理，并根据需要调整。 引用[的端口范围和 DSCP 标记](#port-ranges-and-dscp-markings)的表中，端口范围为可调整，但 DSCP 标记不可配置。 一旦您已实现这些设置，您可能会发现增加或减少端口所需的给定的媒体类型。 在决定实现团队后，并定期根据需要更改调整端口范围，应使用[调用分析和呼叫质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)。

> [!NOTE]
> 如果您已经配置 QoS 基于源的端口范围和业务 online Skype 的 DSCP 标记，相同的配置将应用于工作组和不再客户端或网络映射到需要更改，但您可能已经为[设置范围用于团队 Admin Center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)来匹配内容已配置为 Skype 业务 online。

如果先前已 Business Server 本地部署 Skype，您可能需要重新检查 QoS 策略，并根据需要以匹配您已验证团队提供高品质用户体验的端口范围设置对它们进行调整。

## <a name="validate-the-qos-implementation"></a>验证 QoS 实施

有关 QoS 可以取得高效率、 DSCP 值设置组策略对象都需要呼叫两端都存在。 您可以通过分析由团队客户端生成的流量，验证的 DSCP 值不更改或去除团队工作负荷通信量遍历移动通过网络。

最好，您可以捕获网络出口点处的流量。 您可以使用端口镜像开关或路由器上与此帮助。

### <a name="use-network-monitor-to-verify-dscp-values"></a>使用网络监视器验证 DSCP 值

网络监视器是您可以[从 Microsoft 下载](https://www.microsoft.com/download/4865)分析网络流量的工具。

1. 在 PC 上运行网络监视器，连接到端口镜像和开始捕获数据包已配置的端口。

2. 使用团队客户端发起呼叫。 请确保媒体建立挂断呼叫之前。

3. 停止捕获。

4. 在**显示筛选器**字段中，使用源 IP 地址的 pc 的发出呼叫，并通过定义作为搜索条件的 DSCP 值 46 (hex 0xb8) 优化筛选器，如下面的示例中所示：

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8

    ![网络监视器，显示应用的筛选器中的显示筛选器对话框的屏幕快照。](media/Qos-in-Teams-Image4.png "网络监视器，显示应用的筛选器中的显示筛选器对话框的屏幕快照。")

5. 选择**应用**以激活筛选器。

6. 在**帧摘要**窗口中，选择第一个 UDP 数据包。

7. 在**帧详细信息**窗口中，展开 IPv4 列表项，并注意末尾的行的开头**DSCP**值。

    ![网络监视器，突出显示 DSCP 设置中的帧详细信息对话框的屏幕快照。](media/Qos-in-Teams-Image5.png "网络监视器，突出显示 DSCP 设置中的帧详细信息对话框的屏幕快照。")

在此示例中的 DSCP 值设置为 46。 这是正确的因为使用的源端口是 50019，表示这是语音工作负荷。

为 GPO 标记的每个工作负荷重复执行验证。

## <a name="more-information"></a>更多信息

[视频： 网络规划](https://aka.ms/teams-networking)

[为 Microsoft Teams 准备组织的网络](prepare-network.md)

[ExpressRoute QoS 要求](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
