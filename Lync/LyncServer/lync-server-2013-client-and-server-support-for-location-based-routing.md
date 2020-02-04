---
title: Lync Server 2013：基于位置的路由的客户端和服务器支持
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
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="bb847-102">Lync Server 2013 中基于位置的路由的客户端和服务器支持</span><span class="sxs-lookup"><span data-stu-id="bb847-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb847-103">_**主题上次修改时间：** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="bb847-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="bb847-104">基于位置的路由由 Lync Server 强制执行。</span><span class="sxs-lookup"><span data-stu-id="bb847-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="bb847-105">Lync 服务器可以标识用户从公司网络中连接的网络站点。</span><span class="sxs-lookup"><span data-stu-id="bb847-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="bb847-106">由于远程用户位于企业网络外，其位置将被视为未知。</span><span class="sxs-lookup"><span data-stu-id="bb847-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="bb847-107">Lync Server 支持</span><span class="sxs-lookup"><span data-stu-id="bb847-107">Lync Server Support</span></span>

<span data-ttu-id="bb847-108">基于位置的路由要求 Lync Server 2013 CU1 部署在给定拓扑中的所有前端池和标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="bb847-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="bb847-109">如果在拓扑中的某些 Lync 组件上未安装 Lync Server 2013 CU1，则基于位置的路由限制无法完全强制执行。</span><span class="sxs-lookup"><span data-stu-id="bb847-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="bb847-110">下表标识了基于位置的路由支持的服务器角色和版本的组合。</span><span class="sxs-lookup"><span data-stu-id="bb847-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb847-111">池版本</span><span class="sxs-lookup"><span data-stu-id="bb847-111">Pool version</span></span></th>
<th><span data-ttu-id="bb847-112">中介服务器版本</span><span class="sxs-lookup"><span data-stu-id="bb847-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="bb847-113">支持</span><span class="sxs-lookup"><span data-stu-id="bb847-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb847-114">Lync Server 2013，2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="bb847-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bb847-115">Lync Server 2013，2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="bb847-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bb847-116">支持</span><span class="sxs-lookup"><span data-stu-id="bb847-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb847-117">Lync Server 2013，2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="bb847-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bb847-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb847-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="bb847-119">不支持</span><span class="sxs-lookup"><span data-stu-id="bb847-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb847-120">Lync Server 2013，2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="bb847-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bb847-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bb847-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="bb847-122">不支持</span><span class="sxs-lookup"><span data-stu-id="bb847-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb847-123">Lync Server 2013，2013 2 月累积更新</span><span class="sxs-lookup"><span data-stu-id="bb847-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bb847-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bb847-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="bb847-125">不支持</span><span class="sxs-lookup"><span data-stu-id="bb847-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb847-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb847-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="bb847-127">任意</span><span class="sxs-lookup"><span data-stu-id="bb847-127">any</span></span></p></td>
<td><p><span data-ttu-id="bb847-128">不支持</span><span class="sxs-lookup"><span data-stu-id="bb847-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb847-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bb847-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="bb847-130">任意</span><span class="sxs-lookup"><span data-stu-id="bb847-130">any</span></span></p></td>
<td><p><span data-ttu-id="bb847-131">不支持</span><span class="sxs-lookup"><span data-stu-id="bb847-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb847-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bb847-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="bb847-133">任意</span><span class="sxs-lookup"><span data-stu-id="bb847-133">any</span></span></p></td>
<td><p><span data-ttu-id="bb847-134">不支持</span><span class="sxs-lookup"><span data-stu-id="bb847-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="bb847-135">Lync 客户端支持</span><span class="sxs-lookup"><span data-stu-id="bb847-135">Lync Client Support</span></span>

<span data-ttu-id="bb847-136">下表标识了基于位置的路由支持的客户端。</span><span class="sxs-lookup"><span data-stu-id="bb847-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb847-137">客户端类型</span><span class="sxs-lookup"><span data-stu-id="bb847-137">Client type</span></span></th>
<th><span data-ttu-id="bb847-138">支持</span><span class="sxs-lookup"><span data-stu-id="bb847-138">Supported</span></span></th>
<th><span data-ttu-id="bb847-139">详细信息</span><span class="sxs-lookup"><span data-stu-id="bb847-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb847-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bb847-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="bb847-141">支持</span><span class="sxs-lookup"><span data-stu-id="bb847-141">yes</span></span></p></td>
<td><p><span data-ttu-id="bb847-142">包括 Lync 2013 二月2013累积更新</span><span class="sxs-lookup"><span data-stu-id="bb847-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb847-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bb847-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="bb847-144">支持</span><span class="sxs-lookup"><span data-stu-id="bb847-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb847-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bb847-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="bb847-146">不支持</span><span class="sxs-lookup"><span data-stu-id="bb847-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb847-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="bb847-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="bb847-148">支持</span><span class="sxs-lookup"><span data-stu-id="bb847-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb847-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="bb847-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="bb847-150">支持</span><span class="sxs-lookup"><span data-stu-id="bb847-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb847-151">适用于 Windows 8 的 Lync</span><span class="sxs-lookup"><span data-stu-id="bb847-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="bb847-152">不支持</span><span class="sxs-lookup"><span data-stu-id="bb847-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb847-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="bb847-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="bb847-154">不支持</span><span class="sxs-lookup"><span data-stu-id="bb847-154">no</span></span></p></td>
<td><p><span data-ttu-id="bb847-155">如果启用了基于位置的路由的用户使用，则必须为 Lync Mobile 2013 客户端禁用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="bb847-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb847-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="bb847-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="bb847-157">支持</span><span class="sxs-lookup"><span data-stu-id="bb847-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="bb847-158">若要禁用 Lync Mobile 2013 客户端的 VoIP，请为启用了基于位置的路由的所有用户的设置（IP 音频/视频）分配移动策略。</span><span class="sxs-lookup"><span data-stu-id="bb847-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="bb847-159">有关移动策略的详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>。</span><span class="sxs-lookup"><span data-stu-id="bb847-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb847-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb847-160">See Also</span></span>


[<span data-ttu-id="bb847-161">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="bb847-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

