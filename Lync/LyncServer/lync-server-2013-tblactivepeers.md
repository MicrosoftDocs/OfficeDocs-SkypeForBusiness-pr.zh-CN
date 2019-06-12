---
title: Lync Server 2013：tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615030(v=OCS.15)
ms:contentKeyID: 48185176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb6089cfa3f3a9da8103dd0d0691031dac05d05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblactivepeers-in-lync-server-2013"></a><span data-ttu-id="681a6-102">Lync Server 2013 中的 tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="681a6-102">tblActivePeers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="681a6-103">_**主题上次修改时间:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="681a6-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="681a6-104">tblActivePeers 包含聊天服务之间的当前点对点连接。</span><span class="sxs-lookup"><span data-stu-id="681a6-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>

### <a name="columns"></a><span data-ttu-id="681a6-105">多</span><span class="sxs-lookup"><span data-stu-id="681a6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="681a6-106">列</span><span class="sxs-lookup"><span data-stu-id="681a6-106">Column</span></span></th>
<th><span data-ttu-id="681a6-107">类型</span><span class="sxs-lookup"><span data-stu-id="681a6-107">Type</span></span></th>
<th><span data-ttu-id="681a6-108">说明</span><span class="sxs-lookup"><span data-stu-id="681a6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="681a6-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="681a6-109">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="681a6-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="681a6-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="681a6-111">已发布条目的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="681a6-111">ID of the server that posted the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="681a6-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="681a6-112">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="681a6-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="681a6-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="681a6-114">过帐服务器连接到的对等的 ID。</span><span class="sxs-lookup"><span data-stu-id="681a6-114">ID of the peer that the posting server is connected to.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="681a6-115">标示</span><span class="sxs-lookup"><span data-stu-id="681a6-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="681a6-116">列</span><span class="sxs-lookup"><span data-stu-id="681a6-116">Column</span></span></th>
<th><span data-ttu-id="681a6-117">说明</span><span class="sxs-lookup"><span data-stu-id="681a6-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="681a6-118">&lt;aplServerID, aplPeerID&gt;</span><span class="sxs-lookup"><span data-stu-id="681a6-118">&lt;aplServerID, aplPeerID&gt;</span></span></p></td>
<td><p><span data-ttu-id="681a6-119">主键。</span><span class="sxs-lookup"><span data-stu-id="681a6-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="681a6-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="681a6-120">aplServerID</span></span></p></td>
<td><p><span data-ttu-id="681a6-121">TblServerIdentity 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="681a6-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="681a6-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="681a6-122">aplPeerID</span></span></p></td>
<td><p><span data-ttu-id="681a6-123">TblServerIdentity 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="681a6-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

