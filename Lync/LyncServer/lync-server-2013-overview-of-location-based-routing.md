---
title: Lync Server 2013：基于位置的路由概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc7320ffd8bb4d12483a882b588205d26e7e164
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中基于位置的路由概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

基于位置的路由引入了一组新的规则，这些规则可修改国内和国际 PSTN 呼叫的路由以防止收费绕过。 基于位置的路由可以灵活地将这些规则限定为特定区域、特定网关或仅特定用户集。

以下方案说明了可以强制实施基于位置的限制的主要路由类型：

  - 出局呼叫–基于位置的路由可以强制传出呼叫从位于与呼叫者阻止 PSTN 收费旁路的 PSTN 网关传出的传出呼叫，这样可以防止从位于不同区域的 PSTN 网关传出的传出呼叫者.

  - 入站呼叫–基于位置的路由可以阻止传入 PSTN 呼叫拨打 Lync 终结点，如果传入呼叫与被呼叫 Lync 用户不在同一区域中。

  - 未知区域–基于位置的路由将传入和传出 PSTN 呼叫限制在不确定位置（即从 Internet 连接或位于未知区域的远程用户）中的用户。

  - 国际区域–如果找不到用户所在位置的网关，则基于位置的路由会强制通过国际 PSTN 网关路由传出呼叫。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

