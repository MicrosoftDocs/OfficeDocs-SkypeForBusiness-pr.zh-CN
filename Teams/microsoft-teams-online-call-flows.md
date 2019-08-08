---
title: Microsoft Teams 通话流程
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: 介绍团队如何使用各种拓扑中的 Office 365 流。
ms.openlocfilehash: d98f789017c0f5388a0adebd382d947e716d7fc9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239349"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams 通话流程

> [!Tip]
> 观看以下会话, 了解团队如何利用你的网络以及如何规划最佳网络连接:[团队网络规划](https://aka.ms/teams-networking)

## <a name="overview"></a>概述
本文介绍团队如何使用各种拓扑中的 Office 365 调用流。 此外, 它还介绍了用于对等媒体通信的独特团队流。 文档介绍这些流、其用途以及它们在网络上的来源和终止。 为此, 请考虑以下事项:

- 流 X 由本地 Office 365 客户端用于与云中的 Office 365 服务通信。 它源于客户网络, 它在 Office 365 中作为终结点终止。

- 流 Y 由本地 Office 365 客户端用于与 Office 365 有依赖关系的 Internet 上的服务进行通信。 它源于客户网络, 并作为 Internet 上的终结点终止。

本文包含以下部分:

- **背景**-提供后台信息, 例如 Office 365 流可能遍历的网络、流量的类型、从客户网络到 office 365 服务终结点的连接指南、与第三方组件的互操作性, 以及团队用于选择媒体流的原则。

- **各种拓扑中的通话流**-阐释了各种拓扑中的通话流的使用。 对于每个拓扑, 该部分枚举所有受支持的流, 并阐释如何通过多种使用案例使用这些流。 对于每个用例, 它通过流图描述流的序列和选择。 

- **具有 Express 路线优化的团队**-介绍在部署快速路由以进行优化时如何使用这些流, 通过简单拓扑阐释。

## <a name="background"></a>背景
### <a name="network-segments"></a>网络段
**客户网络**: 这是您控制和管理的网络段。 这包括客户办公室中的所有客户连接, 无论是有线还是无线连接的 office 大楼、本地数据中心, 以及 Internet 提供商、快递路线或任何其他私人对等的连接。 

通常情况下, 客户网络具有多个具有防火墙和/或代理服务器的网络外围, 这些服务器强制实施组织的安全策略, 并且仅允许某些已设置和配置的网络流量。 由于你管理此网络, 你可以直接控制网络性能, 因此强烈建议你完成网络评估, 以验证网络中的网站和网络到 Office 365 网络中的性能。 

**Internet**: 这是整个网络的一部分, 该网段将由从客户网络外部连接到 Office 365 的用户使用。 它还可由从客户网络到 Office 365 的某些流量使用。 

已**访问/来宾专用网络**: 这是客户网络外部的网段, 但不在公共 Internet 中, 您的用户和/或其来宾可能会访问。 例如, 家庭专用网络或企业专用网络, 它不会部署团队, 您的用户和/或其与团队服务交互的客户可能会驻留。

>**注意**: 与 Office 365 的连接也适用于这些网络。

**Office 365**: 这是支持 Office 365 服务的网络段。 在全球各地, 全球各地都有与客户网络邻近的边缘。 本文档中提及的函数包括传输中继、会议服务器和媒体处理器。 

**快速路线 (可选)**: 这是您的整个网络的一部分, 它将为您提供与 Office 365 网络的专用专用连接。

### <a name="types-of-traffic"></a>流量类型

**实时媒体**: 在 RTP (实时传输协议) 内封装的数据, 支持音频、视频和屏幕共享工作负荷。 通常情况下, 媒体流量很长很长, 因此你希望此流量能够充分利用最直接的路径, 并将 UDP 与 TCP 用作传输层协议, 这是从质量角度看交互式实时媒体的最佳传输. (注意: 作为最后的手段, 媒体可以使用 TCP/IP, 也可以在 HTTP 协议中使用隧道, 但不建议由于不良的质量影响。)RTP 流通过 SRTP 进行保护, 其中仅加密负载。

**信号**: 客户端和服务器之间的通信链接, 或用于控制活动的其他客户端 (例如, 启动呼叫时) 和发送即时消息。 大多数信号流量使用基于 HTTPS 的 REST 接口, 但在某些情况下 (例如, Office 365 和会话边界控制器之间的连接), 它将使用 SIP 协议。 请务必了解此流量对延迟的敏感程度不太大, 但如果终结点之间的延迟超过几秒, 可能会导致服务中断或呼叫超时。 

### <a name="connectivity-to-office-365"></a>与 Office 365 的连接

团队需要[连接到 Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)。 团队终结点 Url 和 IP 地址范围在[Office 365 url 和 ip 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中列出。 (注意: 打开到 TCP 端口80和443的连接, 以及 UDP 端口3478到3481的连接。)此外, 团队对 Skype for business Online 有依赖关系, 该功能还必须连接到 Internet。

团队媒体流连接是通过标准的 IETF ICE (交互式连接建立) 过程实现的。

### <a name="interoperability-restrictions"></a>互操作性限制
**第三方媒体中继**: 团队媒体流 (即媒体终结点之一是团队) 可能仅遍历团队或 Skype for business 本机媒体中继。 不支持与第三方媒体中继的互操作。 (注意: PSTN 的第三方 SBC 必须终止 RTP/RTCP 流, 通过 SRTP 进行保护, 而不是将其中继到下一跃点。)

**第三方 SIP 代理服务器**: 带有第三方 SBC 和/或网关的团队发来的 "sip" 对话框可能会遍历团队或 Skype for BUSINESS 本机 SIP 代理。 不支持与第三方 SIP 代理的互操作。

**第三方 B2BUA (即 SBC)**: 团队媒体流由/到 PSTN 由第三方 SBC 终止。 但是, 不支持与团队网络中的第三方 SBC (即第三方 SBC 调节两个团队/Skype for business 终结点) 的互操作性。

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Microsoft 团队不推荐的技术

**VPN 网络**: 不建议媒体流量 (即, 流 2 ')。 VPN 客户端应使用分离的 VPN 和路由媒体流量, 如中https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/所述。

>**注意**: 尽管标题是 Lync, 但它也适用于团队。

**数据包 shapers**: 不推荐任何类型的数据包 snippers、数据包检查或数据包整形设备, 可能会显著降低质量。 

### <a name="principles"></a>规则
有四个一般原则可帮助你理解 Microsoft 团队的通话流:
 
1.  Microsoft 团队会议由与第一个参与者联接的同一区域中的 Office 365 托管。 (注意: 如果在某些拓扑中会出现此规则的例外情况, 将在此文档中介绍这些例外, 并通过相应的通话流进行说明。)

2.  Office 365 中的团队媒体终结点基于媒体处理需求使用, 而不是基于呼叫类型。 (例如, 点到点呼叫可以使用云中的媒体终结点来处理用于脚本和/或录制的媒体, 而两个参与者的会议可能不会使用云中的任何媒体终结点。)但是, 大多数会议会将媒体终结点用于混合和路由用途, 分配了托管会议的位置。 从客户端发送到媒体终结点的媒体流量可能会直接路由, 或者在 Office 365 中使用传输中继 (如果由于客户网络防火墙限制而需要)。 

3.  对等调用的媒体流量将获得可用的最直接路线, 假设该呼叫不会在云中强制使用媒体终结点 (请参阅上面的 #2)。 首选路由直接发送到远程对等 (客户端), 但如果该路由不可用, 则一个或多个传输中继将中继流量。 建议媒体流量不应遍历服务器 (如数据包 shapers、VPN 服务器等), 因为这将影响媒体质量。

4.  信号流量始终转到最接近于用户的服务器。 

若要了解有关所选媒体路径的详细信息, 请参阅https://www.youtube.com/watch?v=1tmHMIlAQdo。

## <a name="call-flows-in-various-topologies"></a>各种拓扑中的呼叫流
### <a name="teams-topology"></a>团队拓扑
此拓扑由客户使用, 它在没有任何本地部署 (如 Skype for Business Server 或手机系统直接路由) 的情况下利用来自云的团队服务。 此外, Office 365 的接口通过不使用 Azure Express 路由的 Internet 完成。 

[![Microsoft 团队在线通话流程图01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*图 1-团队拓扑*

请注意:

- 上图中箭头的方向反映了在企业外围环境中影响连接的通信的初始方向。 在 UDP for media 的情况下, 第一个数据包可能沿相反方向流动, 但这些数据包可能会被阻止, 直到其他方向的数据包才会流动。
- 团队与 Skype for Business Online 并排部署, 因此客户将显示为 "团队/SFB 用户"。

有关详细信息, 请查看本文后面的以下可选拓扑:

- 在**团队混合拓扑**中介绍了 Skype for business 内部部署。
- 手机系统直接路由 (适用于 PSTN 连接) 在**具有直接路由拓扑的团队**中介绍。
- 快速路线在**具有 Express 路线优化的团队**中介绍。

**流说明**:
- **流 2** -表示用户在客户网络上作为用户团队体验的一部分启动的流程。 这些流的示例是 DNS 和对等媒体。
- **流 2 "** –表示由远程移动团队用户发起的流, 其中包含指向客户网络的 VPN。 
- **流 3** -表示由远程移动团队用户从 Office 365/团队终结点发起的流。 
- **流 4** -表示用户在客户网络上由 Office 365/团队终结点发起的流程。
- **流 5** -表示团队用户与其他团队之间的对等媒体流, 或客户网络中的 Skype for business 用户。
- **流 6** -表示远程移动团队用户与其他远程移动团队或 Internet 上的 Skype for business 用户之间的对等媒体流。

#### <a name="use-case-one-to-one"></a>使用案例: 一对一
一对一呼叫使用一个通用模型, 在该模型中, 呼叫者将获得一组候选项, 其中包含 IP 地址/端口, 包括本地、中继和反身 (客户的公共 IP 地址, 如中继) 候选人。 呼叫方将这些候选人发送给被呼叫方;被呼叫方还会获取一组类似的候选项, 并将其发送给呼叫方。 STUN 连接检查消息用于查找哪些呼叫方/被叫方媒体路径正常工作, 并且选择了最佳工作路径。 然后, 将使用所选候选人对发送媒体 (即, 通过 SRTP 保护的 RTP/RTCP 数据包)。 传输中继作为 Office 365 的一部分进行部署。

如果本地 IP 地址/端口候选或反身候选具有连接, 则将为媒体选择客户端 (或通过 NAT) 之间的直接路径。 如果客户端位于客户网络上, 则应选择直接路径。 这需要客户网络内的直接 UDP 连接。 如果客户端都是 nomadic 云用户, 则根据 NAT/防火墙, 媒体可能使用直接连接。

如果一个客户端是客户网络内部的客户端, 而另一个客户端是外部客户端 (例如, 移动云用户), 则本地或反身候选人之间的直接连接不太可能是正常工作。 在这种情况下, 选项是使用来自任何客户端的传输中继候选人之一 (例如, 内部客户从 Office 365 中的传输中继获得中继候选人; 外部客户端需要能够将 STUN/RTP/RTCP 数据包发送到传输中继)。 另一个选项是内部客户端发送到移动云客户端获取的中继候选人。 请注意, 虽然强烈建议媒体的 UDP 连接, 但支持 TCP。

**高级别步骤**:
1. 团队用户 A 通过 flow2 解析 URL 域名 (DNS)
2. 团队用户 A 通过流量4在团队传输中继上分配媒体中继端口
3. 团队用户 A 通过从候选人候选人发送 "邀请", 从流4到 Office 365
4. Office 365 通过流量4向团队用户 B 发送通知
5. 团队用户 B 通过流量4在团队传输中继上分配媒体中继端口
6. 团队用户 B 通过流4通过流4发送 "答案", 通过流4向团队用户 A 转发给团队用户 A。
7. 团队用户 A 和团队用户 B 调用 ICE 连接测试, 并选择最佳可用媒体路径 (请参阅下面的各种使用案例的图表)
8. 团队用户通过流量4向 Office 365 发送遥测

**在客户网络中:**

[![Microsoft 团队在线通话流程图02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*图 2-客户网络内部*
 
在步骤7中, 选择了 "对等媒体流 5"。
 
媒体为双向媒体。 流5的方向表示, 一方从连接的角度启动通信, 与本文档中的所有流一致。 在这种情况下, 使用哪个方向无关紧要, 因为这两个终结点位于客户网络内。

**向外部用户的客户网络 (按团队传输中继的媒体中继):**

[![Microsoft 团队在线通话流程图03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*图 3-向外部用户 (按团队传输中继的媒体中继) 的客户网络*
 
在步骤 7 (从客户网络到 Office 365) 和流程 3 (从 "远程移动团队用户到 Office 365") 中, 选择 "流程 4"。 这些流程由 Office 365 中的团队传输中继进行中继。

媒体是双向的, 其中, 方向指示哪一侧从连接的角度开始通信。 在这种情况下, 这些流程通过不同的传输协议和地址用于发送信号和媒体。

**向外部用户 (直接媒体) 的客户网络:**

[![Microsoft 团队在线通话流程图04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*图 4-外部用户 (直接媒体) 的客户网络*
 
在步骤7中, 选择 "从客户网络到 Internet (客户端对等)" 中的 "流程 2"。
- 带有远程移动用户 (即未通过 Office 365 中继) 的直接媒体是可选的。 换句话说, 客户可能会阻止此路径通过 Office 365 中的传输中继强制执行媒体路径。

- 媒体为双向媒体。 流2到远程移动用户的方向指示一方从连接的角度启动通信。 

**VPN 用户到内部用户 (按团队传输中继的媒体中转)**

[![Microsoft 团队在线通话流程图05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*图 5-向内部用户 (按团队传输中继的媒体中继) 的 VPN 用户*
 
VPN 与客户网络之间的信号传输是通过流程2。 客户网络与 Office 365 之间的信号信号是通过流量4进行的。 但是, 媒体绕过 VPN, 并通过流3和4通过 Office 365 中的团队媒体中继进行路由。

**VPN 用户到内部用户 (直接媒体)**

[![Microsoft 团队在线通话流程图06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*图 6-向内部用户 (直接媒体) 的 VPN 用户*

VPN 与客户网络之间的信号传输是通过流程2。 客户网络与 Office 365 之间的信号信号是通过流量4进行的。 但是, 媒体绕过 VPN, 并通过从客户网络到 Internet 的流程2路由。

媒体为双向媒体。 流2到远程移动用户的方向指示一方从连接的角度启动通信。

**向外部用户 (直接媒体) 的 VPN 用户**

[![Microsoft 团队通话流程图07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*图 7-向外部用户 (直接媒体) 的 VPN 用户*

VPN 用户与客户网络之间的信号传送方式是通过流 2 "和从流4到 Office 365。 但是, 媒体绕过 VPN 并通过流6路由。

媒体为双向媒体。 流6到远程移动用户的方向指示一方从连接的角度启动通信。

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>使用案例: 团队到 PSTN 通过 Office 365 主干
Office 365 具有一个电话系统, 允许从公共交换电话网络 (PSTN) 拨打和接听电话。 如果 PSTN 主干通过电话系统呼叫计划连接, 则此使用情形没有特殊的连接要求。 (如果要将自己的本地 PSTN 主干连接到 Office 365, 可以使用 "电话系统直接路由"。)

[![Microsoft 团队在线通话流程 (见图 08)](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*图 8-通过 Office 365 主干的团队到 PSTN*

#### <a name="use-case-teams-meeting"></a>使用案例: 团队会议

音频/视频/屏幕共享 (VBSS) 会议服务器是 Office 365 的一部分。 它具有必须可从客户网络访问且必须可从 Nomadic 云客户端访问的公共 IP 地址。 每个客户端/终结点都需要能够连接到会议服务器。

内部客户将按照与一对一通话描述的相同方式获取本地、反身和中继候选人。 客户端会将这些候选人发送到邀请中的会议服务器。 会议服务器不使用中继, 因为它具有可公开访问的 IP 地址, 因此它将通过其本地 IP 地址候选进行响应。 客户端和会议服务器将以与一对一呼叫描述的相同方式检查连接。 

请注意:

- 团队客户端无法加入 Skype for Business 会议, 并且 Skype for business 客户端无法加入团队会议。

- PSTN 用户可以选择 "拨入" 或 "拨出", 具体取决于会议的组织者 PSTN 呼叫和/或会议设置。 

- 来宾用户或客户用户可以通过具有严格规则的 FW/NAT 保护的来宾专用网络进行联接。

[![Microsoft 团队在线通话流程图09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*图 9-团队会议*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>使用案例: 使用 Skype for business 内部部署联盟

**按团队在 Office 365 中传输中继的媒体中继**

[![Microsoft 团队在线通话流程图10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*图 10-按组在 Office 365 中传输中继的媒体中继*

请注意:

- 根据定义, 联盟是两个租户之间的通信。 在这种情况下, 租户 A 使用团队, federates 与租户 B 一起使用 Skype for Business 内部部署。 如果租户 B 也使用的是 Office 365, 则 Skype for Business 客户端将使用流3与 Office 365 连接。

- 来自联合 Skype for business 客户端到本地 Skype for Business 服务器的信号和媒体已超出本文档的范围。 但是, 此处对此进行了明确说明。

- 团队和 Skype for business 之间的信号由 Office 365 中的网关桥接。

- 在此情况下, 媒体由团队将 Office 365 中的传输传输到客户网络和通过流4远程 Skype for Business 客户端进行中继。

**联合租户中 Skype for business Media 中继的媒体中继**

[![Microsoft 团队在线通话流程图11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*图 11-联合租户中 Skype for business Media 中继的媒体中继*

请注意:

- 从联合 Skype for business 客户端到本地 Skype for Business 服务器的信号和媒体已超出本文档的范围。 但是, 此处对此进行了明确说明。

- 团队和 Skype for business 之间的信号由 Office 365 中的网关桥接。

- 在这种情况下, 媒体将由 Skype for business 本地媒体中继中继到通过流2的客户网络。 (请注意, "媒体中继" 中来自团队用户到远程媒体中继的流量最初将由媒体中继阻止, 直到流处于相反方向。 但是, 双向流将以两种方向打开连接。)

**直接 (对等)**

[![Microsoft 团队在线通话流程图12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*图 12-直接 (对等)*

### <a name="teams-hybrid-topology"></a>团队混合拓扑
此拓扑包括具有 Skype for Business 内部部署的团队。

[![Microsoft 团队在线通话流程图13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*图 13-团队混合拓扑*
 
- 上图中箭头的方向反映了在企业外围环境中影响连接的通信的初始方向。 在 UDP for media 的情况下, 第一个数据包可能沿相反方向流动, 但这些数据包可能会被阻止, 直到其他方向的数据包才会流动。

- 团队与 Skype for Business Online 并排部署, 因此客户将显示为 "团队/SFB 用户"。

其他流 (在团队拓扑之上):
- **流 5a** –表示客户网络中的团队用户之间的对等媒体流和客户网络边缘的 Skype for business 本地媒体中继。

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>使用案例: 团队到 Skype for business 一对一
**客户网络中的混合**

[![Microsoft 团队在线通话流程图14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*图 14-客户网络中的混合*
 
团队和 Skype for business 之间的信号由 Office 365 中的网关桥接。 但是, 媒体在客户网络中通过流量5直接路由到对等。

**具有外部 Skype for Business 用户的混合客户网络-由 Office 365 中继**

[![Microsoft 团队在线通话流程图15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*图 15-使用外部 Skype for Business 用户的混合客户网络-由 Office 365 进行中继*

请注意:

- 从 Skype for business 客户端到本地 Skype for Business 服务器的信号和媒体已超出本文档的范围。 但是, 此处对此进行了明确说明。

- 团队和 Skype for business 之间的信号由 Office 365 中的网关桥接。

- 媒体通过团队将 Office 365 中的中继传输到流4中的客户网络来进行中继。

**具有外部 Skype for Business 用户的混合客户网络-通过本地边缘进行中继**

[![Microsoft 团队在线通话流程图16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*图 16-具有外部 Skype for Business 用户的混合客户网络-通过本地边缘进行中继*
 
请注意:

- 从 Skype for business 客户端到本地 Skype for Business 服务器的信号和媒体已超出本文档的范围。 但是, 此处对此进行了明确说明。

- 信号由 Office 365 中的网关桥接。

- Skype for business Media 中继中的 skype for business Media 中继可通过媒体流5A 将媒体转发给客户网络中的团队用户。

### <a name="teams-with-phone-system-direct-routing-topology"></a>具有手机系统直接路由拓扑的团队
此拓扑包括具有手机系统直接路由的团队。 

直接路由使你能够通过将支持的本地客户拥有的会话边界控制器 (SBC) 硬件设备与 Office 365 配对, 然后将电话服务主干连接到该服务提供商, 从而使用第三方公共交换电话网络 (PSTN) 服务提供商该设备。 

若要支持此方案, 客户必须部署经认证的 SBC, 以便直接从 Microsoft 认证合作伙伴之一进行路由。 SBC 必须按照供应商的建议进行配置, 并可路由来自 Office 365 的直接 UDP 流量。 媒体可能直接从团队和/或 Skype for business 客户端传递到 SBC (绕过团队网关) 或遍历团队网关。 当主干配置为绕过团队网关时, 与 sbc 的连接是基于 ICE 的, 其中 SBC 支持 ICE, 而团队/Skype for Business media 终结点支持 ICE 完全。 

[![Microsoft 团队在线通话流程图17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* 图 17-具有手机系统直接路由拓扑的团队

请注意:

- 上图中箭头的方向反映了在企业外围环境中影响连接的通信的初始方向。 在 UDP for media 的情况下, 第一个数据包可能沿相反方向流动, 但这些数据包可能会被阻止, 直到其他方向的数据包才会流动。

- 团队与 Skype for Business Online 并排部署, 因此客户将显示为 "团队/SFB 用户"。

其他流 (位于团队联机拓扑的顶部):
- **流 4 "** -表示从 Office 365 到客户网络的流, 用于在云中的团队媒体服务器与 SBC 内部部署之间建立连接。
- **流 5b** -表示客户网络中的团队用户之间的媒体流, 在旁路模式下直接路由 SBC。
- **流 5c** -表示在 PSTN hairpin 呼叫旁路模式下直接路由 sbc 与另一个直接路由 sbc 之间的媒体流。

**具有直接路由的内部用户 (按团队在 Office 365 中传输中继的媒体中转)**

[![Microsoft 团队在线通话流程图18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*图 18-直接路由的内部用户 (按团队在 Office 365 中传输中继的媒体中继)*

请注意:
 
- SBC 必须具有可通过 Office 365 路由的公共 IP 地址。

- 从 SBC 到 Office 365 的信号和媒体 (反之亦然) 使用流4和/或流4。

- 从客户网络中的客户端到 Office 365 的信号和媒体使用流4。


**具有直接路由的远程用户 (通过 Office 365 中的媒体服务器 (MP) 路由媒体)**

[![Microsoft 团队在线通话流程图19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*图 19-使用直接路由的远程用户 (通过 Office 365 中的媒体服务器 (MP) 路由媒体)*
 
请注意:

- SBC 必须具有可通过 Office 365 路由的公共 IP 地址。

- 从 SBC 到 Office 365 的信号和媒体 (反之亦然) 使用流4和/或流4。

- 从 Internet 上的客户端到 Office 365 的信号和媒体使用流程3。

**内部用户直接路由 (媒体旁路)**

[![Microsoft 团队在线通话流程图20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*图 20-内部用户直接路由 (媒体旁路)*
 
请注意:

- SBC 必须具有可通过 Office 365 路由的公共 IP 地址。

- 从 SBC 到 Office 365 的信号, 反之亦然, 使用流程4和/或流4。

- 从客户网络中的客户端发送到 Office 365 的信号使用流4。

- 从客户网络中的客户端到客户网络内的 SBC 的媒体使用流程5B。

**具有直接路由的远程用户 (由团队在 Office 365 中传输中继的媒体绕过中继)**

[![Microsoft 团队在线通话流程图21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*图 21-使用直接路由的远程用户 (由团队在 Office 365 中传输中继的媒体旁路中继)*

请注意:

- SBC 必须具有可通过 Office 365 和 Internet 进行路由的公共 IP 地址。

- 从 SBC 到 Office 365 的信号, 反之亦然, 使用流4和/或流4。

- 从 Internet 上的客户端发送到 Office 365 的信号使用流程3。

- 从 Internet 上的客户端到客户网络中 SBC 的媒体使用流3和 4, 并按团队在 Office 365 中传输中继的方式进行中继。 

**远程用户直接路由 (媒体旁路直接路由)**

[![Microsoft 团队在线通话流程图22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*图 22-远程用户直接路由 (媒体旁路直接路由)*
 
请注意:

- SBC 必须具有可通过 Office 365 和 Internet 进行路由的公共 IP 地址。

- 从 SBC 到 Office 365 的信号, 反之亦然, 使用流4和/或流4。

- 从 Internet 上的客户端发送到 Office 365 的信号使用流程3。

- 从 Internet 上的客户端到客户网络中的 SBC 的媒体使用流2。

**直接路由 (媒体旁路)-PSTN hairpin 呼叫 (由于呼叫转发/传输)**

[![Microsoft 团队在线通话流程图23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*图 23-直接路由 (媒体旁路)-PSTN hairpin 呼叫 (由于呼叫转发/传输)*
 
请注意:

- SBC 必须具有可通过 Office 365 路由的公共 IP 地址。

- 从 SBC 到 Office 365 的信号, 反之亦然, 使用流4和/或流4。

- 从 PSTN 到 PSTN hairpinned 呼叫后, 客户端不会发出信号和媒体循环。

- 从客户网络内的 SBC 实例 A 到客户网络 (其中 A 和 B 可以是同一实例) 内的 sbc 实例 B 的媒体使用流程5C。

**直接路由 (通过 Office 365 的媒体)-跨两个租户的 PSTN hairpin 呼叫**

[![Microsoft 团队在线通话流程图24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*图 24-直接路由 (通过 Office 365 的媒体)-跨两个租户的 PSTN hairpin 呼叫*
 
请注意:

- SBC 必须具有可通过 Office 365 路由的公共 IP 地址。

- 从 SBC 到 Office 365 的信号, 反之亦然, 使用流4和/或流4。

- 从 PSTN 到 PSTN hairpinned 呼叫后, 客户端不会发出信号和媒体循环。

- 来自 SBC 实例 A (从客户网络 X 到 SBC 实例 B) 内部的媒体必须通过 Office 365 媒体服务器中继, 并且无法使用绕过模式。

## <a name="teams-with-express-route-optimization"></a>具有快速路线优化的团队

[![Microsoft 团队在线通话流程图25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*图 25-具有快速路线优化的团队*
 
在显示和部署快速路由的情况下, 团队流可以从流4重新路由到流 1, 从流 4 "重新路由到流 1"。 但是, 团队应用程序对通过 internet 进行的其他 Office 365 流的相关性很难, 因为流4和 4 ';因此, 不能阻止这些流程。 

请注意, Skype for Business 混合边缘流量将路由到 Internet, 而不是快速路由以与外部用户通信并与其他租户联盟。 

若要防止非对称流, 重新路由必须在两个方向上。 换句话说, 客户网络中的地址通过 Internet 或快速路由进行路由, 基于优化, 但不能通过这两者进行路由。

例如：

**向外部用户的客户网络 (按团队传输中继的媒体中继):**

[![Microsoft 团队在线通话流程图26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*图 26-向外部用户 (按团队传输中继的媒体中继) 的客户网络*
 
**高级别步骤:**
1. 客户网络中的团队用户通过 flow2 解析 URL 域名 (DNS)
2. 客户网络中的团队用户通过流1分配团队传输中继的媒体中继端口
3. 客户网络中的团队用户通过将 "邀请" 通过流1到 Office 365 的冰候选人发送 "邀请"
4. OFFICE 365 通过流程3向外部团队用户发送通知
5. 团队外部用户通过流3在团队传输中继上分配媒体中继端口
6. 团队外部用户通过流3发送 "解答" 与 ICE 候选人, 通过流3转发给团队用户 A。
7. 团队用户 A 和团队用户 B 调用 ICE 连接测试并选择流1和 3 (由 Office 365 中的团队传输中继进行中继)
8. 团队用户通过流1和3将遥测发送到 Office 365

>**注意**: 必须启用流4以支持团队应用程序对流程4的其他微服务的依赖关系。
