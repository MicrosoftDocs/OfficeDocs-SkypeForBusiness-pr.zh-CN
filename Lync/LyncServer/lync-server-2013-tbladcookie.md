---
title: Lync Server 2013：tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="70b60-102">Lync Server 2013 中的 tblADCookie</span><span class="sxs-lookup"><span data-stu-id="70b60-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70b60-103">_**主题上次修改时间:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="70b60-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="70b60-104">tblADCookie 包含当前的轻型目录访问协议 (LDAP) 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="70b60-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="70b60-105">多</span><span class="sxs-lookup"><span data-stu-id="70b60-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70b60-106">列</span><span class="sxs-lookup"><span data-stu-id="70b60-106">Column</span></span></th>
<th><span data-ttu-id="70b60-107">类型</span><span class="sxs-lookup"><span data-stu-id="70b60-107">Type</span></span></th>
<th><span data-ttu-id="70b60-108">说明</span><span class="sxs-lookup"><span data-stu-id="70b60-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70b60-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="70b60-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="70b60-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="70b60-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="70b60-111">正在监视的域的主体 GUID。</span><span class="sxs-lookup"><span data-stu-id="70b60-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70b60-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="70b60-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="70b60-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="70b60-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="70b60-114">用于 Active Directory 域服务同步的当前域控制器的完全限定的域名 (FQDN)。有信息值。</span><span class="sxs-lookup"><span data-stu-id="70b60-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70b60-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="70b60-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="70b60-116">图像 (二进制)</span><span class="sxs-lookup"><span data-stu-id="70b60-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="70b60-117">Active Directory 同步 cookie。</span><span class="sxs-lookup"><span data-stu-id="70b60-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70b60-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="70b60-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="70b60-119">datetime</span><span class="sxs-lookup"><span data-stu-id="70b60-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="70b60-120">带有行更新时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="70b60-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70b60-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="70b60-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="70b60-122">datetime</span><span class="sxs-lookup"><span data-stu-id="70b60-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="70b60-123">对行进行更改锁定的时间。</span><span class="sxs-lookup"><span data-stu-id="70b60-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="70b60-124">这是一种软件互操作机制的一部分, 可确保每次只有一个聊天服务执行 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="70b60-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="70b60-125">标示</span><span class="sxs-lookup"><span data-stu-id="70b60-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70b60-126">列</span><span class="sxs-lookup"><span data-stu-id="70b60-126">Column(s)</span></span></th>
<th><span data-ttu-id="70b60-127">说明</span><span class="sxs-lookup"><span data-stu-id="70b60-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70b60-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="70b60-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="70b60-129">主键。</span><span class="sxs-lookup"><span data-stu-id="70b60-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70b60-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="70b60-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="70b60-131">PrinGuid 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="70b60-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

