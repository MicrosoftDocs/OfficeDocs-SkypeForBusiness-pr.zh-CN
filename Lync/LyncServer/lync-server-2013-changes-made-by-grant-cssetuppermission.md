---
title: 'Lync Server 2013: 通过授予 CsSetupPermission 进行的更改'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="644be-102">Lync Server 2013 中的 "授权-CsSetupPermission" 所做的更改</span><span class="sxs-lookup"><span data-stu-id="644be-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="644be-103">_**主题上次修改时间:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="644be-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="644be-104">若要委派设置, 你可以向特定 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 通用组授予权限, 从而允许该 OU 中的 RTCUniversalServerAdmins 组成员在指定的 Active Directory 中安装 Lync Server 2013不是域管理员组成员的域。</span><span class="sxs-lookup"><span data-stu-id="644be-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="644be-105">**CsSetupPermission** cmdlet 授予对 OU 的 RTCUniversalServerAdmins 组权限, 如下表所示:</span><span class="sxs-lookup"><span data-stu-id="644be-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="644be-106">在 OU 中授予对象的权限</span><span class="sxs-lookup"><span data-stu-id="644be-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="644be-107">权限适用于:</span><span class="sxs-lookup"><span data-stu-id="644be-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="644be-108">授予的权限为:</span><span class="sxs-lookup"><span data-stu-id="644be-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="644be-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="644be-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="644be-110">特殊访问:</span><span class="sxs-lookup"><span data-stu-id="644be-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-111">阅读 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="644be-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="644be-112">写入 servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="644be-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="644be-113">删除树</span><span class="sxs-lookup"><span data-stu-id="644be-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="644be-114">复制目录更改</span><span class="sxs-lookup"><span data-stu-id="644be-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="644be-115">后代 serviceConnectionPoint 对象</span><span class="sxs-lookup"><span data-stu-id="644be-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="644be-116">特殊访问:</span><span class="sxs-lookup"><span data-stu-id="644be-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-117">读取权限</span><span class="sxs-lookup"><span data-stu-id="644be-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="644be-118">写入权限</span><span class="sxs-lookup"><span data-stu-id="644be-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="644be-119">创建子元素</span><span class="sxs-lookup"><span data-stu-id="644be-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="644be-120">删除子元素</span><span class="sxs-lookup"><span data-stu-id="644be-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="644be-121">列表内容</span><span class="sxs-lookup"><span data-stu-id="644be-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="644be-122">Write 属性</span><span class="sxs-lookup"><span data-stu-id="644be-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="644be-123">Read 属性</span><span class="sxs-lookup"><span data-stu-id="644be-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="644be-124">删除树</span><span class="sxs-lookup"><span data-stu-id="644be-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="644be-125">子代 msRTCSIP-服务器对象</span><span class="sxs-lookup"><span data-stu-id="644be-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="644be-126">特殊访问:</span><span class="sxs-lookup"><span data-stu-id="644be-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-127">Write 属性</span><span class="sxs-lookup"><span data-stu-id="644be-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="644be-128">Read 属性</span><span class="sxs-lookup"><span data-stu-id="644be-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="644be-129">删除树</span><span class="sxs-lookup"><span data-stu-id="644be-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="644be-130">子代 msRTCSIP-WebComponents 对象</span><span class="sxs-lookup"><span data-stu-id="644be-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="644be-131">特殊访问:</span><span class="sxs-lookup"><span data-stu-id="644be-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-132">Write 属性</span><span class="sxs-lookup"><span data-stu-id="644be-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="644be-133">Read 属性</span><span class="sxs-lookup"><span data-stu-id="644be-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="644be-134">删除树</span><span class="sxs-lookup"><span data-stu-id="644be-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="644be-135">子体 msRTCSIP-MCU 对象</span><span class="sxs-lookup"><span data-stu-id="644be-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="644be-136">特殊访问:</span><span class="sxs-lookup"><span data-stu-id="644be-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-137">Write 属性</span><span class="sxs-lookup"><span data-stu-id="644be-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="644be-138">Read 属性</span><span class="sxs-lookup"><span data-stu-id="644be-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="644be-139">删除树</span><span class="sxs-lookup"><span data-stu-id="644be-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="644be-140">子代 msRTCSIP-MediationServer 对象</span><span class="sxs-lookup"><span data-stu-id="644be-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="644be-141">特殊访问:</span><span class="sxs-lookup"><span data-stu-id="644be-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-142">Write 属性</span><span class="sxs-lookup"><span data-stu-id="644be-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="644be-143">Read 属性</span><span class="sxs-lookup"><span data-stu-id="644be-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="644be-144">删除树</span><span class="sxs-lookup"><span data-stu-id="644be-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="644be-145">子代 msRTCSIP-ApplicationServer 对象</span><span class="sxs-lookup"><span data-stu-id="644be-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="644be-146">特殊访问:</span><span class="sxs-lookup"><span data-stu-id="644be-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-147">Write 属性</span><span class="sxs-lookup"><span data-stu-id="644be-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="644be-148">Read 属性</span><span class="sxs-lookup"><span data-stu-id="644be-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="644be-149">删除树</span><span class="sxs-lookup"><span data-stu-id="644be-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="644be-150">子代 msRTCSIP-ConnectionPoint 对象</span><span class="sxs-lookup"><span data-stu-id="644be-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="644be-151">特殊访问:</span><span class="sxs-lookup"><span data-stu-id="644be-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-152">Write 属性</span><span class="sxs-lookup"><span data-stu-id="644be-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="644be-153">Read 属性</span><span class="sxs-lookup"><span data-stu-id="644be-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="644be-154">删除树</span><span class="sxs-lookup"><span data-stu-id="644be-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="644be-155">子体计算机对象</span><span class="sxs-lookup"><span data-stu-id="644be-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="644be-156">用于 serviceConnectionPoint 的特殊访问:</span><span class="sxs-lookup"><span data-stu-id="644be-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-157">创建子对象</span><span class="sxs-lookup"><span data-stu-id="644be-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="644be-158">删除子对象</span><span class="sxs-lookup"><span data-stu-id="644be-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="644be-159">删除树</span><span class="sxs-lookup"><span data-stu-id="644be-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="644be-160">公共信息的特殊访问权限:</span><span class="sxs-lookup"><span data-stu-id="644be-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-161">Read 属性</span><span class="sxs-lookup"><span data-stu-id="644be-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="644be-162">DNS 主机名的特殊访问权限:</span><span class="sxs-lookup"><span data-stu-id="644be-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="644be-163">Read 属性</span><span class="sxs-lookup"><span data-stu-id="644be-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

