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
ms.openlocfilehash: 164c6e1541869a2976f283443f2fae9246f28007
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="5fe19-102">Lync Server 2013 中的 SIPResponseMetaData 表</span><span class="sxs-lookup"><span data-stu-id="5fe19-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fe19-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5fe19-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5fe19-p101">SIPResponseMetaDataTable 包含 SIP 响应代码的列表以及每种代码的分类和定义。在响应影响 SIP 设备和 SIP 通信会话的事件时生成这些代码；例如，当某个 SIP 设备发出请求，但服务器拒绝服从该请求时，将生成响应代码 403。</span><span class="sxs-lookup"><span data-stu-id="5fe19-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="5fe19-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5fe19-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fe19-107">列</span><span class="sxs-lookup"><span data-stu-id="5fe19-107">Column</span></span></th>
<th><span data-ttu-id="5fe19-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="5fe19-108">Data Type</span></span></th>
<th><span data-ttu-id="5fe19-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="5fe19-109">Key/Index</span></span></th>
<th><span data-ttu-id="5fe19-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="5fe19-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fe19-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5fe19-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5fe19-112">int</span><span class="sxs-lookup"><span data-stu-id="5fe19-112">int</span></span></p></td>
<td><p><span data-ttu-id="5fe19-113">主</span><span class="sxs-lookup"><span data-stu-id="5fe19-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="5fe19-114">表示 SIP 响应代码的数字值。</span><span class="sxs-lookup"><span data-stu-id="5fe19-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe19-115"><strong>类</strong></span><span class="sxs-lookup"><span data-stu-id="5fe19-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="5fe19-116">int</span><span class="sxs-lookup"><span data-stu-id="5fe19-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fe19-p102">响应代码的常规分类。分类包括：</span><span class="sxs-lookup"><span data-stu-id="5fe19-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="5fe19-119">1 – 信息响应</span><span class="sxs-lookup"><span data-stu-id="5fe19-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="5fe19-120">2 – 成功响应</span><span class="sxs-lookup"><span data-stu-id="5fe19-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="5fe19-121">3 – 重定向响应</span><span class="sxs-lookup"><span data-stu-id="5fe19-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="5fe19-122">4 – 客户端失败响应</span><span class="sxs-lookup"><span data-stu-id="5fe19-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="5fe19-123">5--服务器故障响应</span><span class="sxs-lookup"><span data-stu-id="5fe19-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="5fe19-124">6 – 全局失败响应</span><span class="sxs-lookup"><span data-stu-id="5fe19-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fe19-125"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="5fe19-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="5fe19-126">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="5fe19-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fe19-p103">SIP 响应代码的说明。例如，响应代码 181 的说明如下：</span><span class="sxs-lookup"><span data-stu-id="5fe19-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="5fe19-129">Call Is Being Forwarded</span><span class="sxs-lookup"><span data-stu-id="5fe19-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

