---
title: Lync Server 2013：配置企业语音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca998a723e4ef84fc1c203d6eddc5f9016f28739
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532549"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="5647b-102">在 Lync Server 2013 中配置企业语音</span><span class="sxs-lookup"><span data-stu-id="5647b-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5647b-103">_**上次修改的主题：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="5647b-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="5647b-104">若要部署企业语音，需要配置以下各项：</span><span class="sxs-lookup"><span data-stu-id="5647b-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="5647b-105">创建中继</span><span class="sxs-lookup"><span data-stu-id="5647b-105">Create a Trunk</span></span>

  - <span data-ttu-id="5647b-106">定义语音策略</span><span class="sxs-lookup"><span data-stu-id="5647b-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="5647b-107">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="5647b-107">Define a Voice Route</span></span>

  - <span data-ttu-id="5647b-108">为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="5647b-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="5647b-109">创建中继</span><span class="sxs-lookup"><span data-stu-id="5647b-109">Create a Trunk</span></span>

<span data-ttu-id="5647b-110">您必须在企业语音部署中定义中继。</span><span class="sxs-lookup"><span data-stu-id="5647b-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="5647b-111">对于 Location-Based 路由，必须为每个中继创建中继配置。</span><span class="sxs-lookup"><span data-stu-id="5647b-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="5647b-112">使用 Lync Server 拓扑生成器定义中继，并使用 Lync Server Windows PowerShell 命令、Remove-cstrunkconfiguration 或 Lync Server 控制面板定义相应的中继配置。</span><span class="sxs-lookup"><span data-stu-id="5647b-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="5647b-113">有关如何在中继配置中启用 Location-Based 路由的详细信息，请参阅在 [Lync Server 2013 中启用 Location-Based 路由](lync-server-2013-enabling-location-based-routing.md)一节中的 "启用到中继的 Location-Based 路由" 一节。</span><span class="sxs-lookup"><span data-stu-id="5647b-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="5647b-114">对于此示例，下表说明了此方案中使用的中继。</span><span class="sxs-lookup"><span data-stu-id="5647b-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="5647b-115">有关详细信息，请参阅 [在 Lync Server 2013 中的拓扑生成器中定义其他中继](lync-server-2013-define-additional-trunks-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="5647b-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5647b-116">中继名称</span><span class="sxs-lookup"><span data-stu-id="5647b-116">Trunk name</span></span></th>
<th><span data-ttu-id="5647b-117">系统类型</span><span class="sxs-lookup"><span data-stu-id="5647b-117">System type</span></span></th>
<th><span data-ttu-id="5647b-118">名称</span><span class="sxs-lookup"><span data-stu-id="5647b-118">Name</span></span></th>
<th><span data-ttu-id="5647b-119">位置</span><span class="sxs-lookup"><span data-stu-id="5647b-119">Location</span></span></th>
<th><span data-ttu-id="5647b-120">中介服务器</span><span class="sxs-lookup"><span data-stu-id="5647b-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5647b-121">中继 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="5647b-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="5647b-122">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="5647b-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="5647b-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="5647b-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="5647b-124">德里</span><span class="sxs-lookup"><span data-stu-id="5647b-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="5647b-125">MS1</span><span class="sxs-lookup"><span data-stu-id="5647b-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5647b-126">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="5647b-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="5647b-127">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="5647b-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="5647b-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="5647b-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="5647b-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="5647b-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="5647b-130">MS1</span><span class="sxs-lookup"><span data-stu-id="5647b-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5647b-131">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="5647b-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="5647b-132">PBX</span><span class="sxs-lookup"><span data-stu-id="5647b-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="5647b-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="5647b-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="5647b-134">德里</span><span class="sxs-lookup"><span data-stu-id="5647b-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="5647b-135">MS1</span><span class="sxs-lookup"><span data-stu-id="5647b-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5647b-136">中继 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="5647b-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="5647b-137">PBX</span><span class="sxs-lookup"><span data-stu-id="5647b-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="5647b-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="5647b-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="5647b-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="5647b-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="5647b-140">MS1</span><span class="sxs-lookup"><span data-stu-id="5647b-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="5647b-141">定义语音策略</span><span class="sxs-lookup"><span data-stu-id="5647b-141">Defines Voice Policies</span></span>

<span data-ttu-id="5647b-142">您必须为您的企业语音部署定义语音策略。</span><span class="sxs-lookup"><span data-stu-id="5647b-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="5647b-143">定义语音策略，以强制对部分用户 Location-Based 路由限制，前提是只有它们的一部分需要使用 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="5647b-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="5647b-144">对于此示例，下表说明了此方案中使用的语音策略。</span><span class="sxs-lookup"><span data-stu-id="5647b-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="5647b-145">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="5647b-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="5647b-146">有关详细信息，请参阅 [在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="5647b-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="5647b-147">语音策略1</span><span class="sxs-lookup"><span data-stu-id="5647b-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="5647b-148">语音策略2</span><span class="sxs-lookup"><span data-stu-id="5647b-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5647b-149">语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="5647b-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="5647b-150">新德里语音策略</span><span class="sxs-lookup"><span data-stu-id="5647b-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="5647b-151">Hyderabad 语音策略</span><span class="sxs-lookup"><span data-stu-id="5647b-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5647b-152">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="5647b-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="5647b-153">新德里使用，PBX Del 用法，PBX Hyd 用法</span><span class="sxs-lookup"><span data-stu-id="5647b-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="5647b-154">Hyderabad 用法，PBX Hyd usage，PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="5647b-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5647b-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="5647b-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="5647b-156">False</span><span class="sxs-lookup"><span data-stu-id="5647b-156">False</span></span></p></td>
<td><p><span data-ttu-id="5647b-157">False</span><span class="sxs-lookup"><span data-stu-id="5647b-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="5647b-158">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="5647b-158">Define Voice Routes</span></span>

<span data-ttu-id="5647b-159">您必须为您的企业语音部署定义语音路由。</span><span class="sxs-lookup"><span data-stu-id="5647b-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="5647b-160">对于此示例，下表说明了此方案中使用的语音路由。</span><span class="sxs-lookup"><span data-stu-id="5647b-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="5647b-161">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="5647b-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="5647b-162">有关详细信息，请参阅 [在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。</span><span class="sxs-lookup"><span data-stu-id="5647b-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="5647b-163">语音路由1</span><span class="sxs-lookup"><span data-stu-id="5647b-163">Voice route 1</span></span></th>
<th><span data-ttu-id="5647b-164">语音路由2</span><span class="sxs-lookup"><span data-stu-id="5647b-164">Voice route 2</span></span></th>
<th><span data-ttu-id="5647b-165">语音路由3</span><span class="sxs-lookup"><span data-stu-id="5647b-165">Voice route 3</span></span></th>
<th><span data-ttu-id="5647b-166">语音路由4</span><span class="sxs-lookup"><span data-stu-id="5647b-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5647b-167">名称</span><span class="sxs-lookup"><span data-stu-id="5647b-167">Name</span></span></p></td>
<td><p><span data-ttu-id="5647b-168">新德里路线</span><span class="sxs-lookup"><span data-stu-id="5647b-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="5647b-169">Hyderabad 路由</span><span class="sxs-lookup"><span data-stu-id="5647b-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="5647b-170">PBX Del 路由</span><span class="sxs-lookup"><span data-stu-id="5647b-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="5647b-171">PBX Hyd 路由</span><span class="sxs-lookup"><span data-stu-id="5647b-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5647b-172">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="5647b-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="5647b-173">新德里使用</span><span class="sxs-lookup"><span data-stu-id="5647b-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="5647b-174">Hyderabad 用法</span><span class="sxs-lookup"><span data-stu-id="5647b-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="5647b-175">PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="5647b-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="5647b-176">PBX Hyd 使用情况</span><span class="sxs-lookup"><span data-stu-id="5647b-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5647b-177">干线</span><span class="sxs-lookup"><span data-stu-id="5647b-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="5647b-178">中继 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="5647b-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="5647b-179">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="5647b-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="5647b-180">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="5647b-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="5647b-181">中继 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="5647b-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="5647b-182">为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="5647b-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="5647b-183">为用户启用企业语音，并为他们分配之前定义的语音策略。</span><span class="sxs-lookup"><span data-stu-id="5647b-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="5647b-184">对于此示例，下表说明了此方案中使用的工作分配。</span><span class="sxs-lookup"><span data-stu-id="5647b-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="5647b-185">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="5647b-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="5647b-186">有关详细信息，请参阅 [在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="5647b-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="5647b-187">位于新德里的用户</span><span class="sxs-lookup"><span data-stu-id="5647b-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="5647b-188">位于 Hyderabad 中的用户</span><span class="sxs-lookup"><span data-stu-id="5647b-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5647b-189">关联的语音策略</span><span class="sxs-lookup"><span data-stu-id="5647b-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="5647b-190">新德里语音策略</span><span class="sxs-lookup"><span data-stu-id="5647b-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="5647b-191">Hyderabad 语音策略</span><span class="sxs-lookup"><span data-stu-id="5647b-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5647b-192">示例用户</span><span class="sxs-lookup"><span data-stu-id="5647b-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="5647b-193">DEL-LYNC-1，DEL-LYNC-2，DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="5647b-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="5647b-194">HYD-LYNC-1，HYD-LYNC-2，HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="5647b-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5647b-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5647b-195">See Also</span></span>


[<span data-ttu-id="5647b-196">在 Lync Server 2013 中配置 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="5647b-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

