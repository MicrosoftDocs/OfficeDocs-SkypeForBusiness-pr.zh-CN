---
title: Lync Server 2013： IPAddress 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e99e05013d823d5a3a1c1ce1eef6ccc47cfb59
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipaddress-table-in-lync-server-2013"></a><span data-ttu-id="376aa-102">Lync Server 2013 中的 IPAddress 表</span><span class="sxs-lookup"><span data-stu-id="376aa-102">IPAddress table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="376aa-103">_**上次修改的主题：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="376aa-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="376aa-104">IPAddress 表将 IP 地址映射到可在用户体验质量数据库中的任何其他位置使用的唯一 IP 地址标识符。</span><span class="sxs-lookup"><span data-stu-id="376aa-104">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="376aa-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="376aa-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="376aa-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="376aa-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="376aa-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="376aa-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="376aa-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="376aa-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="376aa-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="376aa-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="376aa-110"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="376aa-110"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="376aa-111">int</span><span class="sxs-lookup"><span data-stu-id="376aa-111">int</span></span></p></td>
<td><p><span data-ttu-id="376aa-112">主</span><span class="sxs-lookup"><span data-stu-id="376aa-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="376aa-113">指定的 IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="376aa-113">Unique identifier for the specified IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="376aa-114"><strong>址</strong></span><span class="sxs-lookup"><span data-stu-id="376aa-114"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="376aa-115">varchar （50）</span><span class="sxs-lookup"><span data-stu-id="376aa-115">varchar(50)</span></span></p></td>
<td><p><span data-ttu-id="376aa-116">独特</span><span class="sxs-lookup"><span data-stu-id="376aa-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="376aa-p102">映射到 IpAddressKey 的唯一 IP 地址（例如，189.168.1.1）。这可能是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="376aa-p102">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

