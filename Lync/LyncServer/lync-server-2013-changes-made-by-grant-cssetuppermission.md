---
title: Lync Server 2013：由 Grant-CsSetupPermission 所做的更改
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
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="773ac-102">Lync Server 2013 中的 CsSetupPermission 所做的更改</span><span class="sxs-lookup"><span data-stu-id="773ac-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="773ac-103">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="773ac-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="773ac-104">若要委派安装程序，可以为特定 Active Directory 组织单位（OU）授予对 RTCUniversalServerAdmins 通用组的权限，从而启用该 OU 中 RTCUniversalServerAdmins 组的成员，以在指定的中安装 Lync Server 2013。不是 Domain Admins 组的成员的域。</span><span class="sxs-lookup"><span data-stu-id="773ac-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="773ac-105">**Grant-CsSetupPermission** cmdlet 向 OU 授予 RTCUniversalServerAdmins 组权限，如下表中所述：</span><span class="sxs-lookup"><span data-stu-id="773ac-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="773ac-106">向 OU 中的对象授予的权限</span><span class="sxs-lookup"><span data-stu-id="773ac-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="773ac-107">权限适用于：</span><span class="sxs-lookup"><span data-stu-id="773ac-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="773ac-108">授予的权限为：</span><span class="sxs-lookup"><span data-stu-id="773ac-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="773ac-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="773ac-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="773ac-110">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-111">读取 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="773ac-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="773ac-112">写入 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="773ac-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="773ac-113">删除树</span><span class="sxs-lookup"><span data-stu-id="773ac-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="773ac-114">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="773ac-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="773ac-115">后代 serviceConnectionPoint 对象</span><span class="sxs-lookup"><span data-stu-id="773ac-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="773ac-116">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-117">读取权限</span><span class="sxs-lookup"><span data-stu-id="773ac-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="773ac-118">写入权限</span><span class="sxs-lookup"><span data-stu-id="773ac-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="773ac-119">创建子级</span><span class="sxs-lookup"><span data-stu-id="773ac-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="773ac-120">删除子级</span><span class="sxs-lookup"><span data-stu-id="773ac-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="773ac-121">列出内容</span><span class="sxs-lookup"><span data-stu-id="773ac-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="773ac-122">写入属性</span><span class="sxs-lookup"><span data-stu-id="773ac-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="773ac-123">读取属性</span><span class="sxs-lookup"><span data-stu-id="773ac-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="773ac-124">删除树</span><span class="sxs-lookup"><span data-stu-id="773ac-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="773ac-125">后代 msRTCSIP-Server 对象</span><span class="sxs-lookup"><span data-stu-id="773ac-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="773ac-126">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-127">写入属性</span><span class="sxs-lookup"><span data-stu-id="773ac-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="773ac-128">读取属性</span><span class="sxs-lookup"><span data-stu-id="773ac-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="773ac-129">删除树</span><span class="sxs-lookup"><span data-stu-id="773ac-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="773ac-130">后代 msRTCSIP-WebComponents 对象</span><span class="sxs-lookup"><span data-stu-id="773ac-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="773ac-131">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-132">写入属性</span><span class="sxs-lookup"><span data-stu-id="773ac-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="773ac-133">读取属性</span><span class="sxs-lookup"><span data-stu-id="773ac-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="773ac-134">删除树</span><span class="sxs-lookup"><span data-stu-id="773ac-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="773ac-135">后代 msRTCSIP-MCU 对象</span><span class="sxs-lookup"><span data-stu-id="773ac-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="773ac-136">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-137">写入属性</span><span class="sxs-lookup"><span data-stu-id="773ac-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="773ac-138">读取属性</span><span class="sxs-lookup"><span data-stu-id="773ac-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="773ac-139">删除树</span><span class="sxs-lookup"><span data-stu-id="773ac-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="773ac-140">后代 msRTCSIP-MediationServer 对象</span><span class="sxs-lookup"><span data-stu-id="773ac-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="773ac-141">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-142">写入属性</span><span class="sxs-lookup"><span data-stu-id="773ac-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="773ac-143">读取属性</span><span class="sxs-lookup"><span data-stu-id="773ac-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="773ac-144">删除树</span><span class="sxs-lookup"><span data-stu-id="773ac-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="773ac-145">后代 msRTCSIP-ApplicationServer 对象</span><span class="sxs-lookup"><span data-stu-id="773ac-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="773ac-146">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-147">写入属性</span><span class="sxs-lookup"><span data-stu-id="773ac-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="773ac-148">读取属性</span><span class="sxs-lookup"><span data-stu-id="773ac-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="773ac-149">删除树</span><span class="sxs-lookup"><span data-stu-id="773ac-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="773ac-150">后代 msRTCSIP-ConnectionPoint 对象</span><span class="sxs-lookup"><span data-stu-id="773ac-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="773ac-151">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-152">写入属性</span><span class="sxs-lookup"><span data-stu-id="773ac-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="773ac-153">读取属性</span><span class="sxs-lookup"><span data-stu-id="773ac-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="773ac-154">删除树</span><span class="sxs-lookup"><span data-stu-id="773ac-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="773ac-155">后代计算机对象</span><span class="sxs-lookup"><span data-stu-id="773ac-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="773ac-156">对 serviceConnectionPoint 的特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-157">创建子对象</span><span class="sxs-lookup"><span data-stu-id="773ac-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="773ac-158">删除子对象</span><span class="sxs-lookup"><span data-stu-id="773ac-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="773ac-159">删除树</span><span class="sxs-lookup"><span data-stu-id="773ac-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="773ac-160">对公共信息的特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-161">读取属性</span><span class="sxs-lookup"><span data-stu-id="773ac-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="773ac-162">对 DNS 主机名的特殊访问：</span><span class="sxs-lookup"><span data-stu-id="773ac-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="773ac-163">读取属性</span><span class="sxs-lookup"><span data-stu-id="773ac-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

