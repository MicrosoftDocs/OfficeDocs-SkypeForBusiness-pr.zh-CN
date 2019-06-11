---
title: Lync Server 2013：基于位置的路由的客户端和服务器支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="e39bb-102">Lync Server 2013 中基于位置的路由的客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e39bb-103">_**主题上次修改时间:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="e39bb-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="e39bb-104">基于位置的路由由 Lync Server 强制执行。</span><span class="sxs-lookup"><span data-stu-id="e39bb-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="e39bb-105">Lync 服务器可以标识用户从公司网络中连接的网络站点。</span><span class="sxs-lookup"><span data-stu-id="e39bb-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="e39bb-106">由于远程用户位于企业网络外，其位置将被视为未知。</span><span class="sxs-lookup"><span data-stu-id="e39bb-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="e39bb-107">Lync Server 支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-107">Lync Server Support</span></span>

<span data-ttu-id="e39bb-108">基于位置的路由要求 Lync Server 2013 CU1 部署在给定拓扑中的所有前端池和标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="e39bb-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="e39bb-109">如果在拓扑中的某些 Lync 组件上未安装 Lync Server 2013 CU1, 则基于位置的路由限制无法完全强制执行。</span><span class="sxs-lookup"><span data-stu-id="e39bb-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="e39bb-110">下表标识了基于位置的路由支持的服务器角色和版本的组合。</span><span class="sxs-lookup"><span data-stu-id="e39bb-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e39bb-111">池版本</span><span class="sxs-lookup"><span data-stu-id="e39bb-111">Pool version</span></span></th>
<th><span data-ttu-id="e39bb-112">中介服务器版本</span><span class="sxs-lookup"><span data-stu-id="e39bb-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="e39bb-113">支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e39bb-114">Lync Server 2013, 2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="e39bb-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e39bb-115">Lync Server 2013, 2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="e39bb-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e39bb-116">支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39bb-117">Lync Server 2013, 2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="e39bb-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e39bb-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e39bb-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="e39bb-119">不支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39bb-120">Lync Server 2013, 2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="e39bb-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e39bb-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e39bb-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="e39bb-122">不支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39bb-123">Lync Server 2013, 2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="e39bb-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="e39bb-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e39bb-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="e39bb-125">不支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39bb-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e39bb-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="e39bb-127">任意</span><span class="sxs-lookup"><span data-stu-id="e39bb-127">any</span></span></p></td>
<td><p><span data-ttu-id="e39bb-128">不支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39bb-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e39bb-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="e39bb-130">任意</span><span class="sxs-lookup"><span data-stu-id="e39bb-130">any</span></span></p></td>
<td><p><span data-ttu-id="e39bb-131">不支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39bb-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e39bb-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="e39bb-133">任意</span><span class="sxs-lookup"><span data-stu-id="e39bb-133">any</span></span></p></td>
<td><p><span data-ttu-id="e39bb-134">不支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="e39bb-135">Lync 客户端支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-135">Lync Client Support</span></span>

<span data-ttu-id="e39bb-136">下表标识了基于位置的路由支持的客户端。</span><span class="sxs-lookup"><span data-stu-id="e39bb-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e39bb-137">客户端类型</span><span class="sxs-lookup"><span data-stu-id="e39bb-137">Client type</span></span></th>
<th><span data-ttu-id="e39bb-138">支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-138">Supported</span></span></th>
<th><span data-ttu-id="e39bb-139">详细信息</span><span class="sxs-lookup"><span data-stu-id="e39bb-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e39bb-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e39bb-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="e39bb-141">支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-141">yes</span></span></p></td>
<td><p><span data-ttu-id="e39bb-142">包括 Lync 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="e39bb-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39bb-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e39bb-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="e39bb-144">支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39bb-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e39bb-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="e39bb-146">不支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39bb-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="e39bb-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="e39bb-148">支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39bb-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="e39bb-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="e39bb-150">支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39bb-151">适用于 Windows 8 的 Lync</span><span class="sxs-lookup"><span data-stu-id="e39bb-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="e39bb-152">不支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e39bb-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="e39bb-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="e39bb-154">不支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-154">no</span></span></p></td>
<td><p><span data-ttu-id="e39bb-155">如果启用了基于位置的路由的用户使用, 则必须为 Lync Mobile 2013 客户端禁用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="e39bb-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e39bb-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="e39bb-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="e39bb-157">支持</span><span class="sxs-lookup"><span data-stu-id="e39bb-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="e39bb-158">若要禁用 Lync Mobile 2013 客户端的 VoIP, 请为启用了基于位置的路由的所有用户的设置 (IP 音频/视频) 分配移动策略。</span><span class="sxs-lookup"><span data-stu-id="e39bb-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="e39bb-159">有关移动策略的详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="e39bb-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e39bb-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e39bb-160">See Also</span></span>


[<span data-ttu-id="e39bb-161">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="e39bb-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

