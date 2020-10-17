---
title: Lync Server 2013：中继间路由
description: Lync Server 2013：中继间路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30c838ee94a2df0807195c172d7e2a3a393523af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553138"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a>Lync Server 2013 中的中继间路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

Lync Server 2013 可以将 ip-pbx 互连到公用电话交换网（ (PSTN) 网关），以便可以将来自 PBX 电话的呼叫路由到 PSTN，并将传入 PSTN 呼叫路由到专用分支 exchange (PBX) 电话。 同样，Lync Server 2013 可以互连两个或更多个 ip-pbx 系统，以便可以在不同的 ip-pbx 系统的 PBX 电话之间进行呼叫和接收。

可以使用 Lync Server 命令行管理程序 cmdlet， **remove-cstrunkconfiguration**，使用新参数 PstnUsages 配置此中继间路由功能。 此参数指定一组要使用的 PSTN 用法记录。 中继使用此 PSTN 用法来确定路由并相应地路由所有传入呼叫。

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

下图说明了 Lync Server 2013 在 PSTN 网关和 IP-PBX 之间提供 interconnectivity。

**网关与 IP PBX 之间的中继间路由**

![连接 PSTN 网关（IP PBX 图）的 Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "连接 PSTN 网关（IP PBX 图）的 Lync Server")

下图说明了 Lync Server 2013 互连两个 ip-pbx 系统。

**两个 IP PBX 之间的中继间路由**

![Lync Server 互连 IP-PAX 系统关系图](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 互连 IP-PAX 系统关系图")

</div>

<span> </span>

</div>

</div>

</div>

