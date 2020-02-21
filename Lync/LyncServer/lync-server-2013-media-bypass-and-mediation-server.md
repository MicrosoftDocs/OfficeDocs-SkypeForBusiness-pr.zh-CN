---
title: Lync Server 2013：媒体旁路和中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d346948fc40298f7825a2d141432583a1c2e08
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的媒体旁路和中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

媒体旁路是一种 Lync Server 功能，使管理员能够将呼叫路由配置为直接在用户终结点和公用电话交换网（PSTN）网关之间流动，而无需遍历中介服务器。 媒体旁路通过减少延迟、不必要的转换、数据包丢失的可能性以及潜在的故障点数来提高呼叫质量。 如果没有中介服务器的远程站点通过受限制带宽的一个或多个 WAN 链路连接到中央站点，媒体旁路降低带宽需求的方法是，从远程站点的客户端启用媒体以直接流向本地网关，而不首先必须跨 WAN 链路传递到位于中央站点的中介服务器和背面。媒体处理的缩减还补充了中介服务器控制多个网关的能力。

媒体旁路功能和呼叫允许控制 (CAC) 相互排斥。如果某次呼叫使用媒体旁路功能，则不会为此次呼叫执行 CAC。假定前提是此次呼叫不涉及具有限定带宽的链接。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的呼叫允许控制和中介服务器](lync-server-2013-call-admission-control-and-mediation-server.md)  


[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

