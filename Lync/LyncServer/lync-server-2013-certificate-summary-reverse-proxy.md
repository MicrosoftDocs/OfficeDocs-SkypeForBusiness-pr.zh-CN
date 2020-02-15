---
title: Lync Server 2013：证书摘要-反向代理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56da4c10da99a43c3a93f9ae251c2eb6f1536b37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="60ea5-102">Lync Server 2013 中的证书摘要-反向代理</span><span class="sxs-lookup"><span data-stu-id="60ea5-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60ea5-103">_**上次修改的主题：** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="60ea5-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="60ea5-104">反向代理的证书要求比边缘服务器的证书要求简单得多。</span><span class="sxs-lookup"><span data-stu-id="60ea5-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="60ea5-105">所提供的流程图显示了必需的要求。</span><span class="sxs-lookup"><span data-stu-id="60ea5-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="60ea5-106">随附的表提供了与我们在边缘服务器讨论中审阅的方案相关的典型证书主题名称和使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="60ea5-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="60ea5-107">有关边缘服务器方案的更多详细信息，请参阅[Lync server 2013 中的外部用户访问应用场景](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="60ea5-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="60ea5-108">**反向代理的证书流程图**</span><span class="sxs-lookup"><span data-stu-id="60ea5-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="60ea5-109">![边缘服务器的证书流程图](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "边缘服务器的证书流程图")</span><span class="sxs-lookup"><span data-stu-id="60ea5-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="60ea5-110">反向代理：外部接口</span><span class="sxs-lookup"><span data-stu-id="60ea5-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60ea5-111">组件</span><span class="sxs-lookup"><span data-stu-id="60ea5-111">Component</span></span></th>
<th><span data-ttu-id="60ea5-112">使用者名称</span><span class="sxs-lookup"><span data-stu-id="60ea5-112">Subject name</span></span></th>
<th><span data-ttu-id="60ea5-113">使用者替代名称 (SAN)/顺序</span><span class="sxs-lookup"><span data-stu-id="60ea5-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="60ea5-114">注释</span><span class="sxs-lookup"><span data-stu-id="60ea5-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60ea5-115">反向代理</span><span class="sxs-lookup"><span data-stu-id="60ea5-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="60ea5-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60ea5-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="60ea5-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60ea5-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="60ea5-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60ea5-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="60ea5-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60ea5-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="60ea5-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60ea5-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="60ea5-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60ea5-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="60ea5-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60ea5-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="60ea5-123">（可选）:\* contoso.com</span><span class="sxs-lookup"><span data-stu-id="60ea5-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="60ea5-124">证书必须由公共 CA 颁发，并且必须包含服务器 EKU。</span><span class="sxs-lookup"><span data-stu-id="60ea5-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="60ea5-125">服务包括通讯簿服务、通讯组扩展 Office Web Apps for 会议和 Lync IP 设备发布规则。</span><span class="sxs-lookup"><span data-stu-id="60ea5-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="60ea5-126">使用者替代名称包括：</span><span class="sxs-lookup"><span data-stu-id="60ea5-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="60ea5-127">适用于前端服务器或前端池的外部 Web 服务 FQDN</span><span class="sxs-lookup"><span data-stu-id="60ea5-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="60ea5-128">用于控制器或控制器池的外部 Web 服务 FQDN</span><span class="sxs-lookup"><span data-stu-id="60ea5-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="60ea5-129">电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="60ea5-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="60ea5-130">联机会议发布规则</span><span class="sxs-lookup"><span data-stu-id="60ea5-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="60ea5-131">Office Web Apps for 会议</span><span class="sxs-lookup"><span data-stu-id="60ea5-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="60ea5-132">Lyncdiscover（自动发现）</span><span class="sxs-lookup"><span data-stu-id="60ea5-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="60ea5-133">可选通配符将替换 meet 和 dialin SAN</span><span class="sxs-lookup"><span data-stu-id="60ea5-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

