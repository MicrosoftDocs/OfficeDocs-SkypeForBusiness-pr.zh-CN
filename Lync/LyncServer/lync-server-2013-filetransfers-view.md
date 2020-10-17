---
title: Lync Server 2013： FileTransfers 视图
description: Lync Server 2013： FileTransfers 视图。
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
ms.openlocfilehash: dd2b084274a4d5daa093f2269617214f703ac03e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552618"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="d4e15-103">Lync Server 2013 中的 FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="d4e15-103">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4e15-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d4e15-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d4e15-105">FileTransfer 视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="d4e15-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="d4e15-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d4e15-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4e15-107">FileTransfers 视图包含在 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 的 SessionDetails 视图</A> 中的所有列，此外还列出了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="d4e15-107">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4e15-108">列</span><span class="sxs-lookup"><span data-stu-id="d4e15-108">Column</span></span></th>
<th><span data-ttu-id="d4e15-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="d4e15-109">Data Type</span></span></th>
<th><span data-ttu-id="d4e15-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="d4e15-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4e15-111"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="d4e15-111"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="d4e15-112">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d4e15-112">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4e15-113">文件传输的名称。</span><span class="sxs-lookup"><span data-stu-id="d4e15-113">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4e15-114"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="d4e15-114"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="d4e15-115">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="d4e15-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d4e15-116">用于标识与此关联时的每条后续消息。</span><span class="sxs-lookup"><span data-stu-id="d4e15-116">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4e15-117"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="d4e15-117"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="d4e15-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d4e15-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d4e15-119">涉及相同文件名的文件传输之间标识的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d4e15-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4e15-120"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="d4e15-120"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="d4e15-121">位</span><span class="sxs-lookup"><span data-stu-id="d4e15-121">bit</span></span></p></td>
<td><p><span data-ttu-id="d4e15-p102">可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d4e15-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4e15-124"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="d4e15-124"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="d4e15-125">位</span><span class="sxs-lookup"><span data-stu-id="d4e15-125">bit</span></span></p></td>
<td><p><span data-ttu-id="d4e15-p103">可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d4e15-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4e15-128"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="d4e15-128"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="d4e15-129">位</span><span class="sxs-lookup"><span data-stu-id="d4e15-129">bit</span></span></p></td>
<td><p><span data-ttu-id="d4e15-p104">可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="d4e15-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

