---
title: Lync Server 2013：配置企业语音
description: Lync Server 2013：配置企业语音。
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
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548428"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d466c-103">在 Lync Server 2013 中配置企业语音</span><span class="sxs-lookup"><span data-stu-id="d466c-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d466c-104">_**上次修改的主题：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="d466c-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="d466c-105">若要部署企业语音，需要配置以下各项：</span><span class="sxs-lookup"><span data-stu-id="d466c-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="d466c-106">创建中继</span><span class="sxs-lookup"><span data-stu-id="d466c-106">Create a Trunk</span></span>

  - <span data-ttu-id="d466c-107">定义语音策略</span><span class="sxs-lookup"><span data-stu-id="d466c-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="d466c-108">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="d466c-108">Define a Voice Route</span></span>

  - <span data-ttu-id="d466c-109">为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="d466c-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="d466c-110">创建中继</span><span class="sxs-lookup"><span data-stu-id="d466c-110">Create a Trunk</span></span>

<span data-ttu-id="d466c-111">您必须在企业语音部署中定义中继。</span><span class="sxs-lookup"><span data-stu-id="d466c-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="d466c-112">对于 Location-Based 路由，必须为每个中继创建中继配置。</span><span class="sxs-lookup"><span data-stu-id="d466c-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="d466c-113">使用 Lync Server 拓扑生成器定义中继，并使用 Lync Server Windows PowerShell 命令、Remove-cstrunkconfiguration 或 Lync Server 控制面板定义相应的中继配置。</span><span class="sxs-lookup"><span data-stu-id="d466c-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="d466c-114">有关如何在中继配置中启用 Location-Based 路由的详细信息，请参阅在 [Lync Server 2013 中启用 Location-Based 路由](lync-server-2013-enabling-location-based-routing.md)一节中的 "启用到中继的 Location-Based 路由" 一节。</span><span class="sxs-lookup"><span data-stu-id="d466c-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="d466c-115">对于此示例，下表说明了此方案中使用的中继。</span><span class="sxs-lookup"><span data-stu-id="d466c-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="d466c-116">有关详细信息，请参阅 [在 Lync Server 2013 中的拓扑生成器中定义其他中继](lync-server-2013-define-additional-trunks-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="d466c-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="d466c-117">中继名称</span><span class="sxs-lookup"><span data-stu-id="d466c-117">Trunk name</span></span></th>
<th><span data-ttu-id="d466c-118">系统类型</span><span class="sxs-lookup"><span data-stu-id="d466c-118">System type</span></span></th>
<th><span data-ttu-id="d466c-119">名称</span><span class="sxs-lookup"><span data-stu-id="d466c-119">Name</span></span></th>
<th><span data-ttu-id="d466c-120">位置</span><span class="sxs-lookup"><span data-stu-id="d466c-120">Location</span></span></th>
<th><span data-ttu-id="d466c-121">中介服务器</span><span class="sxs-lookup"><span data-stu-id="d466c-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d466c-122">中继 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d466c-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="d466c-123">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="d466c-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="d466c-124">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d466c-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="d466c-125">德里</span><span class="sxs-lookup"><span data-stu-id="d466c-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d466c-126">MS1</span><span class="sxs-lookup"><span data-stu-id="d466c-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d466c-127">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d466c-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="d466c-128">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="d466c-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="d466c-129">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d466c-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="d466c-130">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d466c-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d466c-131">MS1</span><span class="sxs-lookup"><span data-stu-id="d466c-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d466c-132">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d466c-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="d466c-133">PBX</span><span class="sxs-lookup"><span data-stu-id="d466c-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="d466c-134">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d466c-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="d466c-135">德里</span><span class="sxs-lookup"><span data-stu-id="d466c-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d466c-136">MS1</span><span class="sxs-lookup"><span data-stu-id="d466c-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d466c-137">中继 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="d466c-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="d466c-138">PBX</span><span class="sxs-lookup"><span data-stu-id="d466c-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="d466c-139">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="d466c-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="d466c-140">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d466c-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d466c-141">MS1</span><span class="sxs-lookup"><span data-stu-id="d466c-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="d466c-142">定义语音策略</span><span class="sxs-lookup"><span data-stu-id="d466c-142">Defines Voice Policies</span></span>

<span data-ttu-id="d466c-143">您必须为您的企业语音部署定义语音策略。</span><span class="sxs-lookup"><span data-stu-id="d466c-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="d466c-144">定义语音策略，以强制对部分用户 Location-Based 路由限制，前提是只有它们的一部分需要使用 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="d466c-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="d466c-145">对于此示例，下表说明了此方案中使用的语音策略。</span><span class="sxs-lookup"><span data-stu-id="d466c-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="d466c-146">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="d466c-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="d466c-147">有关详细信息，请参阅 [在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="d466c-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="d466c-148">语音策略1</span><span class="sxs-lookup"><span data-stu-id="d466c-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="d466c-149">语音策略2</span><span class="sxs-lookup"><span data-stu-id="d466c-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d466c-150">语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="d466c-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="d466c-151">新德里语音策略</span><span class="sxs-lookup"><span data-stu-id="d466c-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="d466c-152">Hyderabad 语音策略</span><span class="sxs-lookup"><span data-stu-id="d466c-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d466c-153">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="d466c-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="d466c-154">新德里使用，PBX Del 用法，PBX Hyd 用法</span><span class="sxs-lookup"><span data-stu-id="d466c-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="d466c-155">Hyderabad 用法，PBX Hyd usage，PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="d466c-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d466c-156">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="d466c-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="d466c-157">False</span><span class="sxs-lookup"><span data-stu-id="d466c-157">False</span></span></p></td>
<td><p><span data-ttu-id="d466c-158">False</span><span class="sxs-lookup"><span data-stu-id="d466c-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="d466c-159">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="d466c-159">Define Voice Routes</span></span>

<span data-ttu-id="d466c-160">您必须为您的企业语音部署定义语音路由。</span><span class="sxs-lookup"><span data-stu-id="d466c-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="d466c-161">对于此示例，下表说明了此方案中使用的语音路由。</span><span class="sxs-lookup"><span data-stu-id="d466c-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="d466c-162">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="d466c-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="d466c-163">有关详细信息，请参阅 [在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。</span><span class="sxs-lookup"><span data-stu-id="d466c-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="d466c-164">语音路由1</span><span class="sxs-lookup"><span data-stu-id="d466c-164">Voice route 1</span></span></th>
<th><span data-ttu-id="d466c-165">语音路由2</span><span class="sxs-lookup"><span data-stu-id="d466c-165">Voice route 2</span></span></th>
<th><span data-ttu-id="d466c-166">语音路由3</span><span class="sxs-lookup"><span data-stu-id="d466c-166">Voice route 3</span></span></th>
<th><span data-ttu-id="d466c-167">语音路由4</span><span class="sxs-lookup"><span data-stu-id="d466c-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d466c-168">名称</span><span class="sxs-lookup"><span data-stu-id="d466c-168">Name</span></span></p></td>
<td><p><span data-ttu-id="d466c-169">新德里路线</span><span class="sxs-lookup"><span data-stu-id="d466c-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="d466c-170">Hyderabad 路由</span><span class="sxs-lookup"><span data-stu-id="d466c-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="d466c-171">PBX Del 路由</span><span class="sxs-lookup"><span data-stu-id="d466c-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="d466c-172">PBX Hyd 路由</span><span class="sxs-lookup"><span data-stu-id="d466c-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d466c-173">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="d466c-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="d466c-174">新德里使用</span><span class="sxs-lookup"><span data-stu-id="d466c-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="d466c-175">Hyderabad 用法</span><span class="sxs-lookup"><span data-stu-id="d466c-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="d466c-176">PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="d466c-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="d466c-177">PBX Hyd 使用情况</span><span class="sxs-lookup"><span data-stu-id="d466c-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d466c-178">干线</span><span class="sxs-lookup"><span data-stu-id="d466c-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="d466c-179">中继 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d466c-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="d466c-180">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d466c-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="d466c-181">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d466c-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="d466c-182">中继 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="d466c-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="d466c-183">为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="d466c-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="d466c-184">为用户启用企业语音，并为他们分配之前定义的语音策略。</span><span class="sxs-lookup"><span data-stu-id="d466c-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="d466c-185">对于此示例，下表说明了此方案中使用的工作分配。</span><span class="sxs-lookup"><span data-stu-id="d466c-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="d466c-186">为了便于说明，表中仅包括特定于 Location-Based 路由的设置。</span><span class="sxs-lookup"><span data-stu-id="d466c-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="d466c-187">有关详细信息，请参阅 [在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="d466c-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="d466c-188">位于新德里的用户</span><span class="sxs-lookup"><span data-stu-id="d466c-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="d466c-189">位于 Hyderabad 中的用户</span><span class="sxs-lookup"><span data-stu-id="d466c-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d466c-190">关联的语音策略</span><span class="sxs-lookup"><span data-stu-id="d466c-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="d466c-191">新德里语音策略</span><span class="sxs-lookup"><span data-stu-id="d466c-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="d466c-192">Hyderabad 语音策略</span><span class="sxs-lookup"><span data-stu-id="d466c-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d466c-193">示例用户</span><span class="sxs-lookup"><span data-stu-id="d466c-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="d466c-194">DEL-LYNC-1，DEL-LYNC-2，DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="d466c-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="d466c-195">HYD-LYNC-1，HYD-LYNC-2，HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="d466c-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d466c-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d466c-196">See Also</span></span>


[<span data-ttu-id="d466c-197">在 Lync Server 2013 中配置 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="d466c-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

