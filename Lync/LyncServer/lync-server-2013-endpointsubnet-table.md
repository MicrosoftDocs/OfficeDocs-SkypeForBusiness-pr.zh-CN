---
title: Lync Server 2013：EndpointSubnet 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: EndpointSubnet table
ms:assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398933(v=OCS.15)
ms:contentKeyID: 48185514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1804b383d3d71c12d5c2aa53b276b578d89994bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="01396-102">Lync Server 2013 中的 EndpointSubnet 表</span><span class="sxs-lookup"><span data-stu-id="01396-102">EndpointSubnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01396-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="01396-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="01396-104">EndpointSubnet 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="01396-104">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="01396-105">每条记录表示一个从终结点捕获的子网。</span><span class="sxs-lookup"><span data-stu-id="01396-105">Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01396-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="01396-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="01396-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="01396-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="01396-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="01396-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="01396-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="01396-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01396-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="01396-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="01396-111">int</span><span class="sxs-lookup"><span data-stu-id="01396-111">int</span></span></p></td>
<td><p><span data-ttu-id="01396-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="01396-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="01396-113">子网的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="01396-113">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01396-114"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="01396-114"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="01396-115">datetime</span><span class="sxs-lookup"><span data-stu-id="01396-115">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="01396-116">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="01396-116">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

