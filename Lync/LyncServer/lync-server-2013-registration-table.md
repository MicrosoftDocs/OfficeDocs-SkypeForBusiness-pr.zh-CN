---
title: Lync Server 2013：Registration 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="ed1d1-102">Lync Server 2013 中的 Registration 表</span><span class="sxs-lookup"><span data-stu-id="ed1d1-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed1d1-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ed1d1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ed1d1-104">每条记录表示一个用户注册事件。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed1d1-105">列</span><span class="sxs-lookup"><span data-stu-id="ed1d1-105">Column</span></span></th>
<th><span data-ttu-id="ed1d1-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="ed1d1-106">Data Type</span></span></th>
<th><span data-ttu-id="ed1d1-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="ed1d1-107">Key/Index</span></span></th>
<th><span data-ttu-id="ed1d1-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="ed1d1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ed1d1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-111">主、外部</span><span class="sxs-lookup"><span data-stu-id="ed1d1-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-112">Time of session request.</span></span> <span data-ttu-id="ed1d1-113">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ed1d1-114">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-116">int</span><span class="sxs-lookup"><span data-stu-id="ed1d1-116">int</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="ed1d1-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-118">ID number to identify the session.</span></span> <span data-ttu-id="ed1d1-119">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ed1d1-120">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-122">int</span><span class="sxs-lookup"><span data-stu-id="ed1d1-122">int</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-123">外表</span><span class="sxs-lookup"><span data-stu-id="ed1d1-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-124">用户 ID。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-124">The user ID.</span></span> <span data-ttu-id="ed1d1-125">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-127">标识符</span><span class="sxs-lookup"><span data-stu-id="ed1d1-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-128">用于标识注册终结点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="ed1d1-129">通常, 来自同一用户的同一台计算机的注册事件将具有相同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="ed1d1-130">不同的计算机具有不同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-132">标识符</span><span class="sxs-lookup"><span data-stu-id="ed1d1-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-133">用于区分涉及同一用户和同一终结点的注册的 ID。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="ed1d1-134">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-136">int</span><span class="sxs-lookup"><span data-stu-id="ed1d1-136">int</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-137">外表</span><span class="sxs-lookup"><span data-stu-id="ed1d1-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-138">当前用户的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-138">Client version of current user.</span></span> <span data-ttu-id="ed1d1-139">有关详细信息, 请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-141">int</span><span class="sxs-lookup"><span data-stu-id="ed1d1-141">int</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-142">外表</span><span class="sxs-lookup"><span data-stu-id="ed1d1-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-143">用于注册的注册机构服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="ed1d1-144">有关详细信息, 请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 "服务器" 表。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-146">int</span><span class="sxs-lookup"><span data-stu-id="ed1d1-146">int</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-147">外表</span><span class="sxs-lookup"><span data-stu-id="ed1d1-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-148">捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="ed1d1-149">有关详细信息, 请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-151">int</span><span class="sxs-lookup"><span data-stu-id="ed1d1-151">int</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-152">外表</span><span class="sxs-lookup"><span data-stu-id="ed1d1-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-153">注册要使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="ed1d1-154">有关详细信息, 请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-156">位</span><span class="sxs-lookup"><span data-stu-id="ed1d1-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-157">用户是否已从内部登录。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-159">bit</span><span class="sxs-lookup"><span data-stu-id="ed1d1-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-160">UserService 是否可用。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-162">bit</span><span class="sxs-lookup"><span data-stu-id="ed1d1-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-163">是否注册到主注册机构。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-165">bit</span><span class="sxs-lookup"><span data-stu-id="ed1d1-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-166">指示用户是否已向 survivable 分支设备注册。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="ed1d1-167">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-169">datetime</span><span class="sxs-lookup"><span data-stu-id="ed1d1-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-170">注册时间。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-172">datetime</span><span class="sxs-lookup"><span data-stu-id="ed1d1-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-173">取消注册时间。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-175">int</span><span class="sxs-lookup"><span data-stu-id="ed1d1-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-176">注册请求的响应代码。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-178">int</span><span class="sxs-lookup"><span data-stu-id="ed1d1-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-179">注册请求的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="ed1d1-180">这表示诊断信息类型。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-181"><strong>Keyroutedeventargs.deviceid</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-182">int</span><span class="sxs-lookup"><span data-stu-id="ed1d1-182">int</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-183">外表</span><span class="sxs-lookup"><span data-stu-id="ed1d1-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-184">注册请求来自的设备。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-184">The device that the register request is coming from.</span></span> <span data-ttu-id="ed1d1-185">有关详细信息, 请参阅<a href="lync-server-2013-devices-table.md">Lync Server 2013 中</a>的 "设备" 表。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed1d1-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="ed1d1-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-188">外表</span><span class="sxs-lookup"><span data-stu-id="ed1d1-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed1d1-189">取消注册的原因, 如 "用户启动"、"注册到期"、"客户端失败" 等。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="ed1d1-190">有关详细信息, 请参阅<a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed1d1-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="ed1d1-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="ed1d1-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ed1d1-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed1d1-193">用户注册到的终结点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="ed1d1-194">这可以是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="ed1d1-195">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

