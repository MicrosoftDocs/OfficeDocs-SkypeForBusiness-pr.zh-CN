---
title: Lync Server 2013：通过授予 CsSetupPermission 进行的更改
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
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="853fe-102">Lync Server 2013 中的 "授权-CsSetupPermission" 所做的更改</span><span class="sxs-lookup"><span data-stu-id="853fe-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="853fe-103">_**主题上次修改时间：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="853fe-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="853fe-104">若要委派设置，你可以向特定 Active Directory 组织单位（OU）的 RTCUniversalServerAdmins 通用组授予权限，从而允许该 OU 中的 RTCUniversalServerAdmins 组成员在指定的 Active Directory 中安装 Lync Server 2013不是域管理员组成员的域。</span><span class="sxs-lookup"><span data-stu-id="853fe-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="853fe-105">**CsSetupPermission** cmdlet 授予对 OU 的 RTCUniversalServerAdmins 组权限，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="853fe-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="853fe-106">在 OU 中授予对象的权限</span><span class="sxs-lookup"><span data-stu-id="853fe-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="853fe-107">权限适用于：</span><span class="sxs-lookup"><span data-stu-id="853fe-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="853fe-108">授予的权限为：</span><span class="sxs-lookup"><span data-stu-id="853fe-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="853fe-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="853fe-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="853fe-110">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="853fe-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-111">阅读 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="853fe-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="853fe-112">写入 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="853fe-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="853fe-113">删除树</span><span class="sxs-lookup"><span data-stu-id="853fe-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="853fe-114">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="853fe-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="853fe-115">后代 serviceConnectionPoint 对象</span><span class="sxs-lookup"><span data-stu-id="853fe-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="853fe-116">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="853fe-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-117">读取权限</span><span class="sxs-lookup"><span data-stu-id="853fe-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="853fe-118">写入权限</span><span class="sxs-lookup"><span data-stu-id="853fe-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="853fe-119">创建子元素</span><span class="sxs-lookup"><span data-stu-id="853fe-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="853fe-120">删除子元素</span><span class="sxs-lookup"><span data-stu-id="853fe-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="853fe-121">列表内容</span><span class="sxs-lookup"><span data-stu-id="853fe-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="853fe-122">Write 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="853fe-123">Read 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="853fe-124">删除树</span><span class="sxs-lookup"><span data-stu-id="853fe-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="853fe-125">子代 msRTCSIP-服务器对象</span><span class="sxs-lookup"><span data-stu-id="853fe-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="853fe-126">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="853fe-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-127">Write 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="853fe-128">Read 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="853fe-129">删除树</span><span class="sxs-lookup"><span data-stu-id="853fe-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="853fe-130">子代 msRTCSIP-WebComponents 对象</span><span class="sxs-lookup"><span data-stu-id="853fe-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="853fe-131">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="853fe-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-132">Write 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="853fe-133">Read 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="853fe-134">删除树</span><span class="sxs-lookup"><span data-stu-id="853fe-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="853fe-135">子体 msRTCSIP-MCU 对象</span><span class="sxs-lookup"><span data-stu-id="853fe-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="853fe-136">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="853fe-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-137">Write 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="853fe-138">Read 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="853fe-139">删除树</span><span class="sxs-lookup"><span data-stu-id="853fe-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="853fe-140">子代 msRTCSIP-MediationServer 对象</span><span class="sxs-lookup"><span data-stu-id="853fe-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="853fe-141">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="853fe-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-142">Write 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="853fe-143">Read 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="853fe-144">删除树</span><span class="sxs-lookup"><span data-stu-id="853fe-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="853fe-145">子代 msRTCSIP-ApplicationServer 对象</span><span class="sxs-lookup"><span data-stu-id="853fe-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="853fe-146">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="853fe-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-147">Write 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="853fe-148">Read 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="853fe-149">删除树</span><span class="sxs-lookup"><span data-stu-id="853fe-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="853fe-150">子代 msRTCSIP-ConnectionPoint 对象</span><span class="sxs-lookup"><span data-stu-id="853fe-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="853fe-151">特殊访问：</span><span class="sxs-lookup"><span data-stu-id="853fe-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-152">Write 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="853fe-153">Read 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="853fe-154">删除树</span><span class="sxs-lookup"><span data-stu-id="853fe-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="853fe-155">子体计算机对象</span><span class="sxs-lookup"><span data-stu-id="853fe-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="853fe-156">用于 serviceConnectionPoint 的特殊访问：</span><span class="sxs-lookup"><span data-stu-id="853fe-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-157">创建子对象</span><span class="sxs-lookup"><span data-stu-id="853fe-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="853fe-158">删除子对象</span><span class="sxs-lookup"><span data-stu-id="853fe-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="853fe-159">删除树</span><span class="sxs-lookup"><span data-stu-id="853fe-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="853fe-160">公共信息的特殊访问权限：</span><span class="sxs-lookup"><span data-stu-id="853fe-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-161">Read 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="853fe-162">DNS 主机名的特殊访问权限：</span><span class="sxs-lookup"><span data-stu-id="853fe-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="853fe-163">Read 属性</span><span class="sxs-lookup"><span data-stu-id="853fe-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

