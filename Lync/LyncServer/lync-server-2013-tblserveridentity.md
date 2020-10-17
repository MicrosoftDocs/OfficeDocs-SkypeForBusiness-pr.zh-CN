---
title: Lync Server 2013： tblServerIdentity
description: Lync Server 2013： tblServerIdentity。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e954618cb373f2cf4f1b7ed929c3aaf6d8875e92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564528"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="5455c-103">Lync Server 2013 中的 tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="5455c-103">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5455c-104">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5455c-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5455c-105">tblServerIdentity 包含持久聊天服务器池中的活动聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="5455c-105">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="5455c-106">列数</span><span class="sxs-lookup"><span data-stu-id="5455c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5455c-107">列</span><span class="sxs-lookup"><span data-stu-id="5455c-107">Column</span></span></th>
<th><span data-ttu-id="5455c-108">类型</span><span class="sxs-lookup"><span data-stu-id="5455c-108">Type</span></span></th>
<th><span data-ttu-id="5455c-109">说明</span><span class="sxs-lookup"><span data-stu-id="5455c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5455c-110">serverID</span><span class="sxs-lookup"><span data-stu-id="5455c-110">serverID</span></span></p></td>
<td><p><span data-ttu-id="5455c-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="5455c-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5455c-112">服务器 ID。</span><span class="sxs-lookup"><span data-stu-id="5455c-112">Server ID.</span></span> <span data-ttu-id="5455c-113">与中央管理存储中的实例 ID 相对应。</span><span class="sxs-lookup"><span data-stu-id="5455c-113">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5455c-114">serverAddress</span><span class="sxs-lookup"><span data-stu-id="5455c-114">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="5455c-115">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="5455c-115">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5455c-116">使用 Windows Communication Foundation 地址的服务器地址。</span><span class="sxs-lookup"><span data-stu-id="5455c-116">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5455c-117">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="5455c-117">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="5455c-118">datetime</span><span class="sxs-lookup"><span data-stu-id="5455c-118">datetime</span></span></p></td>
<td><p><span data-ttu-id="5455c-119">通道服务器更新此行以表明服务器正在运行的最新时间。</span><span class="sxs-lookup"><span data-stu-id="5455c-119">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5455c-120">键</span><span class="sxs-lookup"><span data-stu-id="5455c-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5455c-121">列</span><span class="sxs-lookup"><span data-stu-id="5455c-121">Column</span></span></th>
<th><span data-ttu-id="5455c-122">说明</span><span class="sxs-lookup"><span data-stu-id="5455c-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5455c-123">serverID</span><span class="sxs-lookup"><span data-stu-id="5455c-123">serverID</span></span></p></td>
<td><p><span data-ttu-id="5455c-124">主键。</span><span class="sxs-lookup"><span data-stu-id="5455c-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

