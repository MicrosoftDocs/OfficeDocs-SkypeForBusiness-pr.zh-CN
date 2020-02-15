---
title: Lync Server 2013：外围网络 VoIP 组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e3318f6579e3dd9924c0b5d3bfec941dcc4e916
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="b53fe-102">Lync Server 2013 的外围网络 VoIP 组件</span><span class="sxs-lookup"><span data-stu-id="b53fe-102">Perimeter network VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b53fe-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b53fe-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b53fe-104">对个人或会议呼叫使用统一通信客户端的外部呼叫者依靠边缘服务器与同事进行语音通信。</span><span class="sxs-lookup"><span data-stu-id="b53fe-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="b53fe-105">在边缘服务器上，访问边缘服务提供来自你组织的防火墙外部的 Lync 用户呼叫的 SIP 信号。</span><span class="sxs-lookup"><span data-stu-id="b53fe-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="b53fe-106">A/V 边缘服务使媒体可以遍历 NAT 和防火墙。</span><span class="sxs-lookup"><span data-stu-id="b53fe-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="b53fe-107">从公司防火墙的外部使用统一通信 (UC) 客户端的呼叫者依靠 A/V 边缘服务进行个别呼叫和电话会议。</span><span class="sxs-lookup"><span data-stu-id="b53fe-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="b53fe-p102">A/V 身份验证服务与 A/V 边缘服务并置在一起，并为后者提供身份验证服务。外部用户如果想要连接到 A/V 边缘服务，则只有在获得 A/V 身份验证服务提供的身份验证令牌之后，其呼叫才能通过。</span><span class="sxs-lookup"><span data-stu-id="b53fe-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

