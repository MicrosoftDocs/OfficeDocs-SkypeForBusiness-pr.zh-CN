---
title: Lync Server 2013：注册表
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
ms.openlocfilehash: 4c40fddd324cd687b54d0c3317edc533fa559c8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536689"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="84f92-102">Lync Server 2013 中的注册表</span><span class="sxs-lookup"><span data-stu-id="84f92-102">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84f92-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="84f92-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="84f92-104">每条记录代表一个用户注册事件。</span><span class="sxs-lookup"><span data-stu-id="84f92-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84f92-105">列</span><span class="sxs-lookup"><span data-stu-id="84f92-105">Column</span></span></th>
<th><span data-ttu-id="84f92-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="84f92-106">Data Type</span></span></th>
<th><span data-ttu-id="84f92-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="84f92-107">Key/Index</span></span></th>
<th><span data-ttu-id="84f92-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="84f92-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84f92-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-110">datetime</span><span class="sxs-lookup"><span data-stu-id="84f92-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="84f92-111">主、外</span><span class="sxs-lookup"><span data-stu-id="84f92-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="84f92-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="84f92-112">Time of session request.</span></span> <span data-ttu-id="84f92-113">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="84f92-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="84f92-114">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="84f92-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-116">int</span><span class="sxs-lookup"><span data-stu-id="84f92-116">int</span></span></p></td>
<td><p><span data-ttu-id="84f92-117">主、外</span><span class="sxs-lookup"><span data-stu-id="84f92-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="84f92-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="84f92-118">ID number to identify the session.</span></span> <span data-ttu-id="84f92-119">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="84f92-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="84f92-120">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="84f92-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f92-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-122">int</span><span class="sxs-lookup"><span data-stu-id="84f92-122">int</span></span></p></td>
<td><p><span data-ttu-id="84f92-123">对外</span><span class="sxs-lookup"><span data-stu-id="84f92-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84f92-124">用户 ID。</span><span class="sxs-lookup"><span data-stu-id="84f92-124">The user ID.</span></span> <span data-ttu-id="84f92-125">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="84f92-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="84f92-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-p104">标识注册终结点的 GUID。通常，来自同一用户的同一计算机的注册事件具有相同的终结点 ID。不同计算机具有不同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="84f92-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f92-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-132">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="84f92-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-133">ID 用于区分涉及同一用户和同一终结点的注册。</span><span class="sxs-lookup"><span data-stu-id="84f92-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="84f92-134">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="84f92-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-136">int</span><span class="sxs-lookup"><span data-stu-id="84f92-136">int</span></span></p></td>
<td><p><span data-ttu-id="84f92-137">对外</span><span class="sxs-lookup"><span data-stu-id="84f92-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84f92-138">当前用户的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="84f92-138">Client version of current user.</span></span> <span data-ttu-id="84f92-139">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="84f92-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f92-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-141">int</span><span class="sxs-lookup"><span data-stu-id="84f92-141">int</span></span></p></td>
<td><p><span data-ttu-id="84f92-142">对外</span><span class="sxs-lookup"><span data-stu-id="84f92-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84f92-143">用于注册的注册服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="84f92-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="84f92-144">有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="84f92-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-146">int</span><span class="sxs-lookup"><span data-stu-id="84f92-146">int</span></span></p></td>
<td><p><span data-ttu-id="84f92-147">对外</span><span class="sxs-lookup"><span data-stu-id="84f92-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84f92-148">在其中捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="84f92-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="84f92-149">有关详细信息，请参阅 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="84f92-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f92-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-151">int</span><span class="sxs-lookup"><span data-stu-id="84f92-151">int</span></span></p></td>
<td><p><span data-ttu-id="84f92-152">对外</span><span class="sxs-lookup"><span data-stu-id="84f92-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84f92-153">进行注册的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="84f92-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="84f92-154">有关详细信息，请参阅 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="84f92-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-156">位</span><span class="sxs-lookup"><span data-stu-id="84f92-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-157">用户是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="84f92-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f92-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-159">位</span><span class="sxs-lookup"><span data-stu-id="84f92-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-160">UserService 是否可用。</span><span class="sxs-lookup"><span data-stu-id="84f92-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-162">位</span><span class="sxs-lookup"><span data-stu-id="84f92-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-163">是否注册到主注册器。</span><span class="sxs-lookup"><span data-stu-id="84f92-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f92-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-165">位</span><span class="sxs-lookup"><span data-stu-id="84f92-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-166">指示用户是否通过 Survivable Branch Appliance 注册。</span><span class="sxs-lookup"><span data-stu-id="84f92-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="84f92-167">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="84f92-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-169">datetime</span><span class="sxs-lookup"><span data-stu-id="84f92-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-170">注册时间。</span><span class="sxs-lookup"><span data-stu-id="84f92-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f92-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-172">datetime</span><span class="sxs-lookup"><span data-stu-id="84f92-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-173">注销时间。</span><span class="sxs-lookup"><span data-stu-id="84f92-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-175">int</span><span class="sxs-lookup"><span data-stu-id="84f92-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-176">注册请求的响应代码。</span><span class="sxs-lookup"><span data-stu-id="84f92-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f92-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-178">int</span><span class="sxs-lookup"><span data-stu-id="84f92-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-p109">注册请求的诊断 ID。此 ID 用于指示诊断信息类型。</span><span class="sxs-lookup"><span data-stu-id="84f92-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-182">int</span><span class="sxs-lookup"><span data-stu-id="84f92-182">int</span></span></p></td>
<td><p><span data-ttu-id="84f92-183">对外</span><span class="sxs-lookup"><span data-stu-id="84f92-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84f92-184">发出注册请求的设备。</span><span class="sxs-lookup"><span data-stu-id="84f92-184">The device that the register request is coming from.</span></span> <span data-ttu-id="84f92-185">有关详细信息，请参阅 <a href="lync-server-2013-devices-table.md">Lync Server 2013 中</a> 的 "设备" 表。</span><span class="sxs-lookup"><span data-stu-id="84f92-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f92-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="84f92-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="84f92-188">对外</span><span class="sxs-lookup"><span data-stu-id="84f92-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84f92-189">注销原因，例如“用户已启动”、“注册已过期”、“客户端故障”等。</span><span class="sxs-lookup"><span data-stu-id="84f92-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="84f92-190">有关详细信息，请参阅 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="84f92-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f92-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="84f92-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="84f92-192">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="84f92-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84f92-193">用户在其中注册的终结点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="84f92-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="84f92-194">可以是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="84f92-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="84f92-195">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="84f92-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

