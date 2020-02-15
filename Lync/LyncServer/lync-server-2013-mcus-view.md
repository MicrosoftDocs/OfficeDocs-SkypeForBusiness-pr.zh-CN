---
title: Lync Server 2013： Mcu 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus view
ms:assetid: 8e8bbb1b-993b-4b66-862b-7e7654777203
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688127(v=OCS.15)
ms:contentKeyID: 49733725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fe983f12dd01c9cb46b27fdb5dffc3cd41c6671
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-view-in-lync-server-2013"></a><span data-ttu-id="c3729-102">Lync Server 2013 中的 mcu 视图</span><span class="sxs-lookup"><span data-stu-id="c3729-102">Mcus view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3729-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c3729-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c3729-104">Mcus 视图存储有关已参与会议会话的 MCU 的信息。</span><span class="sxs-lookup"><span data-stu-id="c3729-104">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="c3729-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3729-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3729-106">列</span><span class="sxs-lookup"><span data-stu-id="c3729-106">Column</span></span></th>
<th><span data-ttu-id="c3729-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3729-107">Data Type</span></span></th>
<th><span data-ttu-id="c3729-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="c3729-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3729-109"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="c3729-109"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="c3729-110">int</span><span class="sxs-lookup"><span data-stu-id="c3729-110">int</span></span></p></td>
<td><p><span data-ttu-id="c3729-111">标识 MCU 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="c3729-111">Unique number identifying the MCU.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3729-112"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="c3729-112"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c3729-113">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="c3729-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c3729-114">MCU 的 URI。</span><span class="sxs-lookup"><span data-stu-id="c3729-114">URI of the MCU.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3729-115"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c3729-115"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c3729-116">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="c3729-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c3729-117">MCU URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="c3729-117">Type of MCU URI.</span></span> <span data-ttu-id="c3729-118">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c3729-118">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

