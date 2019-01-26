---
title: Online 的 Microsoft 团队呼叫流
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 06/08/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 介绍如何团队工作负荷利用不同拓扑中的 Office 365 流。
ms.openlocfilehash: 455e90d05a26ce387f916f531991ccaf664860d2
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562804"
---
# <a name="microsoft-teams-online-call-flows"></a>Online 的 Microsoft 团队呼叫流

> [!Tip]
> 观看下面的会话，若要了解如何团队利用您的网络和如何最好地规划最佳的网络连接：[团队网络规划](https://aka.ms/teams-networking)

## <a name="overview"></a>概述
本文档介绍团队工作负荷如何利用不同拓扑中的 Office 365 流。 此外，它指定用于对等媒体通信的唯一团队流。 文档枚举这些流程，并介绍其用途和其原点/终止网络。 例如，流 X 用于 Office 365 客户端在本地与云中，来自客户网络和 Office 365 云终结点终止的 Office 365 服务进行通信和流 Y 由本地的 Office 365 客户端与进行通信Internet，Office 365 具有依赖项，从客户网络，发起和终止 Internet 上的终结点上的服务。

文档有三个主要部分。 第一个提供背景信息，如网络 （即 Office 365 流可能遍历）、 类型的通信、 客户网络连接指南 to Office 365 服务终结点、 第三方组件和主体互操作性的使用团队选择媒体流。 第二个说明了在各种拓扑中的这些流程的使用情况。 为每个拓扑，它枚举所有支持的流，并说明了如何使用这些流程通过多个用例。 对于每个用例，它介绍顺序以及选择通过流程图的流。 第三个介绍用于优化，通过简单拓扑中说明了部署 Express 路由时如何使用这些流程。

## <a name="background"></a>背景
### <a name="network-segments"></a>网络分段
**客户网络**： 这是控制并管理总体网络一部分的网络段。 这包括客户办公室内的所有客户连接是否有线或无线，办公楼到本地数据中心之间 Internet 提供商、 Express 路由或任何其他专用对等连接。 

通常情况下，客户网络具有多个网络外围防火墙和/或代理服务器，其强制实施组织的安全策略和的仅允许您设置并配置某些网络流量。 由于客户管理此网络，客户可以直接控制的网络，性能，强烈建议完成客户网络评估，以验证性能这两个网络中以及从网站内的您到 Office 365 网络的网络。 在本地部署的业务和 PSTN 会话边界控制器与 PSTN 连接到网络 （即，直接路由） 的 Skype 是可选的。

**Internet**： 这是您要连接到 Office 365 云从客户网络之外的用户将使用的整个网络一部分的网络段。 它还使用到 Office 365 云客户网络一些流量。 

**已访问/来宾专用网络**： 这是外部客户网络，但不能在公用 Internet，也可以访问您的用户和/或其来宾的网络段。 例如，主专用网络或企业版专用网络的不部署团队，可能位于您的用户和/或其与团队服务进行交互的客户。

>**注意**： 连接到 Office 365b 也是适用于这些网络。

**Office 365 云**： 这是支持 Office 365 服务的网络段。 它与接近大多数位置中的客户网络中的边缘世界各地分布。 本文档中提到的功能包括传输中继、 会议服务器和媒体处理器。 

**Express 路由 （可选）**： 这是您将为您提供专用的专用连接到 Office 365 网络的总体网络一部分的网络段。

### <a name="types-of-traffic"></a>流量类型

**实时媒体**： 封装 RTP （实时传输协议） 和支持音频、 视频和共享工作负荷的屏幕中的数据。 一般情况下，媒体流量高度是延迟敏感，因此您希望采用的最直接路径可能，并使用 UDP 和 TCP 作为传输层协议，它是最佳传输质量角度从交互式实时媒体此通信。 (注意： 媒体作为最后的手段，可以使用 TCP/IP 和还隧道 HTTP 协议内，但不是建议由于错误质量影响。)通过 SRTP，只对负载用于加密被安全 RTP 流。

**信号**： 客户端和服务器或用于控制活动 （例如，当发起呼叫），其他客户端之间的通信链接和提供即时消息。 最信号流量使用基于 HTTPS 的 REST 界面，但在某些情况下 （例如，Office 365 云和会话边界控制器之间的连接） 使用 SIP 协议。 务必要了解此通信是这么对延迟敏感，但可能会导致服务中断或呼叫超时，如果终结点之间的延迟超过几秒钟的时间。 

### <a name="connectivity-to-office-365"></a>连接到 Office 365

团队服务需要[连接到 Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)。 [Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中列出了工作组终结点 Url 和 IP 地址范围。 (注意： 需要打开连接到 TCP 端口 80 和 443 和 UDP 端口 3478 到 3481。)此外，团队服务具有对 Skype 业务联机服务的依赖项，因此它需要连接到 Internet 的还此服务。

通过标准 IETF ICE （互动式连接建立） 过程中实现团队媒体流连接。

### <a name="interoperability-restrictions"></a>互操作性限制
**第三方媒体中继**： 团队媒体流 （即，其中一个媒体端点是团队） 可能遍历仅团队或 Skype 的业务本机媒体中继。 不支持与第三方媒体中继互操作性。 (注意： 与 PSTN 边界上的第三方 SBC 必须终止 RTP/RTCP 流，通过 SRTP 保护并不将其中继到下一个跃点。)

**第三方 SIP 代理服务器**： 团队信号 SIP 对话与第三方 SBC 和/或网关可能的业务本机 SIP 代理遍历团队或 Skype。 不支持与第三方 SIP 代理服务器互操作性。

**第三方 B2BUA (即，SBC)**： 由第三方 SBC 终止团队从/pstn 的媒体流。 但是，与互操作性第三方 SBC 团队网络内 （即，第三方 SBC 作为两个团队/Skype 的业务终结点） 不受支持。

### <a name="technologies-that-are-strongly-not-recommended-with-microsoft-teams"></a>与 Microsoft 团队中不强烈建议使用的技术

**VPN 网络**： 强烈建议不要的媒体流量 （即，流 2）。 VPN 客户端应该使用中指定的任何外部的非 VPN 用户，如拆分 VPN 和路由媒体流量https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/ 

>**注意**： 虽然标题为 Lync，它也适用于团队。

**数据包 Shapers**： 任何类型的数据包 snippers、 数据包检查或数据包整形程序设备强不建议使用，并且会显著可能会降低的质量。 

### <a name="principles"></a>原则
有四个一般原则，帮助您了解 Microsoft 团队的呼叫流。 
1.  由其中第一个参与者加入同一区域中的 Office 365 云承载的 Microsoft 团队会议。 (注意： 如果将在某些拓扑中，此规则的例外，则它们将由相应的呼叫流量所示的本文档中所述。)
2.  使用云的 Office 365 中的团队媒体端点 (MP) 基于媒体处理需求，并不基于呼叫类型。 （例如，点到点呼叫可能用于媒体终结点到过程介质云中转录和/或时具有两个参与者的会议中不能使用任何媒体终结点云录制。）但是，大多数会议将使用 MP 混合和路由目的，分配承载会议。 从客户端发送到 MP 的媒体流量可能会直接路由或 Office 365 云使用传输中继，如果需要由于客户网络防火墙限制。 
3.  媒体流量的对等呼叫发生不可用，假定呼叫不要求在云中 MP 最直接路由 （请参阅上面的 #2）。 首选的路由是直接连接到远程对等方 （客户端），但如果该路由不可用，然后一个或多个传输中继将通信中继。 建议媒体流量应如数据包 shapers、 VPN 服务器等，不遍历服务器，因为这将影响的媒体质量。
4.  始终信号流量转到最近服务器向用户。 

若要了解有关上选择的媒体路径的详细信息，请参阅https://www.youtube.com/watch?v=aD5mUg2ZzLQ。

## <a name="call-flows-in-various-topologies"></a>在不同拓扑中的呼叫流
### <a name="teams-online-pure-topology"></a>团队联机 （"纯"） 拓扑
未部署任何服务器，以进行直接路由内部部署的 SBC 业务的 Skype 等情况下利用团队云服务的客户使用这种拓扑。 此外，通过不 Azure Express 路由 Internet 完成到 Office 365 的接口。 

[![Microsoft 团队联机呼叫流图 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*图 1-团队联机 （纯'） 拓扑*

>**说明**：
>- 在上图上箭头的方向反映影响连接功能的企业外围环境的通信的初始方向。 对于媒体 UDP，第一个数据包可能流的反向方向，但可能被阻止这些数据包，直到在其他方向的数据包将流。
>- 团队 Online 业务 online 部署并排 Skype，因此客户端显示为"团队/SFB 用户"。

- 本文档中的部分**团队 Online 的混合拓扑**中所述为内部部署中的业务的可选 Skype
- 对于 PSTN 的可选直接路由本文档的**团队 Online 与直接路由拓扑**部分中所述
- 本文档中**小组具有 Express 路由优化**部分中所述可选 Express 路由

**流说明**：
- **流 2** – 表示作为其团队体验一部分启动客户网络到 Internet 上的用户的流量。 这些流程的示例是 DNS 和对等媒体。
- **流 2** – 表示启动远程移动团队用户，向客户网络的 VPN 流。 
- **流 3** – 表示启动远程移动团队用户对 Office 365/Teams 终结点的流。 
- **流 4** – 表示启动客户网络到 Office 365/Teams 终结点上的用户的流量。
- **流 5** – 表示客户网络内的业务用户，团队用户与其他工作组或 Skype 之间的对等媒体流。
- **流 6** – 表示对等媒体 internet 的远程移动团队用户和业务用户的另一个远程移动的团队或 Skype 之间流动。

#### <a name="use-case-one-to-one"></a>用例： 一对一
一对一呼叫使用通用模型呼叫者将获取一组候选个 IP 地址/端口;本地中继以及身 （公共 IP 地址的客户端可看见的中继）。 呼叫者发送这些候选人向呼叫方邀请中，调用的方还获取一组类似的候选人，并将其发送到呼叫者。 邮件用来查找的调用方/调用方媒体路径起作用，STUN 连接检查和最佳工作路径处于选中状态。 然后，使用选定的候选对发送介质 （即，通过 SRTP 保护的 RTP/RTCP 数据包）。 传输中继部署作为 Office 365 云的一部分。

如果本地 IP 地址/端口候选人或身候选人具有连接，然后将媒体选择直接路径客户端之间 （或通过 NAT）。 如果客户端都客户网络上，则应选择直接路径。 这需要客户网络内的直接 UDP 连接。 如果客户端这两个游牧云用户，然后根据 NAT/防火墙，媒体可能会使用直接连接。

如果一个客户端是内部客户网络上，一个客户端是外部 （例如，移动云用户），然后它不太之间的本地或身候选的直接连接是否正常工作。 在这种情况下，选择是使用从任一客户端的传输中继候选之一 (例如，内部客户端从 Office 365 云中传输中继获取中继候选、 外部客户端需要能够发送到的 STUN/RTP/RTCP 数据包传输中继）。 另一个选项是内部客户端将发送到移动云客户端获取中继候选。 请注意，但强烈建议 UDP 连接的媒体，支持 TCP。

**简要步骤**：
1. 团队需要用户 A 解析 URL 域 (DNS) 通过名 flow2
2. 团队用户 A 分配媒体中继端口团队传输中继上的通过流 4
3. 团队需要用户 A 发送与通过流 4 到 Office 365 的 ICE 候选人"邀请"
4. OFFICE 365 将通知发送给团队用户 B，通过流 4
5. 团队用户 B 分配媒体中继端口团队传输中继上的通过流 4
6. 团队用户 B 发送而被转接回通过流 4 的团队用户 A 的流 4，通过 ICE 候选人"应答"
7. 团队用户 A 和团队用户 B 调用 ICE 连接测试和选择最佳可用的媒体路径 （的各种使用情况下，请参阅下面的图表）
8. 团队用户发送到 Office 365 通过流 4 的遥测

**客户网络： 中**

[![Microsoft 团队联机呼叫流图 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*图 2-客户的网络内*
 
在步骤 7 中，选择"对等"媒体流 5 
>**注意**： 媒体为双向。 流 5 的方向指示一方启动从连接角度来看，将其与本文档中的所有流一致的通信。 在这种情况下，无论使用哪个方向，因为这两个终结点客户网络内部。

**客户网络向外部用户 （媒体中继的团队传输中继）：**

[![Microsoft 团队联机呼叫流图 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*图 3-客户网络向外部用户 （媒体中继的团队传输中继）*
 
在步骤 7 中，选择 4，从到 Office 365 客户网络和流 3，来自远程移动到 Office 365 的团队用户。 通过 Office 365 中的团队传输中继中继这些流程。

>**注意**： 媒体是双向，其中方向表示哪一侧启动从连接角度通信。 在这种情况下，这些流程用于信号和媒体，通过不同的传输协议和地址。

**客户网络向外部用户 （直接媒体）：**

[![Microsoft 团队联机呼叫流图 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*图 4-客户网络向外部用户 （直接媒体）*
 
在步骤 7 中，从 internet （客户端的对等） 的客户网络的流 2 中，处于选中状态。
>**说明**： 
>- 媒体直接与远程移动用户 （即不中继通过 Office 365 云） 是可选的。 换句话说，客户可以阻止此路径并这样，强制实施通过 Office 365 云中传输中继的媒体路径。
>- 媒体为双向。 到远程移动用户的流 2 的方向指示一方启动从连接角度的通信。 

**VPN 用户与内部用户 （媒体中继的团队传输中继）**

[![Microsoft 团队联机呼叫流图 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*图 5-VPN 用户与内部用户 （媒体中继的团队传输中继）*
 
信号客户通过流 2，并与网络流 4 到 Office 365 的 VPN。 但是，媒体"绕过"VPN 和通过流 3 和 4 到 Office 365 云团队媒体中继路由。

**VPN 用户与内部用户 （直接媒体）**

[![Microsoft 团队联机呼叫流图 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*图 6-VPN 用户与内部用户 （直接媒体）*

通过 2 向客户网络和流 4 到 Office 365 信号到客户网络的 VPN。 但是，媒体"绕过"VPN 和路由通过流 2 从客户的网络到 internet。

>**注意**： 媒体为双向。 到远程移动用户的流 2 的方向指示一方启动从连接角度的通信。

**VPN 用户与外部用户 （直接媒体）**

[![Microsoft 团队联机呼叫流图 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*图 7-VPN 用户与外部用户 （直接媒体）*

通过 2 向客户网络和流 4 到 Office 365 信号到客户网络的 VPN。 但是，媒体"绕过"VPN 和通过流 6 路由。

>**注意**： 媒体为双向。 到远程移动用户的流 6 的方向指示一方启动从连接角度的通信。

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>通过 Office 365 中继的 pstn 的使用案例： 团队
Office 365 云具有允许发出和接收来自公用电话交换网的呼叫的电话系统。 如果 PSTN 中继已通过 Office 365 云连接，则使用本例没有特殊连接要求。 否则为 （直接路由已部署） 然后参阅**TBD**。

[![Microsoft 团队联机呼叫流图 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*图 8-通过 Office 365 中继的 PSTN 团队*

#### <a name="use-case-teams-meeting"></a>使用案例： 团队会议

音频/视频/屏幕共享 (VBSS) 会议服务器是 Office 365 云的一部分。 具有公共 IP 地址必须从客户网络上可以访问，必须将其从游牧云客户端访问。 每个客户端/终结点需要能够连接到会议服务器。

内部客户端将获取本地、 身，和中继候选相同的方式，一对一呼叫所述。 客户端将邀请中的会议服务器发送这些候选人。 会议服务器不使用中继，因为它具有一个公共可访问的 IP 地址，以便它与刚其本地的 IP 地址候选的响应。 客户端和会议服务器将检查连接一对一呼叫所述的方式相同。 

>**说明**：
>- 团队客户端无法加入 Skype 业务会议和 Skype 业务客户端无法加入团队会议。
>- PSTN 用户 （可选）"拨打中"或"拨出"，取决于会议的 PSTN 呼叫的组织者和/或会议设置。 
>- 来宾用户或客户的用户可以加入从来宾专用网络，其通过 FW/NAT 术 シ モ メ 严格的规则。

[![Microsoft 团队联机呼叫流图 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*图 9-团队会议*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>与 Skype 的本地业务的使用案例： 联盟

**媒体中继的 Office 365 云团队传输中继**

[![Microsoft 团队联机呼叫流图 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*图 10-媒体中继的 Office 365 云团队传输中继*

>**说明**： 
>- "联盟"根据定义，是两个租户之间的通信。 在这种情况下，租户 A，使用联机团队，与租户 B，使用本地业务 Skype 建立联盟。 如果租户 B 也使用的 Office 365，然后 Skype 的业务客户端将已使用流 3 与 Office 365 连接。
>- 本文档的范围超出信号和媒体从联合 Skype 的业务客户端到业务其 Skype 部署服务器上。 但是，它所示为清楚起见。

工作组和 for Business 的 Skype 之间信号是"桥接"通过 Office 365 云的网关。

在这种情况下媒体通过团队传输中继到客户网络和远程 Skype 业务客户端通过流 4 的 Office 365 云中继。

**Skype 通过中继进行业务媒体中继联盟租户中的媒体**

[![Microsoft 团队联机呼叫流图 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*图 11-Skype 通过中继进行业务媒体中继联盟租户中的媒体*

>**注意**： 信号和媒体从联合 Skype 的业务客户端到业务其 Skype 部署服务器上已超出本文档的范围。 但是，它所示为清楚起见。

工作组和 for Business 的 Skype 之间信号是"桥接"通过 Office 365 云的网关。

在这种情况下媒体通过内部部署到客户网络媒体中继通过流 2 的业务的 Skype 中继。 （请注意，流量团队用户与联盟的客户网络中远程媒体中继之前将被最初阻止媒体中继反向流量开始流动。 但是，双向流中会打开连接两个方向。）

**直接 （对等）**

[![Microsoft 团队联机呼叫流图 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*图 12-直接 （对等）*

### <a name="teams-online-hybrid-topology"></a>团队 Online 的混合拓扑
这种拓扑适用类似于工作组联机默认 （"纯"），但"上添加"的本地业务 Skype。

[![Microsoft 团队联机呼叫流图 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*图 13-团队 Online 的混合拓扑*
 
>**说明**：
>- 在上图上箭头的方向反映影响连接功能的企业外围环境的通信的初始方向。 对于媒体 UDP，第一个数据包可能流的反向方向，但可能被阻止这些数据包，直到在其他方向的数据包将流。
>- 团队 Online 业务 online 部署并排 Skype，因此客户端显示为"团队/SFB 用户"。

（在工作组联机"纯"拓扑结构） 的其他流：
- **流 5A** – 表示与业务 Skype 客户网络中部署在客户网络边缘媒体中继上的团队用户之间的对等媒体流。

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>使用案例： 业务一对一的 Skype 团队
**客户网络中的混合**

[![Microsoft 团队联机呼叫流图 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*图 14-客户网络中的混合*
 
工作组和 Skype 之间信号 for business 是"桥接"通过 Office 365 云的网关。 但是，媒体直接"对等"客户的网络内通过传送流 5。

**与外部业务用户 – Office 365 中继 Skype 混合客户网络**

[![Microsoft 团队联机呼叫流图 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*图 15-与外部业务用户的 Skype 混合客户网络-Office 365 中继*
 
>**注意**： 信号和媒体从 Skype 业务客户端 for Business 的 Skype 到内部部署服务器上已超出本文档的范围。 但是，它所示为清楚起见。

工作组和 for Business 的 Skype 之间信号是"桥接"通过 Office 365 云的网关。

媒体流 4 通过中继通过团队传输到客户网络的 Office 365 中的中继。

**与外部业务用户 – 通过中继上部署边缘 Skype 混合客户网络**

[![Microsoft 团队联机呼叫流图 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*图 16-混合客户网络与外部业务用户的 Skype-由中继上部署边缘*
 
>**注意**： 信号和媒体从 Skype 业务客户端到 Skype 的内部部署服务器上的业务已超出本文档的范围。 但是，它所示为清楚起见。

信号是"桥接"通过 Office 365 云的网关。

在本地边缘到媒体流 5A 客户网络内部用户团队业务的 Skype 中的业务媒体中继的情况下，媒体中继的 Skype。

### <a name="teams-online-with-direct-routing-topology"></a>团队 Online 与"直接路由"的拓扑
这种拓扑适用类似于工作组联机 （"纯"），但"上添加"直接路由。 

直接路由，以前称为 BYOT （使您自己中继），与第三方公共交换电话服务提供商。 此方法是通过配对的受支持的本地客户拥有会话边界控制器硬件设备到 Office 365 云，并连接到该设备的电话中继可能。 

若要支持这种情况下，客户必须直接路由从 Microsoft 认证合作伙伴的部署认证的 SBC(s)。 SBC 必须按照供应商，建议正确配置，并为可路由从 Office 365 云中的直接 UDP 流量。 媒体可能直接从流向团队/Skype 业务客户端的 SBC （旁路团队网关 (即，MP)） 或遍历通过团队网关。 与 SBC，连接时中继配置为绕过团队网关，基于的 ICE，其中 SBC 支持 ICE Lite，而对业务媒体端点的团队/Skype 支持 ICE 完全。 

[![Microsoft 团队联机呼叫流图 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*图 17-团队 Onine 与直接路由的拓扑*

>**说明**：
>- 在上图上箭头的方向反映影响连接功能的企业外围环境的通信的初始方向。 对于媒体 UDP，第一个数据包可能流的反向方向，但可能被阻止这些数据包，直到在其他方向的数据包将流。
>- 团队 Online 业务 online 部署并排 Skype，因此客户端显示为"团队/SFB 用户"。

（在工作组联机"纯"拓扑结构） 的其他流：
- **流 4** -表示一个从 Office 365 云流向客户网络用于建立与本地 SBC 云中团队媒体服务器之间的连接。
- **流 5B** – 表示与直接路由 SBC 客户网络内"绕过"模式中的团队用户之间的媒体流。
- **流 5c** – 表示之间直接路由 SBC 到另一个直接路由 SBC PSTN 发夹呼叫"绕过"模式中的媒体流。

**内部用户直接路由 （媒体中继的 Office 365 中的团队传输中继）**

[![Microsoft 团队联机呼叫流图 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*图 18-内部用户直接路由 （媒体中继的 Office 365 中的团队传输中继）*
 
>**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

信号和媒体从 SBC 到 Office 365，反之亦然使用流 4，和/或流 4。

信号和媒体从客户的网络内的客户端与 Office 365 云使用流 4。


**远程用户直接路由 （媒体路由至 Office 365 中的媒体服务器 (MP)）**

[![Microsoft 团队联机呼叫流图 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*图 19-远程用户直接路由 （媒体路由至 Office 365 中的媒体服务器 (MP)）*
 
>**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

信号和媒体从 SBC 到 Office 365，反之亦然使用流 4，和/或流 4。

信号和媒体从 Internet 上的客户端与 Office 365 云使用流 3。

**内部用户直接路由 （媒体绕过）**

[![Microsoft 团队联机呼叫流图 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*图 20-直接路由 （媒体绕过） 的内部用户*
 
>**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。

从客户的网络内的客户端到 Office 365 云使用流 4 的信号。

媒体从客户的网络内的客户端到客户的网络内的 SBC 使用流 5B。

**远程用户直接路由 （由 Office 365 中的团队传输中继中继的媒体绕过）**

[![Microsoft 团队联机呼叫流图 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*图 21-远程用户直接路由 （由 Office 365 中的团队传输中继中继的媒体绕过）*
 
>**注意**： SBC 必须是从 Office 365 和 Internet 可路由的公共 IP 地址。

使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。

从 Internet 上的客户端到 Office 365 云使用流 3 信号。

媒体从 Internet 上的客户端到客户的网络内的 SBC 使用流 3 和 4 时，由 Office 365 云团队传输中继中继。 

**远程用户直接路由 （媒体绕过直接）**

[![Microsoft 团队联机呼叫流图 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*图 22-远程用户直接路由 （媒体绕过直接）*
 
>**注意**： SBC 必须是从 Office 365 和 Internet 可路由的公共 IP 地址。

使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。

从 Internet 上的客户端到 Office 365 云使用流 3 信号。

媒体从 Internet 上的客户端到客户的网络内的 SBC 使用流 2。

**直接路由 （媒体绕过） – （由于呼叫转接/传输） 的 PSTN 发夹呼叫**

[![Microsoft 团队联机呼叫流图 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*图 23-直接路由 （媒体绕过）-PSTN 发夹呼叫 （由于呼叫转接/传输）*
 
>**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。

客户端是不足的信号和媒体循环发夹从 PSTN 向 PSTN 呼叫后。

从客户的网络内的 SBC 实例 A 到 SBC 实例 B （其中，A 和 B 可以是同一个实例） 的客户网络内的媒体使用流 5 c。

**跨两个租户 PSTN 发夹呼叫直接路由 （通过 Office 365 的媒体 –）**

[![Microsoft 团队联机呼叫流图 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*跨两个租户的图 24-直接路由 （媒体通过 Office 365） – PSTN 发夹呼叫*
 
>**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。

使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。

客户端是不足的信号和媒体循环发夹从 PSTN 向 PSTN 呼叫后。

从内客户网络 X 的 SBC 实例 A 到 SBC 实例 B 必须通过 O365 媒体服务器中继和不能使用媒体绕过模式。

## <a name="teams-w-express-route-optimization"></a>具有 Express 路由优化的团队

[![Microsoft 团队联机呼叫流图 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*图 25-与 Express 路由优化的团队*
 
在这种情况的两端对齐 Express 路由并将其部署，然后团队流无法重新路由从流流 1 并从流 4 1 的排列的 4。 但是，团队应用程序具有硬依赖项其他 OFFICE 365 流通过流 4 通过 internet 和 4;因此必须不阻止这些流程。 

请注意业务混合边缘流量的 Skype 被路由到 Internet，而不适用于 Express 路由与外部用户和与其他租户的"联盟"进行通信。 

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
7. 团队用户 A 和团队用户 B 调用 ICE 连接测试，并选择流 1 和 3，由 Office 365 云团队传输中继中继。
8. 团队用户通过流 1 和 3 将遥测发送到 Office 365

>**注意**： 必须启用流 4 以对其他微服务要求流 4 支持团队应用程序依赖项。
