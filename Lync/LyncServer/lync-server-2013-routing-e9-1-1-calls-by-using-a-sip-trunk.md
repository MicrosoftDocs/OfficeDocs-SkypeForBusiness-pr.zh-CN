---
title: Lync Server 2013：使用 SIP 中继路由 E9-1-1 呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 918aaf97b1567f012a2b41de7128db23aa383acb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>在 Lync Server 2013 中使用 SIP 中继路由 E9-1-1 呼叫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-29_

使用 SIP 中继连接至限定的 E9-1-1 服务提供商是可用于部署 E9-1-1 的一种方式。 有关使用 ELIN 网关连接到基于互联网交换式电话网络（PSTN）的 E9 服务提供商的详细信息，请参阅[在 Lync Server 2013 中使用 ELIN 网关进行路由 E9-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。

下图显示了使用 SIP 主干和合格的 E9 服务提供商时，如何将紧急呼叫从 Lync Server 路由到公共安全应答点（PSAP）。

**通过 SIP 中继路由 E9-1-1 呼叫**

![从 Lync Server 路由到 PSAP 的紧急呼叫](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "从 Lync Server 路由到 PSAP 的紧急呼叫")

当从兼容的 Lync 服务器客户端发出紧急呼叫时：

1.  包含位置、呼叫者的回拨号码以及（可选）通知 URL 和会议回呼号码的 SIP 邀请将路由到 Lync 服务器。

2.  Lync Server 匹配紧急号码，并将呼叫路由（基于在适用位置策略中定义的**PSTN 使用**值）到中介服务器，并通过 SIP 主干 E9 服务提供商进行路由。

3.  E9-1-1 服务提供商根据呼叫提供的位置将紧急呼叫路由至正确的 PSAP。如果客户端随紧急呼叫提供了已验证的紧急响应位置 (ERL)，则提供商会自动将呼叫路由至相应的 PSAP。如果位置是由用户手动输入的，则在将紧急呼叫路由至 PSAP 之前，紧急呼叫响应中心 (ECRC) 将首先口头与呼叫者核实位置的准确性。

4.  如果为通知配置了位置策略，则会向一个或多个组织的安全专员发送特殊的 Lync 紧急通知即时消息。 此消息始终会在安全主管的屏幕上弹出，并包含呼叫者的姓名、电话号码、时间和位置，使安全人员可以使用即时消息或语音快速应答紧急呼叫者。

5.  如果您配置了用于会议的位置策略并且 E9-1-1 服务提供商支持该策略，则国际安全服务台会通过单向音频或双向音频作为与会者加入呼叫。

6.  如果过早中断呼叫，则 PSAP 使用回拨号码直接与呼叫者联系。

</div>

<span> </span>

</div>

</div>

</div>

