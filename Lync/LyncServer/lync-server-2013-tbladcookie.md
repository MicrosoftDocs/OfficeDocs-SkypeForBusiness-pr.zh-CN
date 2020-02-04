---
title: Lync Server 2013：tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b1b5096c087661bf5afadd2668d6d1bb7ac8330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="c2c2d-102">Lync Server 2013 中的 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="c2c2d-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2c2d-103">_**主题上次修改时间：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="c2c2d-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="c2c2d-104">tblADCookie 包含当前的轻型目录访问协议（LDAP）同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="c2c2d-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="c2c2d-105">多</span><span class="sxs-lookup"><span data-stu-id="c2c2d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2c2d-106">列</span><span class="sxs-lookup"><span data-stu-id="c2c2d-106">Column</span></span></th>
<th><span data-ttu-id="c2c2d-107">类型</span><span class="sxs-lookup"><span data-stu-id="c2c2d-107">Type</span></span></th>
<th><span data-ttu-id="c2c2d-108">说明</span><span class="sxs-lookup"><span data-stu-id="c2c2d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2c2d-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c2c2d-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-110">GUID，not null</span><span class="sxs-lookup"><span data-stu-id="c2c2d-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-111">正在监视的域的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="c2c2d-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2c2d-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="c2c2d-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-113">nvarchar （255）</span><span class="sxs-lookup"><span data-stu-id="c2c2d-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-114">用于 Active Directory 域服务同步的当前域控制器的完全限定的域名（FQDN）。有信息值。</span><span class="sxs-lookup"><span data-stu-id="c2c2d-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2c2d-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="c2c2d-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-116">图像（二进制）</span><span class="sxs-lookup"><span data-stu-id="c2c2d-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-117">Active Directory 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="c2c2d-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2c2d-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="c2c2d-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-119">datetime</span><span class="sxs-lookup"><span data-stu-id="c2c2d-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-120">带有行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="c2c2d-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2c2d-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="c2c2d-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-122">datetime</span><span class="sxs-lookup"><span data-stu-id="c2c2d-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-123">对行进行更改锁定的时间。</span><span class="sxs-lookup"><span data-stu-id="c2c2d-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="c2c2d-124">这是一种软件互操作机制的一部分，可确保每次只有一个聊天服务执行 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="c2c2d-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="c2c2d-125">标示</span><span class="sxs-lookup"><span data-stu-id="c2c2d-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2c2d-126">列</span><span class="sxs-lookup"><span data-stu-id="c2c2d-126">Column(s)</span></span></th>
<th><span data-ttu-id="c2c2d-127">说明</span><span class="sxs-lookup"><span data-stu-id="c2c2d-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2c2d-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c2c2d-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-129">主键。</span><span class="sxs-lookup"><span data-stu-id="c2c2d-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2c2d-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="c2c2d-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="c2c2d-131">PrinGuid 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="c2c2d-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

