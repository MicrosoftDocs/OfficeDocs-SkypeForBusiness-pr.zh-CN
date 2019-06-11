---
title: Lync Server 2013：Subnet 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20318d0ed2f487efccda81936b113044f75e2618
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="42f9c-102">Lync Server 2013 中的 Subnet 表</span><span class="sxs-lookup"><span data-stu-id="42f9c-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42f9c-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="42f9c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="42f9c-104">子网表是支持表。</span><span class="sxs-lookup"><span data-stu-id="42f9c-104">The Subnet table is a supporting table.</span></span> <span data-ttu-id="42f9c-105">每条记录表示网络配置设置中定义的一个子网。</span><span class="sxs-lookup"><span data-stu-id="42f9c-105">Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42f9c-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="42f9c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="42f9c-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="42f9c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="42f9c-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="42f9c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="42f9c-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="42f9c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42f9c-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="42f9c-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="42f9c-111">int</span><span class="sxs-lookup"><span data-stu-id="42f9c-111">int</span></span></p></td>
<td><p><span data-ttu-id="42f9c-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="42f9c-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="42f9c-113">子网 IP 的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="42f9c-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f9c-114"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="42f9c-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="42f9c-115">int</span><span class="sxs-lookup"><span data-stu-id="42f9c-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42f9c-116">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="42f9c-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f9c-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="42f9c-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="42f9c-118">int</span><span class="sxs-lookup"><span data-stu-id="42f9c-118">int</span></span></p></td>
<td><p><span data-ttu-id="42f9c-119">外表</span><span class="sxs-lookup"><span data-stu-id="42f9c-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42f9c-120">从<a href="lync-server-2013-usersite-table.md">Lync Server 2013 中的 UserSite 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="42f9c-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f9c-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="42f9c-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="42f9c-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="42f9c-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42f9c-123">子网的说明。</span><span class="sxs-lookup"><span data-stu-id="42f9c-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

