---
title: Lync Server 2013： Location-Based 路由概述
description: Lync Server 2013： Location-Based 路由的概述。
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
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562808"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中的 Location-Based 路由概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

Location-Based 传送引入了一组新的规则，这些规则可修改国内和国际 PSTN 呼叫的路由以防止收费绕过。 Location-Based 路由可以灵活地将这些规则限定为特定区域、特定网关或仅特定用户集。

以下方案说明了 Location-Based 路由可以强制执行的主要限制类型：

  - 出局呼叫– Location-Based 路由可以强制传出呼叫从位于与呼叫者阻止 PSTN 收费旁路的 PSTN 网关的传出呼叫，这将阻止从位于不同区域中的 PSTN 网关传出的传出呼叫呼叫者。

  - 入站呼叫–如果 PSTN 网关路由传入呼叫不在与被叫 Lync 用户相同的区域中，则 Location-Based 路由可以阻止传入 PSTN 呼叫拨打 Lync 终结点。

  - 未知区域– Location-Based 路由将传入和传出 PSTN 呼叫限制在不确定位置的用户 (例如，从 Internet 连接或位于未知区域中的远程用户) 。

  - 国际区域–如果找不到用户位置的网关，则路由通过国际 PSTN 网关执行传出呼叫的路由（如果找不到用户位置的网关 Location-Based）。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划 Location-Based 路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

