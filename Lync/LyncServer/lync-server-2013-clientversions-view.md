---
title: Lync Server 2013： ClientVersions 视图
description: Lync Server 2013： ClientVersions 视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42ede7107a59db3162ac7f5344e47e81a80d57df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542798"
---
# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="9dc06-103">Lync Server 2013 中的 ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="9dc06-103">ClientVersions view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dc06-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9dc06-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9dc06-105">ClientVersions 视图存储已参与数据库中记录的会话的各种客户端类型和版本的相关信息。</span><span class="sxs-lookup"><span data-stu-id="9dc06-105">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="9dc06-106">视图中的每条记录都代表一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="9dc06-106">Each record in the view represents one client version.</span></span> <span data-ttu-id="9dc06-107">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9dc06-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9dc06-108">某些列可能有多条记录。</span><span class="sxs-lookup"><span data-stu-id="9dc06-108">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dc06-109">列</span><span class="sxs-lookup"><span data-stu-id="9dc06-109">Column</span></span></th>
<th><span data-ttu-id="9dc06-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="9dc06-110">Data Type</span></span></th>
<th><span data-ttu-id="9dc06-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="9dc06-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dc06-112"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="9dc06-112"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="9dc06-113">int</span><span class="sxs-lookup"><span data-stu-id="9dc06-113">int</span></span></p></td>
<td><p><span data-ttu-id="9dc06-114">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="9dc06-114">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dc06-115"><strong>版本</strong></span><span class="sxs-lookup"><span data-stu-id="9dc06-115"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="9dc06-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="9dc06-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9dc06-117">代表用户代理。</span><span class="sxs-lookup"><span data-stu-id="9dc06-117">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dc06-118"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9dc06-118"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9dc06-119">int</span><span class="sxs-lookup"><span data-stu-id="9dc06-119">int</span></span></p></td>
<td><p><span data-ttu-id="9dc06-120">客户端类型。</span><span class="sxs-lookup"><span data-stu-id="9dc06-120">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dc06-121"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9dc06-121"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9dc06-122">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="9dc06-122">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9dc06-p102">客户端所属的类别。例如，客户端 Conferencing_Attendant_1.0 属于 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="9dc06-p102">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

