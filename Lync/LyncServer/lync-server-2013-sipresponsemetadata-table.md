---
title: Lync Server 2013： SIPResponseMetaData 表
description: Lync Server 2013： SIPResponseMetaData 表。
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
ms.openlocfilehash: 402cff331f81a9b46028d76de69deeaace8d5ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558978"
---
# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="8d3ec-103">Lync Server 2013 中的 SIPResponseMetaData 表</span><span class="sxs-lookup"><span data-stu-id="8d3ec-103">SIPResponseMetaData table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d3ec-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8d3ec-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8d3ec-p101">SIPResponseMetaDataTable 包含 SIP 响应代码的列表以及每种代码的分类和定义。在响应影响 SIP 设备和 SIP 通信会话的事件时生成这些代码；例如，当某个 SIP 设备发出请求，但服务器拒绝服从该请求时，将生成响应代码 403。</span><span class="sxs-lookup"><span data-stu-id="8d3ec-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="8d3ec-107">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8d3ec-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d3ec-108">列</span><span class="sxs-lookup"><span data-stu-id="8d3ec-108">Column</span></span></th>
<th><span data-ttu-id="8d3ec-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="8d3ec-109">Data Type</span></span></th>
<th><span data-ttu-id="8d3ec-110">键/索引</span><span class="sxs-lookup"><span data-stu-id="8d3ec-110">Key/Index</span></span></th>
<th><span data-ttu-id="8d3ec-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="8d3ec-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d3ec-112"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="8d3ec-112"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="8d3ec-113">int</span><span class="sxs-lookup"><span data-stu-id="8d3ec-113">int</span></span></p></td>
<td><p><span data-ttu-id="8d3ec-114">主</span><span class="sxs-lookup"><span data-stu-id="8d3ec-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="8d3ec-115">表示 SIP 响应代码的数字值。</span><span class="sxs-lookup"><span data-stu-id="8d3ec-115">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d3ec-116"><strong>Class</strong></span><span class="sxs-lookup"><span data-stu-id="8d3ec-116"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="8d3ec-117">int</span><span class="sxs-lookup"><span data-stu-id="8d3ec-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8d3ec-p102">响应代码的常规分类。分类包括：</span><span class="sxs-lookup"><span data-stu-id="8d3ec-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="8d3ec-120">1 – 信息响应</span><span class="sxs-lookup"><span data-stu-id="8d3ec-120">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="8d3ec-121">2 – 成功响应</span><span class="sxs-lookup"><span data-stu-id="8d3ec-121">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="8d3ec-122">3 – 重定向响应</span><span class="sxs-lookup"><span data-stu-id="8d3ec-122">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="8d3ec-123">4 – 客户端失败响应</span><span class="sxs-lookup"><span data-stu-id="8d3ec-123">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="8d3ec-124">5--服务器故障响应</span><span class="sxs-lookup"><span data-stu-id="8d3ec-124">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="8d3ec-125">6 – 全局失败响应</span><span class="sxs-lookup"><span data-stu-id="8d3ec-125">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d3ec-126"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="8d3ec-126"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="8d3ec-127">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="8d3ec-127">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8d3ec-p103">SIP 响应代码的说明。例如，响应代码 181 的说明如下：</span><span class="sxs-lookup"><span data-stu-id="8d3ec-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="8d3ec-130">Call Is Being Forwarded</span><span class="sxs-lookup"><span data-stu-id="8d3ec-130">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

