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
ms.openlocfilehash: a64bde9cabcae282be83b671115a5cda4e5580e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="3f2ff-102">Lync Server 2013 中的注册表</span><span class="sxs-lookup"><span data-stu-id="3f2ff-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f2ff-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3f2ff-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3f2ff-104">每条记录代表一个用户注册事件。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f2ff-105">列</span><span class="sxs-lookup"><span data-stu-id="3f2ff-105">Column</span></span></th>
<th><span data-ttu-id="3f2ff-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="3f2ff-106">Data Type</span></span></th>
<th><span data-ttu-id="3f2ff-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="3f2ff-107">Key/Index</span></span></th>
<th><span data-ttu-id="3f2ff-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="3f2ff-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-110">datetime</span><span class="sxs-lookup"><span data-stu-id="3f2ff-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-111">主、外</span><span class="sxs-lookup"><span data-stu-id="3f2ff-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-112">Time of session request.</span></span> <span data-ttu-id="3f2ff-113">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="3f2ff-114">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-116">int</span><span class="sxs-lookup"><span data-stu-id="3f2ff-116">int</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-117">主、外</span><span class="sxs-lookup"><span data-stu-id="3f2ff-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-118">ID number to identify the session.</span></span> <span data-ttu-id="3f2ff-119">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="3f2ff-120">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-122">int</span><span class="sxs-lookup"><span data-stu-id="3f2ff-122">int</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-123">对外</span><span class="sxs-lookup"><span data-stu-id="3f2ff-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-124">用户 ID。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-124">The user ID.</span></span> <span data-ttu-id="3f2ff-125">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="3f2ff-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-p104">标识注册终结点的 GUID。通常，来自同一用户的同一计算机的注册事件具有相同的终结点 ID。不同计算机具有不同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-131"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-132">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="3f2ff-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-133">ID 用于区分涉及同一用户和同一终结点的注册。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="3f2ff-134">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-136">int</span><span class="sxs-lookup"><span data-stu-id="3f2ff-136">int</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-137">对外</span><span class="sxs-lookup"><span data-stu-id="3f2ff-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-138">当前用户的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-138">Client version of current user.</span></span> <span data-ttu-id="3f2ff-139">有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-141">int</span><span class="sxs-lookup"><span data-stu-id="3f2ff-141">int</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-142">对外</span><span class="sxs-lookup"><span data-stu-id="3f2ff-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-143">用于注册的注册服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="3f2ff-144">有关详细信息，请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-146">int</span><span class="sxs-lookup"><span data-stu-id="3f2ff-146">int</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-147">对外</span><span class="sxs-lookup"><span data-stu-id="3f2ff-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-148">在其中捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="3f2ff-149">有关详细信息，请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-151">int</span><span class="sxs-lookup"><span data-stu-id="3f2ff-151">int</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-152">对外</span><span class="sxs-lookup"><span data-stu-id="3f2ff-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-153">进行注册的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="3f2ff-154">有关详细信息，请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-156">位</span><span class="sxs-lookup"><span data-stu-id="3f2ff-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-157">用户是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-159">位</span><span class="sxs-lookup"><span data-stu-id="3f2ff-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-160">UserService 是否可用。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-162">位</span><span class="sxs-lookup"><span data-stu-id="3f2ff-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-163">是否注册到主注册器。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-165">位</span><span class="sxs-lookup"><span data-stu-id="3f2ff-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-166">指示用户是否通过 Survivable Branch Appliance 注册。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="3f2ff-167">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-169">datetime</span><span class="sxs-lookup"><span data-stu-id="3f2ff-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-170">注册时间。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-172">datetime</span><span class="sxs-lookup"><span data-stu-id="3f2ff-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-173">注销时间。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-175">int</span><span class="sxs-lookup"><span data-stu-id="3f2ff-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-176">注册请求的响应代码。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-178">int</span><span class="sxs-lookup"><span data-stu-id="3f2ff-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-p109">注册请求的诊断 ID。此 ID 用于指示诊断信息类型。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-182">int</span><span class="sxs-lookup"><span data-stu-id="3f2ff-182">int</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-183">对外</span><span class="sxs-lookup"><span data-stu-id="3f2ff-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-184">发出注册请求的设备。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-184">The device that the register request is coming from.</span></span> <span data-ttu-id="3f2ff-185">有关详细信息，请参阅<a href="lync-server-2013-devices-table.md">Lync Server 2013 中</a>的 "设备" 表。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f2ff-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="3f2ff-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-188">对外</span><span class="sxs-lookup"><span data-stu-id="3f2ff-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3f2ff-189">注销原因，例如“用户已启动”、“注册已过期”、“客户端故障”等。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="3f2ff-190">有关详细信息，请参阅<a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a>。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f2ff-191"><strong>址</strong></span><span class="sxs-lookup"><span data-stu-id="3f2ff-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="3f2ff-192">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="3f2ff-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3f2ff-193">用户在其中注册的终结点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="3f2ff-194">可以是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="3f2ff-195">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3f2ff-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

