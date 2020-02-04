---
title: Lync Server 2013： ClientVersions 视图
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
ms.openlocfilehash: 8fd25da49e8a3b6ad7838ff27a4472e711b97421
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="b63ac-102">Lync Server 2013 中的 ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="b63ac-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b63ac-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b63ac-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b63ac-104">ClientVersions 视图存储参与数据库中记录的会话的各种客户端类型和版本的相关信息。</span><span class="sxs-lookup"><span data-stu-id="b63ac-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="b63ac-105">视图中的每条记录表示一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="b63ac-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="b63ac-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="b63ac-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b63ac-107">某些列可能有多条记录。</span><span class="sxs-lookup"><span data-stu-id="b63ac-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b63ac-108">列</span><span class="sxs-lookup"><span data-stu-id="b63ac-108">Column</span></span></th>
<th><span data-ttu-id="b63ac-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="b63ac-109">Data Type</span></span></th>
<th><span data-ttu-id="b63ac-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="b63ac-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b63ac-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="b63ac-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="b63ac-112">int</span><span class="sxs-lookup"><span data-stu-id="b63ac-112">int</span></span></p></td>
<td><p><span data-ttu-id="b63ac-113">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="b63ac-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b63ac-114"><strong>版本</strong></span><span class="sxs-lookup"><span data-stu-id="b63ac-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="b63ac-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b63ac-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b63ac-116">表示用户代理。</span><span class="sxs-lookup"><span data-stu-id="b63ac-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b63ac-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b63ac-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b63ac-118">int</span><span class="sxs-lookup"><span data-stu-id="b63ac-118">int</span></span></p></td>
<td><p><span data-ttu-id="b63ac-119">客户端的类型。</span><span class="sxs-lookup"><span data-stu-id="b63ac-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b63ac-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b63ac-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b63ac-121">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="b63ac-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b63ac-122">客户端所属的类别。</span><span class="sxs-lookup"><span data-stu-id="b63ac-122">Category that the client belongs to.</span></span> <span data-ttu-id="b63ac-123">例如，客户端 Conferencing_Attendant_1 .0 属于 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="b63ac-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

