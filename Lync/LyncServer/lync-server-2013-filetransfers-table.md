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
ms.openlocfilehash: cacd637caec827a87008c3a6554750b7e5b61719
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500919"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="ebd4a-102">Lync Server 2013 中的 FileTransfers 表</span><span class="sxs-lookup"><span data-stu-id="ebd4a-102">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebd4a-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ebd4a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ebd4a-104">每条记录代表一个文件传输会话。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebd4a-105">列</span><span class="sxs-lookup"><span data-stu-id="ebd4a-105">Column</span></span></th>
<th><span data-ttu-id="ebd4a-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="ebd4a-106">Data Type</span></span></th>
<th><span data-ttu-id="ebd4a-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="ebd4a-107">Key/Index</span></span></th>
<th><span data-ttu-id="ebd4a-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="ebd4a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebd4a-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ebd4a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ebd4a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ebd4a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ebd4a-111">主、外</span><span class="sxs-lookup"><span data-stu-id="ebd4a-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebd4a-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-112">Time of session request.</span></span> <span data-ttu-id="ebd4a-113">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ebd4a-114">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebd4a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ebd4a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ebd4a-116">int</span><span class="sxs-lookup"><span data-stu-id="ebd4a-116">int</span></span></p></td>
<td><p><span data-ttu-id="ebd4a-117">主、外</span><span class="sxs-lookup"><span data-stu-id="ebd4a-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebd4a-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-118">ID number to identify the session.</span></span> <span data-ttu-id="ebd4a-119">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ebd4a-120">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebd4a-121"><strong>File Name</strong></span><span class="sxs-lookup"><span data-stu-id="ebd4a-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ebd4a-122">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ebd4a-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ebd4a-123">文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebd4a-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="ebd4a-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="ebd4a-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ebd4a-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ebd4a-126">用于区分涉及同一文件名的各个文件传输的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebd4a-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="ebd4a-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="ebd4a-128">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="ebd4a-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ebd4a-129">主</span><span class="sxs-lookup"><span data-stu-id="ebd4a-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="ebd4a-130">用于标识与此关联时的每条后续消息。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebd4a-131"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="ebd4a-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="ebd4a-132">位</span><span class="sxs-lookup"><span data-stu-id="ebd4a-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ebd4a-p103">可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebd4a-135"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="ebd4a-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="ebd4a-136">位</span><span class="sxs-lookup"><span data-stu-id="ebd4a-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ebd4a-p104">可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebd4a-139"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="ebd4a-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="ebd4a-140">位</span><span class="sxs-lookup"><span data-stu-id="ebd4a-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ebd4a-p105">可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ebd4a-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

