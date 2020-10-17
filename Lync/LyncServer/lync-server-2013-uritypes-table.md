---
title: Lync Server 2013： UriTypes 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UriTypes table
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48184553
ms.date: 06/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca63f2ea00ab05f767642045663c934a6f4728d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530299"
---
# <a name="uritypes-table-in-lync-server-2013"></a><span data-ttu-id="8546c-102">Lync Server 2013 中的 UriTypes 表</span><span class="sxs-lookup"><span data-stu-id="8546c-102">UriTypes table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8546c-103">_**上次修改的主题：** 2015-06-16_</span><span class="sxs-lookup"><span data-stu-id="8546c-103">_**Topic Last Modified:** 2015-06-16_</span></span>

<span data-ttu-id="8546c-104">UriTypes 表包含在 Microsoft Lync Server 2013 中监视的不同 URI (统一资源标识符) 类型。</span><span class="sxs-lookup"><span data-stu-id="8546c-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8546c-105">列</span><span class="sxs-lookup"><span data-stu-id="8546c-105">Column</span></span></th>
<th><span data-ttu-id="8546c-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="8546c-106">Data Type</span></span></th>
<th><span data-ttu-id="8546c-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="8546c-107">Key/Index</span></span></th>
<th><span data-ttu-id="8546c-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="8546c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8546c-109"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="8546c-109"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="8546c-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="8546c-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8546c-111">主</span><span class="sxs-lookup"><span data-stu-id="8546c-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="8546c-112">分配给 URI 类型的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8546c-112">Unique identifier assigned to a URI type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8546c-113"><strong>UriType</strong></span><span class="sxs-lookup"><span data-stu-id="8546c-113"><strong>UriType</strong></span></span></p></td>
<td><p><span data-ttu-id="8546c-114">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="8546c-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8546c-p101">不同的 URI 类型的描述。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="8546c-p101">Descriptions of the different URI types. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8546c-117">1–电话 Uri</span><span class="sxs-lookup"><span data-stu-id="8546c-117">1 – Phone Uri</span></span></p></li>
<li><p><span data-ttu-id="8546c-118">0–用户 Uri</span><span class="sxs-lookup"><span data-stu-id="8546c-118">0 – User Uri</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

