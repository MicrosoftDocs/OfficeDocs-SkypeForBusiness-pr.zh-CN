---
title: Lync Server 2013： tblConfig
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
ms.openlocfilehash: 85d0c571ba4e206dc825784c2aaea1c6ceddbf89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="c3932-102">Lync Server 2013 中的 tblConfig</span><span class="sxs-lookup"><span data-stu-id="c3932-102">tblConfig in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3932-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c3932-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c3932-104">tblConfig 在一行中包含一些持久聊天服务器不支持的配置。</span><span class="sxs-lookup"><span data-stu-id="c3932-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="c3932-105">Columns</span><span class="sxs-lookup"><span data-stu-id="c3932-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3932-106">列</span><span class="sxs-lookup"><span data-stu-id="c3932-106">Column</span></span></th>
<th><span data-ttu-id="c3932-107">类型</span><span class="sxs-lookup"><span data-stu-id="c3932-107">Type</span></span></th>
<th><span data-ttu-id="c3932-108">说明</span><span class="sxs-lookup"><span data-stu-id="c3932-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3932-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="c3932-109">configLabel</span></span></p></td>
<td><p><span data-ttu-id="c3932-110">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="c3932-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="c3932-111">包含&quot;池。&quot;</span><span class="sxs-lookup"><span data-stu-id="c3932-111">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3932-112">configContent</span><span class="sxs-lookup"><span data-stu-id="c3932-112">configContent</span></span></p></td>
<td><p><span data-ttu-id="c3932-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="c3932-113">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="c3932-114">配置内容。</span><span class="sxs-lookup"><span data-stu-id="c3932-114">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3932-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="c3932-115">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="c3932-116">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="c3932-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="c3932-117">数据库实例的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c3932-117">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c3932-118">键</span><span class="sxs-lookup"><span data-stu-id="c3932-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3932-119">列</span><span class="sxs-lookup"><span data-stu-id="c3932-119">Column</span></span></th>
<th><span data-ttu-id="c3932-120">说明</span><span class="sxs-lookup"><span data-stu-id="c3932-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3932-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="c3932-121">configLabel</span></span></p></td>
<td><p><span data-ttu-id="c3932-122">主键。</span><span class="sxs-lookup"><span data-stu-id="c3932-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

