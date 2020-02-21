---
title: Lync Server 2013： tblComplianceData
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
ms.openlocfilehash: f159a71469335cfb2af1401e8693802b3c8d1870
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="47b5b-102">Lync Server 2013 中的 tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="47b5b-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47b5b-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="47b5b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="47b5b-104">tblComplianceData 包含合规适配器尚未处理的合规事件。</span><span class="sxs-lookup"><span data-stu-id="47b5b-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="47b5b-105">Columns</span><span class="sxs-lookup"><span data-stu-id="47b5b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47b5b-106">列</span><span class="sxs-lookup"><span data-stu-id="47b5b-106">Column</span></span></th>
<th><span data-ttu-id="47b5b-107">类型</span><span class="sxs-lookup"><span data-stu-id="47b5b-107">Type</span></span></th>
<th><span data-ttu-id="47b5b-108">说明</span><span class="sxs-lookup"><span data-stu-id="47b5b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47b5b-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="47b5b-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="47b5b-110">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="47b5b-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="47b5b-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="47b5b-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b5b-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="47b5b-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="47b5b-113">smalldatetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="47b5b-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="47b5b-114">插入时间（将来对于 cmplType=9，可能比较遥远，因为该条目在那种情况下只是一个占位符）。</span><span class="sxs-lookup"><span data-stu-id="47b5b-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b5b-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="47b5b-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="47b5b-116">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="47b5b-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="47b5b-117">合规事件的类型：</span><span class="sxs-lookup"><span data-stu-id="47b5b-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="47b5b-118">1：聊天</span><span class="sxs-lookup"><span data-stu-id="47b5b-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="47b5b-119">2：聊天记录</span><span class="sxs-lookup"><span data-stu-id="47b5b-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="47b5b-120">3：文件下载</span><span class="sxs-lookup"><span data-stu-id="47b5b-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="47b5b-121">4：文件上载</span><span class="sxs-lookup"><span data-stu-id="47b5b-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="47b5b-122">9：临时文件传输</span><span class="sxs-lookup"><span data-stu-id="47b5b-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="47b5b-123">10：删除聊天（通过替换）</span><span class="sxs-lookup"><span data-stu-id="47b5b-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="47b5b-124">11：清除聊天</span><span class="sxs-lookup"><span data-stu-id="47b5b-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b5b-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="47b5b-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="47b5b-126">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="47b5b-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="47b5b-127">事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="47b5b-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b5b-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="47b5b-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="47b5b-129">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="47b5b-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="47b5b-130">通道统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="47b5b-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b5b-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="47b5b-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="47b5b-132">bigint</span><span class="sxs-lookup"><span data-stu-id="47b5b-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="47b5b-133">聊天 ID（与 tblChat.chatId 表对应）。</span><span class="sxs-lookup"><span data-stu-id="47b5b-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b5b-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="47b5b-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="47b5b-135">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="47b5b-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="47b5b-136">发布人的主体 ID（与 tblPrincipal.prinID 表对应）。</span><span class="sxs-lookup"><span data-stu-id="47b5b-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b5b-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="47b5b-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="47b5b-138">nvarchar (255)，不为 null</span><span class="sxs-lookup"><span data-stu-id="47b5b-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="47b5b-139">用户 URI。</span><span class="sxs-lookup"><span data-stu-id="47b5b-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b5b-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="47b5b-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="47b5b-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="47b5b-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="47b5b-142">消息（编码方式取决于 cmplType）。</span><span class="sxs-lookup"><span data-stu-id="47b5b-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="47b5b-143">键</span><span class="sxs-lookup"><span data-stu-id="47b5b-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47b5b-144">列</span><span class="sxs-lookup"><span data-stu-id="47b5b-144">Column</span></span></th>
<th><span data-ttu-id="47b5b-145">说明</span><span class="sxs-lookup"><span data-stu-id="47b5b-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47b5b-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="47b5b-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="47b5b-147">主键。</span><span class="sxs-lookup"><span data-stu-id="47b5b-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

