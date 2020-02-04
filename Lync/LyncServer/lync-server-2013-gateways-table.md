---
title: Lync Server 2013：Gateways 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Gateways table
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48185034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5ee7296b93b3a9e1d7900b3ddde5c1b850c3580
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="gateways-table-in-lync-server-2013"></a><span data-ttu-id="2b317-102">Lync Server 2013 中的 Gateways 表</span><span class="sxs-lookup"><span data-stu-id="2b317-102">Gateways table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b317-103">_**主题上次修改时间：** 2010-11-05_</span><span class="sxs-lookup"><span data-stu-id="2b317-103">_**Topic Last Modified:** 2010-11-05_</span></span>

<span data-ttu-id="2b317-104">网关表是支持表。</span><span class="sxs-lookup"><span data-stu-id="2b317-104">The Gateways table is a supporting table.</span></span> <span data-ttu-id="2b317-105">每条记录存储有关一个网关的信息，这些信息涉及到数据库中有记录的公共交换电话网络（PSTN）呼叫。</span><span class="sxs-lookup"><span data-stu-id="2b317-105">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b317-106">列</span><span class="sxs-lookup"><span data-stu-id="2b317-106">Column</span></span></th>
<th><span data-ttu-id="2b317-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="2b317-107">Data Type</span></span></th>
<th><span data-ttu-id="2b317-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="2b317-108">Key/Index</span></span></th>
<th><span data-ttu-id="2b317-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="2b317-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b317-110"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="2b317-110"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b317-111">int</span><span class="sxs-lookup"><span data-stu-id="2b317-111">int</span></span></p></td>
<td><p><span data-ttu-id="2b317-112">Primary</span><span class="sxs-lookup"><span data-stu-id="2b317-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="2b317-113">标识此网关的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="2b317-113">Unique number identifying this gateway.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b317-114"><strong>网关</strong></span><span class="sxs-lookup"><span data-stu-id="2b317-114"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2b317-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b317-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2b317-116">网关名称。</span><span class="sxs-lookup"><span data-stu-id="2b317-116">Gateway name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

