---
title: Lync Server 2013：呼叫允许控制和中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 787e312bcdee289050f2147912e87ef542433db4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的呼叫允许控制和中介服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

呼叫许可控制 (CAC), 首次在 Lync Server 2010 中引入, 可管理基于可用带宽的实时会话建立, 以帮助防止用户在拥挤的网络上出现质量较差的用户 (QoE)。 为支持此功能, 中介服务器提供企业语音基础设施和网关或 SIP 中继提供商之间的信号和媒体转换, 负责在 Lync 上的两个交互中使用带宽管理服务器端和网关端。 在呼叫允许控制中，呼叫的端接实体处理带宽预留。 中介服务器与网关端交互的网关对等 (PSTN 网关子、SBC) 不支持 Lync Server 2013 呼叫许可控制。 因此, 中介服务器必须以网关对等的名义处理带宽交互。 如果可能, 中介服务器将提前预留带宽。 如果不可能（例如，如果网关端的最终媒体终结点位置对于发往对等网关的传出呼叫是未知的），则会在发出呼叫时预留带宽。 此行为可能导致带宽订阅过度，但这是防止错误响铃的唯一方法。

媒体旁路和带宽预留相互排斥。 如果将媒体绕过用于呼叫, 则不会为该呼叫执行呼叫许可控制。 此处假定前提是此次呼叫不涉及具有限定带宽的链接。 如果呼叫许可控制用于涉及中介服务器的特定呼叫, 则该呼叫无法使用媒体绕过。

有关媒体绕过或呼叫许可控制的详细信息, 请参阅规划文档中的 "[在 lync server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)" 或 "[在 lync Server 2013 中规划呼叫许可控制](lync-server-2013-planning-for-call-admission-control.md)"。

</div>

<span> </span>

</div>

</div>

</div>

