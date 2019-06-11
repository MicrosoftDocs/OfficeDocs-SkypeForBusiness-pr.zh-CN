---
title: Lync Server 2013：tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fce70f05b317ac7467fd17306d6933c66087e5e6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="82b62-102">Lync Server 2013 中的 tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="82b62-102">tblComplianceState in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82b62-103">_**主题上次修改时间:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="82b62-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="82b62-104">tblComplianceState 包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="82b62-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="82b62-105">多</span><span class="sxs-lookup"><span data-stu-id="82b62-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82b62-106">列</span><span class="sxs-lookup"><span data-stu-id="82b62-106">Column</span></span></th>
<th><span data-ttu-id="82b62-107">类型</span><span class="sxs-lookup"><span data-stu-id="82b62-107">Type</span></span></th>
<th><span data-ttu-id="82b62-108">说明</span><span class="sxs-lookup"><span data-stu-id="82b62-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82b62-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="82b62-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="82b62-110">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="82b62-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="82b62-111">最新的已处理合规性事件的 ID。</span><span class="sxs-lookup"><span data-stu-id="82b62-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82b62-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="82b62-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="82b62-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="82b62-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="82b62-114">在数据库上持有独占锁的合规性服务器 ID, 或者, 如果没有, 则为-1。</span><span class="sxs-lookup"><span data-stu-id="82b62-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82b62-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="82b62-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="82b62-116">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="82b62-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="82b62-117">锁过期时间 (如果 activeServerID 不是-1)。</span><span class="sxs-lookup"><span data-stu-id="82b62-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

