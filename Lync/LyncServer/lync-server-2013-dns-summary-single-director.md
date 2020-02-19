---
title: Lync Server 2013： DNS 摘要-单一控制器
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
ms.openlocfilehash: 76fe7663e0af8eeeb049ca80f1dd92a7cc882b98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="e25b1-102">DNS 摘要-Lync Server 2013 中的单个控制器</span><span class="sxs-lookup"><span data-stu-id="e25b1-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e25b1-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e25b1-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e25b1-104">下表列出了支持单个控制器所需的 DNS 记录的摘要。</span><span class="sxs-lookup"><span data-stu-id="e25b1-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="e25b1-105">Director 的角色需要类似的 DNS 记录作为前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e25b1-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="e25b1-106">所需的记录数反映在控制器证书所需的主题替代名称中。</span><span class="sxs-lookup"><span data-stu-id="e25b1-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="e25b1-107">与前端服务器不同，控制器不承载用户帐户或承载移动服务。</span><span class="sxs-lookup"><span data-stu-id="e25b1-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="e25b1-108">控制器所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="e25b1-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e25b1-109">位置/类型/端口</span><span class="sxs-lookup"><span data-stu-id="e25b1-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="e25b1-110">FQDN/DNS 记录</span><span class="sxs-lookup"><span data-stu-id="e25b1-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="e25b1-111">IP 地址/FQDN</span><span class="sxs-lookup"><span data-stu-id="e25b1-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="e25b1-112">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="e25b1-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-113">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e25b1-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e25b1-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="e25b1-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="e25b1-115">控制器</span><span class="sxs-lookup"><span data-stu-id="e25b1-115">Director</span></span></p></td>
<td><p><span data-ttu-id="e25b1-116">用于复制和服务器到服务器的控制器主机记录</span><span class="sxs-lookup"><span data-stu-id="e25b1-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-117">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e25b1-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e25b1-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e25b1-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e25b1-119">控制器</span><span class="sxs-lookup"><span data-stu-id="e25b1-119">Director</span></span></p></td>
<td><p><span data-ttu-id="e25b1-120">来自边缘服务器的内部边缘接口的入站会话初始协议（SIP）</span><span class="sxs-lookup"><span data-stu-id="e25b1-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-121">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e25b1-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e25b1-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e25b1-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e25b1-123">控制器</span><span class="sxs-lookup"><span data-stu-id="e25b1-123">Director</span></span></p></td>
<td><p><span data-ttu-id="e25b1-124">反向代理中的已发布电话拨入式 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e25b1-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e25b1-125">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e25b1-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e25b1-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e25b1-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e25b1-127">控制器</span><span class="sxs-lookup"><span data-stu-id="e25b1-127">Director</span></span></p></td>
<td><p><span data-ttu-id="e25b1-128">反向代理中的已发布的会议 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e25b1-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e25b1-129">内部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="e25b1-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="e25b1-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e25b1-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e25b1-131">控制器</span><span class="sxs-lookup"><span data-stu-id="e25b1-131">Director</span></span></p></td>
<td><p><span data-ttu-id="e25b1-132">由 Director 的反向代理 Web 票证外部 web 服务发布和定义</span><span class="sxs-lookup"><span data-stu-id="e25b1-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

