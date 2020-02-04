---
title: Lync Server 2013：tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85fc3dd6575433b605d6ce9100aacfde56782e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="f5a65-102">Lync Server 2013 中的 tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="f5a65-102">tblSiopWhiteList in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5a65-103">_**主题上次修改时间：** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="f5a65-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="f5a65-104">tblSiopWhiteList 是可与节点相关联的注册外接程序的列表。</span><span class="sxs-lookup"><span data-stu-id="f5a65-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="f5a65-105">多</span><span class="sxs-lookup"><span data-stu-id="f5a65-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5a65-106">列</span><span class="sxs-lookup"><span data-stu-id="f5a65-106">Column</span></span></th>
<th><span data-ttu-id="f5a65-107">类型</span><span class="sxs-lookup"><span data-stu-id="f5a65-107">Type</span></span></th>
<th><span data-ttu-id="f5a65-108">说明</span><span class="sxs-lookup"><span data-stu-id="f5a65-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5a65-109">siopID</span><span class="sxs-lookup"><span data-stu-id="f5a65-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="f5a65-110">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="f5a65-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f5a65-111">外接程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f5a65-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5a65-112">siopName</span><span class="sxs-lookup"><span data-stu-id="f5a65-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="f5a65-113">nvarchar （50），not null</span><span class="sxs-lookup"><span data-stu-id="f5a65-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="f5a65-114">显示-外接程序的名称。</span><span class="sxs-lookup"><span data-stu-id="f5a65-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5a65-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="f5a65-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="f5a65-116">nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="f5a65-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="f5a65-117">外接程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="f5a65-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f5a65-118">关键字</span><span class="sxs-lookup"><span data-stu-id="f5a65-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5a65-119">列</span><span class="sxs-lookup"><span data-stu-id="f5a65-119">Column</span></span></th>
<th><span data-ttu-id="f5a65-120">说明</span><span class="sxs-lookup"><span data-stu-id="f5a65-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5a65-121">siopID</span><span class="sxs-lookup"><span data-stu-id="f5a65-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="f5a65-122">主键。</span><span class="sxs-lookup"><span data-stu-id="f5a65-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

