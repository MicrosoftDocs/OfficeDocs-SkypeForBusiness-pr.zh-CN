---
title: Lync Server 2013： tblComplianceData
description: Lync Server 2013： tblComplianceData。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568098"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="38fde-103">Lync Server 2013 中的 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="38fde-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38fde-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="38fde-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="38fde-105">tblComplianceData 包含合规适配器尚未处理的合规事件。</span><span class="sxs-lookup"><span data-stu-id="38fde-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="38fde-106">列数</span><span class="sxs-lookup"><span data-stu-id="38fde-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38fde-107">列</span><span class="sxs-lookup"><span data-stu-id="38fde-107">Column</span></span></th>
<th><span data-ttu-id="38fde-108">类型</span><span class="sxs-lookup"><span data-stu-id="38fde-108">Type</span></span></th>
<th><span data-ttu-id="38fde-109">说明</span><span class="sxs-lookup"><span data-stu-id="38fde-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38fde-110">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="38fde-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="38fde-111">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="38fde-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="38fde-112">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="38fde-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38fde-113">entryDate</span><span class="sxs-lookup"><span data-stu-id="38fde-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="38fde-114">smalldatetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="38fde-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="38fde-115">插入时间（将来对于 cmplType=9，可能比较遥远，因为该条目在那种情况下只是一个占位符）。</span><span class="sxs-lookup"><span data-stu-id="38fde-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38fde-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="38fde-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="38fde-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="38fde-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="38fde-118">合规事件的类型：</span><span class="sxs-lookup"><span data-stu-id="38fde-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="38fde-119">1：聊天</span><span class="sxs-lookup"><span data-stu-id="38fde-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="38fde-120">2：聊天记录</span><span class="sxs-lookup"><span data-stu-id="38fde-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="38fde-121">3：文件下载</span><span class="sxs-lookup"><span data-stu-id="38fde-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="38fde-122">4：文件上载</span><span class="sxs-lookup"><span data-stu-id="38fde-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="38fde-123">9：临时文件传输</span><span class="sxs-lookup"><span data-stu-id="38fde-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="38fde-124">10：删除聊天（通过替换）</span><span class="sxs-lookup"><span data-stu-id="38fde-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="38fde-125">11：清除聊天</span><span class="sxs-lookup"><span data-stu-id="38fde-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38fde-126">cmplTime</span><span class="sxs-lookup"><span data-stu-id="38fde-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="38fde-127">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="38fde-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="38fde-128">事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="38fde-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38fde-129">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="38fde-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="38fde-130">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="38fde-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="38fde-131">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="38fde-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38fde-132">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="38fde-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="38fde-133">bigint</span><span class="sxs-lookup"><span data-stu-id="38fde-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="38fde-134">聊天 ID（与 tblChat.chatId 表对应）。</span><span class="sxs-lookup"><span data-stu-id="38fde-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38fde-135">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="38fde-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="38fde-136">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="38fde-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="38fde-137">发布人的主体 ID（与 tblPrincipal.prinID 表对应）。</span><span class="sxs-lookup"><span data-stu-id="38fde-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38fde-138">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="38fde-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="38fde-139">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="38fde-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="38fde-140">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="38fde-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38fde-141">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="38fde-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="38fde-142">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="38fde-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="38fde-143">消息（编码方式取决于 cmplType）。</span><span class="sxs-lookup"><span data-stu-id="38fde-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="38fde-144">键</span><span class="sxs-lookup"><span data-stu-id="38fde-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38fde-145">列</span><span class="sxs-lookup"><span data-stu-id="38fde-145">Column</span></span></th>
<th><span data-ttu-id="38fde-146">说明</span><span class="sxs-lookup"><span data-stu-id="38fde-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38fde-147">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="38fde-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="38fde-148">主键。</span><span class="sxs-lookup"><span data-stu-id="38fde-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

