---
title: Lync Server 2013：基于位置的路由不支持的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff96f72ff7d71c005f97142ed9844b7c9509e022
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中基于位置的路由不支持的功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-03-12_

基于位置的路由不适用于以下类型的交互。 当 Lync 终结点使用这些功能与 PSTN 终结点进行交互时，不会强制执行基于位置的路由。

  - PSTN 电话拨入会议

  - 通过响应组的传入和传出 PSTN 呼叫

  - 通过呼叫寄存呼叫寄存或检索 PSTN 呼叫

  - 到公告服务的传入 PSTN 呼叫

  - 通过组呼叫应答检索的传入 PSTN 呼叫

若要对以下列表中的交互类型强制执行基于位置的路由规则，您必须为会议启用基于位置的路由：

  - 来自会议的 PSTN 拨出

  - 从对等音频对话到涉及 PSTN 终结点的会议的升级

  - 涉及 PSTN 终结点的咨询转移

若要为会议启用基于位置的路由，请参阅[Lync Server 2013 中的会议的基于位置的路由](lync-server-2013-location-based-routing-for-conferencing.md)。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

