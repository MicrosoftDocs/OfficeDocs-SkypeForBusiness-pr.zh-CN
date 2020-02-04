---
title: Lync Server 2013：tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196911f4fdcb7f2713ed25cca114ff9954b0c6e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="d49af-102">Lync Server 2013 中的 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="d49af-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d49af-103">_**主题上次修改时间：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d49af-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d49af-104">tblComplianceFanout 包含处理合规性事件的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="d49af-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="d49af-105">多</span><span class="sxs-lookup"><span data-stu-id="d49af-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d49af-106">列</span><span class="sxs-lookup"><span data-stu-id="d49af-106">Column</span></span></th>
<th><span data-ttu-id="d49af-107">类型</span><span class="sxs-lookup"><span data-stu-id="d49af-107">Type</span></span></th>
<th><span data-ttu-id="d49af-108">说明</span><span class="sxs-lookup"><span data-stu-id="d49af-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d49af-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d49af-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="d49af-110">int</span><span class="sxs-lookup"><span data-stu-id="d49af-110">int</span></span></p></td>
<td><p><span data-ttu-id="d49af-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="d49af-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49af-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="d49af-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="d49af-113">int</span><span class="sxs-lookup"><span data-stu-id="d49af-113">int</span></span></p></td>
<td><p><span data-ttu-id="d49af-114">服务器标识（对应于 tblServerIdentity 表）。</span><span class="sxs-lookup"><span data-stu-id="d49af-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="d49af-115">关键字</span><span class="sxs-lookup"><span data-stu-id="d49af-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d49af-116">列</span><span class="sxs-lookup"><span data-stu-id="d49af-116">Column</span></span></th>
<th><span data-ttu-id="d49af-117">说明</span><span class="sxs-lookup"><span data-stu-id="d49af-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d49af-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d49af-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="d49af-119">TblComplianceData 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="d49af-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

