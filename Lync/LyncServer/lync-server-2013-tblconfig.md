---
title: Lync Server 2013：tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745b8a1894ebca821474afdb82284fcf6bb09eb9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="5333e-102">Lync Server 2013 中的 tblConfig</span><span class="sxs-lookup"><span data-stu-id="5333e-102">tblConfig in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5333e-103">_**主题上次修改时间:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5333e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5333e-104">tblConfig 包含一些持久聊天服务器不支持的配置, 其中一行。</span><span class="sxs-lookup"><span data-stu-id="5333e-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="5333e-105">多</span><span class="sxs-lookup"><span data-stu-id="5333e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5333e-106">列</span><span class="sxs-lookup"><span data-stu-id="5333e-106">Column</span></span></th>
<th><span data-ttu-id="5333e-107">类型</span><span class="sxs-lookup"><span data-stu-id="5333e-107">Type</span></span></th>
<th><span data-ttu-id="5333e-108">说明</span><span class="sxs-lookup"><span data-stu-id="5333e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5333e-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="5333e-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="5333e-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="5333e-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5333e-111">包含&quot;池。&quot;</span><span class="sxs-lookup"><span data-stu-id="5333e-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5333e-112">configContent</span><span class="sxs-lookup"><span data-stu-id="5333e-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="5333e-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5333e-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="5333e-114">配置内容。</span><span class="sxs-lookup"><span data-stu-id="5333e-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5333e-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="5333e-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="5333e-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="5333e-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5333e-117">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="5333e-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5333e-118">关键字</span><span class="sxs-lookup"><span data-stu-id="5333e-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5333e-119">列</span><span class="sxs-lookup"><span data-stu-id="5333e-119">Column</span></span></th>
<th><span data-ttu-id="5333e-120">说明</span><span class="sxs-lookup"><span data-stu-id="5333e-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5333e-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="5333e-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="5333e-122">主键。</span><span class="sxs-lookup"><span data-stu-id="5333e-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

