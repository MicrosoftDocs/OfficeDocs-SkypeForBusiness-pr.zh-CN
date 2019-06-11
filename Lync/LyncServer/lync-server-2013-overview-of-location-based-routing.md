---
title: 'Lync Server 2013: 基于位置的路由概述'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b3a5cb2e89376a356daf54c6e5bc443ab52207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中基于位置的路由概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

基于位置的路由引入了一组新规则，它们可修改国内和国际 PSTN 呼叫的路由以防止收费绕路情形。使用基于位置的路由可灵活地将这些规则限定为仅特定区域、特定网关或特定用户集。

以下方案说明了基于位置的主要路由可强制执行的主要类型:

  - 外出呼叫–基于位置的路由可以强制传出调用来自与呼叫者在同一区域中的传出呼叫, 该网关位于与呼叫者阻止 PSTN 免绕过的位置, 从而阻止从其他区域中的 PSTN 网关传出的传出呼叫程序.

  - 入站呼叫-基于位置的路由可以阻止传入的 PSTN 呼叫拨打 Lync 终结点, 前提是传入呼叫与被呼叫的 Lync 用户没有位于同一区域。

  - 未知区域-基于位置的路由对位于不确定位置 (即从 Internet 连接或位于未知区域中的远程用户) 的用户限制传入和传出 PSTN 呼叫。

  - 国际区域-基于位置的路由通过国际 PSTN 网关 (如果找不到用户位置的本地网关) 来强制路由传出呼叫。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

