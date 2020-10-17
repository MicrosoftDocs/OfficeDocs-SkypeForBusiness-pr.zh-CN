---
title: Lync Server 2013： Grant-CsSetupPermission 所做的更改
description: Lync Server 2013： CsSetupPermission 所做的更改。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543598"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="2d5ba-103">Lync Server 2013 中 Grant-CsSetupPermission 所做的更改</span><span class="sxs-lookup"><span data-stu-id="2d5ba-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d5ba-104">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="2d5ba-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="2d5ba-105">若要委派设置，可以向 RTCUniversalServerAdmins 通用组授予对特定 Active Directory 组织单位 (OU) 的权限，从而启用该 OU 中 RTCUniversalServerAdmins 组的成员，以在指定域中安装 Lync Server 2013，而不是 Domain Admins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="2d5ba-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="2d5ba-106">**Grant-CsSetupPermission** cmdlet 向 OU 授予 RTCUniversalServerAdmins 组权限，如下表中所述：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="2d5ba-107">向 OU 中的对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="2d5ba-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d5ba-108">权限适用于：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="2d5ba-109">授予的权限为：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d5ba-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2d5ba-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2d5ba-111">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-112">读取 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="2d5ba-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-113">写入 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="2d5ba-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-114">删除树</span><span class="sxs-lookup"><span data-stu-id="2d5ba-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-115">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="2d5ba-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d5ba-116">后代 serviceConnectionPoint 对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="2d5ba-117">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-118">读取权限</span><span class="sxs-lookup"><span data-stu-id="2d5ba-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-119">写入权限</span><span class="sxs-lookup"><span data-stu-id="2d5ba-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-120">创建子级</span><span class="sxs-lookup"><span data-stu-id="2d5ba-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-121">删除子级</span><span class="sxs-lookup"><span data-stu-id="2d5ba-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-122">列出内容</span><span class="sxs-lookup"><span data-stu-id="2d5ba-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-123">写入属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-124">读取属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-125">删除树</span><span class="sxs-lookup"><span data-stu-id="2d5ba-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d5ba-126">后代 msRTCSIP-Server 对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="2d5ba-127">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-128">写入属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-129">读取属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-130">删除树</span><span class="sxs-lookup"><span data-stu-id="2d5ba-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d5ba-131">后代 msRTCSIP-WebComponents 对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="2d5ba-132">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-133">写入属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-134">读取属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-135">删除树</span><span class="sxs-lookup"><span data-stu-id="2d5ba-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d5ba-136">后代 msRTCSIP-MCU 对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="2d5ba-137">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-138">写入属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-139">读取属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-140">删除树</span><span class="sxs-lookup"><span data-stu-id="2d5ba-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d5ba-141">后代 msRTCSIP-MediationServer 对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="2d5ba-142">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-143">写入属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-144">读取属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-145">删除树</span><span class="sxs-lookup"><span data-stu-id="2d5ba-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d5ba-146">后代 msRTCSIP-ApplicationServer 对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="2d5ba-147">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-148">写入属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-149">读取属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-150">删除树</span><span class="sxs-lookup"><span data-stu-id="2d5ba-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d5ba-151">后代 msRTCSIP-ConnectionPoint 对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="2d5ba-152">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-153">写入属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-154">读取属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-155">删除树</span><span class="sxs-lookup"><span data-stu-id="2d5ba-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d5ba-156">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="2d5ba-157">对 serviceConnectionPoint 的特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-158">创建子对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-159">删除子对象</span><span class="sxs-lookup"><span data-stu-id="2d5ba-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="2d5ba-160">删除树</span><span class="sxs-lookup"><span data-stu-id="2d5ba-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="2d5ba-161">对公共信息的特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-162">读取属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="2d5ba-163">对 DNS 主机名的特殊访问：</span><span class="sxs-lookup"><span data-stu-id="2d5ba-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d5ba-164">读取属性</span><span class="sxs-lookup"><span data-stu-id="2d5ba-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

