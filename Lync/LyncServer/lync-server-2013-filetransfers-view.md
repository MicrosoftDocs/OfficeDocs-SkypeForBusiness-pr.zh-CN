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
ms.openlocfilehash: e0fdfae0cefafc7ee6273af75e84e0ea6545188b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500869"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="f802b-102">Lync Server 2013 中的 FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="f802b-102">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f802b-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f802b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f802b-104">FileTransfer 视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="f802b-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="f802b-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f802b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f802b-106">FileTransfers 视图包含在 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 的 SessionDetails 视图</A> 中的所有列，此外还列出了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="f802b-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f802b-107">列</span><span class="sxs-lookup"><span data-stu-id="f802b-107">Column</span></span></th>
<th><span data-ttu-id="f802b-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="f802b-108">Data Type</span></span></th>
<th><span data-ttu-id="f802b-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="f802b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f802b-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="f802b-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="f802b-111">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f802b-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f802b-112">文件传输的名称。</span><span class="sxs-lookup"><span data-stu-id="f802b-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f802b-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="f802b-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="f802b-114">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f802b-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f802b-115">用于标识与此关联时的每条后续消息。</span><span class="sxs-lookup"><span data-stu-id="f802b-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f802b-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="f802b-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="f802b-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f802b-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f802b-118">涉及相同文件名的文件传输之间标识的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f802b-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f802b-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="f802b-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="f802b-120">位</span><span class="sxs-lookup"><span data-stu-id="f802b-120">bit</span></span></p></td>
<td><p><span data-ttu-id="f802b-p102">可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f802b-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f802b-123"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="f802b-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="f802b-124">位</span><span class="sxs-lookup"><span data-stu-id="f802b-124">bit</span></span></p></td>
<td><p><span data-ttu-id="f802b-p103">可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f802b-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f802b-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="f802b-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="f802b-128">位</span><span class="sxs-lookup"><span data-stu-id="f802b-128">bit</span></span></p></td>
<td><p><span data-ttu-id="f802b-p104">可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f802b-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

