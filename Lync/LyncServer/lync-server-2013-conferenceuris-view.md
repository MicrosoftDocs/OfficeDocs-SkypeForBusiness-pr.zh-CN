---
title: Lync Server 2013： ConferenceUris 视图
description: Lync Server 2013： ConferenceUris 视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris view
ms:assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688148(v=OCS.15)
ms:contentKeyID: 49733750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba643a1992462d501800b4b2fc36b93a2740e72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561188"
---
# <a name="conferenceuris-view-in-lync-server-2013"></a><span data-ttu-id="70ad0-103">Lync Server 2013 中的 ConferenceUris 视图</span><span class="sxs-lookup"><span data-stu-id="70ad0-103">ConferenceUris view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70ad0-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="70ad0-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="70ad0-105">ConfernceUris 视图存储有关已参与会议会话的 URI 的信息。</span><span class="sxs-lookup"><span data-stu-id="70ad0-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="70ad0-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="70ad0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70ad0-107">列</span><span class="sxs-lookup"><span data-stu-id="70ad0-107">Column</span></span></th>
<th><span data-ttu-id="70ad0-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="70ad0-108">Data Type</span></span></th>
<th><span data-ttu-id="70ad0-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="70ad0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70ad0-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="70ad0-110">ConferenceUriId</span></span></p></td>
<td><p><span data-ttu-id="70ad0-111">int</span><span class="sxs-lookup"><span data-stu-id="70ad0-111">int</span></span></p></td>
<td><p><span data-ttu-id="70ad0-112">标识此会议 URI 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="70ad0-112">Unique number identifying the conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ad0-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="70ad0-113">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="70ad0-114">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="70ad0-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="70ad0-115">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="70ad0-115">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ad0-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="70ad0-116">ConferenceUriType</span></span></p></td>
<td><p><span data-ttu-id="70ad0-117">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="70ad0-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="70ad0-118">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="70ad0-118">Type of conference URI.</span></span> <span data-ttu-id="70ad0-119">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="70ad0-119">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

