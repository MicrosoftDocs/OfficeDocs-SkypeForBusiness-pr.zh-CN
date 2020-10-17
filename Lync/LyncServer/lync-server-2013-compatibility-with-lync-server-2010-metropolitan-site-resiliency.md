---
title: Lync Server 2013 与 Lync Server 2010 大都市网站恢复兼容性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04b3cca41b0ea7a7060e6349127dc7c7fb1732ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526049"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Lync Server 2010 大都市站点恢复能力

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-03-19_

Lync Server 2013 不支持 Lync Server 2010 支持的大都市站点恢复解决方案。 此解决方案涉及在同一都市圈中的两个数据中心之间跨越使用一个前端池。

大都市站点恢复解决方案旨在从丢失完整数据中心时进行恢复。 跨两个数据中心跨越池时，通常会在一个数据中心中放置半个前端，在第二个数据中心中放置另一半。 如果丢失整个数据中心，则会丢失一半前端服务器。 在 Lync Server 2013 中，这可能会导致前端池的新分布式系统模型出现问题。 有关详细信息，请参阅 [Lync Server 2013 中的前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

</div>

<span> </span>

</div>

</div>

</div>

