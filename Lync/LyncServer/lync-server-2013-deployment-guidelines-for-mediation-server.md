---
title: Lync Server 2013：中介服务器的部署指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c91ea4368d96e6a558a25eda86d163e4ced4cb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的中介服务器部署指南

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-12_

本主题介绍了中介服务器部署的规划指南。 查看这些指南后，我们建议你使用计划工具来创建和查看可能的替代拓扑，这些拓扑可以用作你确定要部署的最终定制拓扑的模型。

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>Collocated 还是独立中介服务器？

默认情况下，在中央站点的前端池中的标准版服务器或前端服务器上 collocated 中介服务器。 可以处理的公用电话交换网 (PSTN) 呼叫数和池中所需的计算机数取决于以下因素：

  - 中介服务器池控制的网关对等的数量

  - 通过这些网关的高流量时段

  - 媒体绕过中介服务器的呼叫的通话百分比

规划时，请确保考虑未进行媒体旁路配置的 PSTN 呼叫和 A/V 会议的媒体处理要求，同时考虑处理必须支持的忙时呼叫数量的信号交互所需的处理要求。 如果没有足够的 CPU，则必须部署一个单独的中介池服务器池;PSTN 网关、IP-Pbx 和 SBCs 需要拆分为多个子集，这些子集由一个池中的 collocated 中介服务器和一个或多个独立的池内的独立中介服务器控制。

如果你部署的 PSTN 网关、IP-Pbx 或会话边界控制器（SBCs）不支持与中介服务器池进行交互的正确功能（包括以下情况），则需要将它们与一个独立的池相关联，包括在单个中介服务器中：

  - 在池中的中介服务器上执行网络层域名系统（DNS）负载平衡（或以统一方式将流量统一到池中的所有中介服务器）

  - 接受来自池中的任何中介服务器的流量

你可以使用 Microsoft Lync Server 2013、计划工具评估 collocating 前端池的中介服务器是否可以处理负载。 如果你的环境无法满足这些要求，则必须部署独立的中介服务器池。

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>中央站点和分支站点注意事项

中心站点上的中介服务器可用于路由分支站点上的 IP-Pbx 或 PSTN 网关的呼叫。 但是，如果你部署 SIP 中继，则必须在每个主干终止的站点上部署中介服务器。 对于分支站点上的 IP PBX 或 PSTN 网关，在中心站点路由呼叫中拥有中介服务器不需要使用媒体旁路。 但是，如果你可以启用媒体绕过，这样做将减少媒体路径延迟，因此，由于不再需要媒体路径来跟踪信号路径，因此提高了媒体质量。 媒体绕过还将减少池中的处理负载。

<div>


> [!NOTE]  
> 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。 只有在统一通信中列出的产品和版本才支持媒体绕开互操作性计划- <A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>Lync Server at。



</div>

如果需要分支站点弹性，必须在分支站点上部署 Survivable 分支装置或前端服务器、中介服务器和网关的组合。 （具有分支站点弹性的假设是状态和会议在网站上不能复原。）有关针对语音进行分支站点规划的指南，请参阅[Lync Server 2013 中的规划分支站点语音复原](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

对于与 IP PBX 的交互，如果 IP PBX 不能正确支持具有多个早期对话框和 RFC 3960 交互的早期媒体交互，则可以将来自 IP PBX 的来电的前几个字与 Lync 终结点进行剪辑。 如果中央站点上的中介服务器是路由在分支站点上终止的 IP-PBX 的路由呼叫，则这种行为可能更严重，因为发送信号需要更多的时间才能完成。 如果你遇到此行为，则在分支站点上部署中介服务器是减少前几个字词的剪辑的唯一方法。

最后，如果你的中心网站具有 TDM PBX，或者如果你的 IP PBX 不能消除 PSTN 网关的需要，则必须在连接中介服务器和 PBX 的呼叫路由上部署网关。

<div>


> [!NOTE]  
> 要提高独立的中介服务器的媒体性能，应在这些服务器的网络适配器上启用接收方缩放 (RSS)。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅的 "Windows Server 中的接收端缩放<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>增强功能增强"。 有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

