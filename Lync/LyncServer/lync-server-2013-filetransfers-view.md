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
ms.openlocfilehash: c2bf6f78a564ef1fd526ba8d265bedf81c845810
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="186f6-102">Lync Server 2013 中的 FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="186f6-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="186f6-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="186f6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="186f6-104">FileTransfer 视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="186f6-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="186f6-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="186f6-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="186f6-106">FileTransfers 视图包含在<A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 的 SessionDetails 视图</A>中的所有列，此外还列出了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="186f6-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="186f6-107">列</span><span class="sxs-lookup"><span data-stu-id="186f6-107">Column</span></span></th>
<th><span data-ttu-id="186f6-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="186f6-108">Data Type</span></span></th>
<th><span data-ttu-id="186f6-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="186f6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="186f6-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="186f6-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="186f6-111">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="186f6-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="186f6-112">文件传输的名称。</span><span class="sxs-lookup"><span data-stu-id="186f6-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="186f6-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="186f6-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="186f6-114">nvarchar</span><span class="sxs-lookup"><span data-stu-id="186f6-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="186f6-115">用于标识与此关联时的每条后续消息。</span><span class="sxs-lookup"><span data-stu-id="186f6-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="186f6-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="186f6-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="186f6-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="186f6-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="186f6-118">涉及相同文件名的文件传输之间标识的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="186f6-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="186f6-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="186f6-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="186f6-120">位</span><span class="sxs-lookup"><span data-stu-id="186f6-120">bit</span></span></p></td>
<td><p><span data-ttu-id="186f6-p102">可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="186f6-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="186f6-123"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="186f6-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="186f6-124">位</span><span class="sxs-lookup"><span data-stu-id="186f6-124">bit</span></span></p></td>
<td><p><span data-ttu-id="186f6-p103">可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="186f6-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="186f6-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="186f6-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="186f6-128">位</span><span class="sxs-lookup"><span data-stu-id="186f6-128">bit</span></span></p></td>
<td><p><span data-ttu-id="186f6-p104">可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="186f6-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

