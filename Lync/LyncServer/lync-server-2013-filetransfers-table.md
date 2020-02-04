---
title: Lync Server 2013：FileTransfers 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="2ba80-102">Lync Server 2013 中的 FileTransfers 表</span><span class="sxs-lookup"><span data-stu-id="2ba80-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ba80-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2ba80-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2ba80-104">每条记录表示一个文件传输会话。</span><span class="sxs-lookup"><span data-stu-id="2ba80-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ba80-105">列</span><span class="sxs-lookup"><span data-stu-id="2ba80-105">Column</span></span></th>
<th><span data-ttu-id="2ba80-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="2ba80-106">Data Type</span></span></th>
<th><span data-ttu-id="2ba80-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="2ba80-107">Key/Index</span></span></th>
<th><span data-ttu-id="2ba80-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="2ba80-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ba80-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2ba80-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2ba80-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2ba80-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2ba80-111">主、外部</span><span class="sxs-lookup"><span data-stu-id="2ba80-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2ba80-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="2ba80-112">Time of session request.</span></span> <span data-ttu-id="2ba80-113">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="2ba80-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2ba80-114">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ba80-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ba80-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2ba80-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2ba80-116">int</span><span class="sxs-lookup"><span data-stu-id="2ba80-116">int</span></span></p></td>
<td><p><span data-ttu-id="2ba80-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="2ba80-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2ba80-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="2ba80-118">ID number to identify the session.</span></span> <span data-ttu-id="2ba80-119">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="2ba80-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2ba80-120">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ba80-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ba80-121"><strong>文件名</strong></span><span class="sxs-lookup"><span data-stu-id="2ba80-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="2ba80-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ba80-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ba80-123">文件的名称。</span><span class="sxs-lookup"><span data-stu-id="2ba80-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ba80-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="2ba80-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="2ba80-125">标识符</span><span class="sxs-lookup"><span data-stu-id="2ba80-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ba80-126">唯一标识符，用于区分涉及相同文件名的文件传输。</span><span class="sxs-lookup"><span data-stu-id="2ba80-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ba80-127"><strong>票证</strong></span><span class="sxs-lookup"><span data-stu-id="2ba80-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="2ba80-128">nvarchar</span><span class="sxs-lookup"><span data-stu-id="2ba80-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="2ba80-129">Primary</span><span class="sxs-lookup"><span data-stu-id="2ba80-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="2ba80-130">用于标识要与此邮件关联的每个后续消息。</span><span class="sxs-lookup"><span data-stu-id="2ba80-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ba80-131"><strong>容纳</strong></span><span class="sxs-lookup"><span data-stu-id="2ba80-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="2ba80-132">bit</span><span class="sxs-lookup"><span data-stu-id="2ba80-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ba80-133">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="2ba80-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="2ba80-134">如果为 TRUE，则 "拒绝" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2ba80-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ba80-135"><strong>&</strong></span><span class="sxs-lookup"><span data-stu-id="2ba80-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="2ba80-136">bit</span><span class="sxs-lookup"><span data-stu-id="2ba80-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ba80-137">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="2ba80-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="2ba80-138">如果为 TRUE，则 "接受" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2ba80-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ba80-139"><strong>取消</strong></span><span class="sxs-lookup"><span data-stu-id="2ba80-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="2ba80-140">bit</span><span class="sxs-lookup"><span data-stu-id="2ba80-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ba80-141">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="2ba80-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="2ba80-142">如果为 TRUE，则 "接受" 和 "拒绝" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2ba80-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

