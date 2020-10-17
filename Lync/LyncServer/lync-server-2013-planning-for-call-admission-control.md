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
ms.openlocfilehash: a7c101ab49d16b01dd35d4fc498f002747cd31cd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497809"
---
# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中规划呼叫允许控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

对于基于 IP 的统一通信 (UC) 应用程序，例如电话、视频和应用程序共享，通常不会将企业网络的可用带宽视为 LAN 环境内的限制因素。但是，在相互连接站点的 WAN 链路中，可以限制网络带宽。当过多网络流量通过 WAN 链路时，将使用当前的诸如队列、缓冲和数据包丢弃等机制解决拥塞问题。额外的流量通常会延迟，直到网络拥塞问题得以缓解，或者必要时会丢弃流量。对于这些情况下的传统数据流量，接收客户端可以恢复。对于实时流量（如统一通信），则不能采用这种方式解决网络拥塞问题，因为统一通信流量对延迟和数据包丢失非常敏感。WAN 上的拥塞会导致用户的用户体验质量 (QoE) 降低。对于发生拥塞时的实时流量，最好拒绝呼叫，而不是提供质量欠佳的连接。

呼叫允许控制 (CAC) 可确定是否有足够的网络带宽来建立质量可接受的实时会话。 在 Lync Server 2013 中，CAC 仅控制音频和视频的实时流量，但不会影响数据流量。 如果默认 WAN 路径不具备所需的带宽，则 CAC 可尝试通过 Internet 路径或公用电话交换网 (PSTN) 路由呼叫。 CAC 仅在 Lync Server 中可用。

本节介绍了呼叫允许控制功能，并解释了如何规划 CAC。

<div>


> [!NOTE]  
> Lync Server 具有三个高级企业语音功能：呼叫允许控制 (CAC) 、紧急服务 (E9-1-1) 和媒体旁路。 有关这三种功能共有的规划信息的概述，请参阅 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的 "高级企业语音功能的网络设置"</A>。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md)

  - [在 Lync Server 2013 中定义呼叫允许控制的要求](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [示例：收集 Lync Server 2013 中的呼叫允许控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Lync Server 2013 中 CAC 的组件和拓扑](lync-server-2013-components-and-topologies-for-cac.md)

  - [Lync Server 2013 中的呼叫允许控制最佳实践](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lync Server 2013 中呼叫允许控制的部署清单](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

