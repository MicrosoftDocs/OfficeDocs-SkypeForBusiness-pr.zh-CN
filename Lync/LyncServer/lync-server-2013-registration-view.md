---
title: Lync Server 2013：注册视图
description: Lync Server 2013：注册视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578520"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="fb395-103">Lync Server 2013 中的 "注册" 视图</span><span class="sxs-lookup"><span data-stu-id="fb395-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb395-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fb395-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fb395-105">注册视图存储有关用户注册的信息。</span><span class="sxs-lookup"><span data-stu-id="fb395-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="fb395-106">此视图是在 Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fb395-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb395-107">列</span><span class="sxs-lookup"><span data-stu-id="fb395-107">Column</span></span></th>
<th><span data-ttu-id="fb395-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="fb395-108">Data Type</span></span></th>
<th><span data-ttu-id="fb395-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="fb395-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb395-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-111">datetime</span><span class="sxs-lookup"><span data-stu-id="fb395-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fb395-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="fb395-112">Time of session request.</span></span> <span data-ttu-id="fb395-113">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="fb395-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="fb395-114">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="fb395-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-116">int</span><span class="sxs-lookup"><span data-stu-id="fb395-116">int</span></span></p></td>
<td><p><span data-ttu-id="fb395-117">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="fb395-117">ID number to identify the session.</span></span> <span data-ttu-id="fb395-118">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="fb395-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="fb395-119">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="fb395-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-120"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-121">datetime</span><span class="sxs-lookup"><span data-stu-id="fb395-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="fb395-122">注册发生的时间。</span><span class="sxs-lookup"><span data-stu-id="fb395-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-123"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-124">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="fb395-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fb395-125">注册用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="fb395-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-126"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-127">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-128">注册用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="fb395-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="fb395-129">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="fb395-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-130"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-131">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-132">注册用户的租户。</span><span class="sxs-lookup"><span data-stu-id="fb395-132">Tenant of the user who registered.</span></span> <span data-ttu-id="fb395-133">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="fb395-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-134"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="fb395-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fb395-136">用户注册使用的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="fb395-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-137"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-138">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="fb395-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fb395-139">用于区分涉及相同用户和相同终结点的注册的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="fb395-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-141">datetime</span><span class="sxs-lookup"><span data-stu-id="fb395-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="fb395-142">取消注册发生的时间。</span><span class="sxs-lookup"><span data-stu-id="fb395-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-143"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-144">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-145">取消注册的原因。</span><span class="sxs-lookup"><span data-stu-id="fb395-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-146"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-147">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-148">注册用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="fb395-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-150">int</span><span class="sxs-lookup"><span data-stu-id="fb395-150">int</span></span></p></td>
<td><p><span data-ttu-id="fb395-151">注册用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="fb395-151">Client used by the user who registered.</span></span> <span data-ttu-id="fb395-152">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="fb395-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-153"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-154">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="fb395-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fb395-155">注册用户使用的客户端的类别。</span><span class="sxs-lookup"><span data-stu-id="fb395-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-156"><strong>址</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-157">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-158">用户注册使用的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fb395-158">IP Address the user registered with.</span></span> <span data-ttu-id="fb395-159">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="fb395-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-160"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-161">varstring (775) </span><span class="sxs-lookup"><span data-stu-id="fb395-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="fb395-p108">SIP 对话 ID。格式如下：</span><span class="sxs-lookup"><span data-stu-id="fb395-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="fb395-164">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="fb395-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-166">int</span><span class="sxs-lookup"><span data-stu-id="fb395-166">int</span></span></p></td>
<td><p><span data-ttu-id="fb395-p109">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="fb395-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-170"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-171">int</span><span class="sxs-lookup"><span data-stu-id="fb395-171">int</span></span></p></td>
<td><p><span data-ttu-id="fb395-172">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="fb395-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-173"><strong>注册</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-174">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-175">注册器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb395-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-177">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-178">已捕获会话的数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb395-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-179"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-180">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-181">注册用户使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fb395-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-183">位</span><span class="sxs-lookup"><span data-stu-id="fb395-183">bit</span></span></p></td>
<td><p><span data-ttu-id="fb395-184">指示用户是否是从内部网络登录的。</span><span class="sxs-lookup"><span data-stu-id="fb395-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-185"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-186">位</span><span class="sxs-lookup"><span data-stu-id="fb395-186">bit</span></span></p></td>
<td><p><span data-ttu-id="fb395-187">指示 UserService 在注册时是否可用。</span><span class="sxs-lookup"><span data-stu-id="fb395-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-188"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-189">位</span><span class="sxs-lookup"><span data-stu-id="fb395-189">bit</span></span></p></td>
<td><p><span data-ttu-id="fb395-190">指示注册是否是使用主注册器的注册。</span><span class="sxs-lookup"><span data-stu-id="fb395-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-191"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-192">bigint</span><span class="sxs-lookup"><span data-stu-id="fb395-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="fb395-193">已注册设备的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="fb395-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb395-194"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-195">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-196">已注册设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="fb395-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="fb395-197">有关详细信息，请参阅 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的制造商表</a> 。</span><span class="sxs-lookup"><span data-stu-id="fb395-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb395-198"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="fb395-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fb395-199">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="fb395-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fb395-200">已注册设备的硬件版本。</span><span class="sxs-lookup"><span data-stu-id="fb395-200">Hardware version of the device registered.</span></span> <span data-ttu-id="fb395-201">有关详细信息，请参阅 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="fb395-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

