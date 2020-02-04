---
title: Lync Server 2013：规划呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de1f39b32503be758e10f3fbf712acdc07bd956b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中规划呼叫允许控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

对于基于 IP 的统一通信（UC）应用程序（如电话、视频和应用程序共享），企业网络的可用带宽一般视为 LAN 环境中的限制因素。 但是，在相互连接站点的 WAN 链路中，网络带宽可能受限。 当 oversubscribes WAN 链接的网络流量 influx 时，将使用队列、缓冲和数据包删除等当前机制来解决拥塞问题。 额外的流量通常会延迟，直到网络拥塞问题得以缓解，或者必要时会丢弃流量。 对于这些情况下的传统数据流量，接收客户端可以恢复。 对于实时通信（如统一通信），无法以这种方式解决网络拥塞，因为统一通信流量对延迟和数据包丢失都很敏感。 WAN 上的拥塞会导致用户的用户体验质量 (QoE) 降低。 对于在拥挤情况下的实时通信，最好拒绝呼叫，而不是提供质量较差的连接。

呼叫允许控制 (CAC) 可确定是否有足够的网络带宽来建立质量可接受的实时会话。 在 Lync Server 2013 中，CAC 仅控制音频和视频的实时流量，但不会影响数据流量。 如果默认 WAN 路径不具备所需的带宽，则 CAC 可尝试通过 Internet 路径或公用电话交换网 (PSTN) 路由呼叫。 CAC 仅在 Lync Server 中可用。

本节介绍了呼叫允许控制功能，并解释了如何规划 CAC。

<div>


> [!NOTE]  
> Lync 服务器具有三个高级的企业语音功能：呼叫许可控制（CAC）、紧急服务（E9-1）和媒体旁路。 有关所有三种功能通用的计划信息的概述，请参阅<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的高级企业语音功能的网络设置</A>。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的呼叫许可控制概述](lync-server-2013-overview-of-call-admission-control.md)

  - [在 Lync Server 2013 中定义呼叫允许控制要求](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [示例：在 Lync Server 2013 中收集呼叫许可控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013 中 CAC 的组件和拓扑](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013 中呼叫允许控制的最佳做法](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013 中呼叫允许控制的部署清单](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

