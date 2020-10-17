---
title: Lync Server 2013： EndpointSubnet 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: EndpointSubnet table
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398933(v=OCS.15)
ms:contentKeyID: 48185514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00b8414675109a69bec6baeceef4f4496bcf0c84
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533309"
---
# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="1871c-102">Lync Server 2013 中的 EndpointSubnet 表</span><span class="sxs-lookup"><span data-stu-id="1871c-102">EndpointSubnet table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1871c-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1871c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1871c-p101">EndpointSubnet 表是一个支持表。每个记录代表从终结点捕获的一个子网。</span><span class="sxs-lookup"><span data-stu-id="1871c-p101">The EndpointSubnet table is a supporting table. Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1871c-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="1871c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1871c-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="1871c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1871c-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="1871c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1871c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="1871c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1871c-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="1871c-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="1871c-111">int</span><span class="sxs-lookup"><span data-stu-id="1871c-111">int</span></span></p></td>
<td><p><span data-ttu-id="1871c-112">主、外</span><span class="sxs-lookup"><span data-stu-id="1871c-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1871c-113">子网的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="1871c-113">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1871c-114"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="1871c-114"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="1871c-115">datetime</span><span class="sxs-lookup"><span data-stu-id="1871c-115">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1871c-116">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1871c-116">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

