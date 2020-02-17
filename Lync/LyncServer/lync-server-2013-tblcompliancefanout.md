---
title: Lync Server 2013： tblComplianceFanout
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
ms.openlocfilehash: c535dc860c5d1a8725d27217e8269c3d6c4902d2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="17e3f-102">Lync Server 2013 中的 tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="17e3f-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17e3f-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="17e3f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="17e3f-104">tblComplianceFanout 包含处理合规性事件的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="17e3f-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="17e3f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="17e3f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17e3f-106">列</span><span class="sxs-lookup"><span data-stu-id="17e3f-106">Column</span></span></th>
<th><span data-ttu-id="17e3f-107">类型</span><span class="sxs-lookup"><span data-stu-id="17e3f-107">Type</span></span></th>
<th><span data-ttu-id="17e3f-108">描述</span><span class="sxs-lookup"><span data-stu-id="17e3f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17e3f-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="17e3f-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="17e3f-110">int</span><span class="sxs-lookup"><span data-stu-id="17e3f-110">int</span></span></p></td>
<td><p><span data-ttu-id="17e3f-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="17e3f-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17e3f-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="17e3f-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="17e3f-113">int</span><span class="sxs-lookup"><span data-stu-id="17e3f-113">int</span></span></p></td>
<td><p><span data-ttu-id="17e3f-114">服务器标识（与 tblServerIdentity.serverID 表对应）。</span><span class="sxs-lookup"><span data-stu-id="17e3f-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="17e3f-115">键</span><span class="sxs-lookup"><span data-stu-id="17e3f-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17e3f-116">列</span><span class="sxs-lookup"><span data-stu-id="17e3f-116">Column</span></span></th>
<th><span data-ttu-id="17e3f-117">说明</span><span class="sxs-lookup"><span data-stu-id="17e3f-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17e3f-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="17e3f-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="17e3f-119">其查找包含在 tblComplianceData.cmplEventID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="17e3f-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

