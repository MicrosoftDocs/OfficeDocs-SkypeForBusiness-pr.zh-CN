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
ms.openlocfilehash: 95cc6790766d68ee478cf1b80326c974f7c15f1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="7391c-102">Lync Server 2013 中的 FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="7391c-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7391c-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7391c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7391c-104">FileTransfer 视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="7391c-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="7391c-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7391c-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7391c-106">FileTransfers 视图包含在<A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 的 SessionDetails 视图</A>中的所有列，此外还列出了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="7391c-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7391c-107">列</span><span class="sxs-lookup"><span data-stu-id="7391c-107">Column</span></span></th>
<th><span data-ttu-id="7391c-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="7391c-108">Data Type</span></span></th>
<th><span data-ttu-id="7391c-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="7391c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7391c-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="7391c-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="7391c-111">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="7391c-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7391c-112">文件传输的名称。</span><span class="sxs-lookup"><span data-stu-id="7391c-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7391c-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="7391c-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="7391c-114">nvarchar</span><span class="sxs-lookup"><span data-stu-id="7391c-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7391c-115">用于标识与此关联时的每条后续消息。</span><span class="sxs-lookup"><span data-stu-id="7391c-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7391c-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="7391c-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="7391c-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="7391c-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7391c-118">涉及相同文件名的文件传输之间标识的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7391c-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7391c-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="7391c-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="7391c-120">位</span><span class="sxs-lookup"><span data-stu-id="7391c-120">bit</span></span></p></td>
<td><p><span data-ttu-id="7391c-p102">可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7391c-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7391c-123"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="7391c-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="7391c-124">位</span><span class="sxs-lookup"><span data-stu-id="7391c-124">bit</span></span></p></td>
<td><p><span data-ttu-id="7391c-p103">可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7391c-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7391c-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="7391c-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="7391c-128">位</span><span class="sxs-lookup"><span data-stu-id="7391c-128">bit</span></span></p></td>
<td><p><span data-ttu-id="7391c-p104">可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="7391c-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

