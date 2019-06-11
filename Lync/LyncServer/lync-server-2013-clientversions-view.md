---
title: 'Lync Server 2013: ClientVersions 视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d219b8666afc0684b0d61f02f06618ea6ef60f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="5c5df-102">Lync Server 2013 中的 ClientVersions 视图</span><span class="sxs-lookup"><span data-stu-id="5c5df-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c5df-103">_**主题上次修改时间:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5c5df-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5c5df-104">ClientVersions 视图存储参与数据库中记录的会话的各种客户端类型和版本的相关信息。</span><span class="sxs-lookup"><span data-stu-id="5c5df-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="5c5df-105">视图中的每条记录表示一个客户端版本。</span><span class="sxs-lookup"><span data-stu-id="5c5df-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="5c5df-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="5c5df-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5c5df-107">某些列可能有多条记录。</span><span class="sxs-lookup"><span data-stu-id="5c5df-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c5df-108">列</span><span class="sxs-lookup"><span data-stu-id="5c5df-108">Column</span></span></th>
<th><span data-ttu-id="5c5df-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="5c5df-109">Data Type</span></span></th>
<th><span data-ttu-id="5c5df-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="5c5df-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c5df-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="5c5df-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5df-112">int</span><span class="sxs-lookup"><span data-stu-id="5c5df-112">int</span></span></p></td>
<td><p><span data-ttu-id="5c5df-113">标识此客户端类型和版本的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="5c5df-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c5df-114"><strong>版本</strong></span><span class="sxs-lookup"><span data-stu-id="5c5df-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5df-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5c5df-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c5df-116">表示用户代理。</span><span class="sxs-lookup"><span data-stu-id="5c5df-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c5df-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5c5df-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5df-118">int</span><span class="sxs-lookup"><span data-stu-id="5c5df-118">int</span></span></p></td>
<td><p><span data-ttu-id="5c5df-119">客户端的类型。</span><span class="sxs-lookup"><span data-stu-id="5c5df-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c5df-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5c5df-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5c5df-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5c5df-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5c5df-122">客户端所属的类别。</span><span class="sxs-lookup"><span data-stu-id="5c5df-122">Category that the client belongs to.</span></span> <span data-ttu-id="5c5df-123">例如, 客户端 Conferencing_Attendant_ 1.0 属于 ClientCategory CAA。</span><span class="sxs-lookup"><span data-stu-id="5c5df-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

