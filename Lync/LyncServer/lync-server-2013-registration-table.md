---
title: Lync Server 2013：Registration 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bc19c35893b12aae7842be5fc474f7831b7f979
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="1f34a-102">Lync Server 2013 中的 Registration 表</span><span class="sxs-lookup"><span data-stu-id="1f34a-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f34a-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1f34a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1f34a-104">每条记录表示一个用户注册事件。</span><span class="sxs-lookup"><span data-stu-id="1f34a-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f34a-105">列</span><span class="sxs-lookup"><span data-stu-id="1f34a-105">Column</span></span></th>
<th><span data-ttu-id="1f34a-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="1f34a-106">Data Type</span></span></th>
<th><span data-ttu-id="1f34a-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="1f34a-107">Key/Index</span></span></th>
<th><span data-ttu-id="1f34a-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="1f34a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1f34a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1f34a-111">主、外部</span><span class="sxs-lookup"><span data-stu-id="1f34a-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f34a-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="1f34a-112">Time of session request.</span></span> <span data-ttu-id="1f34a-113">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="1f34a-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1f34a-114">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f34a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-116">int</span><span class="sxs-lookup"><span data-stu-id="1f34a-116">int</span></span></p></td>
<td><p><span data-ttu-id="1f34a-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="1f34a-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f34a-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1f34a-118">ID number to identify the session.</span></span> <span data-ttu-id="1f34a-119">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="1f34a-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1f34a-120">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f34a-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-122">int</span><span class="sxs-lookup"><span data-stu-id="1f34a-122">int</span></span></p></td>
<td><p><span data-ttu-id="1f34a-123">外表</span><span class="sxs-lookup"><span data-stu-id="1f34a-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f34a-124">用户 ID。</span><span class="sxs-lookup"><span data-stu-id="1f34a-124">The user ID.</span></span> <span data-ttu-id="1f34a-125">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="1f34a-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-127">标识符</span><span class="sxs-lookup"><span data-stu-id="1f34a-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-128">用于标识注册终结点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="1f34a-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="1f34a-129">通常，来自同一用户的同一台计算机的注册事件将具有相同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="1f34a-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="1f34a-130">不同的计算机具有不同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="1f34a-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-132">标识符</span><span class="sxs-lookup"><span data-stu-id="1f34a-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-133">用于区分涉及同一用户和同一终结点的注册的 ID。</span><span class="sxs-lookup"><span data-stu-id="1f34a-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="1f34a-134">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1f34a-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-136">int</span><span class="sxs-lookup"><span data-stu-id="1f34a-136">int</span></span></p></td>
<td><p><span data-ttu-id="1f34a-137">外表</span><span class="sxs-lookup"><span data-stu-id="1f34a-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f34a-138">当前用户的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="1f34a-138">Client version of current user.</span></span> <span data-ttu-id="1f34a-139">有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f34a-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-141">int</span><span class="sxs-lookup"><span data-stu-id="1f34a-141">int</span></span></p></td>
<td><p><span data-ttu-id="1f34a-142">外表</span><span class="sxs-lookup"><span data-stu-id="1f34a-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f34a-143">用于注册的注册机构服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="1f34a-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="1f34a-144">有关详细信息，请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 "服务器" 表。</span><span class="sxs-lookup"><span data-stu-id="1f34a-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-146">int</span><span class="sxs-lookup"><span data-stu-id="1f34a-146">int</span></span></p></td>
<td><p><span data-ttu-id="1f34a-147">外表</span><span class="sxs-lookup"><span data-stu-id="1f34a-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f34a-148">捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="1f34a-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="1f34a-149">有关详细信息，请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f34a-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-151">int</span><span class="sxs-lookup"><span data-stu-id="1f34a-151">int</span></span></p></td>
<td><p><span data-ttu-id="1f34a-152">外表</span><span class="sxs-lookup"><span data-stu-id="1f34a-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f34a-153">注册要使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="1f34a-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="1f34a-154">有关详细信息，请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f34a-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-156">位</span><span class="sxs-lookup"><span data-stu-id="1f34a-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-157">用户是否已从内部登录。</span><span class="sxs-lookup"><span data-stu-id="1f34a-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-159">bit</span><span class="sxs-lookup"><span data-stu-id="1f34a-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-160">UserService 是否可用。</span><span class="sxs-lookup"><span data-stu-id="1f34a-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-162">bit</span><span class="sxs-lookup"><span data-stu-id="1f34a-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-163">是否注册到主注册机构。</span><span class="sxs-lookup"><span data-stu-id="1f34a-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-165">bit</span><span class="sxs-lookup"><span data-stu-id="1f34a-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-166">指示用户是否已向 survivable 分支设备注册。</span><span class="sxs-lookup"><span data-stu-id="1f34a-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="1f34a-167">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1f34a-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-169">datetime</span><span class="sxs-lookup"><span data-stu-id="1f34a-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-170">注册时间。</span><span class="sxs-lookup"><span data-stu-id="1f34a-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-172">datetime</span><span class="sxs-lookup"><span data-stu-id="1f34a-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-173">取消注册时间。</span><span class="sxs-lookup"><span data-stu-id="1f34a-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-175">int</span><span class="sxs-lookup"><span data-stu-id="1f34a-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-176">注册请求的响应代码。</span><span class="sxs-lookup"><span data-stu-id="1f34a-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-178">int</span><span class="sxs-lookup"><span data-stu-id="1f34a-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-179">注册请求的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="1f34a-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="1f34a-180">这表示诊断信息类型。</span><span class="sxs-lookup"><span data-stu-id="1f34a-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-181"><strong>Keyroutedeventargs.deviceid</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-182">int</span><span class="sxs-lookup"><span data-stu-id="1f34a-182">int</span></span></p></td>
<td><p><span data-ttu-id="1f34a-183">外表</span><span class="sxs-lookup"><span data-stu-id="1f34a-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f34a-184">注册请求来自的设备。</span><span class="sxs-lookup"><span data-stu-id="1f34a-184">The device that the register request is coming from.</span></span> <span data-ttu-id="1f34a-185">有关详细信息，请参阅<a href="lync-server-2013-devices-table.md">Lync Server 2013 中</a>的 "设备" 表。</span><span class="sxs-lookup"><span data-stu-id="1f34a-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f34a-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="1f34a-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1f34a-188">外表</span><span class="sxs-lookup"><span data-stu-id="1f34a-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1f34a-189">取消注册的原因，如 "用户启动"、"注册到期"、"客户端失败" 等。</span><span class="sxs-lookup"><span data-stu-id="1f34a-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="1f34a-190">有关详细信息，请参阅<a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f34a-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f34a-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="1f34a-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="1f34a-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f34a-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f34a-193">用户注册到的终结点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1f34a-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="1f34a-194">这可以是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="1f34a-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="1f34a-195">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1f34a-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

