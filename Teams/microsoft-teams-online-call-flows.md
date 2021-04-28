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
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 了解 Teams 如何在各种拓扑中使用 Office 365 流，以及用于点对点媒体通信的唯一团队流。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 27a2c68483c3d54cb3f3572bbed3a06a53ccc67e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059206"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams 通话流程

> [!TIP]
> 观看此会话，了解 Teams 如何利用你的网络以及如何规划最佳网络连接 [：Teams 网络规划](https://aka.ms/teams-networking)。

## <a name="overview"></a>概述

本文介绍 Teams 如何在各种拓扑中使用 Microsoft 365 或 Office 365 呼叫流。 此外，还介绍了用于点对点媒体通信的唯一 Teams 流。 本文档介绍这些流及其用途，以及网络上流的来源和终止。 出于本文的目的，假设以下各项：

- 本地客户端使用流 X 与云中的 Microsoft 365 或 Office 365 服务通信。 它源自客户网络，在 Microsoft 365 或 Office 365 中终止为终结点。

- 本地客户端使用流 Y 与 Microsoft 365 或 Office 365 所依赖的 Internet 上的服务通信。 它源自客户网络，在 Internet 上终止为终结点。

本文介绍以下信息：

- **背景**。 提供背景信息，例如流可能遍历的网络、流量类型、从客户网络到 Microsoft 365 或 Office 365 服务终结点的连接指南、第三方组件的互操作性，以及 Teams 用于选择媒体流的原则。

- **调用各种拓扑中的流**。 演示如何在各种拓扑中使用调用流。 对于每个拓扑，该部分枚举所有受支持的流，并说明如何在多种用例中使用这些流。 对于每个用例，它使用流程图描述流的序列和选择。

- **具有 Express Route 优化的团队**。 介绍部署 Express Route 进行优化时如何使用这些流，使用简单的拓扑进行演示。

## <a name="background"></a>背景

### <a name="network-segments"></a>网段

**客户网络**。 这是您控制和管理的网络段。 这包括客户办公室内的所有客户连接，无论是有线连接还是无线连接、办公大楼间的连接、与本地数据中心的连接，以及 Internet 提供商、Express Route 或其他任何专用对等互连的连接。

通常，客户网络具有多个网络外围，防火墙和/或代理服务器强制实施组织的安全策略，并且仅允许已设置和配置的某些网络流量。 由于您管理此网络，因此您可以直接控制网络的性能，我们建议您完成网络评估，以验证网络站点内部的性能以及从网络到 Microsoft 365 或 Office 365 网络的性能。

**Internet。** 这是整个网络的一部分，由从客户网络外部连接到 Microsoft 365 或 Office 365 的用户使用。 从客户网络发到 Microsoft 365 或 Office 365 的一些流量也使用这种流量。

**访问的或来宾专用网络**。 这是用户及其来宾可能访问 (（例如，家庭专用网络或企业专用网络）不在客户网络外部（但不在公共 Internet 中）访问的网络段，不部署 Teams，而用户及其与 Teams 服务交互的客户可能驻留在) 。

> [!NOTE]
> 与 Microsoft 365 或 Office 365 的连接也适用于这些网络。

**Microsoft 365 或 Office 365。** 这是支持 Microsoft 365 或 Office 365 服务的网段。 它分布在世界各地，在大多数位置具有靠近客户网络的边缘。 函数包括传输中继、会议服务器和媒体处理器。

**Express Route (可选) 。** 这是整个网络的一部分网络段，可让你与 Microsoft 365 或 Office 365 网络建立专用连接。

### <a name="types-of-traffic"></a>流量类型

**实时媒体**。 支持音频、视频和屏幕共享工作负荷 (RTP) 实时传输协议内封装的数据。 通常，媒体流量对延迟高度敏感，因此，你可能希望此流量采用尽可能最直接的路径，并使用 UDP 与 TCP 作为传输层协议，这是从质量角度对交互式实时媒体的最佳传输。  (请注意，作为最后手段，媒体可以使用 TCP/IP，也可在 HTTP 协议内进行隧道传输，但由于质量影响不佳，不建议这样做。) RTP 流使用 SRTP 进行保护，其中只加密有效负载。

**发出信号**。 客户端与服务器或其他客户端之间的通信链接，用于控制活动 (例如，当发起呼叫时) 发送即时消息。 大多数信令流量使用基于 HTTPS 的 REST 接口，但在某些情况下 (例如，Microsoft 365 或 Office 365 之间的连接与会话边界控制器) 它使用 SIP 协议。 必须了解，此流量对延迟不太敏感，但如果终结点之间的延迟超过几秒，则可能会导致服务中断或调用超时。

### <a name="connectivity-to-microsoft-365-or-office-365"></a>与 Microsoft 365 或 Office 365 的连接

Teams[需要连接到 Internet。](/office365/enterprise/assessing-network-connectivity) Office [365](/office365/enterprise/urls-and-ip-address-ranges)URL 和 IP 地址范围中列出了 Teams 终结点 URL 和 IP 地址范围。  (请注意，需要打开到 TCP 端口 80 和 443 以及到 UDP 端口 3478 到 3481 的连接。) 此外，Teams 依赖于 Skype for Business Online，而 Skype for Business Online 也必须连接到 Internet。

Teams 媒体流连接是使用标准 IETF 交互式连接建立 (ICE) 过程实现的。

### <a name="interoperability-restrictions"></a>互操作性限制

**第三方媒体中继**。 Teams 媒体流 (，即其中一个媒体终结点是 Teams) 只能遍历 Teams 或 Skype for Business 本机媒体中继。 不支持第三方媒体中继的互操作性。  (PSTN 边界上的第三方 SBC 必须终止使用 SRTP 保护的 RTP/RTCP 流，而不是中继到下一跃点.) 

**第三方 SIP 代理服务器**。 具有第三方 SBC 和/或网关的 Teams 信号 SIP 对话框可能遍历 Teams 或 Skype for Business 本机 SIP 代理。 不支持第三方 SIP 代理的互操作性。

**第三方 B2BUA (或 SBC) 。** 流入和流出 PSTN 的 Teams 媒体流由第三方 SBC 终止。 但是，在 Teams 网络内与第三方 SBC 的互操作性 (其中第三方 SBC 协调两个 Teams 或 Skype for Business 终结点) 不受支持。

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Microsoft Teams 不建议使用的技术

**VPN 网络**。 不建议将媒体流量 (流 2') 。 VPN 客户端应像任何外部非 VPN 用户一样使用拆分隧道并路由 Teams 媒体流量，如启用 Lync 媒体绕过 VPN 隧道 [中指定](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)。

> [!NOTE]
> 尽管游戏指示 Lync，但它也适用于 Teams。

**数据包形状。** 对于 Teams 媒体流量，不建议使用任何类型的数据包捕获器、数据包检查或数据包形状器设备，并且可能会显著降低质量。

### <a name="principles"></a>原则

有四个一般性原则可帮助你了解 Microsoft Teams 的呼叫流：

- Microsoft Teams 会议由 Microsoft 365 或 Office 365 在首次参与者加入的同一区域主持。  (请注意，如果某些拓扑中存在此规则例外，本文档中将介绍这些异常，并按相应的调用流.) 

- Microsoft 365 或 Office 365 中的 Teams 媒体终结点基于媒体处理需求使用，而不是基于呼叫类型。  (例如，点到点呼叫可以使用云中的媒体终结点处理媒体听录或录制，而包含两个参与者的会议可能不会使用云中任何媒体终结点。) 但是，大多数会议将使用媒体终结点进行混合和路由，而该终结点是在托管会议时分配的。 由于客户网络防火墙限制，从客户端发送到媒体终结点的媒体流量可直接路由或使用 Microsoft 365 或 Office 365 中的传输中继（如果需要）。

- 点对点呼叫的媒体流量采用最直接的可用路由，假设该调用不强制云中的媒体终结点 (请参阅前面的原则) 。 首选路由将直接路由到远程对等 (客户端) ，但如果该路由不可用，则一个或多个传输中继将中继流量。 建议媒体流量不要转置数据包形状器、VPN 服务器等服务器，因为这会影响媒体质量。

- 信令流量始终会转到离用户最近的服务器。

若要了解有关所选媒体路径的详细信息，请参阅了解 Microsoft Teams 中的媒体流[- BRK4016。](https://www.youtube.com/watch?v=1tmHMIlAQdo)

## <a name="call-flows-in-various-topologies"></a>各种拓扑中的调用流

### <a name="teams-topology"></a>Teams 拓扑

此拓扑由利用云中的 Teams 服务的客户使用，无需任何本地部署，例如 Skype for Business Server 或电话系统直接路由。 此外，无需 Azure Express Route 即可通过 Internet 完成 Microsoft 365 或 Office 365 的界面。

[![Microsoft Teams Online 呼叫流图 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*图 1 - Teams 拓扑*

请注意：

- 上图中箭头的方向反映影响企业外围连接的通信的启动方向。 对于媒体的 UDP，第一 (数据包) 反向流动，但可能会阻止这些数据包，直到其他方向的数据包流动。
- Teams 与 Skype for Business Online 并排部署，因此客户端显示为"Teams/SFB 用户"。

可以在本文的稍后部分找到有关以下可选拓扑详细信息：

- Teams 混合拓扑 中介绍了 Skype for Business **本地部署**。
- 使用直接路由 (Teams) **PSTN 连接的电话系统直接路由方法**。
- Express Route 在 **具有 Express Route 优化的 Teams 中进行了介绍**。

**流说明**：

- **流 2** – 表示作为用户 Teams 体验的一部分，由客户网络上用户启动的流到 Internet。 这些流的示例包括 DNS 和对等媒体。
- **Flow 2'** – 表示由远程移动 Teams 用户启动的流，具有到客户网络的 VPN。
- **流 3** – 表示由远程移动 Teams 用户启动到 Microsoft 365 或 Office 365/Teams 终结点的流。
- **流 4** – 表示客户网络上用户启动到 Microsoft 365 或 Office 365/Teams 终结点的流。
- **流 5** – 表示 Teams 用户与客户网络中另一个 Teams 或 Skype for Business 用户之间的对等媒体流。
- **Flow 6** – 表示远程移动 Teams 用户与通过 Internet 的另一个远程移动 Teams 或 Skype for Business 用户之间的对等媒体流。

#### <a name="use-case-one-to-one"></a>用例：一对一

一对一调用使用通用模型，调用方将获取一组候选项，其中包括 IP 地址/端口，包括客户端的本地、中继和反身 (公共 IP 地址，如中继候选) 所看到的。 调用方将这些候选者发送到被调用方;被调用方还会获取一组类似的候选项，并将其发送给调用方。 STUN 连接性检查消息用于查找哪些调用方/被呼叫方媒体路径工作，并且选择了最佳工作路径。 媒体 (，即使用 SRTP 保护的 RTP/RTCP 数据包) 所选候选对发送。 传输中继部署为 Microsoft 365 和 Office 365 的一部分。

如果本地 IP 地址/候选端口或反身候选项具有连接性，则客户端之间的直接路径 (或者使用 NAT) 媒体。 如果客户端都位于客户网络上，应选择直接路径。 这需要在客户网络中建立直接 UDP 连接。 如果客户端都是云用户，则根据 NAT/防火墙，媒体可能会使用直接连接。

如果一个客户端位于客户网络内部，一个客户端是外部客户端 (例如移动云用户) ，则本地候选者或反身候选者之间的直接连接不太可能正常。 在这种情况下，一个选项是使用任一客户端中的一个传输中继候选项 (例如，内部客户端从 Microsoft 365 或 Office 365 中的传输中继获取中继候选项;外部客户端需要能够将 STUN/RTP/RTCP 数据包发送到传输中继) 。 另一个选项是内部客户端发送到移动云客户端获取的中继候选项。 请注意，尽管强烈建议建立媒体的 UDP 连接，但支持 TCP。

**高级步骤**：

1. Teams 用户 A 使用流 2 (DNS) 解析 URL 域名。
1. Teams 用户 A 使用流 4 在 Teams 传输中继上分配媒体中继端口。
1. Teams 用户 A 使用流 4 向 Microsoft 365 或 Office 365 发送 ICE 候选项的"邀请"。
1. Microsoft 365 或 Office 365 使用流 4 向 Teams 用户 B 发送通知。
1. Teams 用户 B 使用流 4 在 Teams 传输中继上分配媒体中继端口。
1. Teams 用户 B 使用流 4 向 ICE 候选项发送"答案"，流 4 将流 4 转发回 Teams 用户 A。
1. Teams 用户 A 和 Teams 用户 B 调用 ICE 连接测试，并选择了最佳可用媒体路径 (请参阅下图了解各种用例) 。
1. Teams 用户使用流 4 向 Microsoft 365 或 Office 365 发送遥测数据。

**在客户网络中：**

[![Microsoft Teams Online 呼叫流图 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*图 2 - 在客户网络中*

在步骤 7 中，选择"对等媒体流 5"。

媒体是双向的。 流 5 的方向指示一端从连接角度启动通信，与本文档中所有流一致。 在这种情况下，使用哪个方向并不重要，因为两个终结点都位于客户网络中。

**客户网络与外部用户 (Teams 传输中继中继的) ：**

[![Microsoft Teams Online 呼叫流图 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*图 3 - 客户网络到外部用户 (Teams 传输中继服务中继)*

在步骤 7 中，选择从客户网络到 Microsoft 365 或 Office 365 的流 4，以及从远程移动 Teams 用户到 Microsoft 365 或 Office 365 的流 3。 这些流由 Microsoft 365 或 Office 365 中的 Teams 传输中继中继。

媒体是双向的，其中方向指示哪个端从连接角度启动通信。 在这种情况下，这些流用于信令和媒体，使用不同的传输协议和地址。

**客户网络与外部用户 (媒体) ：**

[![Microsoft Teams Online 呼叫流图 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*图 4 - 客户网络与外部用户 (媒体)*

在步骤 7 中，选择"流 2"，即从客户网络 (客户端对等) Internet。

- 不通过 Microsoft 365 或 Office 365 (远程移动用户的直接媒体) 可选。 换言之，客户可能会阻止此路径，以在 Microsoft 365 或 Office 365 中通过传输中继强制使用媒体路径。

- 媒体是双向的。 流 2 到远程移动用户的方向指示一端从连接角度启动通信。

**Teams 传输中继 (中继的 VPN 用户到内部)**

[![Microsoft Teams Online 呼叫流图 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*图 5 - Teams 传输中继 (中继的 VPN 用户到内部)*

VPN 与客户网络之间的信号发送使用的是流 2'。 客户网络和 Microsoft 365 或 Office 365 之间的信号使用流 4。 但是，媒体绕过 VPN，使用流 3 和流 4 通过 Microsoft 365 或 Office 365 中的 Teams 媒体中继进行路由。

**VPN 用户到内部用户 (媒体)**

[![Microsoft Teams Online 呼叫流图 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*图 6 - VPN 用户到内部用户 (媒体)*

VPN 与客户网络之间的信号发送使用的是流 2'。 客户网络和 Microsoft 365 或 Office 365 之间的信号使用流 4。 但是，媒体绕过 VPN，使用流 2 从客户网络路由到 Internet。

媒体是双向的。 流 2 到远程移动用户的方向指示一端从连接角度启动通信。

**VPN 用户到外部用户 (媒体)**

[![Microsoft Teams 呼叫流图 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*图 7 - VPN 用户到外部用户 (媒体)*

VPN 用户与客户网络之间的信号发送使用的是流 2'，使用流 4 到 Microsoft 365 或 Office 365。 但是，媒体绕过 VPN，并且使用流 6 进行路由。

媒体是双向的。 流 6 到远程移动用户的方向指示一端从连接角度启动通信。

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>用例：Teams 到 PSTN 通过 Microsoft 365 或 Office 365 Trunk

Microsoft 365 和 Office 365 有一个电话系统，允许从 PSTN 公用电话交换网络 (呼叫) 。 如果使用电话系统呼叫计划连接 PSTN 中继，则此用例没有特殊的连接要求。  (如果要将自己的本地 PSTN 中继连接到 Microsoft 365 或 Office 365，可以使用电话系统直接路由.) 

[![Microsoft Teams Online 呼叫流图 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*图 8 - 通过 Office 365 中继将团队到 PSTN*

#### <a name="use-case-teams-meeting"></a>用例：Teams 会议

VBSS 会议服务器 (/) /视频/屏幕共享是 Microsoft 365 和 Office 365 的一部分。 它拥有一个公共 IP 地址，该地址必须从客户网络访问，并且必须从 Nomadic 云客户端访问。 每个客户端/终结点都需要能够连接到会议服务器。

内部客户端将像一对一调用所述一样获取本地、反身和中继候选项。 客户将在邀请中将这些候选者发送到会议服务器。 会议服务器不使用中继，因为它具有可公开访问的 IP 地址，因此它使用其本地 IP 地址候选项进行响应。 客户端和会议服务器以一对一呼叫中所述的相同方式检查连接。

请注意：

- Teams 客户端无法加入 Skype for Business 会议，Skype for Business 客户端无法加入 Teams 会议。

- PSTN 用户可选择"拨入"或"拨出"，具体取决于会议的组织者 PSTN 呼叫和/或会议预配。

- 来宾用户或客户用户可以从来宾专用网络加入，该网络通过严格的规则使用 FW/NAT 进行保护。

[![Microsoft Teams Online 呼叫流图 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*图 9 - Teams 会议*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>用例：与本地 Skype for Business 联合

**Microsoft 365 或 Office 365 中的 Teams 传输中继中继的媒体**

[![Microsoft Teams Online 呼叫流图 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*图 10 - 由 Office 365 中的 Teams 传输中继中继的媒体*

请注意：

- 根据定义，联合身份验证是两个租户之间的通信。 在这种情况下，使用 Teams 的租户 A 与使用本地 Skype for Business 的租户 B 联合。 如果租户 B 也在使用 Microsoft 365 或 Office 365，则 Skype for Business 客户端会使用流 3 连接到 Microsoft 365 或 Office 365。

- 从联合 Skype for Business 客户端向本地 Skype for Business Server 发送信号和媒体超出了本文档的范围。 但是，为了清楚起见，此处说明了这一点。

- Teams 和 Skype for Business 之间的信号由网关桥接。

- 在这种情况下，媒体由 Teams 传输中继通过流 4 中继中继到客户网络和远程 Skype for Business 客户端。

**由联合租户中的 Skype for Business 媒体中继中继的媒体**

[![Microsoft Teams Online 呼叫流图 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*图 11 - 由联合租户中的 Skype for Business 媒体中继中继的媒体*

请注意：

- 从联合 Skype for Business 客户端向本地 Skype for Business Server 发送信号和媒体超出了本文档的范围。 但是，为了清楚起见，此处说明了这一点。

- Teams 和 Skype for Business 之间的信号由网关桥接。

- 在这种情况下，媒体由 Skype for Business 本地媒体中继使用流 2 中继中继到客户网络。  (请注意，从 Teams 用户到联合客户网络中远程媒体中继的流量最初将被媒体中继阻止，直到反向流量开始流动。 但是，双向流将在两个方向打开连接。) 

**直接 (对等)**

[![Microsoft Teams Online 呼叫流图 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*图 12 - (直接对等)*

### <a name="teams-hybrid-topology"></a>Teams 混合拓扑

此拓扑包括 Teams 和 Skype for Business 本地部署。

[![Microsoft Teams Online 呼叫流图 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*图 13 - Teams 混合拓扑*

- 上图中箭头的方向反映影响企业外围连接的通信的启动方向。 对于媒体的 UDP，第一 (数据包) 反向流动，但可能会阻止这些数据包，直到其他方向的数据包流动。

- Teams 与 Skype for Business Online 并排部署，因此客户端显示为"Teams/SFB 用户"。

Teams 拓扑 (的其他流) ：

- **流 5A** – 表示客户网络中 Teams 用户与客户网络边缘的 Skype for Business 本地媒体中继之间的对等媒体流。

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>用例：Teams 到 Skype for Business 一对一

**客户网络内的混合**

[![Microsoft Teams Online 呼叫流图 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*图 14 - 客户网络内部的混合*

Teams 和 Skype for Business 之间的信号由网关桥接。 但是，媒体使用流 5 直接在客户网络中点对点路由。

**与外部 Skype for Business 用户建立混合客户网络 - 由 Microsoft 365 或 Office 365 中继**

[![Microsoft Teams Online 呼叫流图 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*图 15 - 具有外部 Skype for Business 用户的混合客户网络 - 由 Office 365 中继*

请注意：

- 从 Skype for Business 客户端向本地 Skype for Business Server 发送信号和媒体超出了本文档的范围。 但是，为了清楚起见，此处说明了这一点。

- Teams 和 Skype for Business 之间的信号由网关桥接。

- 媒体通过 Teams 传输中继通过流 4 中继中继到客户网络。

**与外部 Skype for Business 用户建立混合客户网络 - 由本地 Edge 中继**

[![Microsoft Teams Online 呼叫流图 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*图 16 - 具有外部 Skype for Business 用户的混合客户网络 - 由本地 Edge 中继*

请注意：

- 从 Skype for Business 客户端向本地 Skype for Business Server 发送信号和媒体超出了本文档的范围。 但是，为了清楚起见，此处说明了这一点。

- 信号由网关桥接。

- 媒体由本地 Skype for Business Edge 中的 Skype for Business 媒体中继通过媒体流 5A 中继中继到客户网络内的 Teams 用户。

### <a name="teams-with-phone-system-direct-routing-topology"></a>具有电话系统直接路由拓扑的团队

此拓扑包括 Teams 和电话系统直接路由。

直接路由使你能够使用第三方公用电话交换网 (PSTN) 服务提供商，通过将受支持的本地客户拥有的会话边界控制器 (SBC) 硬件设备与 Microsoft 365 或 Office 365 配对，然后将电话中继连接到该设备。

若要支持此方案，客户必须部署 Microsoft 的认证合作伙伴之一的经认证的 SBC 进行直接路由。 SBC 必须按照供应商的建议进行配置，并且对于直接 UDP 流量，可从 Microsoft 365 或 Office 365 进行路由。 媒体可以直接从 Teams 和/或 Skype for Business 客户端流向 SBC (绕过 Teams 网关) 遍历 Teams 网关。 当中继配置为绕过 Teams 网关时，与 SBC 的连接基于 ICE，其中 SBC 支持 ICE-Lite，而 Teams/Skype for Business 媒体终结点支持 ICE 完整格式。

[![Microsoft Teams Online 呼叫流图 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*图 17 - 具有电话系统直接路由拓扑的团队

请注意：

- 上图中箭头的方向反映影响企业外围连接的通信的启动方向。 对于媒体的 UDP，第一 (数据包) 反向流动，但可能会阻止这些数据包，直到其他方向的数据包流动。

- Teams 与 Skype for Business Online 并排部署，因此客户端显示为"Teams/SFB 用户"。

其他流 (Teams 联机拓扑) ：

- **Flow 4'** - 表示从 Microsoft 365 或 Office 365 流向客户网络的流，用于在云中的 Teams 媒体服务器与本地 SBC 建立连接。
- **流 5B** – 表示客户网络中 Direct Routing SBC 在绕过模式下的 Teams 用户之间的媒体流。
- **流 5C** – 表示 PSTN hairpin 呼叫绕过模式下直接路由 SBC 到另一个直接路由 SBC 之间的媒体流。

**使用 Teams 传输中继 (中继媒体进行直接路由的内部)**

[![Microsoft Teams Online 呼叫流图 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*图 18 - 具有直接路由 (由 Teams 传输中继设备中继的媒体)*

请注意：

- SBC 必须具有从 Microsoft 365 或 Office 365 路由的公共 IP 地址。

- 从 SBC 向 Microsoft 365 或 Office 365 发送信号和媒体，反之亦然，使用流 4 和/或流 4'。

- 从客户网络内的客户端向 Microsoft 365 或 Office 365 发送信号和媒体使用流 4。

**使用直接路由的远程 (媒体通过媒体服务器和 MP (路由) )**

[![Microsoft Teams Online 呼叫流图 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*图 19 - 使用直接路由 (媒体的远程用户通过媒体服务器 (MP) )*

请注意：

- SBC 必须具有从 Microsoft 365 或 Office 365 路由的公共 IP 地址。

- 从 SBC 向 Microsoft 365 或 Office 365 发送信号和媒体，反之亦然，使用流 4 和/或流 4'。

- 从 Internet 上的客户端向 Microsoft 365 或 Office 365 发送信号和媒体使用流 3。

**内部用户直接路由 (绕过媒体)**

[![Microsoft Teams Online 呼叫流图 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*图 20 - 内部用户直接路由 (绕过媒体)*

请注意：

- SBC 必须具有从 Microsoft 365 或 Office 365 路由的公共 IP 地址。

- 从 SBC 向 Microsoft 365 或 Office 365 发送信号，反之亦然，使用流 4 和/或流 4'。

- 从客户网络内的客户端向 Microsoft 365 或 Office 365 发送信号使用流 4。

- 从客户网络内的客户端到客户网络内的 SBC 的媒体使用流 5B。

**使用直接路由的远程用户 (Teams 传输中继的媒体旁路)**

[![Microsoft Teams Online 呼叫流图 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*图 21 - 具有直接路由的远程用户 (Teams 传输中继的媒体旁路)*

请注意：

- SBC 必须具有从 Microsoft 365 或 Office 365 和 Internet 路由的公共 IP 地址。

- 从 SBC 发信号到 Microsoft 365 或 Office 365，反之亦然，使用流 4 和/或流 4'。

- 从 Internet 上的客户端发信号到 Microsoft 365 或 Office 365 使用流 3。

- 从 Internet 上的客户端到客户网络中 SBC 的媒体使用由 Teams 传输中继中继的流 3 和流 4。

**远程用户直接路由 (绕过媒体直接)**

[![Microsoft Teams Online 呼叫流图 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*图 22 - 远程用户直接路由 (绕过媒体直接)*

请注意：

- SBC 必须具有从 Microsoft 365 或 Office 365 和 Internet 路由的公共 IP 地址。

- 从 SBC 发信号到 Microsoft 365 或 Office 365，反之亦然，使用流 4 和/或流 4'。

- 从 Internet 上的客户端发信号到 Microsoft 365 或 Office 365 使用流 3。

- 从 Internet 上的客户端到客户网络中 SBC 的媒体使用流 2。

**直接路由 (媒体旁路) – 由于呼叫转接/转接 (PSTN)**

[![Microsoft Teams Online 呼叫流图 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*图 23 - 直接路由 (媒体旁路) - 由于呼叫转接/转接 (PSTN hairpin 呼叫)*

请注意：

- SBC 必须具有从 Microsoft 365 或 Office 365 路由的公共 IP 地址。

- 从 SBC 发信号到 Microsoft 365 或 Office 365，反之亦然，使用流 4 和/或流 4'。

- 将呼叫从 PSTN 固定到 PSTN 后，客户端将退出信号和媒体循环。

- 从客户网络内的 SBC 实例 A 到客户网络内的 SBC 实例 B 的媒体 (其中，A 和 B 可以是使用流 5C 的) 实例。

**直接路由 (Microsoft 365 或 Office 365) - 跨两个租户的 PSTN hairpin 呼叫**

[![Microsoft Teams Online 呼叫流图 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*图 24 - 通过 Microsoft 365 或 Office 365 (直接路由媒体 - 跨两个租户) PSTN hairpin 呼叫*

请注意：

- SBC 必须具有从 Microsoft 365 或 Office 365 路由的公共 IP 地址。

- 从 SBC 发信号到 Microsoft 365 或 Office 365，反之亦然，使用流 4 和/或流 4'。

- 将呼叫从 PSTN 固定到 PSTN 后，客户端将退出信号和媒体循环。

- 客户网络 X 中的 SBC 实例 A 到 SBC 实例 B 的媒体必须通过 Microsoft 365 或 Office 365 媒体服务器中继，并且不能使用绕过模式。

## <a name="teams-with-express-route-optimization"></a>具有 Express Route 优化的团队

[![Microsoft Teams Online 呼叫流图 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*图 25 - 具有快速路由优化的团队*

如果已对齐并部署了 Express Route，则 Teams 流可以重新路由从流 4 到流 1，从流 4'重新路由到流 1'。 但是，Teams 应用程序依赖于其他 Microsoft 365 或 Office 365 流，这些流通过 Internet 使用流 4 和 4';因此，不得阻止这些流。

请注意，Skype for Business 混合边缘流量将路由到 Internet 而不是 Express Route，以便与外部用户通信并与其他租户联合。

为了防止非对称流，重新路由必须同时朝两个方向进行。 换言之，客户网络内的地址可以基于优化通过 Internet 或 Express Route 进行路由，但不能同时通过两者。


**客户网络与外部用户 (Teams 传输中继中继的) ：**

[![Microsoft Teams Online 呼叫流图 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*图 26 - 客户网络与外部用户 (Teams 传输中继)*

**高级步骤：**

1. 客户网络内的 Teams 用户使用 flow2 (DNS) URL 域名。
1. 客户网络内的 Teams 用户使用流 1 在 Teams 传输中继上分配媒体中继端口。
1. 客户网络内的 Teams 用户使用流 1 向 Microsoft 365 或 Office 365 发送具有 ICE 候选项的"邀请"。
1. Microsoft 365 或 Office 365 使用流 3 向外部 Teams 用户发送通知。
1. Teams 外部用户使用流 3 在 Teams 传输中继上分配媒体中继端口。
1. Teams 外部用户使用流 3 向 ICE 候选用户发送"答案"，使用流 1 将其转发回 Teams 用户 A。
1. Teams 用户 A 和 Teams 用户 B 调用 ICE 连接测试，并选择由 Teams 传输中继中继的流 1 和流 3。
1. Teams 用户使用流 1 和流 3 向 Microsoft 365 或 Office 365 发送遥测数据。

> [!NOTE]
> 必须启用流 4，以支持 Teams 应用程序依赖于要求流 4 的其他微服务。
