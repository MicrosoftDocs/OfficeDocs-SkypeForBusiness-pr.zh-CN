---
title: Lync Server 2013： Location-Based 路由的客户端和服务器支持
description: Lync Server 2013：支持 Location-Based 路由的客户端和服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549628"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="9fa95-103">Lync Server 2013 中的 Location-Based 路由的客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="9fa95-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fa95-104">_**上次修改的主题：** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="9fa95-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="9fa95-105">Location-Based 由 Lync Server 强制执行路由。</span><span class="sxs-lookup"><span data-stu-id="9fa95-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="9fa95-106">Lync Server 可以标识用户从公司网络中连接的网络站点。</span><span class="sxs-lookup"><span data-stu-id="9fa95-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="9fa95-107">由于远程用户位于企业网络外部，因此其位置被视为未知。</span><span class="sxs-lookup"><span data-stu-id="9fa95-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="9fa95-108">Lync Server 支持</span><span class="sxs-lookup"><span data-stu-id="9fa95-108">Lync Server Support</span></span>

<span data-ttu-id="9fa95-109">Location-Based 路由要求在给定拓扑中的所有前端池和 Standard Edition 服务器上部署 Lync Server 2013 CU1。</span><span class="sxs-lookup"><span data-stu-id="9fa95-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="9fa95-110">如果未在拓扑中的某些 Lync 组件上安装 Lync Server 2013 CU1 Location-Based，则不能完全强制执行路由限制。</span><span class="sxs-lookup"><span data-stu-id="9fa95-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="9fa95-111">下表标识 Location-Based 路由支持的服务器角色和版本的组合。</span><span class="sxs-lookup"><span data-stu-id="9fa95-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fa95-112">池版本</span><span class="sxs-lookup"><span data-stu-id="9fa95-112">Pool version</span></span></th>
<th><span data-ttu-id="9fa95-113">中介服务器版本</span><span class="sxs-lookup"><span data-stu-id="9fa95-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="9fa95-114">支持</span><span class="sxs-lookup"><span data-stu-id="9fa95-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fa95-115">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="9fa95-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="9fa95-116">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="9fa95-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="9fa95-117">是</span><span class="sxs-lookup"><span data-stu-id="9fa95-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa95-118">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="9fa95-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="9fa95-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fa95-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="9fa95-120">否</span><span class="sxs-lookup"><span data-stu-id="9fa95-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa95-121">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="9fa95-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="9fa95-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9fa95-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="9fa95-123">否</span><span class="sxs-lookup"><span data-stu-id="9fa95-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa95-124">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="9fa95-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="9fa95-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9fa95-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="9fa95-126">否</span><span class="sxs-lookup"><span data-stu-id="9fa95-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa95-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fa95-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="9fa95-128">任意</span><span class="sxs-lookup"><span data-stu-id="9fa95-128">any</span></span></p></td>
<td><p><span data-ttu-id="9fa95-129">否</span><span class="sxs-lookup"><span data-stu-id="9fa95-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa95-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9fa95-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="9fa95-131">任意</span><span class="sxs-lookup"><span data-stu-id="9fa95-131">any</span></span></p></td>
<td><p><span data-ttu-id="9fa95-132">否</span><span class="sxs-lookup"><span data-stu-id="9fa95-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa95-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9fa95-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="9fa95-134">任意</span><span class="sxs-lookup"><span data-stu-id="9fa95-134">any</span></span></p></td>
<td><p><span data-ttu-id="9fa95-135">否</span><span class="sxs-lookup"><span data-stu-id="9fa95-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="9fa95-136">Lync 客户端支持</span><span class="sxs-lookup"><span data-stu-id="9fa95-136">Lync Client Support</span></span>

<span data-ttu-id="9fa95-137">下表标识 Location-Based 路由支持的客户端。</span><span class="sxs-lookup"><span data-stu-id="9fa95-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fa95-138">客户端类型</span><span class="sxs-lookup"><span data-stu-id="9fa95-138">Client type</span></span></th>
<th><span data-ttu-id="9fa95-139">支持</span><span class="sxs-lookup"><span data-stu-id="9fa95-139">Supported</span></span></th>
<th><span data-ttu-id="9fa95-140">详细信息</span><span class="sxs-lookup"><span data-stu-id="9fa95-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fa95-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9fa95-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="9fa95-142">是</span><span class="sxs-lookup"><span data-stu-id="9fa95-142">yes</span></span></p></td>
<td><p><span data-ttu-id="9fa95-143">包括 Lync 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="9fa95-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa95-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="9fa95-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="9fa95-145">是</span><span class="sxs-lookup"><span data-stu-id="9fa95-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa95-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9fa95-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="9fa95-147">否</span><span class="sxs-lookup"><span data-stu-id="9fa95-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa95-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="9fa95-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="9fa95-149">是</span><span class="sxs-lookup"><span data-stu-id="9fa95-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa95-150">Lync 助理</span><span class="sxs-lookup"><span data-stu-id="9fa95-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="9fa95-151">是</span><span class="sxs-lookup"><span data-stu-id="9fa95-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa95-152">适用于 Windows 8 的 Lync</span><span class="sxs-lookup"><span data-stu-id="9fa95-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="9fa95-153">否</span><span class="sxs-lookup"><span data-stu-id="9fa95-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa95-154">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="9fa95-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="9fa95-155">否</span><span class="sxs-lookup"><span data-stu-id="9fa95-155">no</span></span></p></td>
<td><p><span data-ttu-id="9fa95-156">如果启用 Location-Based 路由的用户使用，则必须对 Lync Mobile 2013 客户端禁用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="9fa95-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa95-157">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="9fa95-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="9fa95-158">是</span><span class="sxs-lookup"><span data-stu-id="9fa95-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="9fa95-159">若要对 Lync Mobile 2013 客户端禁用 VoIP，请为启用了基于位置的路由的所有用户的设置（IP 音频/视频）分配移动策略。</span><span class="sxs-lookup"><span data-stu-id="9fa95-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="9fa95-160">有关移动策略的更多详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">set-csmobilitypolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="9fa95-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9fa95-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fa95-161">See Also</span></span>


[<span data-ttu-id="9fa95-162">在 Lync Server 2013 中规划 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="9fa95-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

