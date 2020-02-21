---
title: Lync Server 2013：为 E9-1-1 设计 SIP 中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c4191ed20497b4136b4e836da112054bef5a446
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>在 Lync Server 2013 中为 E9-1-1 设计 SIP 中继

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

Lync Server 使用 SIP 中继将紧急呼叫连接到 E9-1-1 服务提供商。 您可以为一个中央站点、多个中央站点或每个分支站点的 E9-1-1 设置紧急服务 SIP 中继。 但是，如果呼叫者站点与承载紧急服务 SIP 中继的站点之间的 WAN 链路不可用，则孤立站点的用户发出的呼叫将需要使用用户语音策略中的特殊电话使用记录，以通过本地公用电话交换网 (PSTN) 网关将该呼叫路由到 ECRC。 如果呼叫允许控制并发呼叫限制有效，则会出现相同情况。

<div>


> [!NOTE]  
> 有两种方法可以在 Lync Server 环境中实施 SIP 中继： 
> <UL>
> <LI>
> <P>使用具有面向外部的公共路由接口的多宿主中介服务器与 SIP 中继提供程序进行通信。</P>
> <LI>
> <P>使用本地会话边界控制器（SBC）在中介服务器和 SIP 中继提供程序的服务之间提供安全的分界点。</P></LI></UL>如果您选择后一种方法，请确保您选择的 SBC 品牌和型号已经过认证并且支持将状态信息数据格式位置对象 (PIDF-LO) 位置数据作为其 SIP INVITE 一部分传递。 否则，呼叫将在缺少位置信息的情况下到达紧急服务的服务提供商。 有关认证的 SBCs 的详细信息，请参阅中的 "Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>的基础结构合格"。<BR>E9-1-1 的服务提供商会向您提供对 SBC 对的访问权，以实现冗余。 您需要针对中介服务器拓扑和呼叫路由配置做出几个决策。 您是否平等看待两个 SBC 并对它们之间的呼叫使用循环路由，或者您是否以其中一个 SBC 为主，而另一个为辅？



</div>

有关在 Lync Server 中部署 SIP 中继的详细信息，请参阅[如何在 Lync server 2013 中实现 sip 中继？](lync-server-2013-how-do-i-implement-sip-trunking.md)。 下列问题将帮助您确定如何部署 E9-1-1 的 SIP 中继。

  - **应该通过专门租用的 Internet 连接还是共享的 Internet 连接部署 SIP 中继？**  
    紧急呼叫必须始终保持连接状态，这一点很重要。专用线路将提供不会被网络中其他流量抢占的连接以及实现服务质量 (QoS) 的功能。请记住，如果通过公共 Internet 连接到紧急服务的服务提供商，并且需要确保紧急呼叫的保密性，则需要 IPSec 加密。

<!-- end list -->

  - **您的 E9-1-1 部署是否是为实现灾难容限而设计的？**  
    由于这是紧急解决方案，因此复原很重要。 在灾难容错位置部署主中介服务器和 SIP 中继。 最好将主中介服务器部署到其支持的用户最近，并通过辅助中介服务器（位于不同的地理位置）路由故障转移呼叫。

<!-- end list -->

  - **是否应该为每个分支机构部署单独的 SIP 中继？**  
    Lync Server 提供了几种用于在分支机构中处理语音弹性的策略，包括：具有可恢复的数据网络、在每个分支中部署 SIP 中继或在中断期间将呼叫推送到本地网关。 有关详细信息，请参阅[Lync Server 2013 中的分支站点 SIP 中继](lync-server-2013-branch-site-sip-trunking.md)。

<!-- end list -->

  - **是否已启用呼叫允许控制 (CAC)？**  
    Lync Server 不会以不同于普通呼叫的方式处理紧急呼叫。 因此，带宽管理或呼叫允许控制 (CAC) 将对 E9-1-1 配置产生负面影响。 如果已启用 CAC，并且路由紧急呼叫的链接上的流量超过配置的限制，那么将阻止紧急呼叫或将其路由至本地 PSTN 网关。 如本主题前面所述，此类呼叫不包含位置数据，必须手动将其路由到 ECRC。

</div>

<span> </span>

</div>

</div>

</div>

