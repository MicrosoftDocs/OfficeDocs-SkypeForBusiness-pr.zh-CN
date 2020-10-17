---
title: Lync Server 2013： tblComplianceState
description: Lync Server 2013： tblComplianceState。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eaf35eee8b4e24ec4d04e607fa77fd91b91e4e8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568078"
---
# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="9bdb5-103">Lync Server 2013 中的 tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="9bdb5-103">tblComplianceState in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bdb5-104">_**上次修改的主题：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="9bdb5-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="9bdb5-105">tblComplianceState 包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="9bdb5-105">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="9bdb5-106">列数</span><span class="sxs-lookup"><span data-stu-id="9bdb5-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bdb5-107">列</span><span class="sxs-lookup"><span data-stu-id="9bdb5-107">Column</span></span></th>
<th><span data-ttu-id="9bdb5-108">类型</span><span class="sxs-lookup"><span data-stu-id="9bdb5-108">Type</span></span></th>
<th><span data-ttu-id="9bdb5-109">说明</span><span class="sxs-lookup"><span data-stu-id="9bdb5-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bdb5-110">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="9bdb5-110">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="9bdb5-111">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="9bdb5-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="9bdb5-112">最新处理的合规性事件的 ID。</span><span class="sxs-lookup"><span data-stu-id="9bdb5-112">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bdb5-113">activeServerID</span><span class="sxs-lookup"><span data-stu-id="9bdb5-113">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="9bdb5-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="9bdb5-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9bdb5-115">数据库上保留排除锁的合规性服务器 ID，或者，如果无则为 -1。</span><span class="sxs-lookup"><span data-stu-id="9bdb5-115">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bdb5-116">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="9bdb5-116">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="9bdb5-117">datetime2，不为 null</span><span class="sxs-lookup"><span data-stu-id="9bdb5-117">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="9bdb5-118">锁定到期时间（如果 activeServerID 不为 -1）。</span><span class="sxs-lookup"><span data-stu-id="9bdb5-118">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

