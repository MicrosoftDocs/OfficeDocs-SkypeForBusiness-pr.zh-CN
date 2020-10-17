---
title: Lync Server 2013： tblConfig
description: Lync Server 2013： tblConfig。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8990e0b2c8724a5e90c36e706b92f9985f288772
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550428"
---
# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="b9eae-103">Lync Server 2013 中的 tblConfig</span><span class="sxs-lookup"><span data-stu-id="b9eae-103">tblConfig in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9eae-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b9eae-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b9eae-105">tblConfig 在一行中包含一些持久聊天服务器不支持的配置。</span><span class="sxs-lookup"><span data-stu-id="b9eae-105">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="b9eae-106">列数</span><span class="sxs-lookup"><span data-stu-id="b9eae-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9eae-107">列</span><span class="sxs-lookup"><span data-stu-id="b9eae-107">Column</span></span></th>
<th><span data-ttu-id="b9eae-108">类型</span><span class="sxs-lookup"><span data-stu-id="b9eae-108">Type</span></span></th>
<th><span data-ttu-id="b9eae-109">说明</span><span class="sxs-lookup"><span data-stu-id="b9eae-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9eae-110">configLabel</span><span class="sxs-lookup"><span data-stu-id="b9eae-110">configLabel</span></span></p></td>
<td><p><span data-ttu-id="b9eae-111">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="b9eae-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="b9eae-112">包含 &quot; 池。&quot;</span><span class="sxs-lookup"><span data-stu-id="b9eae-112">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9eae-113">configContent</span><span class="sxs-lookup"><span data-stu-id="b9eae-113">configContent</span></span></p></td>
<td><p><span data-ttu-id="b9eae-114">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="b9eae-114">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="b9eae-115">配置内容。</span><span class="sxs-lookup"><span data-stu-id="b9eae-115">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9eae-116">configPoolID</span><span class="sxs-lookup"><span data-stu-id="b9eae-116">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="b9eae-117">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="b9eae-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="b9eae-118">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="b9eae-118">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b9eae-119">键</span><span class="sxs-lookup"><span data-stu-id="b9eae-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9eae-120">列</span><span class="sxs-lookup"><span data-stu-id="b9eae-120">Column</span></span></th>
<th><span data-ttu-id="b9eae-121">说明</span><span class="sxs-lookup"><span data-stu-id="b9eae-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9eae-122">configLabel</span><span class="sxs-lookup"><span data-stu-id="b9eae-122">configLabel</span></span></p></td>
<td><p><span data-ttu-id="b9eae-123">主键。</span><span class="sxs-lookup"><span data-stu-id="b9eae-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

