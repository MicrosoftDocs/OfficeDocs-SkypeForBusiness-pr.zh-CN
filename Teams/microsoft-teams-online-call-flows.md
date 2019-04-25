---
title: Microsoft Teams 通话流程
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: 介绍团队如何在各种拓扑中使用 Office 365 流。
ms.openlocfilehash: ecdeb6dc4e1e7219dc8c01c710877437661e0ceb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232036"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams 通话流程

> [!Tip]
> 观看以下会话，从而了解团队如何利用您的网络，以及如何规划最佳的网络连接：[团队网络规划](https://aka.ms/teams-networking)

## <a name="overview"></a>概述
本文介绍团队使用 Office 365 如何在各种拓扑中呼叫流。 此外，它介绍了用于对等媒体通信的唯一团队流。 文档在网络上介绍这些流程，其目的，及其原点和终止。 出于本文，假定以下几点：

- 流 X 使用内部部署 Office 365 客户端与 Office 365 服务在云中进行通信。 来自客户网络，并作为 Office 365 中的终结点终止。

- 流 Y 使用内部部署 Office 365 客户端与 Office 365 具有依赖项 Internet 上的服务进行通信。 来自客户网络，并为 Internet 上的终结点终止。

本文包含以下各节：

- **背景**-提供背景信息，如网络的 Office 365 流可能遍历，通信、 连接到 Office 365 服务终结点的客户网络、 与第三方组件互操作性指南的类型和团队用于选择媒体流的原则。

- **调用各种拓扑中的流程**-演示如何使用各种拓扑中的呼叫流。 为每个拓扑，部分枚举所有受支持的数据流，并说明了如何使用这些流程通过多个用例。 对于每个用例，它介绍顺序以及选择通过流程图的流。 

- **团队和 Express 路由优化**-介绍用于优化，通过简单拓扑中说明了部署 Express 路由时如何使用这些流程。

## <a name="background"></a>背景
### <a name="network-segments"></a>网络段
**客户网络**： 这是网络段的控制和管理。 这包括客户办公室内的所有客户连接是否有线或无线，办公楼到本地数据中心之间的连接到 Internet 提供程序、 Express 路由或任何其他专用对等。 

通常情况下，客户网络具有多个网络外围防火墙和/或代理服务器，其强制实施组织的安全策略，以及仅允许您已设置和配置的某些网络流量。 由于管理此网络，您可以直接控制的网络，性能，强烈建议您完成网络评估，以验证从您的网络到 Office 365 网络中的网络和网站中的性能。 

**Internet**： 这是客户网络外部连接到 Office 365 中的用户将使用您整个网络一部分的网络段。 它还使用到 Office 365 客户网络一些流量。 

**已访问/来宾专用网络**： 这是外部客户网络，但不能在公用 Internet，也可以访问您的用户和/或其来宾的网络段。 例如，主专用网络或企业版专用网络的不部署团队，可能位于您的用户和/或其与团队服务进行交互的客户。

>**注意**： 连接到 Office 365 也是适用于这些网络。

**Office 365**： 这是支持 Office 365 服务的网络段。 它与接近大多数位置中的客户网络中的边缘世界各地分布。 本文档中提到的功能包括传输中继、 会议服务器和媒体处理器。 

**Express 路由 （可选）**： 这是您将为您提供专用的专用连接到 Office 365 网络的总体网络一部分的网络段。

### <a name="types-of-traffic"></a>类型的通信

**实时媒体**： 封装在支持音频、 视频和屏幕共享工作负荷的 RTP （实时传输协议） 的数据。 一般情况下，媒体流量是高延迟敏感的因此您希望采用的最直接路径可能，并使用 UDP 和 TCP 作为传输层协议，它是最佳传输质量角度从交互式实时媒体此通信. (注意： 媒体作为最后的手段，可以使用 TCP/IP 和还隧道 HTTP 协议内，但不是建议由于错误质量影响。)通过 SRTP，只对负载用于加密被安全 RTP 流。

**信号**： 客户端和服务器或用于控制活动 （例如，当发起呼叫），其他客户端之间的通信链接和提供即时消息。 最信号流量使用了基于 HTTPS 的 REST 接口，但在某些情况下 （例如，Office 365 和会话边界控制器之间的连接），它使用 SIP 协议。 务必要了解此通信是这么对延迟敏感，但可能会导致服务中断或呼叫超时，如果终结点之间的延迟超过几秒钟的时间。 

### <a name="connectivity-to-office-365"></a>连接到 Office 365

团队需要[连接到 Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)。 [Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中列出了工作组终结点 Url 和 IP 地址范围。 (注意： 打开连接到 TCP 端口 80 和 443，并且 UDP 端口通过 3481 3478 是必选。)此外，团队依赖 Skype 业务 online，其必须连接到 Internet。

通过标准 IETF ICE （互动式连接建立） 过程中实现团队媒体流连接。

### <a name="interoperability-restrictions"></a>互操作性限制
**第三方媒体中继**： 团队媒体流 （即，其中一个媒体端点是团队） 可能遍历仅团队或 Skype 的业务本机媒体中继。 不支持与第三方媒体中继互操作性。 (注意： 与 PSTN 边界上的第三方 SBC 必须终止 RTP/RTCP 流，通过 SRTP 保护并不将其中继到下一个跃点。)

**第三方 SIP 代理服务器**： 团队信号 SIP 对话与第三方 SBC 和/或网关可能的业务本机 SIP 代理遍历团队或 Skype。 不支持与第三方 SIP 代理互操作性。

**第三方 B2BUA (即，SBC)**： 由第三方 SBC 终止团队从/到 PSTN 的媒体流。 但是，与互操作性第三方 SBC 团队网络内 （即，第三方 SBC 作为两个团队/Skype 业务终结点） 不受支持。

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>建议不要使用的 Microsoft 团队的技术

**VPN 网络**： 不建议用于的媒体流量 （即，流 2）。 VPN 客户端应使用中指定的拆分 VPN 和路由媒体流量的任何外部的非 VPN 用户，如https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/。

>**注意**： 虽然标题为 Lync，它也适用于团队。

**数据包 shapers**： 任何类型的数据包 snippers、 数据包检查或数据包整形程序设备不建议使用，并且会显著可能会降低的质量。 

### <a name="principles"></a>原则
有四个一般原则，帮助您了解 Microsoft 团队的呼叫流：
 
1.  由 Office 365，其中第一个参与者加入同一区域中承载的 Microsoft 团队会议。 (注意： 如果将在某些拓扑中，此规则的例外，则将此文档中所述并由相应的呼叫流量所示。)

2.  使用 Office 365 中的媒体终结点团队基于媒体处理需求，并不基于呼叫类型。 （例如，点对点呼叫可能用于媒体终结点到过程介质云中转录和/或时具有两个参与者的会议中不能使用任何媒体终结点云录制。）但是，大多数会议将用于混合和路由目的，分配承载会议使用媒体终结点。 从客户端发送到的媒体端点的媒体流量可能会直接路由或 Office 365 中使用传输中继，如果需要由于客户网络防火墙限制。 

3.  媒体流量的对等呼叫发生不可用，假定呼叫不要求在云中的媒体终结点的最直接路由 （请参阅上面的 #2）。 首选的路由是直接连接到远程对等方 （客户端），但如果该路由不可用，然后一个或多个传输中继将通信中继。 建议媒体流量应如数据包 shapers、 VPN 服务器和等等，不遍历服务器，因为这将影响的媒体质量。

4.  始终信号流量转到最近服务器向用户。 

若要了解有关上选择的媒体路径的详细信息，请参阅https://www.youtube.com/watch?v=1tmHMIlAQdo。

## <a name="call-flows-in-various-topologies"></a>在不同拓扑中的呼叫流
### <a name="teams-topology"></a>团队拓扑
利用团队中不通过任何本地部署，如业务服务器或电话系统直接路由的 Skype 云的服务的客户使用这种拓扑。 此外，通过不 Azure Express 路由 Internet 完成到 Office 365 的接口。 

[![Microsoft 团队联机呼叫流图 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*图 1-团队拓扑*

注意：

- 在上图上箭头的方向反映影响连接功能的企业外围环境的通信的初始方向。 对于媒体 UDP，第一个数据包可能流的反向方向，但可能被阻止这些数据包，直到在其他方向的数据包将流。
- 团队业务 online 部署并排 Skype，因此客户端显示为"团队/SFB 用户"。

您可以更高版本一文中找到以下可选拓扑的详细信息：

- Skype for Business 的本地部署所述**团队混合拓扑**。
- **使用直接路由拓扑的团队**中介绍了电话系统直接路由 （对于 PSTN 连接）。
- Express 路由所述**使用 Express 路由优化的团队**。

**流说明**：
- **流 2** – 表示由客户网络到 Internet 上的用户启动的用户的工作组体验一部分流。 这些流程的示例是 DNS 和对等媒体。
- **流 2** – 表示的远程移动团队用户，具有到客户网络的 VPN 启动流。 
- **流 3** – 表示启动远程移动团队用户对 Office 365/Teams 终结点的流。 
- **流 4** – 表示启动客户网络到 Office 365/Teams 终结点上的用户的流量。
- **流 5** – 表示客户网络内的业务用户团队用户与其他工作组或 Skype 之间的对等媒体流。
- **流 6** – 表示通过 Internet 的远程移动团队用户和业务用户的另一个远程移动的团队或 Skype 之间的对等媒体流。

#### <a name="use-case-one-to-one"></a>用例： 一对一
一对一呼叫使用通用模型呼叫者将在其中获取一的 IP 地址/端口-包括本地、 中继和身 （公共 IP 地址的查看者中继的客户端） 的候选项组成的候选人。 呼叫者发送到呼叫方; 这些候选人调用的方还获取一组类似的候选人，并将其发送到呼叫者。 邮件用来查找的调用方/调用方媒体路径起作用，STUN 连接检查和最佳工作路径处于选中状态。 然后，使用选定的候选对发送介质 （即，通过 SRTP 保护的 RTP/RTCP 数据包）。 传输中继部署作为 Office 365 的一部分。

如果本地 IP 地址/端口候选人或身候选人具有连接，然后将媒体选择直接路径客户端之间 （或通过 NAT）。 如果客户端都客户网络上，则应选择直接路径。 这需要客户网络内的直接 UDP 连接。 如果客户端这两个游牧云用户，然后根据 NAT/防火墙，媒体可能会使用直接连接。

如果一个客户端是内部客户网络上，一个客户端是外部 （例如，移动云用户），则不太可能之间的本地或身候选的直接连接是否正常工作。 在这种情况下，选择是使用从任一客户端的传输中继候选之一 (例如，内部客户端从 Office 365 中的传输中继获取中继候选; 外部客户端需要能够发送到的 STUN/RTP/RTCP 数据包传输中继）。 另一个选项是内部客户端将发送到移动云客户端获取中继候选。 请注意，但强烈建议 UDP 连接的媒体，支持使用 TCP。

**简要步骤**：
1. 团队需要用户 A 解析 URL 域 (DNS) 通过名 flow2
2. 团队用户 A 分配媒体中继端口团队传输中继上的通过流 4
3. 团队需要用户 A 发送与通过流 4 到 Office 365 的 ICE 候选人"邀请"
4. Office 365 将通知发送给团队用户 B，通过流 4
5. 团队用户 B 分配媒体中继端口团队传输中继上的通过流 4
6. 团队用户 B 发送而被转接回通过流 4 的团队用户 A 的流 4，通过 ICE 候选人"应答"
7. 团队用户 A 和团队用户 B 调用 ICE 连接测试和选择最佳可用的媒体路径 （的各种使用情况下，请参阅下面的图表）
8. 团队用户发送到 Office 365 通过流 4 的遥测

**客户网络： 中**

[![Microsoft 团队联机呼叫流图 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*图 2-客户的网络内*
 
在步骤 7 中，对等媒体流 5 处于选中状态。
 
媒体为双向。 流 5 的方向指示一方启动从连接角度看，与本文档中的所有流一致的通信。 在这种情况下，无论使用哪个方向，因为这两个终结点客户网络内部。

**客户网络向外部用户 （媒体中继的团队传输中继）：**

[![Microsoft 团队联机呼叫流图 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*图 3-客户网络向外部用户 （媒体中继的团队传输中继）*
 
在步骤 7 中，选择 4，从到 Office 365 客户网络和流 3，来自远程移动到 Office 365 的团队用户。 通过 Office 365 中的团队传输中继中继这些流程。

媒体是双向，其中方向表示哪一侧启动从连接角度通信。 在这种情况下，这些流程用于信号和媒体，通过不同的传输协议和地址。

**客户网络向外部用户 （直接媒体）：**

[![Microsoft 团队联机呼叫流图 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*图 4-客户网络向外部用户 （直接媒体）*
 
在步骤 7 中，从 internet （客户端的对等） 的客户网络的流 2 中，处于选中状态。
- 与远程移动用户 （即，不通过 Office 365 中继） 的直接媒体是可选的。 换句话说，客户可能会阻止此路径强制实施通过 Office 365 中的传输中继的媒体路径。

- 媒体为双向。 到远程移动用户的流 2 的方向指示一方启动从连接角度的通信。 

**VPN 用户与内部用户 （媒体中继的团队传输中继）**

[![Microsoft 团队联机呼叫流图 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*图 5-VPN 用户与内部用户 （媒体中继的团队传输中继）*
 
到客户网络 VPN 之间信号是通过流 2。 客户网络与 Office 365 之间信号是通过流 4。 但是，媒体绕过 VPN 和通过流 3 和 4 到 Office 365 中的团队媒体中继路由。

**VPN 用户与内部用户 （直接媒体）**

[![Microsoft 团队联机呼叫流图 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*图 6-VPN 用户与内部用户 （直接媒体）*

到客户网络 VPN 之间信号是通过流 2。 客户网络与 Office 365 之间信号是通过流 4。 但是，媒体绕过 VPN 和路由通过流 2 来自客户网络到 Internet。

媒体为双向。 到远程移动用户的流 2 的方向指示一方启动从连接角度的通信。

**VPN 用户与外部用户 （直接媒体）**

[![Microsoft 团队呼叫流图 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*图 7-VPN 用户与外部用户 （直接媒体）*

客户网络 VPN 用户之间信号是通过流 2，并通过流 4 到 Office 365。 但是，媒体绕过 VPN 和通过流 6 路由。

媒体为双向。 到远程移动用户的流 6 的方向指示一方启动从连接角度的通信。

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>通过 Office 365 中继的 pstn 的使用案例： 团队
Office 365 具有允许发起和接收呼叫从公共公用电话交换网 (PSTN) 电话系统。 如果通过电话系统调用规划所连接的 PSTN 中继，则使用本例没有特殊连接要求。 （如果您想要连接到 Office 365 您自己的本地 PSTN 中继，您可以使用电话系统直接路由。）

[![Microsoft 团队联机呼叫流图 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*图 8-通过 Office 365 中继的 PSTN 团队*

#### <a name="use-case-teams-meeting"></a>使用案例： 团队会议

音频/视频/屏幕共享 (VBSS) 会议服务器是 Office 365 的一部分。 具有公共 IP 地址必须从客户网络上可以访问，必须将其从游牧云客户端访问。 每个客户端/终结点需要能够连接到会议服务器。

内部客户端将获取本地、 身，和中继候选相同的方式，一对一呼叫所述。 客户端将邀请中的会议服务器发送这些候选人。 会议服务器不使用中继，因为它具有一个公共可访问的 IP 地址，以便它使用其本地 IP 地址应聘者的响应。 客户端和会议服务器将检查连接一对一呼叫所述的方式相同。 

注意：

- 团队客户端无法加入 Skype 业务会议和 Skype 业务客户端无法加入团队会议。

- PSTN 用户 （可选）"拨打中"或"拨出"，具体取决于会议组织者 PSTN 呼叫和/或会议设置。 

- 来宾用户或客户的用户可以加入从来宾专用网络，其通过 FW/NAT 术 シ モ メ 严格的规则。

[![Microsoft 团队联机呼叫流图 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*图 9-团队会议*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>与 Skype 的本地业务的使用案例： 联盟

**媒体中继的 Office 365 中的团队传输中继**

[![Microsoft 团队联机呼叫流图 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*图 10-媒体中继的 Office 365 中的团队传输中继*

注意：

- 根据定义，联合身份验证是两个租户之间的通信。 在这种情况下，租户，以使用团队，与租户 B，使用本地业务 Skype 建立联盟。 如果租户 B 也使用的 Office 365，然后业务客户端 Skype 将已使用流 3 与 Office 365 连接。

- 信号和媒体从业务客户端的联合 Skype 到业务服务器的内部部署 Skype 已超出本文档的范围。 但是，它所示为清楚起见。

- 工作组和 for Business 的 Skype 之间信号桥接 Office 365 中的网关。

- 媒体在这种情况下被中继通过 Office 365 中的团队传输中继到客户网络和远程 Skype 业务通过流 4 的客户端。

**Skype 通过中继进行业务媒体中继联盟租户中的媒体**

[![Microsoft 团队联机呼叫流图 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*图 11-Skype 通过中继进行业务媒体中继联盟租户中的媒体*

注意：

- 本文档的范围超出信号和媒体从业务客户端的联合 Skype 到业务服务器的内部部署 Skype。 但是，它所示为清楚起见。

- 工作组和 for Business 的 Skype 之间信号桥接 Office 365 中的网关。

- 媒体在这种情况下是由中继 Skype 的业务本地媒体中继到通过流 2 客户网络。 （请注意，到远程媒体中继的联盟的客户网络中的团队用户流量之前将被最初阻止媒体中继反向流量开始流动。 但是，双向流中会打开连接两个方向。）

**直接 （对等）**

[![Microsoft 团队联机呼叫流图 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*图 12-直接 （对等）*

### <a name="teams-hybrid-topology"></a>团队混合拓扑
此拓扑包括与业务在本地部署 Skype 的团队。

[![Microsoft 团队联机呼叫流图 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*图 13-团队混合拓扑*
 
- 在上图上箭头的方向反映影响连接功能的企业外围环境的通信的初始方向。 对于媒体 UDP，第一个数据包可能流的反向方向，但可能被阻止这些数据包，直到在其他方向的数据包将流。

- 团队业务 online 部署并排 Skype，因此客户端显示为"团队/SFB 用户"。

（在工作组拓扑） 的其他流：
- **流 5A** – 表示客户网络内的团队用户和业务在客户网络边缘的内部部署媒体中继 Skype 之间的对等媒体流。

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>使用案例： 业务一对一的 Skype 团队
**客户网络中的混合**

[![Microsoft 团队联机呼叫流图 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*图 14-客户网络中的混合*
 
工作组和 for Business 的 Skype 之间信号桥接 Office 365 中的网关。 但是，媒体直接通过流 5-对等客户中网络路由。

**与外部业务用户 – Office 365 中继 Skype 混合客户网络**

[![Microsoft 团队联机呼叫流图 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*图 15-与外部业务用户的 Skype 混合客户网络-Office 365 中继*

注意：

- 本文档的范围超出信号和媒体从业务客户端 Skype 到业务服务器的内部部署 Skype。 但是，它所示为清楚起见。

- 工作组和 for Business 的 Skype 之间信号桥接 Office 365 中的网关。

- 通过 Office 365 中的团队传输中继情况下，媒体中继到通过流 4 客户网络。

**与外部业务用户 – 内部部署边缘中继 Skype 混合客户网络**

[![Microsoft 团队联机呼叫流图 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*图 16-混合客户网络与外部 Skype 业务用户的内部部署边缘中继*
 
注意：

- 信号和媒体从 Skype 业务客户端到业务服务器的内部部署 Skype 已超出本文档的范围。 但是，它所示为清楚起见。

- 信号桥接 Office 365 中的网关。

- 媒体中继的 Skype 进行中的业务给团队用户通过媒体流 5A 客户网络内的内部部署边缘 Skype 业务媒体中继。

### <a name="teams-with-phone-system-direct-routing-topology"></a>与电话系统直接路由拓扑的团队
此拓扑包括与电话系统直接路由的团队。 

直接路由，您可以通过配对的受支持的本地客户拥有会话边界控制器 (SBC) 硬件设备到 Office 365，然后将连接到电话中继使用第三方公共公用电话交换网 (PSTN) 服务提供商该设备。 

若要支持这种情况下，客户必须直接路由从 Microsoft 认证合作伙伴的部署认证的 SBC。 SBC 所推荐供应商，必须配置并为可从 Office 365 的直接 UDP 流量路由。 媒体可能直接从工作组和/或业务客户端 Skype 流向 SBC （绕过团队网关） 或遍历通过团队网关。 与 SBC，连接时中继配置为绕过团队网关，基于的 ICE，其中 SBC 支持 ICE Lite，而对业务媒体端点团队/Skype 支持 ICE 完全。 

[![Microsoft 团队联机呼叫流图 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* 图与电话系统直接路由拓扑 17-团队

注意：

- 在上图上箭头的方向反映影响连接功能的企业外围环境的通信的初始方向。 对于媒体 UDP，第一个数据包可能流的反向方向，但可能被阻止这些数据包，直到在其他方向的数据包将流。

- 团队业务 online 部署并排 Skype，因此客户端显示为"团队/SFB 用户"。

（在工作组联机拓扑） 的其他流：
- **流 4** -表示流来自 Office 365 客户网络，用于在云中使用本地 SBC 中的团队媒体服务器之间建立连接。
- **流 5B** – 表示团队用户在具有直接路由以绕过模式 SBC 客户网络之间的媒体流。
- **流 5c** – 表示之间直接路由到另一个直接路由 SBC PSTN 发夹呼叫绕过模式 SBC 媒体流。

**内部用户与直接路由 （媒体中继的 Office 365 中的团队传输中继）**

[![Microsoft 团队联机呼叫流图 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*图 18-直接路由 （媒体中继的 Office 365 中的团队传输中继） 的内部用户*

注意：
 
- SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

- 信号和媒体从 SBC 到 Office 365，反之亦然使用流 4，和/或流 4。

- 信号和媒体客户网络内的客户端到 Office 365 使用流 4。


**远程用户直接路由 （媒体路由至 Office 365 中的媒体服务器 (MP)）**

[![Microsoft 团队联机呼叫流图 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*图 19-远程用户直接路由 （媒体路由至 Office 365 中的媒体服务器 (MP)）*
 
注意：

- SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

- 信号和媒体从 SBC 到 Office 365，反之亦然使用流 4，和/或流 4。

- 信号和媒体从 Internet 上的客户端到 Office 365 使用流 3。

**内部用户直接路由 （媒体绕过）**

[![Microsoft 团队联机呼叫流图 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*图 20-直接路由 （媒体绕过） 的内部用户*
 
注意：

- SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

- 使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。

- 从客户的网络内的客户端到 Office 365 使用流 4 的信号。

- 媒体从客户的网络内的客户端到客户网络内的 SBC 使用流 5B。

**远程用户直接路由 （由 Office 365 中的团队传输中继中继的媒体绕过）**

[![Microsoft 团队联机呼叫流图 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*图 21-远程用户直接路由 （由 Office 365 中的团队传输中继中继的媒体绕过）*

注意：

- SBC 必须是从 Office 365 和 Internet 可路由的公共 IP 地址。

- 从 SBC 到 Office 365，反之亦然信号使用流 4 和/或流 4。

- 从 Internet 上的客户端信号到 Office 365 使用流 3。

- 媒体从 Internet 上的客户端到客户网络内 SBC 使用流 3 和 4 时，由 Office 365 中的团队传输中继中继。 

**远程用户直接路由 （媒体绕过直接）**

[![Microsoft 团队联机呼叫流图 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*图 22-远程用户直接路由 （媒体绕过直接）*
 
注意：

- SBC 必须是从 Office 365 和 Internet 可路由的公共 IP 地址。

- 从 SBC 到 Office 365，反之亦然信号使用流 4 和/或流 4。

- 从 Internet 上的客户端信号到 Office 365 使用流 3。

- 媒体从 Internet 上的客户端到客户网络内 SBC 使用流 2。

**直接路由 （媒体绕过） – （由于呼叫转接/传输） 的 PSTN 发夹呼叫**

[![Microsoft 团队联机呼叫流图 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*图 23-直接路由 （媒体绕过）-PSTN 发夹呼叫 （由于呼叫转接/传输）*
 
注意：

- SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

- 从 SBC 到 Office 365，反之亦然信号使用流 4 和/或流 4。

- 客户端是不足的信号和媒体循环 hairpinned 从 PSTN 向 PSTN 呼叫后。

- 从客户的网络内的 SBC 实例 A 到 SBC 实例 B 中 （其中，A 和 B 可以是同一个实例） 的客户网络媒体使用流 5 c。

**跨两个租户 PSTN 发夹呼叫直接路由 （通过 Office 365 的媒体 –）**

[![Microsoft 团队联机呼叫流图 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*跨两个租户的图 24-直接路由 （媒体通过 Office 365） – PSTN 发夹呼叫*
 
注意：

- SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

- 从 SBC 到 Office 365，反之亦然信号使用流 4 和/或流 4。

- 客户端是不足的信号和媒体循环 hairpinned 从 PSTN 向 PSTN 呼叫后。

- 从客户网络 X 内的 SBC 实例 A 到 SBC 实例 B 必须通过 Office 365 媒体服务器中继和不能使用媒体绕过模式。

## <a name="teams-with-express-route-optimization"></a>与 Express 路由优化的团队

[![Microsoft 团队联机呼叫流图 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*图 25-与 Express 路由优化的团队*
 
在这种情况的两端对齐 Express 路由并将其部署，然后团队流无法重新路由从流流 1 并从流 4 1 的排列的 4。 但是，团队应用程序依赖硬其他 Office 365 流通过流 4 通过 internet 和 4;因此必须不阻止这些流程。 

请注意业务混合边缘流量的 Skype 被路由到 Internet，而不适用于 Express 路由与外部用户通信并与其他租户联盟。 

若要阻止非对称流，请重新路由而必须在两个方向。 换句话说，客户网络内的地址是通过 Internet 或 Express 路由，基于优化，而不是通过同时，可穿绕的。

例如：

**客户网络向外部用户 （媒体中继的团队传输中继）：**

[![Microsoft 团队联机呼叫流图 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*图 26-客户网络向外部用户 （媒体中继的团队传输中继）*
 
**简要步骤：**
1. 客户网络中的团队用户解析 URL 域名 (DNS) 通过 flow2
2. 客户网络中的团队用户分配媒体中继端口团队传输中继上的通过流 1
3. 客户网络中的团队用户发送与通过流 1 到 Office 365 的 ICE 候选人"邀请"
4. OFFICE 365 将通知发送给外部团队用户通过流 3
5. 团队外部用户分配媒体中继端口团队传输中继上的通过流 3
6. 团队外部用户发送与通过流 3，转发回到通过流 1 的团队用户 A 的 ICE 候选人"应答"
7. 团队用户 A 团队用户 B 调用 ICE 连接测试和选择流 1 和 3，由 Office 365 中的团队传输中继中继
8. 团队用户通过流 1 和 3 将遥测发送到 Office 365

>**注意**： 必须启用流 4 以对其他微服务要求流 4 支持团队应用程序依赖项。
