---
title: Lync Server 2013：电话表
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
ms.openlocfilehash: 0f7a03cdad1e3b080bb62db31ea1796e14cd2887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="6248e-102">Lync Server 2013 中的电话表</span><span class="sxs-lookup"><span data-stu-id="6248e-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6248e-103">_**上次修改的主题：** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="6248e-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="6248e-104">电话表是支持表格。</span><span class="sxs-lookup"><span data-stu-id="6248e-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="6248e-105">表中的每条记录存储在包含数据库中的记录的 VoIP 呼叫中涉及的一个电话号码的相关信息。</span><span class="sxs-lookup"><span data-stu-id="6248e-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6248e-106">列</span><span class="sxs-lookup"><span data-stu-id="6248e-106">Column</span></span></th>
<th><span data-ttu-id="6248e-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="6248e-107">Data Type</span></span></th>
<th><span data-ttu-id="6248e-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="6248e-108">Key/Index</span></span></th>
<th><span data-ttu-id="6248e-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="6248e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6248e-110"><strong>PhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="6248e-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="6248e-111">int</span><span class="sxs-lookup"><span data-stu-id="6248e-111">int</span></span></p></td>
<td><p><span data-ttu-id="6248e-112">主</span><span class="sxs-lookup"><span data-stu-id="6248e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6248e-113">标识此电话的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="6248e-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6248e-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="6248e-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6248e-115">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="6248e-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6248e-116">电话号码。</span><span class="sxs-lookup"><span data-stu-id="6248e-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6248e-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="6248e-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="6248e-118">dateTime</span><span class="sxs-lookup"><span data-stu-id="6248e-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6248e-119">时间戳（仅供内部使用）。</span><span class="sxs-lookup"><span data-stu-id="6248e-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="6248e-120">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="6248e-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

