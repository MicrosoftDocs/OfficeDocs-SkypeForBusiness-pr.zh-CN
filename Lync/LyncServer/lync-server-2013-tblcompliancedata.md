---
title: Lync Server 2013：tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044a57645a8c49ea74ec4e003f9e12720d0b2268
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="a853d-102">Lync Server 2013 中的 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="a853d-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a853d-103">_**主题上次修改时间:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a853d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a853d-104">tblComplianceData 包含尚未由合规性适配器处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="a853d-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="a853d-105">多</span><span class="sxs-lookup"><span data-stu-id="a853d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a853d-106">列</span><span class="sxs-lookup"><span data-stu-id="a853d-106">Column</span></span></th>
<th><span data-ttu-id="a853d-107">类型</span><span class="sxs-lookup"><span data-stu-id="a853d-107">Type</span></span></th>
<th><span data-ttu-id="a853d-108">说明</span><span class="sxs-lookup"><span data-stu-id="a853d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a853d-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a853d-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="a853d-110">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="a853d-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a853d-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="a853d-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a853d-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="a853d-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="a853d-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="a853d-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="a853d-114">插入时间 (对于 cmplType = 9, 将来可能会是很远), 因为在该情况下, 条目只是占位符。</span><span class="sxs-lookup"><span data-stu-id="a853d-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a853d-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="a853d-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="a853d-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="a853d-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a853d-117">合规性事件的类型:</span><span class="sxs-lookup"><span data-stu-id="a853d-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="a853d-118">1: 聊天</span><span class="sxs-lookup"><span data-stu-id="a853d-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="a853d-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="a853d-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="a853d-120">3: 文件下载</span><span class="sxs-lookup"><span data-stu-id="a853d-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="a853d-121">4: 文件上载</span><span class="sxs-lookup"><span data-stu-id="a853d-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="a853d-122">9: 临时文件传输</span><span class="sxs-lookup"><span data-stu-id="a853d-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="a853d-123">10: 删除聊天 (带替换)</span><span class="sxs-lookup"><span data-stu-id="a853d-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="a853d-124">11: 聊天清除</span><span class="sxs-lookup"><span data-stu-id="a853d-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a853d-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="a853d-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="a853d-126">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="a853d-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a853d-127">事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="a853d-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a853d-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="a853d-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="a853d-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="a853d-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="a853d-130">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="a853d-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a853d-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="a853d-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="a853d-132">bigint</span><span class="sxs-lookup"><span data-stu-id="a853d-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="a853d-133">聊天 ID (对应于 tblChat 表)。</span><span class="sxs-lookup"><span data-stu-id="a853d-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a853d-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="a853d-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="a853d-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="a853d-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a853d-136">海报的主体 ID (对应于 tblPrincipal 表)。</span><span class="sxs-lookup"><span data-stu-id="a853d-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a853d-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="a853d-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="a853d-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="a853d-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="a853d-139">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="a853d-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a853d-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="a853d-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="a853d-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a853d-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="a853d-142">邮件 (编码取决于 cmplType)。</span><span class="sxs-lookup"><span data-stu-id="a853d-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a853d-143">关键字</span><span class="sxs-lookup"><span data-stu-id="a853d-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a853d-144">列</span><span class="sxs-lookup"><span data-stu-id="a853d-144">Column</span></span></th>
<th><span data-ttu-id="a853d-145">说明</span><span class="sxs-lookup"><span data-stu-id="a853d-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a853d-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a853d-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="a853d-147">主键。</span><span class="sxs-lookup"><span data-stu-id="a853d-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

