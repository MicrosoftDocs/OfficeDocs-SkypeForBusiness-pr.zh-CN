---
title: Lync Server 2013： FileTransfers 表
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
ms.openlocfilehash: 33dbfdc6d7b0c8317b0f6ec56f837023398c0696
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="41d45-102">Lync Server 2013 中的 FileTransfers 表</span><span class="sxs-lookup"><span data-stu-id="41d45-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41d45-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="41d45-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="41d45-104">每条记录代表一个文件传输会话。</span><span class="sxs-lookup"><span data-stu-id="41d45-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41d45-105">列</span><span class="sxs-lookup"><span data-stu-id="41d45-105">Column</span></span></th>
<th><span data-ttu-id="41d45-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="41d45-106">Data Type</span></span></th>
<th><span data-ttu-id="41d45-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="41d45-107">Key/Index</span></span></th>
<th><span data-ttu-id="41d45-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="41d45-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41d45-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="41d45-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41d45-110">datetime</span><span class="sxs-lookup"><span data-stu-id="41d45-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="41d45-111">主、外</span><span class="sxs-lookup"><span data-stu-id="41d45-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41d45-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="41d45-112">Time of session request.</span></span> <span data-ttu-id="41d45-113">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="41d45-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="41d45-114">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="41d45-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d45-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="41d45-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="41d45-116">int</span><span class="sxs-lookup"><span data-stu-id="41d45-116">int</span></span></p></td>
<td><p><span data-ttu-id="41d45-117">主、外</span><span class="sxs-lookup"><span data-stu-id="41d45-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41d45-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="41d45-118">ID number to identify the session.</span></span> <span data-ttu-id="41d45-119">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="41d45-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="41d45-120">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="41d45-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d45-121"><strong>File Name</strong></span><span class="sxs-lookup"><span data-stu-id="41d45-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="41d45-122">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="41d45-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41d45-123">文件的名称。</span><span class="sxs-lookup"><span data-stu-id="41d45-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d45-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="41d45-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="41d45-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="41d45-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41d45-126">用于区分涉及同一文件名的各个文件传输的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="41d45-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d45-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="41d45-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="41d45-128">nvarchar</span><span class="sxs-lookup"><span data-stu-id="41d45-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="41d45-129">主</span><span class="sxs-lookup"><span data-stu-id="41d45-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="41d45-130">用于标识与此关联时的每条后续消息。</span><span class="sxs-lookup"><span data-stu-id="41d45-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d45-131"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="41d45-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="41d45-132">位</span><span class="sxs-lookup"><span data-stu-id="41d45-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41d45-p103">可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="41d45-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41d45-135"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="41d45-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="41d45-136">位</span><span class="sxs-lookup"><span data-stu-id="41d45-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41d45-p104">可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="41d45-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41d45-139"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="41d45-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="41d45-140">位</span><span class="sxs-lookup"><span data-stu-id="41d45-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41d45-p105">可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="41d45-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

