---
title: Lync Server 2013：EndpointSubnet 表
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
ms.openlocfilehash: 055aa9460fb63e96d20472d6102c249ecf71a78b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpointsubnet-table-in-lync-server-2013"></a><span data-ttu-id="adc0d-102">Lync Server 2013 中的 EndpointSubnet 表</span><span class="sxs-lookup"><span data-stu-id="adc0d-102">EndpointSubnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adc0d-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="adc0d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="adc0d-104">EndpointSubnet 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="adc0d-104">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="adc0d-105">每条记录表示一个从终结点捕获的子网。</span><span class="sxs-lookup"><span data-stu-id="adc0d-105">Each record represents one subnet captured from endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="adc0d-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="adc0d-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="adc0d-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="adc0d-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="adc0d-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="adc0d-111">int</span><span class="sxs-lookup"><span data-stu-id="adc0d-111">int</span></span></p></td>
<td><p><span data-ttu-id="adc0d-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="adc0d-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="adc0d-113">子网的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="adc0d-113">Integer representation for the subnet.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="adc0d-114"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="adc0d-114"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="adc0d-115">datetime</span><span class="sxs-lookup"><span data-stu-id="adc0d-115">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="adc0d-116">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="adc0d-116">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

