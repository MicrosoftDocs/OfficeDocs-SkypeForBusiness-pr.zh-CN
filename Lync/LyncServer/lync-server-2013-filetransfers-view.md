---
title: Lync Server 2013： FileTransfers 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="2f6eb-102">Lync Server 2013 中的 FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="2f6eb-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f6eb-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2f6eb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2f6eb-104">FileTransfer 视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="2f6eb-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f6eb-106">FileTransfers 视图包含<A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 的 SessionDetails 视图</A>中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f6eb-107">列</span><span class="sxs-lookup"><span data-stu-id="2f6eb-107">Column</span></span></th>
<th><span data-ttu-id="2f6eb-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="2f6eb-108">Data Type</span></span></th>
<th><span data-ttu-id="2f6eb-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="2f6eb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f6eb-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="2f6eb-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="2f6eb-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2f6eb-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f6eb-112">已传输的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f6eb-113"><strong>票证</strong></span><span class="sxs-lookup"><span data-stu-id="2f6eb-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="2f6eb-114">nvarchar</span><span class="sxs-lookup"><span data-stu-id="2f6eb-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="2f6eb-115">用于标识要与此邮件关联的每个后续消息。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f6eb-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="2f6eb-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="2f6eb-117">标识符</span><span class="sxs-lookup"><span data-stu-id="2f6eb-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2f6eb-118">唯一标识符，用于区分涉及相同文件名的文件传输。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f6eb-119"><strong>容纳</strong></span><span class="sxs-lookup"><span data-stu-id="2f6eb-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="2f6eb-120">bit</span><span class="sxs-lookup"><span data-stu-id="2f6eb-120">bit</span></span></p></td>
<td><p><span data-ttu-id="2f6eb-121">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="2f6eb-122">如果为 TRUE，则 "拒绝" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f6eb-123"><strong>&</strong></span><span class="sxs-lookup"><span data-stu-id="2f6eb-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="2f6eb-124">bit</span><span class="sxs-lookup"><span data-stu-id="2f6eb-124">bit</span></span></p></td>
<td><p><span data-ttu-id="2f6eb-125">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="2f6eb-126">如果为 TRUE，则 "接受" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f6eb-127"><strong>取消</strong></span><span class="sxs-lookup"><span data-stu-id="2f6eb-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="2f6eb-128">bit</span><span class="sxs-lookup"><span data-stu-id="2f6eb-128">bit</span></span></p></td>
<td><p><span data-ttu-id="2f6eb-129">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="2f6eb-130">如果为 TRUE，则 "接受" 和 "拒绝" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2f6eb-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

