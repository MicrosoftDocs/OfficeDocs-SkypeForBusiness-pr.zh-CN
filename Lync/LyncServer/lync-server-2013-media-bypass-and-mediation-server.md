---
title: Lync Server 2013：媒体绕过和中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524c0f2556eec339b6698f156966ea95538dbaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的媒体绕过和中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

"媒体绕过" 是一种 Lync 服务器功能, 使管理员能够将呼叫路由配置为直接流过用户终结点和公共交换电话网络 (PSTN) 网关, 而无需遍历中介服务器。 媒体旁路通过减少延迟、不必要的转换、数据包丢失的可能性以及潜在的故障点数量来提高通话质量。 在以下情况下, 如果没有中介服务器的远程网站通过受限制带宽的一个或多个 WAN 链接连接到中心站点, 则媒体绕过会通过从远程站点的客户端中启用媒体直接流向本地网关来降低带宽要求, 而无需首先必须跨 WAN 链接流过中央站点的中介服务器。媒体处理的减少还会补充中介服务器控制多个网关的能力。

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

