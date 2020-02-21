---
title: Lync Server 2013：呼叫允许控制概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df9d65a56a8e2ed398dc5277045efeaaf68b8f58
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中的呼叫允许控制概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-22_

实时通信会受到拥堵网络上可能发生的延迟和数据包丢失情况的影响。 呼叫允许控制 (CAC) 根据可用网络带宽确定是否允许建立实时通信会话（如语音呼叫或视频呼叫）。 Lync Server 2013 中的 CAC 设计提供了四个主要属性：

  - 不需要使用其他设备（如经过特殊配置的路由器），即可轻松部署和管理。

  - 它可处理关键的统一通信用例，例如漫游用户和多点登录。根据终结点的位置（而非用户的驻留位置）实施 CAC 策略。

  - 除了语音呼叫，它还可以应用于其他通信，例如视频呼叫和音频/视频会议会话。

  - 能够灵活地表示各种网络拓扑。 有关示例，请参阅[Lync Server 2013 中的 CAC 的组件和拓扑](lync-server-2013-components-and-topologies-for-cac.md)。

如果新语音会话或视频会话超出您在 WAN 链路上设置的带宽限制，该会话将被阻止或（仅在电话呼叫情况下）重新路由至 PSTN。

CAC 仅控制实时语音和视频流量，不控制数据流量。

管理员定义 CAC 策略，这些策略由随每个前端池一起安装的带宽策略服务强制实施。 CAC 设置将自动传播到网络中的所有 Lync Server 前端服务器。

对于因 CAC 策略而失败的呼叫，重新路由呼叫的优先顺序如下：

1.  Internet

2.  PSTN

3.  语音邮件

呼叫详细信息记录 (CDR) 捕获有关重新路由至 PSTN 或语音邮件的呼叫的信息。CDR 不会捕获有关重新路由至 Internet 的呼叫的信息，因为 Internet 被视为备用路径而非次要选项。

<div>


> [!NOTE]  
> 语音邮件处理不会因为带宽限制而被拒绝。



</div>

带宽策略服务生成两种逗号分隔值 (CSV) 格式的日志文件。“检查失败”**** 日志文件捕获带宽请求被拒绝时的信息。“链接利用率”**** 日志文件捕获网络拓扑快照和 WAN 链路带宽用量。这两种日志文件都有助于根据利用率微调 CAC 策略。

<div>

## <a name="call-admission-control-considerations"></a>呼叫允许控制注意事项

管理员选择将带宽策略服务安装在中央站点中配置的第一个池上。 由于每个网络区域有一个中央站点，因此每个网络区域只有一个带宽策略服务，它管理用于该区域、其关联站点和到这些站点的链接的带宽策略。 带宽策略服务作为前端服务器的一部分运行，因此在该池内内置了高可用性。 每台前端服务器上运行的带宽策略服务每15秒同步一次。 如果前端池发生故障，则在前端池之前，不会再为该站点强制使用 CAC 策略，因此带宽策略服务将再次正常运行。 这意味着，在带宽策略服务停用期间，所有呼叫都将通过。 因此，在此期间可能会出现链接的带宽订阅过度的情况。

带宽策略服务在前端池内提供了高可用性;但是，它不提供跨前端池的冗余。 带宽策略服务无法从一个前端池故障转移到另一个前端池。 在还原对前端池的服务后，会恢复带宽策略服务，并可以再次强制实施带宽策略检查。

<div>

## <a name="network-considerations"></a>网络注意事项

尽管 Lync Server 2013 中的带宽策略服务强制执行音频和视频的带宽限制，但不会在网络路由器（第2层和第3层）上强制此限制。 Lync Server 2010 CAC 无法阻止数据应用程序，例如，在 WAN 链路上使用整个网络带宽，包括您的 CAC 策略为音频和视频保留的带宽。 要提供必需的网络带宽保护，您可以部署服务质量 (QoS) 协议，例如差分服务 (DiffServ)。 因此，最佳实践是协调按照您可能部署的任何 QoS 设置定义的 CAC 带宽策略。

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>VPN 上的媒体和信号路径

如果您的企业支持通过 VPN 的媒体，则请确保媒体流和信号流都能通过 VPN，或两者都通过 Internet 进行路由。默认情况下，媒体流和信号流通过 VPN 通道。

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>外部用户的呼叫允许控制

不对通过 Internet 传输网络流量的远程用户实施呼叫允许控制。 由于媒体流量正在遍历 Internet （不受 Lync Server 管理），因此无法应用 CAC。 但是，仍将对通过企业网络的部分呼叫执行 CAC 检查。

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>PSTN 连接的呼叫允许控制

呼叫允许控制在中介服务器上是可强制的，而不管它是连接到 IP/PBX、PSTN 网关还是 SIP 中继。 由于中介服务器是后端到后端用户代理（B2BUA），因此它会终止媒体。 它有两个连接方：连接到 Lync Server 的一端，以及连接到 PSTN 网关、IP/Pbx 或 SIP 中继的网关端。 有关 PSTN 连接的详细信息，请参阅[在 Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)。

除非启用媒体旁路，否则在中介服务器的两端都可以实施 CAC。 如果启用媒体旁路，媒体流量不会遍历中介服务器，而是直接在 Lync 客户端和网关之间流动。 在这种情况下，不需要使用 CAC。 有关详细信息，请参阅[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)。

下图说明了如何在启用和不启用媒体旁路的情况下在 PSTN 连接上实施 CAC。

**在 PSTN 连接上实施呼叫允许控制**

![语音 CAC 媒体绕过连接强制实施](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "语音 CAC 媒体绕过连接强制实施")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>呼叫允许控制与早期版本的 Office Communications Server 的兼容性

只能在为 Lync Server 2010 和更高版本启用的终结点上启用呼叫允许控制。

无法在运行 Office Communicator 2007 R2 或更早版本的终结点上启用呼叫允许控制。

**在不同版本的 Lync Server 上应用 CAC**

![语音 CAC 版本比较关系图](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "语音 CAC 版本比较关系图")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

