---
title: Lync Server 2013：子网表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cdf1ded3a63d790db78476b91a458d07921200a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="26207-102">Lync Server 2013 中的子网表</span><span class="sxs-lookup"><span data-stu-id="26207-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26207-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="26207-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="26207-p101">Subnet 表是一个支持表。每条记录均表示网络配置设置中定义的一个子网。</span><span class="sxs-lookup"><span data-stu-id="26207-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26207-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="26207-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="26207-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="26207-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="26207-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="26207-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="26207-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="26207-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26207-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="26207-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="26207-111">int</span><span class="sxs-lookup"><span data-stu-id="26207-111">int</span></span></p></td>
<td><p><span data-ttu-id="26207-112">主、外</span><span class="sxs-lookup"><span data-stu-id="26207-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="26207-113">子网 IP 的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="26207-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26207-114"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="26207-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="26207-115">int</span><span class="sxs-lookup"><span data-stu-id="26207-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26207-116">子网掩码。</span><span class="sxs-lookup"><span data-stu-id="26207-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26207-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="26207-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="26207-118">int</span><span class="sxs-lookup"><span data-stu-id="26207-118">int</span></span></p></td>
<td><p><span data-ttu-id="26207-119">对外</span><span class="sxs-lookup"><span data-stu-id="26207-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="26207-120"><a href="lync-server-2013-usersite-table.md">在 Lync Server 2013 中从 UserSite 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="26207-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26207-121"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="26207-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="26207-122">nvarchar （512）</span><span class="sxs-lookup"><span data-stu-id="26207-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26207-123">子网的说明。</span><span class="sxs-lookup"><span data-stu-id="26207-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

