---
title: Lync Server 2013：Phones 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cddf5eac7cc85852f4a7f61f4b746091158257e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="4c23d-102">Lync Server 2013 中的 Phones 表</span><span class="sxs-lookup"><span data-stu-id="4c23d-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c23d-103">_**主题上次修改时间：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="4c23d-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="4c23d-104">"电话" 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="4c23d-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="4c23d-105">表中的每条记录存储了在具有数据库中的记录的 VoIP 呼叫中涉及的一个电话号码的相关信息。</span><span class="sxs-lookup"><span data-stu-id="4c23d-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c23d-106">列</span><span class="sxs-lookup"><span data-stu-id="4c23d-106">Column</span></span></th>
<th><span data-ttu-id="4c23d-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="4c23d-107">Data Type</span></span></th>
<th><span data-ttu-id="4c23d-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="4c23d-108">Key/Index</span></span></th>
<th><span data-ttu-id="4c23d-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="4c23d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c23d-110"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="4c23d-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="4c23d-111">int</span><span class="sxs-lookup"><span data-stu-id="4c23d-111">int</span></span></p></td>
<td><p><span data-ttu-id="4c23d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="4c23d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4c23d-113">标识此电话的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="4c23d-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c23d-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="4c23d-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4c23d-115">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="4c23d-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4c23d-116">电话号码。</span><span class="sxs-lookup"><span data-stu-id="4c23d-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c23d-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="4c23d-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="4c23d-118">从中</span><span class="sxs-lookup"><span data-stu-id="4c23d-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4c23d-119">时间戳（仅供内部使用）。</span><span class="sxs-lookup"><span data-stu-id="4c23d-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="4c23d-120">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4c23d-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

