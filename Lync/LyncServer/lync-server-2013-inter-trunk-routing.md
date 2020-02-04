---
title: Lync Server 2013：中继间路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37a9feb818f48317f9a3dddd78a70700e3f6ccfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a>Lync Server 2013 中的中继间路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-08_

Lync Server 2013 通过支持 intertrunk 路由提供基本的会话管理。 此新功能使 Lync 服务器能够向下游电话系统提供呼叫控制功能。 中继间路由可将 IP-PBX 互联到公用电话交换网 (PSTN) 网关，以便将来自专用交换机 (PBX) 电话的呼叫路由到 PSTN，而将传入 PSTN 呼叫路由到 PBX 电话。 同样，Lync Server 可以互连两个或更多的 IP PBX 系统，以便可以在不同的 IP PBX 系统的 PBX 电话之间放置和接收呼叫。

下图说明了 Lync Server 2013 在 PSTN 网关和 IP PBX 之间提供 interconnectivity。

![Lync Server - 连接 PSTN 网关/IP-PBX 图示](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server - 连接 PSTN 网关/IP-PBX 图示")

下图说明了连接两个 IP PBX 系统的 Lync Server 2013。

![Lync Server - 将 IP-PAX 系统相互连接的图示](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server - 将 IP-PAX 系统相互连接的图示")

</div>

<span> </span>

</div>

</div>

</div>

