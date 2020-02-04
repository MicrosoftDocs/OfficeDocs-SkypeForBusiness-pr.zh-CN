---
title: Lync Server 2013：注册视图
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
ms.openlocfilehash: 120f0cb40bb3401a327e495a460db400a9359891
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="9c0d0-102">Lync Server 2013 中的注册视图</span><span class="sxs-lookup"><span data-stu-id="9c0d0-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c0d0-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9c0d0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9c0d0-104">"注册" 视图存储有关用户注册的信息。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="9c0d0-105">此视图已引入 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c0d0-106">列</span><span class="sxs-lookup"><span data-stu-id="9c0d0-106">Column</span></span></th>
<th><span data-ttu-id="9c0d0-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="9c0d0-107">Data Type</span></span></th>
<th><span data-ttu-id="9c0d0-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="9c0d0-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9c0d0-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-111">Time of session request.</span></span> <span data-ttu-id="9c0d0-112">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9c0d0-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-115">int</span><span class="sxs-lookup"><span data-stu-id="9c0d0-115">int</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-116">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-116">ID number to identify the session.</span></span> <span data-ttu-id="9c0d0-117">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="9c0d0-118">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-120">datetime</span><span class="sxs-lookup"><span data-stu-id="9c0d0-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-121">发生注册的时间。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-123">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="9c0d0-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-124">注册用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-127">注册用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="9c0d0-128">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-131">注册用户的租户。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-131">Tenant of the user who registered.</span></span> <span data-ttu-id="9c0d0-132">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-134">标识符</span><span class="sxs-lookup"><span data-stu-id="9c0d0-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-135">注册的用户终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-137">标识符</span><span class="sxs-lookup"><span data-stu-id="9c0d0-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-138">唯一标识符，用于区分涉及同一用户和同一终结点的注册。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-140">datetime</span><span class="sxs-lookup"><span data-stu-id="9c0d0-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-141">发生取消注册的时间。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-144">取消注册的原因。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-147">注册用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-149">int</span><span class="sxs-lookup"><span data-stu-id="9c0d0-149">int</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-150">注册用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-150">Client used by the user who registered.</span></span> <span data-ttu-id="9c0d0-151">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-153">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="9c0d0-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-154">注册用户使用的客户端的类别。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-155"><strong>地址</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-157">用户注册使用的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-157">IP Address the user registered with.</span></span> <span data-ttu-id="9c0d0-158">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-160">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="9c0d0-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-161">SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-161">SIP dialog ID.</span></span> <span data-ttu-id="9c0d0-162">的格式为：</span><span class="sxs-lookup"><span data-stu-id="9c0d0-162">The format of the is:</span></span></p>
<p><span data-ttu-id="9c0d0-163">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="9c0d0-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-165">int</span><span class="sxs-lookup"><span data-stu-id="9c0d0-165">int</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-166">会议邀请的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="9c0d0-167">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9c0d0-168">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-170">int</span><span class="sxs-lookup"><span data-stu-id="9c0d0-170">int</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-171">从 SIP 标题捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-172"><strong>注册器</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-174">注册机构的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-177">捕获会话的数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-180">注册用户使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-182">bit</span><span class="sxs-lookup"><span data-stu-id="9c0d0-182">bit</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-183">指示用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-185">bit</span><span class="sxs-lookup"><span data-stu-id="9c0d0-185">bit</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-186">指示 UserService 在注册时是否可用。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-188">bit</span><span class="sxs-lookup"><span data-stu-id="9c0d0-188">bit</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-189">指示注册是否与主注册机构一起注册。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-191">bigint</span><span class="sxs-lookup"><span data-stu-id="9c0d0-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-192">注册的设备的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c0d0-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-195">注册设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="9c0d0-196">有关详细信息，请参阅<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的制造商表</a>。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c0d0-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9c0d0-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9c0d0-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c0d0-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c0d0-199">注册设备的硬件版本。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-199">Hardware version of the device registered.</span></span> <span data-ttu-id="9c0d0-200">有关详细信息，请参阅<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9c0d0-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

