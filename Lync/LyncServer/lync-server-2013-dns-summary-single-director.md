---
title: Lync Server 2013：DNS 摘要 - 单一控制器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca7fea825267dcdc5aa03a2e6c3c9fb3fc26a84b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="79d53-102">Lync Server 2013 中的 DNS 摘要 - 单一控制器</span><span class="sxs-lookup"><span data-stu-id="79d53-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79d53-103">_**主题上次修改时间:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="79d53-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="79d53-104">下表包含支持单个控制器所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="79d53-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="79d53-105">Director 的角色需要类似的 DNS 记录作为前端服务器。</span><span class="sxs-lookup"><span data-stu-id="79d53-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="79d53-106">所需的记录数反映在 Director 证书所需的主题备用名称中。</span><span class="sxs-lookup"><span data-stu-id="79d53-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="79d53-107">与前端服务器不同, 控制器不会托管用户帐户或托管移动服务。</span><span class="sxs-lookup"><span data-stu-id="79d53-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="79d53-108">Director 所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="79d53-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79d53-109">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="79d53-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="79d53-110">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="79d53-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="79d53-111">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="79d53-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="79d53-112">映射到/批注</span><span class="sxs-lookup"><span data-stu-id="79d53-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79d53-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79d53-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79d53-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="79d53-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="79d53-115">控制器</span><span class="sxs-lookup"><span data-stu-id="79d53-115">Director</span></span></p></td>
<td><p><span data-ttu-id="79d53-116">用于复制和服务器到服务器的控制器主机记录</span><span class="sxs-lookup"><span data-stu-id="79d53-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79d53-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79d53-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79d53-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79d53-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79d53-119">控制器</span><span class="sxs-lookup"><span data-stu-id="79d53-119">Director</span></span></p></td>
<td><p><span data-ttu-id="79d53-120">来自边缘服务器的内部边缘接口的入站会话初始协议 (SIP)</span><span class="sxs-lookup"><span data-stu-id="79d53-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79d53-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79d53-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79d53-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79d53-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79d53-123">控制器</span><span class="sxs-lookup"><span data-stu-id="79d53-123">Director</span></span></p></td>
<td><p><span data-ttu-id="79d53-124">从反向代理已发布的拨入 web 服务</span><span class="sxs-lookup"><span data-stu-id="79d53-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79d53-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79d53-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79d53-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79d53-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79d53-127">控制器</span><span class="sxs-lookup"><span data-stu-id="79d53-127">Director</span></span></p></td>
<td><p><span data-ttu-id="79d53-128">已发布通过反向代理的 web 服务</span><span class="sxs-lookup"><span data-stu-id="79d53-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79d53-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79d53-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79d53-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79d53-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79d53-131">控制器</span><span class="sxs-lookup"><span data-stu-id="79d53-131">Director</span></span></p></td>
<td><p><span data-ttu-id="79d53-132">由 "反向代理 Web 票" 发布和定义的由 Director 的外部 web 服务</span><span class="sxs-lookup"><span data-stu-id="79d53-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

