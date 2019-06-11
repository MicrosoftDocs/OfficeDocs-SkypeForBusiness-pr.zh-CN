---
title: Lync Server 2013：中继间路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Lync Server 2013 中的中继间路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-20_

Lync Server 2013 可以将 IP PBX 互连到公共交换式电话网络 (PSTN) 网关, 以便从 PBX 手机拨出的电话可以路由到 PSTN, 并且传入的 PSTN 呼叫可以路由到专用的分支 exchange (PBX) 手机。 同样, Lync Server 2013 可以互连两个或更多的 IP PBX 系统, 以便可以在不同的 IP PBX 系统中的 PBX 手机之间呼叫和接收呼叫。

此 intertrunk 路由功能可通过使用 Lync Server Management Shell cmdlet ( **new-cstrunkconfiguration**) 以及新参数 PstnUsages 进行配置。 此参数指定要使用的 PSTN 使用记录集。 主干使用此 PSTN 用法确定路由并相应地路由所有传入呼叫。

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

下图说明了 Lync Server 2013 在 PSTN 网关和 IP PBX 之间提供 interconnectivity。

**网关和 IP PBX 之间的 Intertrunk 路由**

![连接 PSTN 网关/IP 的 Lync 服务器-PBX 图](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "连接 PSTN 网关/IP 的 Lync 服务器-PBX 图")

下图说明了 Lync Server 2013 互连两个 IP PBX 系统的互连。

**两个 IP Pbx 之间的 Intertrunk 路由**

![Lync Server 互连 IP-PAX 系统关系图](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 互连 IP-PAX 系统关系图")

</div>

<span> </span>

</div>

</div>

</div>

