---
title: 'Lync Server 2013: 配置企业语音'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e46bd64efd8aa2eb6e1aead17083aa8593c8544
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="bcac6-102">在 Lync Server 2013 中配置企业语音</span><span class="sxs-lookup"><span data-stu-id="bcac6-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcac6-103">_**主题上次修改时间:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="bcac6-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="bcac6-104">若要部署企业语音, 需要配置下列内容:</span><span class="sxs-lookup"><span data-stu-id="bcac6-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="bcac6-105">创建主干</span><span class="sxs-lookup"><span data-stu-id="bcac6-105">Create a Trunk</span></span>

  - <span data-ttu-id="bcac6-106">定义语音策略</span><span class="sxs-lookup"><span data-stu-id="bcac6-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="bcac6-107">定义语音路线</span><span class="sxs-lookup"><span data-stu-id="bcac6-107">Define a Voice Route</span></span>

  - <span data-ttu-id="bcac6-108">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="bcac6-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="bcac6-109">创建主干</span><span class="sxs-lookup"><span data-stu-id="bcac6-109">Create a Trunk</span></span>

<span data-ttu-id="bcac6-110">您必须在您的企业语音部署中定义中继。</span><span class="sxs-lookup"><span data-stu-id="bcac6-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="bcac6-111">对于基于位置的路由, 必须为每个主干创建中继配置。</span><span class="sxs-lookup"><span data-stu-id="bcac6-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="bcac6-112">使用 Lync Server 拓扑生成器定义你的中继, 并使用 Lync Server Windows PowerShell 命令、新 New-cstrunkconfiguration 或 Lync Server 控制面板定义相应的 trunk 配置。</span><span class="sxs-lookup"><span data-stu-id="bcac6-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="bcac6-113">有关如何在中继配置上启用基于位置的路由的详细信息, 请参阅本部分中的 "在[Lync Server 2013 中启用基于位置的路由](lync-server-2013-enabling-location-based-routing.md)" 中继中的 "基于位置的路由"。</span><span class="sxs-lookup"><span data-stu-id="bcac6-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="bcac6-114">对于此示例, 下表介绍了此方案中使用的中继。</span><span class="sxs-lookup"><span data-stu-id="bcac6-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="bcac6-115">有关详细信息, 请参阅[在 Lync Server 2013 的拓扑生成器中定义其他中继](lync-server-2013-define-additional-trunks-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="bcac6-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="bcac6-116">主干名称</span><span class="sxs-lookup"><span data-stu-id="bcac6-116">Trunk name</span></span></th>
<th><span data-ttu-id="bcac6-117">系统类型</span><span class="sxs-lookup"><span data-stu-id="bcac6-117">System type</span></span></th>
<th><span data-ttu-id="bcac6-118">名称</span><span class="sxs-lookup"><span data-stu-id="bcac6-118">Name</span></span></th>
<th><span data-ttu-id="bcac6-119">位置</span><span class="sxs-lookup"><span data-stu-id="bcac6-119">Location</span></span></th>
<th><span data-ttu-id="bcac6-120">中介服务器</span><span class="sxs-lookup"><span data-stu-id="bcac6-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcac6-121">干线 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="bcac6-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="bcac6-122">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="bcac6-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="bcac6-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="bcac6-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="bcac6-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="bcac6-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="bcac6-125">MS1</span><span class="sxs-lookup"><span data-stu-id="bcac6-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcac6-126">主干 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="bcac6-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="bcac6-127">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="bcac6-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="bcac6-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="bcac6-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="bcac6-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="bcac6-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="bcac6-130">MS1</span><span class="sxs-lookup"><span data-stu-id="bcac6-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcac6-131">干线 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="bcac6-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="bcac6-132">PBX</span><span class="sxs-lookup"><span data-stu-id="bcac6-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="bcac6-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="bcac6-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="bcac6-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="bcac6-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="bcac6-135">MS1</span><span class="sxs-lookup"><span data-stu-id="bcac6-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcac6-136">主干 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="bcac6-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="bcac6-137">PBX</span><span class="sxs-lookup"><span data-stu-id="bcac6-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="bcac6-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="bcac6-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="bcac6-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="bcac6-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="bcac6-140">MS1</span><span class="sxs-lookup"><span data-stu-id="bcac6-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="bcac6-141">定义语音策略</span><span class="sxs-lookup"><span data-stu-id="bcac6-141">Defines Voice Policies</span></span>

<span data-ttu-id="bcac6-142">您必须为您的企业语音部署定义语音策略。</span><span class="sxs-lookup"><span data-stu-id="bcac6-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="bcac6-143">定义语音策略, 以便对用户的子集强制使用基于位置的路由限制 (如果只有它们的子集才能使用基于位置的路由)。</span><span class="sxs-lookup"><span data-stu-id="bcac6-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="bcac6-144">对于此示例, 下表介绍了此方案中使用的语音策略。</span><span class="sxs-lookup"><span data-stu-id="bcac6-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="bcac6-145">只有特定于基于位置的路由的设置才会包含在表中, 以便进行图解。</span><span class="sxs-lookup"><span data-stu-id="bcac6-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="bcac6-146">有关详细信息, 请参阅[配置语音策略和 PSTN 使用记录以在 Lync Server 2013 中授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。</span><span class="sxs-lookup"><span data-stu-id="bcac6-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="bcac6-147">语音策略1</span><span class="sxs-lookup"><span data-stu-id="bcac6-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="bcac6-148">语音政策2</span><span class="sxs-lookup"><span data-stu-id="bcac6-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcac6-149">语音策略 ID</span><span class="sxs-lookup"><span data-stu-id="bcac6-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="bcac6-150">新德里语音政策</span><span class="sxs-lookup"><span data-stu-id="bcac6-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="bcac6-151">Hyderabad 语音政策</span><span class="sxs-lookup"><span data-stu-id="bcac6-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcac6-152">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="bcac6-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="bcac6-153">新德里使用, PBX Del 用法, PBX Hyd 用法</span><span class="sxs-lookup"><span data-stu-id="bcac6-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="bcac6-154">Hyderabad 使用, PBX Hyd 使用, PBX Del 使用</span><span class="sxs-lookup"><span data-stu-id="bcac6-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcac6-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="bcac6-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="bcac6-156">False</span><span class="sxs-lookup"><span data-stu-id="bcac6-156">False</span></span></p></td>
<td><p><span data-ttu-id="bcac6-157">False</span><span class="sxs-lookup"><span data-stu-id="bcac6-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="bcac6-158">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="bcac6-158">Define Voice Routes</span></span>

<span data-ttu-id="bcac6-159">您必须为您的企业语音部署定义语音路由。</span><span class="sxs-lookup"><span data-stu-id="bcac6-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="bcac6-160">对于此示例, 下表介绍了在此方案中使用的语音路线。</span><span class="sxs-lookup"><span data-stu-id="bcac6-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="bcac6-161">只有特定于基于位置的路由的设置才会包含在表中, 以便进行图解。</span><span class="sxs-lookup"><span data-stu-id="bcac6-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="bcac6-162">有关详细信息, 请参阅[在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。</span><span class="sxs-lookup"><span data-stu-id="bcac6-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="bcac6-163">语音路由1</span><span class="sxs-lookup"><span data-stu-id="bcac6-163">Voice route 1</span></span></th>
<th><span data-ttu-id="bcac6-164">语音路由2</span><span class="sxs-lookup"><span data-stu-id="bcac6-164">Voice route 2</span></span></th>
<th><span data-ttu-id="bcac6-165">语音路由3</span><span class="sxs-lookup"><span data-stu-id="bcac6-165">Voice route 3</span></span></th>
<th><span data-ttu-id="bcac6-166">语音路由4</span><span class="sxs-lookup"><span data-stu-id="bcac6-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcac6-167">名称</span><span class="sxs-lookup"><span data-stu-id="bcac6-167">Name</span></span></p></td>
<td><p><span data-ttu-id="bcac6-168">新德里路线</span><span class="sxs-lookup"><span data-stu-id="bcac6-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="bcac6-169">Hyderabad 路线</span><span class="sxs-lookup"><span data-stu-id="bcac6-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="bcac6-170">PBX Del 路由</span><span class="sxs-lookup"><span data-stu-id="bcac6-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="bcac6-171">PBX Hyd 路线</span><span class="sxs-lookup"><span data-stu-id="bcac6-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcac6-172">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="bcac6-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="bcac6-173">新德里使用</span><span class="sxs-lookup"><span data-stu-id="bcac6-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="bcac6-174">Hyderabad 用法</span><span class="sxs-lookup"><span data-stu-id="bcac6-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="bcac6-175">PBX Del 使用</span><span class="sxs-lookup"><span data-stu-id="bcac6-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="bcac6-176">PBX Hyd 使用情况</span><span class="sxs-lookup"><span data-stu-id="bcac6-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bcac6-177">中继</span><span class="sxs-lookup"><span data-stu-id="bcac6-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="bcac6-178">干线 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="bcac6-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="bcac6-179">主干 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="bcac6-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="bcac6-180">干线 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="bcac6-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="bcac6-181">主干 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="bcac6-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="bcac6-182">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="bcac6-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="bcac6-183">为用户启用企业语音, 并为他们分配你以前定义的语音策略。</span><span class="sxs-lookup"><span data-stu-id="bcac6-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="bcac6-184">对于此示例, 下表介绍了此方案中使用的作业。</span><span class="sxs-lookup"><span data-stu-id="bcac6-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="bcac6-185">只有特定于基于位置的路由的设置才会包含在表中, 以便进行图解。</span><span class="sxs-lookup"><span data-stu-id="bcac6-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="bcac6-186">有关详细信息, 请参阅[在 Lync Server 2013 中启用企业语音用户](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="bcac6-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="bcac6-187">位于新德里的用户</span><span class="sxs-lookup"><span data-stu-id="bcac6-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="bcac6-188">位于 Hyderabad 的用户</span><span class="sxs-lookup"><span data-stu-id="bcac6-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bcac6-189">关联的语音政策</span><span class="sxs-lookup"><span data-stu-id="bcac6-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="bcac6-190">新德里语音政策</span><span class="sxs-lookup"><span data-stu-id="bcac6-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="bcac6-191">Hyderabad 语音政策</span><span class="sxs-lookup"><span data-stu-id="bcac6-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bcac6-192">示例用户</span><span class="sxs-lookup"><span data-stu-id="bcac6-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="bcac6-193">DEL-LYNC-1、DEL-LYNC-2、DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="bcac6-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="bcac6-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="bcac6-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bcac6-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcac6-195">See Also</span></span>


[<span data-ttu-id="bcac6-196">在 Lync Server 2013 中配置基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="bcac6-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

