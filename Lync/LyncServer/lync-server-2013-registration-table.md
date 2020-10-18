---
title: Lync Server 2013：注册表
description: Lync Server 2013：注册表。
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
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578519"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="64edb-103">Lync Server 2013 中的注册表</span><span class="sxs-lookup"><span data-stu-id="64edb-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64edb-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="64edb-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="64edb-105">每条记录代表一个用户注册事件。</span><span class="sxs-lookup"><span data-stu-id="64edb-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64edb-106">列</span><span class="sxs-lookup"><span data-stu-id="64edb-106">Column</span></span></th>
<th><span data-ttu-id="64edb-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="64edb-107">Data Type</span></span></th>
<th><span data-ttu-id="64edb-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="64edb-108">Key/Index</span></span></th>
<th><span data-ttu-id="64edb-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="64edb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64edb-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-111">datetime</span><span class="sxs-lookup"><span data-stu-id="64edb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="64edb-112">主、外</span><span class="sxs-lookup"><span data-stu-id="64edb-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="64edb-113">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="64edb-113">Time of session request.</span></span> <span data-ttu-id="64edb-114">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="64edb-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="64edb-115">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="64edb-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-117">int</span><span class="sxs-lookup"><span data-stu-id="64edb-117">int</span></span></p></td>
<td><p><span data-ttu-id="64edb-118">主、外</span><span class="sxs-lookup"><span data-stu-id="64edb-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="64edb-119">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="64edb-119">ID number to identify the session.</span></span> <span data-ttu-id="64edb-120">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="64edb-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="64edb-121">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="64edb-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64edb-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-123">int</span><span class="sxs-lookup"><span data-stu-id="64edb-123">int</span></span></p></td>
<td><p><span data-ttu-id="64edb-124">对外</span><span class="sxs-lookup"><span data-stu-id="64edb-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64edb-125">用户 ID。</span><span class="sxs-lookup"><span data-stu-id="64edb-125">The user ID.</span></span> <span data-ttu-id="64edb-126">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="64edb-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-127"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-128">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="64edb-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-p104">标识注册终结点的 GUID。通常，来自同一用户的同一计算机的注册事件具有相同的终结点 ID。不同计算机具有不同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="64edb-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64edb-132"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-133">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="64edb-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-134">ID 用于区分涉及同一用户和同一终结点的注册。</span><span class="sxs-lookup"><span data-stu-id="64edb-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="64edb-135">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="64edb-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-136"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-137">int</span><span class="sxs-lookup"><span data-stu-id="64edb-137">int</span></span></p></td>
<td><p><span data-ttu-id="64edb-138">对外</span><span class="sxs-lookup"><span data-stu-id="64edb-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64edb-139">当前用户的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="64edb-139">Client version of current user.</span></span> <span data-ttu-id="64edb-140">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="64edb-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64edb-141"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-142">int</span><span class="sxs-lookup"><span data-stu-id="64edb-142">int</span></span></p></td>
<td><p><span data-ttu-id="64edb-143">对外</span><span class="sxs-lookup"><span data-stu-id="64edb-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64edb-144">用于注册的注册服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="64edb-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="64edb-145">有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="64edb-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-146"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-147">int</span><span class="sxs-lookup"><span data-stu-id="64edb-147">int</span></span></p></td>
<td><p><span data-ttu-id="64edb-148">对外</span><span class="sxs-lookup"><span data-stu-id="64edb-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64edb-149">在其中捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="64edb-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="64edb-150">有关详细信息，请参阅 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="64edb-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64edb-151"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-152">int</span><span class="sxs-lookup"><span data-stu-id="64edb-152">int</span></span></p></td>
<td><p><span data-ttu-id="64edb-153">对外</span><span class="sxs-lookup"><span data-stu-id="64edb-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64edb-154">进行注册的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="64edb-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="64edb-155">有关详细信息，请参阅 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="64edb-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-157">位</span><span class="sxs-lookup"><span data-stu-id="64edb-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-158">用户是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="64edb-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64edb-159"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-160">位</span><span class="sxs-lookup"><span data-stu-id="64edb-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-161">UserService 是否可用。</span><span class="sxs-lookup"><span data-stu-id="64edb-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-162"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-163">位</span><span class="sxs-lookup"><span data-stu-id="64edb-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-164">是否注册到主注册器。</span><span class="sxs-lookup"><span data-stu-id="64edb-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64edb-165"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-166">位</span><span class="sxs-lookup"><span data-stu-id="64edb-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-167">指示用户是否通过 Survivable Branch Appliance 注册。</span><span class="sxs-lookup"><span data-stu-id="64edb-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="64edb-168">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="64edb-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-169"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-170">datetime</span><span class="sxs-lookup"><span data-stu-id="64edb-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-171">注册时间。</span><span class="sxs-lookup"><span data-stu-id="64edb-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64edb-172"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-173">datetime</span><span class="sxs-lookup"><span data-stu-id="64edb-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-174">注销时间。</span><span class="sxs-lookup"><span data-stu-id="64edb-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-176">int</span><span class="sxs-lookup"><span data-stu-id="64edb-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-177">注册请求的响应代码。</span><span class="sxs-lookup"><span data-stu-id="64edb-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64edb-178"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-179">int</span><span class="sxs-lookup"><span data-stu-id="64edb-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-p109">注册请求的诊断 ID。此 ID 用于指示诊断信息类型。</span><span class="sxs-lookup"><span data-stu-id="64edb-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-182"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-183">int</span><span class="sxs-lookup"><span data-stu-id="64edb-183">int</span></span></p></td>
<td><p><span data-ttu-id="64edb-184">对外</span><span class="sxs-lookup"><span data-stu-id="64edb-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64edb-185">发出注册请求的设备。</span><span class="sxs-lookup"><span data-stu-id="64edb-185">The device that the register request is coming from.</span></span> <span data-ttu-id="64edb-186">有关详细信息，请参阅 <a href="lync-server-2013-devices-table.md">Lync Server 2013 中</a> 的 "设备" 表。</span><span class="sxs-lookup"><span data-stu-id="64edb-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64edb-187"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="64edb-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="64edb-189">对外</span><span class="sxs-lookup"><span data-stu-id="64edb-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="64edb-190">注销原因，例如“用户已启动”、“注册已过期”、“客户端故障”等。</span><span class="sxs-lookup"><span data-stu-id="64edb-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="64edb-191">有关详细信息，请参阅 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="64edb-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64edb-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="64edb-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="64edb-193">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="64edb-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="64edb-194">用户在其中注册的终结点的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="64edb-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="64edb-195">可以是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="64edb-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="64edb-196">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="64edb-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

