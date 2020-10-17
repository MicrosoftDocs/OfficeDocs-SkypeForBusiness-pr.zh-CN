---
title: Lync Server 2013： Location-Based 路由的客户端和服务器支持
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
ms.openlocfilehash: d85e2ce1738ee5de9d4d542cedd7a9e544771938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529339"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="96515-102">Lync Server 2013 中的 Location-Based 路由的客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="96515-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96515-103">_**上次修改的主题：** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="96515-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="96515-104">Location-Based 由 Lync Server 强制执行路由。</span><span class="sxs-lookup"><span data-stu-id="96515-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="96515-105">Lync Server 可以标识用户从公司网络中连接的网络站点。</span><span class="sxs-lookup"><span data-stu-id="96515-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="96515-106">由于远程用户位于企业网络外部，因此其位置被视为未知。</span><span class="sxs-lookup"><span data-stu-id="96515-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="96515-107">Lync Server 支持</span><span class="sxs-lookup"><span data-stu-id="96515-107">Lync Server Support</span></span>

<span data-ttu-id="96515-108">Location-Based 路由要求在给定拓扑中的所有前端池和 Standard Edition 服务器上部署 Lync Server 2013 CU1。</span><span class="sxs-lookup"><span data-stu-id="96515-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="96515-109">如果未在拓扑中的某些 Lync 组件上安装 Lync Server 2013 CU1 Location-Based，则不能完全强制执行路由限制。</span><span class="sxs-lookup"><span data-stu-id="96515-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="96515-110">下表标识 Location-Based 路由支持的服务器角色和版本的组合。</span><span class="sxs-lookup"><span data-stu-id="96515-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96515-111">池版本</span><span class="sxs-lookup"><span data-stu-id="96515-111">Pool version</span></span></th>
<th><span data-ttu-id="96515-112">中介服务器版本</span><span class="sxs-lookup"><span data-stu-id="96515-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="96515-113">支持</span><span class="sxs-lookup"><span data-stu-id="96515-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96515-114">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="96515-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="96515-115">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="96515-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="96515-116">是</span><span class="sxs-lookup"><span data-stu-id="96515-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96515-117">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="96515-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="96515-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96515-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="96515-119">否</span><span class="sxs-lookup"><span data-stu-id="96515-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96515-120">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="96515-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="96515-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="96515-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="96515-122">否</span><span class="sxs-lookup"><span data-stu-id="96515-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96515-123">Lync Server 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="96515-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="96515-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="96515-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="96515-125">否</span><span class="sxs-lookup"><span data-stu-id="96515-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96515-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96515-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="96515-127">任意</span><span class="sxs-lookup"><span data-stu-id="96515-127">any</span></span></p></td>
<td><p><span data-ttu-id="96515-128">否</span><span class="sxs-lookup"><span data-stu-id="96515-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96515-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="96515-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="96515-130">任意</span><span class="sxs-lookup"><span data-stu-id="96515-130">any</span></span></p></td>
<td><p><span data-ttu-id="96515-131">否</span><span class="sxs-lookup"><span data-stu-id="96515-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96515-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="96515-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="96515-133">任意</span><span class="sxs-lookup"><span data-stu-id="96515-133">any</span></span></p></td>
<td><p><span data-ttu-id="96515-134">否</span><span class="sxs-lookup"><span data-stu-id="96515-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="96515-135">Lync 客户端支持</span><span class="sxs-lookup"><span data-stu-id="96515-135">Lync Client Support</span></span>

<span data-ttu-id="96515-136">下表标识 Location-Based 路由支持的客户端。</span><span class="sxs-lookup"><span data-stu-id="96515-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96515-137">客户端类型</span><span class="sxs-lookup"><span data-stu-id="96515-137">Client type</span></span></th>
<th><span data-ttu-id="96515-138">支持</span><span class="sxs-lookup"><span data-stu-id="96515-138">Supported</span></span></th>
<th><span data-ttu-id="96515-139">详细信息</span><span class="sxs-lookup"><span data-stu-id="96515-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96515-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="96515-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="96515-141">是</span><span class="sxs-lookup"><span data-stu-id="96515-141">yes</span></span></p></td>
<td><p><span data-ttu-id="96515-142">包括 Lync 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="96515-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96515-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="96515-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="96515-144">是</span><span class="sxs-lookup"><span data-stu-id="96515-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96515-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="96515-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="96515-146">否</span><span class="sxs-lookup"><span data-stu-id="96515-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96515-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="96515-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="96515-148">是</span><span class="sxs-lookup"><span data-stu-id="96515-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96515-149">Lync 助理</span><span class="sxs-lookup"><span data-stu-id="96515-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="96515-150">是</span><span class="sxs-lookup"><span data-stu-id="96515-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96515-151">适用于 Windows 8 的 Lync</span><span class="sxs-lookup"><span data-stu-id="96515-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="96515-152">否</span><span class="sxs-lookup"><span data-stu-id="96515-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96515-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="96515-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="96515-154">否</span><span class="sxs-lookup"><span data-stu-id="96515-154">no</span></span></p></td>
<td><p><span data-ttu-id="96515-155">如果启用 Location-Based 路由的用户使用，则必须对 Lync Mobile 2013 客户端禁用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="96515-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96515-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="96515-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="96515-157">是</span><span class="sxs-lookup"><span data-stu-id="96515-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="96515-158">若要对 Lync Mobile 2013 客户端禁用 VoIP，请为启用了基于位置的路由的所有用户的设置（IP 音频/视频）分配移动策略。</span><span class="sxs-lookup"><span data-stu-id="96515-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="96515-159">有关移动策略的更多详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">set-csmobilitypolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="96515-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96515-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96515-160">See Also</span></span>


[<span data-ttu-id="96515-161">在 Lync Server 2013 中规划 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="96515-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

