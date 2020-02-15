---
title: Lync Server 2013： tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a8236145f86fa86039b4030fe82327d9fc4dfa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="f798e-102">Lync Server 2013 中的 tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="f798e-102">tblAdminLock in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f798e-103">_**上次修改的主题：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="f798e-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="f798e-104">tblAdminLock 包含运行一些管理员命令所需的管理员锁。</span><span class="sxs-lookup"><span data-stu-id="f798e-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="f798e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="f798e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f798e-106">列</span><span class="sxs-lookup"><span data-stu-id="f798e-106">Column</span></span></th>
<th><span data-ttu-id="f798e-107">类型</span><span class="sxs-lookup"><span data-stu-id="f798e-107">Type</span></span></th>
<th><span data-ttu-id="f798e-108">说明</span><span class="sxs-lookup"><span data-stu-id="f798e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f798e-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="f798e-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="f798e-110">datetime，不为 null</span><span class="sxs-lookup"><span data-stu-id="f798e-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f798e-p101">锁到期日期和时间。所有者可以定期延长该值。</span><span class="sxs-lookup"><span data-stu-id="f798e-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f798e-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="f798e-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="f798e-114">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="f798e-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f798e-115">拥有锁的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="f798e-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f798e-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="f798e-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="f798e-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="f798e-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f798e-118">拥有锁的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="f798e-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

