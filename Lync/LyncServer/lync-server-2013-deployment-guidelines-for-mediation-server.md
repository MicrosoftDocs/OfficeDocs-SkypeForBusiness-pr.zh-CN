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
ms.openlocfilehash: 0404590ab5b3208de989093df7ede55a3aee2f54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的中介服务器的部署指南

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-12_

本主题介绍了中介服务器部署的规划准则。 查看这些准则后，我们建议您使用规划工具来创建和查看可能的备用拓扑，这可以作为您决定要部署的最终定制拓扑的模型，如下所示。

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>并置还是独立中介服务器？

默认情况下，在中央站点上的 Standard Edition Server 或前端池中的前端服务器上并置中介服务器。 可以处理的公共交换电话网络（PSTN）呼叫数和池中所需的计算机数取决于以下几项：

  - 中介服务器池控制的网关对等方的数量

  - 通过这些网关的高容量通信周期

  - 其媒体绕过中介服务器的呼叫的呼叫百分比

在规划时，请务必考虑 PSTN 呼叫的媒体处理要求以及没有为媒体旁路配置的 A/V 会议，以及处理需要支持的繁忙小时数的信号交互所需的处理。 如果没有足够的 CPU，则必须部署一台独立的中介服务器池;而 PSTN 网关、IP Pbx 和 SBCs 需要分成多个子集，这些子集由一个池中的并置中介服务器和一个或多个独立池中的独立中介服务器控制。

如果部署的 PSTN 网关、IP Pbx 或会话边界控制器（SBCs）不支持与中介服务器池进行交互的正确功能（包括以下各项），则需要将它们与包含以下各项的独立池相关联：在单个中介服务器上：

  - 在池中的中介服务器之间执行网络层域名系统（DNS）负载平衡（或者以统一方式将流量统一路由到池中的所有中介服务器）

  - 接受来自池中任意中介服务器的流量

您可以使用 Microsoft Lync Server 2013、规划工具来评估并置使用前端池的中介服务器是否可以处理负载。 如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>中央站点和分支站点注意事项

中央站点的中介服务器可用于为分支站点的 IP-PBX 或 PSTN 网关路由呼叫。但是，如果部署 SIP 中继，则必须在每个中继终止的站点上部署一台中介服务器。使用中央站点的中介服务器为分支站点的 IP-PBX 或 PSTN 网关路由呼叫时，不需要使用媒体绕过。但是，如果可以启用媒体绕过，则可以降低媒体路径延迟，从而改善媒体质量，因为媒体路径不再需要遵循信号路径。媒体绕过还将减少池中的处理负载。

<div>


> [!NOTE]  
> 媒体绕过将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 已使用认证的合作伙伴测试了一组 PSTN 网关和 SBCs，并且已通过 Cisco IP Pbx 进行了一些测试。 仅在统一通信开放互操作性计划– Lync Server 上列出的产品和版本支持媒体<A href="http://go.microsoft.com/fwlink/p/?linkid=268730">http://go.microsoft.com/fwlink/p/?LinkId=268730</A>旁路。



</div>

如果要求具有分支站点恢复能力，则必须在分支站点部署 Survivable Branch Appliance 或部署前端服务器、中介服务器和网关的组合。 （具有分支站点恢复能力的假设是网站上的状态和会议不是可恢复的。有关分支站点规划语音的指南，请参阅[Lync Server 2013 中的规划分支站点语音恢复](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

对于与 ip-pbx 的交互，如果 ip-pbx 不能正确支持与多个早期对话框和 RFC 3960 交互的早期媒体交互，则可以将来自 ip-pbx 的传入呼叫的问候语的前几个字剪辑到 Lync 终结点。 如果中央站点上的中介服务器为 IP-PBX 路由呼叫，其中路由终止于分支站点，这种行为可能更为严重，因为完成信号需要更长时间。 如果您遇到此行为，在分支站点部署中介服务器是减少前几个词的修剪的唯一方法。

最后，如果中央站点具有 TDM PBX，或者 IP-PBX 仍然需要 PSTN 网关，则必须在连接中介服务器和 PBX 的呼叫路由上部署网关。

<div>


> [!NOTE]  
> 若要提高独立中介服务器的媒体性能，应在这些服务器上的网络适配器上启用接收端扩展（RSS）。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅中的 "在<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?LinkId=268731</A>Windows Server 中接收端扩展功能增强"。 有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

