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
ms.openlocfilehash: 1f6a48780535960a71a06f2edfcb6c2b8a95d999
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="1745b-102">Lync Server 2013 中的 "注册" 视图</span><span class="sxs-lookup"><span data-stu-id="1745b-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1745b-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1745b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1745b-104">注册视图存储有关用户注册的信息。</span><span class="sxs-lookup"><span data-stu-id="1745b-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="1745b-105">此视图是在 Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1745b-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1745b-106">列</span><span class="sxs-lookup"><span data-stu-id="1745b-106">Column</span></span></th>
<th><span data-ttu-id="1745b-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="1745b-107">Data Type</span></span></th>
<th><span data-ttu-id="1745b-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="1745b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1745b-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1745b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1745b-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="1745b-111">Time of session request.</span></span> <span data-ttu-id="1745b-112">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="1745b-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="1745b-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="1745b-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-115">int</span><span class="sxs-lookup"><span data-stu-id="1745b-115">int</span></span></p></td>
<td><p><span data-ttu-id="1745b-116">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1745b-116">ID number to identify the session.</span></span> <span data-ttu-id="1745b-117">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="1745b-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="1745b-118">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="1745b-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-120">datetime</span><span class="sxs-lookup"><span data-stu-id="1745b-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="1745b-121">注册发生的时间。</span><span class="sxs-lookup"><span data-stu-id="1745b-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-123">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="1745b-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1745b-124">注册用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="1745b-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-126">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-127">注册用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="1745b-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="1745b-128">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="1745b-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-130">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-131">注册用户的租户。</span><span class="sxs-lookup"><span data-stu-id="1745b-131">Tenant of the user who registered.</span></span> <span data-ttu-id="1745b-132">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="1745b-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1745b-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1745b-135">用户注册使用的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1745b-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-136"><strong>EndpointEra</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-137">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1745b-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1745b-138">用于区分涉及相同用户和相同终结点的注册的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1745b-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-140">datetime</span><span class="sxs-lookup"><span data-stu-id="1745b-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="1745b-141">取消注册发生的时间。</span><span class="sxs-lookup"><span data-stu-id="1745b-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-143">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-144">取消注册的原因。</span><span class="sxs-lookup"><span data-stu-id="1745b-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-146">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-147">注册用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="1745b-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-149">int</span><span class="sxs-lookup"><span data-stu-id="1745b-149">int</span></span></p></td>
<td><p><span data-ttu-id="1745b-150">注册用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="1745b-150">Client used by the user who registered.</span></span> <span data-ttu-id="1745b-151">有关更多详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="1745b-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-153">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="1745b-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1745b-154">注册用户使用的客户端的类别。</span><span class="sxs-lookup"><span data-stu-id="1745b-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-155"><strong>址</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-156">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-157">用户注册使用的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1745b-157">IP Address the user registered with.</span></span> <span data-ttu-id="1745b-158">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="1745b-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-160">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="1745b-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="1745b-p108">SIP 对话 ID。格式如下：</span><span class="sxs-lookup"><span data-stu-id="1745b-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="1745b-163">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="1745b-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-165">int</span><span class="sxs-lookup"><span data-stu-id="1745b-165">int</span></span></p></td>
<td><p><span data-ttu-id="1745b-p109">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="1745b-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-170">int</span><span class="sxs-lookup"><span data-stu-id="1745b-170">int</span></span></p></td>
<td><p><span data-ttu-id="1745b-171">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="1745b-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-172"><strong>注册</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-173">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-174">注册器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1745b-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-176">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-177">已捕获会话的数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1745b-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-179">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-180">注册用户使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1745b-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-182">位</span><span class="sxs-lookup"><span data-stu-id="1745b-182">bit</span></span></p></td>
<td><p><span data-ttu-id="1745b-183">指示用户是否是从内部网络登录的。</span><span class="sxs-lookup"><span data-stu-id="1745b-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-185">位</span><span class="sxs-lookup"><span data-stu-id="1745b-185">bit</span></span></p></td>
<td><p><span data-ttu-id="1745b-186">指示 UserService 在注册时是否可用。</span><span class="sxs-lookup"><span data-stu-id="1745b-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-188">位</span><span class="sxs-lookup"><span data-stu-id="1745b-188">bit</span></span></p></td>
<td><p><span data-ttu-id="1745b-189">指示注册是否是使用主注册器的注册。</span><span class="sxs-lookup"><span data-stu-id="1745b-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-191">bigint</span><span class="sxs-lookup"><span data-stu-id="1745b-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="1745b-192">已注册设备的 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="1745b-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1745b-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-194">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-195">已注册设备的制造商。</span><span class="sxs-lookup"><span data-stu-id="1745b-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="1745b-196">有关详细信息，请参阅<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的制造商表</a>。</span><span class="sxs-lookup"><span data-stu-id="1745b-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1745b-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1745b-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1745b-198">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1745b-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1745b-199">已注册设备的硬件版本。</span><span class="sxs-lookup"><span data-stu-id="1745b-199">Hardware version of the device registered.</span></span> <span data-ttu-id="1745b-200">有关详细信息，请参阅<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="1745b-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

