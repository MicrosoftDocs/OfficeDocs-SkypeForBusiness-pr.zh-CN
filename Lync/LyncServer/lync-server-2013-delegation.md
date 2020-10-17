---
title: Lync Server 2013：委派
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b31224228a4f2fbdad879e43bab61292852e009c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516300"
---
# <a name="delegation-in-lync-server-2013"></a>Lync Server 2013 中的委派

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-09_

Lync 中的委派功能受按以下方式 Location-Based 路由的影响：

  - 当启用 Location-Based 路由的代理代表经理发出呼叫时，代理的语音策略将用于授权呼叫，代理的站点语音路由策略将用于路由呼叫

  - 对于 manager 的传入 PSTN 呼叫，适用于呼叫转接或同时响铃的相同规则将按呼叫转移和转发和同时响铃主题中所述进行应用。

  - 如果委派将 PSTN 终结点设置为同时响铃的目标，则对管理器的传入呼叫将使用与传入中继关联的站点的语音路由策略将呼叫路由到代理的 PSTN 终结点。

  - 对于委派，建议经理和他的关联委派通常位于同一个网络站点中。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中 Location-Based 路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

