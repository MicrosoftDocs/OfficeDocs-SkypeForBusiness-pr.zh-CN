---
title: Lync Server 2013： SIPResponseMetaData 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="b9004-102">Lync Server 2013 中的 SIPResponseMetaData 表</span><span class="sxs-lookup"><span data-stu-id="b9004-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9004-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b9004-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b9004-104">SIPResponseMetaDataTable 包含 SIP 响应代码列表以及每个代码的分类和定义。</span><span class="sxs-lookup"><span data-stu-id="b9004-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="b9004-105">系统会生成这些代码，以响应影响 SIP 设备和 SIP 通信会话的事件;例如，在 SIP 设备发出请求时，将生成响应代码403，但服务器拒绝接受该请求。</span><span class="sxs-lookup"><span data-stu-id="b9004-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="b9004-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="b9004-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9004-107">列</span><span class="sxs-lookup"><span data-stu-id="b9004-107">Column</span></span></th>
<th><span data-ttu-id="b9004-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="b9004-108">Data Type</span></span></th>
<th><span data-ttu-id="b9004-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="b9004-109">Key/Index</span></span></th>
<th><span data-ttu-id="b9004-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="b9004-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9004-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b9004-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b9004-112">int</span><span class="sxs-lookup"><span data-stu-id="b9004-112">int</span></span></p></td>
<td><p><span data-ttu-id="b9004-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b9004-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b9004-114">表示 SIP 响应代码的数值。</span><span class="sxs-lookup"><span data-stu-id="b9004-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9004-115"><strong>种类</strong></span><span class="sxs-lookup"><span data-stu-id="b9004-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="b9004-116">int</span><span class="sxs-lookup"><span data-stu-id="b9004-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9004-117">响应代码的常规分类。</span><span class="sxs-lookup"><span data-stu-id="b9004-117">General classification for the response code.</span></span> <span data-ttu-id="b9004-118">分类包括：</span><span class="sxs-lookup"><span data-stu-id="b9004-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9004-119">1-信息答复</span><span class="sxs-lookup"><span data-stu-id="b9004-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="b9004-120">2–成功的答复</span><span class="sxs-lookup"><span data-stu-id="b9004-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="b9004-121">3-重定向响应</span><span class="sxs-lookup"><span data-stu-id="b9004-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="b9004-122">4-客户端故障响应</span><span class="sxs-lookup"><span data-stu-id="b9004-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="b9004-123">5--服务器故障响应</span><span class="sxs-lookup"><span data-stu-id="b9004-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="b9004-124">6-全球故障回复</span><span class="sxs-lookup"><span data-stu-id="b9004-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9004-125"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="b9004-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="b9004-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b9004-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9004-127">SIP 响应代码的说明。</span><span class="sxs-lookup"><span data-stu-id="b9004-127">Description of the SIP response code.</span></span> <span data-ttu-id="b9004-128">例如，响应代码181具有以下说明：</span><span class="sxs-lookup"><span data-stu-id="b9004-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="b9004-129">正在转发呼叫</span><span class="sxs-lookup"><span data-stu-id="b9004-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

