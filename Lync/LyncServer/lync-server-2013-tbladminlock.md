---
title: Lync Server 2013：tblAdminLock
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
ms.openlocfilehash: 89e1509a1a84e0a9dd03527eedfb0b9e6da1590e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="fecdc-102">Lync Server 2013 中的 tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="fecdc-102">tblAdminLock in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fecdc-103">_**主题上次修改时间：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="fecdc-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="fecdc-104">tblAdminLock 包含运行某些管理员命令所需的管理员锁。</span><span class="sxs-lookup"><span data-stu-id="fecdc-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="fecdc-105">多</span><span class="sxs-lookup"><span data-stu-id="fecdc-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fecdc-106">列</span><span class="sxs-lookup"><span data-stu-id="fecdc-106">Column</span></span></th>
<th><span data-ttu-id="fecdc-107">类型</span><span class="sxs-lookup"><span data-stu-id="fecdc-107">Type</span></span></th>
<th><span data-ttu-id="fecdc-108">说明</span><span class="sxs-lookup"><span data-stu-id="fecdc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fecdc-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="fecdc-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="fecdc-110">datetime，not null</span><span class="sxs-lookup"><span data-stu-id="fecdc-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fecdc-111">锁定到期日期和时间。</span><span class="sxs-lookup"><span data-stu-id="fecdc-111">Lock expiration date and time.</span></span> <span data-ttu-id="fecdc-112">所有者可以定期延长此值。</span><span class="sxs-lookup"><span data-stu-id="fecdc-112">The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecdc-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="fecdc-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="fecdc-114">int，not null</span><span class="sxs-lookup"><span data-stu-id="fecdc-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fecdc-115">拥有锁定的服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="fecdc-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecdc-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="fecdc-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="fecdc-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="fecdc-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fecdc-118">拥有锁定的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="fecdc-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

