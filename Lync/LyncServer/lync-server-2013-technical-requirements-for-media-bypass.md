---
title: Lync Server 2013：媒体旁路的技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f59e0c025935ca8c2cd341549cdb58a44e7dbb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013 中媒体旁路的技术要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

对于每个对 PSTN 的调用, 中介服务器确定来自 Lync 终结点的媒体是否可以直接发送到中介服务器对等, 而不遍历中介服务器。 对等方可以是与其中路由呼叫的中介服务器之间的中继关联的 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。

当满足以下要求时，可采用媒体旁路功能：

  - 中介服务器对等必须支持媒体绕过所需的功能, 最重要的是处理多个分叉响应 (称为 "早期对话框") 的能力。 与网关、PBX 制造商或 ITSP 联系，以获取网关、PBX 或 SBC 可接受的最大早期对话数的值。

  - 中介服务器对等必须直接从 Lync 终结点接受媒体流量。 许多 ITSPs 允许其 SBC 仅从中介服务器接收通信。 联系你的 ITSP 以确定其 SBC 是否直接从 Lync 终结点接受媒体流量。

  - Lync 客户端和中介服务器对等必须已连接正常, 这意味着它们位于同一网络区域或网络站点上, 这些网络区域或网络站点与没有带宽限制的 WAN 链接上的区域相连接

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的媒体绕过模式](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 中的媒体绕过和呼叫允许控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

