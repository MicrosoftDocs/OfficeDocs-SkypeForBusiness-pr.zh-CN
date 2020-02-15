---
title: Lync Server 2013： tblADCookie
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
ms.openlocfilehash: 1f733397483693ad4c18418f3e82b9f99cfa640f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="812f6-102">Lync Server 2013 中的 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="812f6-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="812f6-103">_**上次修改的主题：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="812f6-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="812f6-104">tblADCookie 包含当前轻型目录访问协议 (LDAP) 同步 Cookie。</span><span class="sxs-lookup"><span data-stu-id="812f6-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="812f6-105">Columns</span><span class="sxs-lookup"><span data-stu-id="812f6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="812f6-106">列</span><span class="sxs-lookup"><span data-stu-id="812f6-106">Column</span></span></th>
<th><span data-ttu-id="812f6-107">类型</span><span class="sxs-lookup"><span data-stu-id="812f6-107">Type</span></span></th>
<th><span data-ttu-id="812f6-108">说明</span><span class="sxs-lookup"><span data-stu-id="812f6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="812f6-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="812f6-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="812f6-110">GUID，不为 null</span><span class="sxs-lookup"><span data-stu-id="812f6-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="812f6-111">要监控的域的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="812f6-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="812f6-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="812f6-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="812f6-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="812f6-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="812f6-114">用于 Active Directory 域服务同步的当前域控制器的完全限定的域名（FQDN）。具有信息性值。</span><span class="sxs-lookup"><span data-stu-id="812f6-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="812f6-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="812f6-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="812f6-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="812f6-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="812f6-117">Active Directory 同步 Cookie。</span><span class="sxs-lookup"><span data-stu-id="812f6-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="812f6-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="812f6-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="812f6-119">datetime</span><span class="sxs-lookup"><span data-stu-id="812f6-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="812f6-120">具有行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="812f6-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="812f6-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="812f6-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="812f6-122">datetime</span><span class="sxs-lookup"><span data-stu-id="812f6-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="812f6-p101">为更改锁定行的截止时间。此时间是软件联锁机制的一部分，可确保一次仅使其中一个聊天服务执行 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="812f6-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="812f6-125">Keys</span><span class="sxs-lookup"><span data-stu-id="812f6-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="812f6-126">列</span><span class="sxs-lookup"><span data-stu-id="812f6-126">Column(s)</span></span></th>
<th><span data-ttu-id="812f6-127">说明</span><span class="sxs-lookup"><span data-stu-id="812f6-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="812f6-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="812f6-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="812f6-129">主键。</span><span class="sxs-lookup"><span data-stu-id="812f6-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="812f6-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="812f6-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="812f6-131">其查找包含在 Principal.prinGuid 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="812f6-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

