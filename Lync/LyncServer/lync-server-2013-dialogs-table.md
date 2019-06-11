---
title: Lync Server 2013：Dialogs 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a25ae1d298f1cf5908c4669a78485491fadd617d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="f394d-102">Lync Server 2013 中的 Dialogs 表</span><span class="sxs-lookup"><span data-stu-id="f394d-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f394d-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f394d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f394d-104">对话框表是一个支持表, 用于存储有关对等会话的 DialogIDs 的信息。</span><span class="sxs-lookup"><span data-stu-id="f394d-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f394d-105">列</span><span class="sxs-lookup"><span data-stu-id="f394d-105">Column</span></span></th>
<th><span data-ttu-id="f394d-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="f394d-106">Data Type</span></span></th>
<th><span data-ttu-id="f394d-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="f394d-107">Key/Index</span></span></th>
<th><span data-ttu-id="f394d-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="f394d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f394d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f394d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f394d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f394d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f394d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="f394d-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="f394d-112">会话请求的时间;与 SessionIDSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="f394d-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f394d-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f394d-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f394d-114">int</span><span class="sxs-lookup"><span data-stu-id="f394d-114">int</span></span></p></td>
<td><p><span data-ttu-id="f394d-115">Primary</span><span class="sxs-lookup"><span data-stu-id="f394d-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="f394d-116">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="f394d-116">ID number to identify the session.</span></span> <span data-ttu-id="f394d-117">与 SessionIDTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="f394d-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f394d-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="f394d-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="f394d-119">int</span><span class="sxs-lookup"><span data-stu-id="f394d-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f394d-120">ExternalID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="f394d-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="f394d-121">此字段用于提高数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="f394d-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f394d-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="f394d-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="f394d-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="f394d-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f394d-124">SIP 对话框 ID, 存储为二进制。</span><span class="sxs-lookup"><span data-stu-id="f394d-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="f394d-125">二进制文件的格式为:</span><span class="sxs-lookup"><span data-stu-id="f394d-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="f394d-126">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="f394d-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="f394d-127">可以使用以下语法将此数据转换为文本格式:</span><span class="sxs-lookup"><span data-stu-id="f394d-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

