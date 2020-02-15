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
ms.openlocfilehash: 76105b9bee5ce35801196b5a4cd20b2a1feed3e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="ca05f-102">在 Lync Server 2013 中配置企业语音</span><span class="sxs-lookup"><span data-stu-id="ca05f-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca05f-103">_**上次修改的主题：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="ca05f-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="ca05f-104">若要部署企业语音，需要配置以下各项：</span><span class="sxs-lookup"><span data-stu-id="ca05f-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="ca05f-105">创建中继</span><span class="sxs-lookup"><span data-stu-id="ca05f-105">Create a Trunk</span></span>

  - <span data-ttu-id="ca05f-106">定义语音策略</span><span class="sxs-lookup"><span data-stu-id="ca05f-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="ca05f-107">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="ca05f-107">Define a Voice Route</span></span>

  - <span data-ttu-id="ca05f-108">为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="ca05f-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="ca05f-109">创建中继</span><span class="sxs-lookup"><span data-stu-id="ca05f-109">Create a Trunk</span></span>

<span data-ttu-id="ca05f-110">您必须在企业语音部署中定义中继。</span><span class="sxs-lookup"><span data-stu-id="ca05f-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="ca05f-111">对于基于位置的路由，必须为每个中继创建中继配置。</span><span class="sxs-lookup"><span data-stu-id="ca05f-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="ca05f-112">使用 Lync Server 拓扑生成器定义中继，并使用 Lync Server Windows PowerShell 命令、Remove-cstrunkconfiguration 或 Lync Server 控制面板定义相应的中继配置。</span><span class="sxs-lookup"><span data-stu-id="ca05f-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="ca05f-113">有关如何在中继配置上启用基于位置的路由的详细信息，请参阅在中继中启用基于位置的路由的 "在[Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)中启用基于位置的路由" 一节。</span><span class="sxs-lookup"><span data-stu-id="ca05f-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="ca05f-114">对于此示例，下表说明了此方案中使用的中继。</span><span class="sxs-lookup"><span data-stu-id="ca05f-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="ca05f-115">有关详细信息，请参阅[在 Lync Server 2013 中的拓扑生成器中定义其他中继](lync-server-2013-define-additional-trunks-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="ca05f-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="ca05f-116">中继名称</span><span class="sxs-lookup"><span data-stu-id="ca05f-116">Trunk name</span></span></th>
<th><span data-ttu-id="ca05f-117">系统类型</span><span class="sxs-lookup"><span data-stu-id="ca05f-117">System type</span></span></th>
<th><span data-ttu-id="ca05f-118">名称</span><span class="sxs-lookup"><span data-stu-id="ca05f-118">Name</span></span></th>
<th><span data-ttu-id="ca05f-119">位置</span><span class="sxs-lookup"><span data-stu-id="ca05f-119">Location</span></span></th>
<th><span data-ttu-id="ca05f-120">中介服务器</span><span class="sxs-lookup"><span data-stu-id="ca05f-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca05f-121">中继 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="ca05f-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="ca05f-122">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="ca05f-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="ca05f-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="ca05f-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="ca05f-124">德里</span><span class="sxs-lookup"><span data-stu-id="ca05f-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="ca05f-125">MS1</span><span class="sxs-lookup"><span data-stu-id="ca05f-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca05f-126">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="ca05f-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="ca05f-127">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="ca05f-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="ca05f-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="ca05f-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="ca05f-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="ca05f-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="ca05f-130">MS1</span><span class="sxs-lookup"><span data-stu-id="ca05f-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca05f-131">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="ca05f-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="ca05f-132">PBX</span><span class="sxs-lookup"><span data-stu-id="ca05f-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="ca05f-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="ca05f-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="ca05f-134">德里</span><span class="sxs-lookup"><span data-stu-id="ca05f-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="ca05f-135">MS1</span><span class="sxs-lookup"><span data-stu-id="ca05f-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca05f-136">中继 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="ca05f-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="ca05f-137">PBX</span><span class="sxs-lookup"><span data-stu-id="ca05f-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="ca05f-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="ca05f-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="ca05f-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="ca05f-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="ca05f-140">MS1</span><span class="sxs-lookup"><span data-stu-id="ca05f-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="ca05f-141">定义语音策略</span><span class="sxs-lookup"><span data-stu-id="ca05f-141">Defines Voice Policies</span></span>

<span data-ttu-id="ca05f-142">您必须为您的企业语音部署定义语音策略。</span><span class="sxs-lookup"><span data-stu-id="ca05f-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="ca05f-143">定义语音策略，以便向用户的子集强制实施基于位置的路由限制，前提是只有它们的一部分需要使用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="ca05f-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="ca05f-144">对于此示例，下表说明了此方案中使用的语音策略。</span><span class="sxs-lookup"><span data-stu-id="ca05f-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="ca05f-145">为了便于说明，仅在表中包含特定于基于位置的路由的设置。</span><span class="sxs-lookup"><span data-stu-id="ca05f-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="ca05f-146">有关详细信息，请参阅[在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="ca05f-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="ca05f-147">语音策略1</span><span class="sxs-lookup"><span data-stu-id="ca05f-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="ca05f-148">语音策略2</span><span class="sxs-lookup"><span data-stu-id="ca05f-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca05f-149">语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="ca05f-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="ca05f-150">新德里语音策略</span><span class="sxs-lookup"><span data-stu-id="ca05f-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="ca05f-151">Hyderabad 语音策略</span><span class="sxs-lookup"><span data-stu-id="ca05f-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca05f-152">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="ca05f-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="ca05f-153">新德里使用，PBX Del 用法，PBX Hyd 用法</span><span class="sxs-lookup"><span data-stu-id="ca05f-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="ca05f-154">Hyderabad 用法，PBX Hyd usage，PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="ca05f-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca05f-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="ca05f-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="ca05f-156">False</span><span class="sxs-lookup"><span data-stu-id="ca05f-156">False</span></span></p></td>
<td><p><span data-ttu-id="ca05f-157">False</span><span class="sxs-lookup"><span data-stu-id="ca05f-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="ca05f-158">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="ca05f-158">Define Voice Routes</span></span>

<span data-ttu-id="ca05f-159">您必须为您的企业语音部署定义语音路由。</span><span class="sxs-lookup"><span data-stu-id="ca05f-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="ca05f-160">对于此示例，下表说明了此方案中使用的语音路由。</span><span class="sxs-lookup"><span data-stu-id="ca05f-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="ca05f-161">为了便于说明，仅在表中包含特定于基于位置的路由的设置。</span><span class="sxs-lookup"><span data-stu-id="ca05f-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="ca05f-162">有关详细信息，请参阅[在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。</span><span class="sxs-lookup"><span data-stu-id="ca05f-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="ca05f-163">语音路由1</span><span class="sxs-lookup"><span data-stu-id="ca05f-163">Voice route 1</span></span></th>
<th><span data-ttu-id="ca05f-164">语音路由2</span><span class="sxs-lookup"><span data-stu-id="ca05f-164">Voice route 2</span></span></th>
<th><span data-ttu-id="ca05f-165">语音路由3</span><span class="sxs-lookup"><span data-stu-id="ca05f-165">Voice route 3</span></span></th>
<th><span data-ttu-id="ca05f-166">语音路由4</span><span class="sxs-lookup"><span data-stu-id="ca05f-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca05f-167">名称</span><span class="sxs-lookup"><span data-stu-id="ca05f-167">Name</span></span></p></td>
<td><p><span data-ttu-id="ca05f-168">新德里路线</span><span class="sxs-lookup"><span data-stu-id="ca05f-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="ca05f-169">Hyderabad 路由</span><span class="sxs-lookup"><span data-stu-id="ca05f-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="ca05f-170">PBX Del 路由</span><span class="sxs-lookup"><span data-stu-id="ca05f-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="ca05f-171">PBX Hyd 路由</span><span class="sxs-lookup"><span data-stu-id="ca05f-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca05f-172">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="ca05f-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="ca05f-173">新德里使用</span><span class="sxs-lookup"><span data-stu-id="ca05f-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="ca05f-174">Hyderabad 用法</span><span class="sxs-lookup"><span data-stu-id="ca05f-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="ca05f-175">PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="ca05f-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="ca05f-176">PBX Hyd 使用情况</span><span class="sxs-lookup"><span data-stu-id="ca05f-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca05f-177">干线</span><span class="sxs-lookup"><span data-stu-id="ca05f-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="ca05f-178">中继 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="ca05f-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="ca05f-179">Trunk 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="ca05f-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="ca05f-180">Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="ca05f-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="ca05f-181">中继 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="ca05f-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="ca05f-182">为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="ca05f-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="ca05f-183">为用户启用企业语音，并为他们分配之前定义的语音策略。</span><span class="sxs-lookup"><span data-stu-id="ca05f-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="ca05f-184">对于此示例，下表说明了此方案中使用的工作分配。</span><span class="sxs-lookup"><span data-stu-id="ca05f-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="ca05f-185">为了便于说明，仅在表中包含特定于基于位置的路由的设置。</span><span class="sxs-lookup"><span data-stu-id="ca05f-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="ca05f-186">有关详细信息，请参阅[在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="ca05f-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="ca05f-187">位于新德里的用户</span><span class="sxs-lookup"><span data-stu-id="ca05f-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="ca05f-188">位于 Hyderabad 中的用户</span><span class="sxs-lookup"><span data-stu-id="ca05f-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca05f-189">关联的语音策略</span><span class="sxs-lookup"><span data-stu-id="ca05f-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="ca05f-190">新德里语音策略</span><span class="sxs-lookup"><span data-stu-id="ca05f-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="ca05f-191">Hyderabad 语音策略</span><span class="sxs-lookup"><span data-stu-id="ca05f-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca05f-192">示例用户</span><span class="sxs-lookup"><span data-stu-id="ca05f-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="ca05f-193">DEL-LYNC-1，DEL-LYNC-2，DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="ca05f-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="ca05f-194">HYD-LYNC-1，HYD-LYNC-2，HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="ca05f-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca05f-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca05f-195">See Also</span></span>


[<span data-ttu-id="ca05f-196">在 Lync Server 2013 中配置基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="ca05f-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

