---
title: Lync Server 2013： tblADCookie
description: Lync Server 2013： tblADCookie。
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
ms.openlocfilehash: 41c3dde3730ede07b204a473c7fe0a5ab68054d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573718"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="2cba2-103">Lync Server 2013 中的 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="2cba2-103">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cba2-104">_**上次修改的主题：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="2cba2-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="2cba2-105">tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 Cookie。</span><span class="sxs-lookup"><span data-stu-id="2cba2-105">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="2cba2-106">列数</span><span class="sxs-lookup"><span data-stu-id="2cba2-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cba2-107">列</span><span class="sxs-lookup"><span data-stu-id="2cba2-107">Column</span></span></th>
<th><span data-ttu-id="2cba2-108">类型</span><span class="sxs-lookup"><span data-stu-id="2cba2-108">Type</span></span></th>
<th><span data-ttu-id="2cba2-109">说明</span><span class="sxs-lookup"><span data-stu-id="2cba2-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cba2-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2cba2-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2cba2-111">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="2cba2-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2cba2-112">要监控的域的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="2cba2-112">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cba2-113">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="2cba2-113">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="2cba2-114">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="2cba2-114">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="2cba2-115">用于 Active Directory 域服务同步的当前域控制器 (FQDN) 的完全限定的域名称。具有信息性值。</span><span class="sxs-lookup"><span data-stu-id="2cba2-115">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cba2-116">adcContent</span><span class="sxs-lookup"><span data-stu-id="2cba2-116">adcContent</span></span></p></td>
<td><p><span data-ttu-id="2cba2-117">image (binary)</span><span class="sxs-lookup"><span data-stu-id="2cba2-117">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="2cba2-118">Active Directory 同步 Cookie。</span><span class="sxs-lookup"><span data-stu-id="2cba2-118">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cba2-119">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="2cba2-119">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="2cba2-120">datetime</span><span class="sxs-lookup"><span data-stu-id="2cba2-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="2cba2-121">具有行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="2cba2-121">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cba2-122">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="2cba2-122">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="2cba2-123">datetime</span><span class="sxs-lookup"><span data-stu-id="2cba2-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="2cba2-p101">为更改锁定行的截止时间。此时间是软件联锁机制的一部分，可确保一次仅使其中一个聊天服务执行 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="2cba2-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2cba2-126">Keys</span><span class="sxs-lookup"><span data-stu-id="2cba2-126">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cba2-127">列 (s) </span><span class="sxs-lookup"><span data-stu-id="2cba2-127">Column(s)</span></span></th>
<th><span data-ttu-id="2cba2-128">说明</span><span class="sxs-lookup"><span data-stu-id="2cba2-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cba2-129">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2cba2-129">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2cba2-130">主键。</span><span class="sxs-lookup"><span data-stu-id="2cba2-130">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cba2-131">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2cba2-131">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2cba2-132">其查找包含在 Principal.prinGuid 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="2cba2-132">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

