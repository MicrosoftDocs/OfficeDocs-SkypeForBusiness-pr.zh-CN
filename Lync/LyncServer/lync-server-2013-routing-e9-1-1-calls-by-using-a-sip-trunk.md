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
ms.openlocfilehash: d58507d72a096cb3fbf6deb0d09cddc542fdc2d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>在 Lync Server 2013 中使用 SIP 中继路由 E9-1-1 呼叫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-29_

使用 SIP 中继连接到合格的 E9-1-1 服务提供商是部署 E9-1-1 的一种方法。 有关使用 ELIN 网关连接到基于公用电话交换网（PSTN）的 E9-1-1 服务提供商的详细信息，请参阅[使用 Lync Server 2013 中的 ELIN 网关路由 E9-1-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。

下图显示了在使用 SIP 中继和合格的 E9-1-1 服务提供商时，如何将紧急呼叫从 Lync Server 路由到公共安全应答点（PSAP）。

**通过 SIP 中继路由 E9-1-1 呼叫**

![从 Lync Server 到 PSAP 的紧急呼叫路由](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "从 Lync Server 到 PSAP 的紧急呼叫路由")

当从兼容的 Lync Server 客户端发出紧急呼叫时：

1.  包含位置、呼叫者的回拨号码以及（可选）通知 URL 和会议回拨号码的 SIP INVITE 将路由到 Lync Server。

2.  Lync Server 匹配紧急号码，并将呼叫（基于适用位置策略中定义的**PSTN 用法**值）路由到中介服务器，并将该呼叫路由到 E9-1-1 服务提供商的 SIP 中继。

3.  E9-1-1 服务提供商根据呼叫提供的位置将紧急呼叫路由至正确的 PSAP。当客户端在紧急呼叫中包括验证的紧急响应位置 (ERL) 时，提供商会自动将呼叫路由至正确的 PSAP。如果位置由用户手动输入，那么紧急呼叫响应中心 (ECRC) 会首先口头与呼叫者验证位置的准确性，再将紧急呼叫路由至 PSAP。

4.  如果为通知配置了位置策略，则会向一个或多个组织的安全主管发送特殊的 Lync 急诊通知即时消息。 此消息始终会在安全主管的屏幕上弹出，并包含呼叫者的姓名、电话号码、时间和位置，使安全人员可以使用即时消息或声音快速应答紧急呼叫者。

5.  如果您配置了用于会议的位置策略并且 E9-1-1 服务提供商支持该策略，则国际安全服务台会通过单向音频或双向音频作为与会者加入呼叫。

6.  如果呼叫过早地中断，那么 PSAP 使用回拨号码直接联系呼叫者。

</div>

<span> </span>

</div>

</div>

</div>

