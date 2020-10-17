---
title: Lync Server 2013：呼叫允许控制和中介服务器
description: Lync Server 2013：呼叫允许控制和中介服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e4b12a11f941923d50f3ffcab7a8f9b6a9edc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569218"
---
# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的呼叫允许控制和中介服务器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

呼叫允许控制 (CAC) （首次在 Lync Server 2010 中引入）可管理基于可用带宽的实时会话建立，以帮助防止拥挤的网络上的用户 (QoE) 的较差的体验。 为支持此功能，在企业语音基础结构和网关或 SIP 中继提供商之间提供信号和媒体转换的中介服务器负责在 Lync Server 端和网关端的两个交互中进行带宽管理。 在呼叫允许控制中，呼叫的端接实体处理带宽预留。 中介服务器与网关端交互的 PSTN 网关 (PSTN 网关（IP-PBX）) 不支持 Lync Server 2013 呼叫允许控制。 因此，中介服务器必须代表其网关对等方处理带宽交互。 只要有可能，中介服务器将提前预留带宽。 如果不可能（例如，如果网关端的最终媒体终结点位置对于发往对等网关的传出呼叫是未知的），则会在发出呼叫时预留带宽。 此行为可能导致带宽订阅过度，但这是防止错误响铃的唯一方法。

媒体旁路和带宽预留相互排斥。 如果对呼叫使用媒体旁路功能，则不会对该呼叫执行呼叫允许控制。 此处假定前提是此次呼叫不涉及具有限定带宽的链接。 如果呼叫允许控制用于涉及中介服务器的特定呼叫，则该呼叫无法使用媒体旁路。

有关媒体旁路或呼叫允许控制的详细信息，请参阅规划文档中的在 lync server [2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md) 或在 [lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md) 。

</div>

<span> </span>

</div>

</div>

</div>

