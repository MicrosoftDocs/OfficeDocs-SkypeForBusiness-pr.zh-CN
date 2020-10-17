---
title: Lync Server 2013： DNS 摘要-单一控制器
description: Lync Server 2013： DNS 摘要-单个控制器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553228"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="23f40-103">DNS 摘要-Lync Server 2013 中的单个控制器</span><span class="sxs-lookup"><span data-stu-id="23f40-103">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23f40-104">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="23f40-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="23f40-105">下表列出了支持单个控制器所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="23f40-105">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="23f40-106">Director 的角色需要类似的 DNS 记录作为前端服务器。</span><span class="sxs-lookup"><span data-stu-id="23f40-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="23f40-107">所需的记录数反映在控制器证书所需的主题替代名称中。</span><span class="sxs-lookup"><span data-stu-id="23f40-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="23f40-108">与前端服务器不同，控制器不承载用户帐户或承载移动服务。</span><span class="sxs-lookup"><span data-stu-id="23f40-108">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="23f40-109">控制器所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="23f40-109">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23f40-110">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="23f40-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="23f40-111">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="23f40-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="23f40-112">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="23f40-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="23f40-113">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="23f40-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23f40-114">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="23f40-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="23f40-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="23f40-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="23f40-116">控制器</span><span class="sxs-lookup"><span data-stu-id="23f40-116">Director</span></span></p></td>
<td><p><span data-ttu-id="23f40-117">用于复制和服务器到服务器的控制器主机记录</span><span class="sxs-lookup"><span data-stu-id="23f40-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f40-118">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="23f40-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="23f40-119">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23f40-119">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="23f40-120">控制器</span><span class="sxs-lookup"><span data-stu-id="23f40-120">Director</span></span></p></td>
<td><p><span data-ttu-id="23f40-121">来自边缘服务器的内部边缘接口 (SIP) 的入站会话初始协议</span><span class="sxs-lookup"><span data-stu-id="23f40-121">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f40-122">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="23f40-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="23f40-123">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23f40-123">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="23f40-124">控制器</span><span class="sxs-lookup"><span data-stu-id="23f40-124">Director</span></span></p></td>
<td><p><span data-ttu-id="23f40-125">反向代理中的已发布电话拨入式 Web 服务</span><span class="sxs-lookup"><span data-stu-id="23f40-125">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f40-126">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="23f40-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="23f40-127">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23f40-127">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="23f40-128">控制器</span><span class="sxs-lookup"><span data-stu-id="23f40-128">Director</span></span></p></td>
<td><p><span data-ttu-id="23f40-129">反向代理中的已发布的会议 Web 服务</span><span class="sxs-lookup"><span data-stu-id="23f40-129">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f40-130">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="23f40-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="23f40-131">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23f40-131">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="23f40-132">控制器</span><span class="sxs-lookup"><span data-stu-id="23f40-132">Director</span></span></p></td>
<td><p><span data-ttu-id="23f40-133">由 Director 的反向代理 Web 票证外部 web 服务发布和定义</span><span class="sxs-lookup"><span data-stu-id="23f40-133">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

