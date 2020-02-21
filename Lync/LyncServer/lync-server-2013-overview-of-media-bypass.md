---
title: Lync Server 2013：媒体旁路概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66c2484b656cce15a6f7d013060c1fc95047f49d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Lync Server 2013 中的媒体旁路概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

如果希望将部署的中介服务器数目降至最低，媒体绕过非常有用。 通常会在中央站点部署中介服务器池，中介服务器池将控制分支站点的网关。 启用媒体旁路后，来自分支站点中客户端的公用电话交换网 (PSTN) 呼叫的媒体可直接通过这些站点中的网关流动。 必须正确配置 Lync Server 2013 出站呼叫路由和企业语音策略，以便将来自分支站点的客户端的 PSTN 呼叫路由到相应的网关。

Wi-Fi 网络通常会比有线网络丢失更多的数据包。通常网关无法恢复这些丢失的数据包。因此，我们建议，在决定是否对无线子网启用绕过功能之前，先评估 Wi-Fi 网络的质量。同时，还需要在降低延迟和恢复丢失的数据包之间取得平衡。RTAudio 是一种可用于未绕过中介服务器的呼叫的编解码器，它更适合处理数据包丢失。

安装企业语音结构后，规划媒体绕过将变得非常简单。

  - 如果您的拓扑属于集中式拓扑，但没有指向分支站点的 WAN 链路，则可以启用全局媒体旁路，因为没有必要进行细化的控制。

  - 如果您的拓扑属于分布式拓扑，其中包含一个或多个网络区域以及附属的分支站点，请确定以下信息：
    
      - 您的中介服务器对等方是否支持媒体旁路所需的功能。
    
      - 每个网络区域中的哪些站点是正确连接的。
    
      - 哪种媒体旁路与呼叫允许控制的组合适合您的网络。

启用媒体旁路后，会自动为某个网络区域和该区域中没有带宽限制的所有网络站点生成唯一的绕过 ID。在该区域内具有带宽限制的站点和通过具有带宽限制的 WAN 链路连接到该区域的站点都分配有其自己的唯一绕过 ID。

当用户对 PSTN 进行呼叫时，中介服务器会将客户端子网的绕过 ID 与网关子网的绕过 ID 进行比较。 如果这两个绕过 ID 匹配，则对该呼叫使用媒体旁路。 如果绕过 Id 不匹配，则该呼叫的媒体必须通过中介服务器流动。

用户收到来自 PSTN 的呼叫时，用户的客户端会将其绕过 ID 与 PSTN 网关的绕过 ID 进行比较。 如果两个绕过 Id 匹配，媒体将直接从网关流向客户端，而不会绕过中介服务器。

只有 Lync 2010 或更高版本的客户端和设备支持与中介服务器的媒体旁路交互。

<div>


> [!IMPORTANT]  
> 除了全局启用媒体旁路之外，还必须在每个 PSTN 中继中分别启用媒体旁路。如果已全局启用绕过，但没有为特定的 PSTN 中继启用，则不会为涉及该 PSTN 中继的任何呼叫调用媒体旁路。此外，当媒体旁路设置为“使用站点和区域信息”<STRONG></STRONG>时，必须将所有可路由的子网与它们所在的站点关联起来。如果不需要绕过的站点内有可路由的子网，则在启用媒体旁路之前，应该将这些子网分组到一个新的站点内。执行该操作可确保为不可路由的子网分配不同的绕过 ID。



</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的媒体旁路模式](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 中的媒体旁路和呼叫允许控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013 中媒体旁路的技术要求](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

