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
ms.openlocfilehash: f45bd91eade0de6f290fd87e52effb25c669999a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="d7b2f-102">在 Lync Server 2013 中使用 SIP 中继路由 E9-1-1 呼叫</span><span class="sxs-lookup"><span data-stu-id="d7b2f-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7b2f-103">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="d7b2f-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="d7b2f-104">使用 SIP 中继连接到合格的 E9-1-1 服务提供商是部署 E9-1-1 的一种方法。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="d7b2f-105">有关使用 ELIN 网关连接到基于公用电话交换网（PSTN）的 E9-1-1 服务提供商的详细信息，请参阅[使用 Lync Server 2013 中的 ELIN 网关路由 E9-1-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="d7b2f-106">下图显示了在使用 SIP 中继和合格的 E9-1-1 服务提供商时，如何将紧急呼叫从 Lync Server 路由到公共安全应答点（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="d7b2f-107">**通过 SIP 中继路由 E9-1-1 呼叫**</span><span class="sxs-lookup"><span data-stu-id="d7b2f-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="d7b2f-108">![从 Lync Server 到 PSAP 的紧急呼叫路由](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "从 Lync Server 到 PSAP 的紧急呼叫路由")</span><span class="sxs-lookup"><span data-stu-id="d7b2f-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="d7b2f-109">当从兼容的 Lync Server 客户端发出紧急呼叫时：</span><span class="sxs-lookup"><span data-stu-id="d7b2f-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="d7b2f-110">包含位置、呼叫者的回拨号码以及（可选）通知 URL 和会议回拨号码的 SIP INVITE 将路由到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="d7b2f-111">Lync Server 匹配紧急号码，并将呼叫（基于适用位置策略中定义的**PSTN 用法**值）路由到中介服务器，并将该呼叫路由到 E9-1-1 服务提供商的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="d7b2f-p102">E9-1-1 服务提供商根据呼叫提供的位置将紧急呼叫路由至正确的 PSAP。当客户端在紧急呼叫中包括验证的紧急响应位置 (ERL) 时，提供商会自动将呼叫路由至正确的 PSAP。如果位置由用户手动输入，那么紧急呼叫响应中心 (ECRC) 会首先口头与呼叫者验证位置的准确性，再将紧急呼叫路由至 PSAP。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="d7b2f-115">如果为通知配置了位置策略，则会向一个或多个组织的安全主管发送特殊的 Lync 急诊通知即时消息。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="d7b2f-116">此消息始终会在安全主管的屏幕上弹出，并包含呼叫者的姓名、电话号码、时间和位置，使安全人员可以使用即时消息或声音快速应答紧急呼叫者。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="d7b2f-117">如果您配置了用于会议的位置策略并且 E9-1-1 服务提供商支持该策略，则国际安全服务台会通过单向音频或双向音频作为与会者加入呼叫。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="d7b2f-118">如果呼叫过早地中断，那么 PSAP 使用回拨号码直接联系呼叫者。</span><span class="sxs-lookup"><span data-stu-id="d7b2f-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

