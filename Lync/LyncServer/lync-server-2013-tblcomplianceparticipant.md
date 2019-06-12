---
title: Lync Server 2013：tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="45c1c-102">Lync Server 2013 中的 tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="45c1c-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45c1c-103">_**主题上次修改时间:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="45c1c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="45c1c-104">tblComplianceParticipant 包含每个频道和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="45c1c-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="45c1c-105">多</span><span class="sxs-lookup"><span data-stu-id="45c1c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45c1c-106">列</span><span class="sxs-lookup"><span data-stu-id="45c1c-106">Column</span></span></th>
<th><span data-ttu-id="45c1c-107">类型</span><span class="sxs-lookup"><span data-stu-id="45c1c-107">Type</span></span></th>
<th><span data-ttu-id="45c1c-108">说明</span><span class="sxs-lookup"><span data-stu-id="45c1c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45c1c-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="45c1c-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="45c1c-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="45c1c-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="45c1c-111">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="45c1c-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45c1c-112">userId</span><span class="sxs-lookup"><span data-stu-id="45c1c-112">userId</span></span></p></td>
<td><p><span data-ttu-id="45c1c-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="45c1c-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="45c1c-114">参与者的主体 ID (对应于 tblPrincipal 表)。</span><span class="sxs-lookup"><span data-stu-id="45c1c-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45c1c-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="45c1c-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="45c1c-116">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="45c1c-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="45c1c-117">联接事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="45c1c-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45c1c-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="45c1c-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="45c1c-119">bigint</span><span class="sxs-lookup"><span data-stu-id="45c1c-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="45c1c-120">如果参与者仍处于加入, 则为 Null。</span><span class="sxs-lookup"><span data-stu-id="45c1c-120">Null if participant is still joined.</span></span> <span data-ttu-id="45c1c-121">如果 not null, 则通道的时间戳会留下事件。</span><span class="sxs-lookup"><span data-stu-id="45c1c-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="45c1c-122">这些条目最终会在所有翻译人员处理该事件时被删除。</span><span class="sxs-lookup"><span data-stu-id="45c1c-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45c1c-123">userUri</span><span class="sxs-lookup"><span data-stu-id="45c1c-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="45c1c-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="45c1c-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="45c1c-125">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="45c1c-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45c1c-126">serverID</span><span class="sxs-lookup"><span data-stu-id="45c1c-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="45c1c-127">int</span><span class="sxs-lookup"><span data-stu-id="45c1c-127">int</span></span></p></td>
<td><p><span data-ttu-id="45c1c-128">服务器标识 (如 tblServerIdentity 表中所示)。</span><span class="sxs-lookup"><span data-stu-id="45c1c-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45c1c-129">标识符</span><span class="sxs-lookup"><span data-stu-id="45c1c-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="45c1c-130">bigint</span><span class="sxs-lookup"><span data-stu-id="45c1c-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="45c1c-131">服务器会话。</span><span class="sxs-lookup"><span data-stu-id="45c1c-131">Server session.</span></span> <span data-ttu-id="45c1c-132">这是每次启动聊天服务时生成的随机数字。</span><span class="sxs-lookup"><span data-stu-id="45c1c-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="45c1c-133">它用于为识别孤立参与者的目的而区分会话。</span><span class="sxs-lookup"><span data-stu-id="45c1c-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="45c1c-134">关键字</span><span class="sxs-lookup"><span data-stu-id="45c1c-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45c1c-135">列</span><span class="sxs-lookup"><span data-stu-id="45c1c-135">Column</span></span></th>
<th><span data-ttu-id="45c1c-136">说明</span><span class="sxs-lookup"><span data-stu-id="45c1c-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45c1c-137">&lt;channelUri、userId、joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="45c1c-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="45c1c-138">主键。</span><span class="sxs-lookup"><span data-stu-id="45c1c-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

