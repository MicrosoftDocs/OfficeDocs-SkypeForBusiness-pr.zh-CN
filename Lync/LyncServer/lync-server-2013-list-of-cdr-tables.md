---
title: Lync Server 2013： CDR 表的列表
description: Lync Server 2013： CDR 表的列表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558698"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="54768-103">Lync Server 2013 中的 CDR 表的列表</span><span class="sxs-lookup"><span data-stu-id="54768-103">List of CDR tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54768-104">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="54768-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="54768-105">呼叫详细信息记录 (CDR) 数据库架构由以下表组成。</span><span class="sxs-lookup"><span data-stu-id="54768-105">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="54768-106">静态表</span><span class="sxs-lookup"><span data-stu-id="54768-106">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54768-107">Table</span><span class="sxs-lookup"><span data-stu-id="54768-107">Table</span></span></th>
<th><span data-ttu-id="54768-108">说明</span><span class="sxs-lookup"><span data-stu-id="54768-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54768-109"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-109"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-110">存储可能的呼叫优先级（例如紧急、紧迫、普通、非紧迫等）列表。</span><span class="sxs-lookup"><span data-stu-id="54768-110">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-112">存储会议加入时间摘要报表所使用的分类边界。</span><span class="sxs-lookup"><span data-stu-id="54768-112">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-113"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-113"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-114">存储可能的用户取消注册原因的列表，如 &quot; 客户端启动、 &quot; &quot; 注册过期、 &quot; &quot; 客户端崩溃等 &quot; 。</span><span class="sxs-lookup"><span data-stu-id="54768-114">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-115"><a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-115"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-116">存储可生成数据库条目的媒体类型（例如，IM、音频、视频和文件传输）列表。</span><span class="sxs-lookup"><span data-stu-id="54768-116">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-117"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 中的 PurgeSettings 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-117"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-118">存储指定是否（以及何时）从 CDR 数据库自动删除过时的呼叫详细信息记录的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-118">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-119"><a href="lync-server-2013-roles-table.md">Lync Server 2013 中的 Roles 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-119"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-120">存储可能的会议角色（例如，与会者和演示者）列表。</span><span class="sxs-lookup"><span data-stu-id="54768-120">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-121"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 中的 SIPResponseMetaData 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-121"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-122">存储 SIP 响应代码列表以及每个代码的分类和定义。</span><span class="sxs-lookup"><span data-stu-id="54768-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="54768-123">支持表</span><span class="sxs-lookup"><span data-stu-id="54768-123">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54768-124">Table</span><span class="sxs-lookup"><span data-stu-id="54768-124">Table</span></span></th>
<th><span data-ttu-id="54768-125">说明</span><span class="sxs-lookup"><span data-stu-id="54768-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54768-126"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-126"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-127">存储呼叫中涉及的每个客户端的客户端信息（客户端类型和版本号）以及在此数据库中捕获的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-127">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-128"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-128"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-129">存储用于会议相关呼叫的 ConferenceURI 列表。</span><span class="sxs-lookup"><span data-stu-id="54768-129">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-130"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-130"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-131">存储用于点对点呼叫和会议呼叫的会话初始协议 (SIP) 内容类型列表。</span><span class="sxs-lookup"><span data-stu-id="54768-131">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-132"><a href="lync-server-2013-devices-table.md">Lync Server 2013 中的 "设备" 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-132"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-133">存储设备列表，包括其制造商、硬件版本和 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="54768-133">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-134"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a></span><span class="sxs-lookup"><span data-stu-id="54768-134"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-135">存储有关数据库中每个会话的对话 ID 的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-135">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-136"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-136"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-137">存储用于外部呼叫的边缘服务器列表。</span><span class="sxs-lookup"><span data-stu-id="54768-137">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-138"><a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a></span><span class="sxs-lookup"><span data-stu-id="54768-138"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-139">存储用于 IP 语音 (VoIP) 呼叫的网关列表。</span><span class="sxs-lookup"><span data-stu-id="54768-139">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-140"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-140"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-141">存储设备（桌面电话）的硬件版本列表。</span><span class="sxs-lookup"><span data-stu-id="54768-141">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-142"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 "制造商" 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-142"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-143">存储设备（桌面电话）的制造商列表。</span><span class="sxs-lookup"><span data-stu-id="54768-143">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-144"><a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 mcu 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-144"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-145">存储有关各种 A/V 会议服务器及其 URI 的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-145">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-146"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-146"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-147">存储用于 VoIP 呼叫的中介服务器列表。</span><span class="sxs-lookup"><span data-stu-id="54768-147">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-148"><a href="lync-server-2013-phones-table.md">Lync Server 2013 中的电话表</a></span><span class="sxs-lookup"><span data-stu-id="54768-148"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-149">存储已存档的或已记录其呼叫详细信息的 VoIP 呼叫使用的所有电话号码。</span><span class="sxs-lookup"><span data-stu-id="54768-149">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-150"><a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-150"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-151">存储在其中捕获 IM 消息的池的名称。</span><span class="sxs-lookup"><span data-stu-id="54768-151">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-152"><a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 "服务器" 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-152"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-153">存储呼叫涉及的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="54768-153">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-154"><a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a></span><span class="sxs-lookup"><span data-stu-id="54768-154"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-155">存储当前部署支持的租户。</span><span class="sxs-lookup"><span data-stu-id="54768-155">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="54768-156">其中包含企业用户、联盟用户、公共 IM 连接用户和匿名用户的某些内置租户。</span><span class="sxs-lookup"><span data-stu-id="54768-156">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-157"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-157"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-158">将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="54768-158">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-159"><a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-159"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-160">存储已参与此数据库中记录或存档的会话的用户的用户 URI。</span><span class="sxs-lookup"><span data-stu-id="54768-160">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-161"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 中的 UserStatistics 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-161"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-162">存储有关单个用户的系统使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-162">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="54768-163">特定于会议 CDR 记录的表</span><span class="sxs-lookup"><span data-stu-id="54768-163">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54768-164">Table</span><span class="sxs-lookup"><span data-stu-id="54768-164">Table</span></span></th>
<th><span data-ttu-id="54768-165">说明</span><span class="sxs-lookup"><span data-stu-id="54768-165">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54768-166"><a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的 "会议" 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-166"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-167">存储有关已存档的或已记录其详细信息的所有会议的信息，包括 ConferenceURI 以及开始时间和结束时间。</span><span class="sxs-lookup"><span data-stu-id="54768-167">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-168"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 中的 ConferenceSessionDetails 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-168"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-169">存储有关每个基于 SIP 的会议会话的信息，包括每个会话的开始时间和结束时间、用户 ID、响应代码以及诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="54768-169">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 中的 FocusJoinsAndLeaves 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-171">存储有关会议加入和离开的信息，包括用户的角色和客户端版本。</span><span class="sxs-lookup"><span data-stu-id="54768-171">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 中的 McuJoinsAndLeaves 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-173">存储有关会议涉及的 A/V 会议服务器以及用户加入和离开时间的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-173">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="54768-174">IM 会议的消息表</span><span class="sxs-lookup"><span data-stu-id="54768-174">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54768-175">Table</span><span class="sxs-lookup"><span data-stu-id="54768-175">Table</span></span></th>
<th><span data-ttu-id="54768-176">说明</span><span class="sxs-lookup"><span data-stu-id="54768-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54768-177"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 中的 ConferenceMessageCount 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-177"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-178">对于每个 IM 会议，存储每个用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="54768-178">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-179"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 中的 IMReportSummary 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-179"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-180">提供有关组织内进行的即时消息会话的全面报告。</span><span class="sxs-lookup"><span data-stu-id="54768-180">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="54768-181">点对点会话表</span><span class="sxs-lookup"><span data-stu-id="54768-181">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54768-182">Table</span><span class="sxs-lookup"><span data-stu-id="54768-182">Table</span></span></th>
<th><span data-ttu-id="54768-183">说明</span><span class="sxs-lookup"><span data-stu-id="54768-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54768-184"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-184"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-185">存储有关每个点对点会话的信息，包括每个用户的开始时间和结束时间、用户 ID、响应代码以及消息计数。</span><span class="sxs-lookup"><span data-stu-id="54768-185">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-186"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 中的 FileTransfers 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-186"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-187">存储有关文件传输会话的信息，包括文件名和结果（接受、拒绝或取消）。</span><span class="sxs-lookup"><span data-stu-id="54768-187">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-188"><a href="lync-server-2013-media-table.md">Lync Server 2013 中的媒体表</a></span><span class="sxs-lookup"><span data-stu-id="54768-188"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-189">存储有关点对点会话涉及的不同媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-189">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="54768-190">VoIP 呼叫详细信息表</span><span class="sxs-lookup"><span data-stu-id="54768-190">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54768-191">Table</span><span class="sxs-lookup"><span data-stu-id="54768-191">Table</span></span></th>
<th><span data-ttu-id="54768-192">说明</span><span class="sxs-lookup"><span data-stu-id="54768-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54768-193"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 中的 VoipDetails 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-193"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-194">对于每个双方 VoIP/PSTN 呼叫，存储有关呼叫的信息，例如 VoIP 电话的电话 ID、使用的网关以及断开连接方。</span><span class="sxs-lookup"><span data-stu-id="54768-194">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="54768-195">将 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a> 称为 "呼叫开始/结束时间" 和 "响应代码"。</span><span class="sxs-lookup"><span data-stu-id="54768-195">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="54768-196">如果呼叫的一方是 VoIP 用户，或者呼叫涉及中介服务器，则会在此表中创建一个记录。</span><span class="sxs-lookup"><span data-stu-id="54768-196">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="54768-197">在 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 的 SessionDetails 表</A>中捕获了有关 VoIP/voip 呼叫的信息，而不涉及公开交换的电话网络 (PSTN) 电话。</span><span class="sxs-lookup"><span data-stu-id="54768-197">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="54768-198">E9-1-1 呼叫审核表</span><span class="sxs-lookup"><span data-stu-id="54768-198">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54768-199">Table</span><span class="sxs-lookup"><span data-stu-id="54768-199">Table</span></span></th>
<th><span data-ttu-id="54768-200">说明</span><span class="sxs-lookup"><span data-stu-id="54768-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54768-201"><a href="lync-server-2013-locations-table.md">Lync Server 2013 中的位置表</a></span><span class="sxs-lookup"><span data-stu-id="54768-201"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-202">对于每个紧急呼叫（例如增强型 9-1-1 (E9-1-1) 呼叫），存储有关该呼叫的位置信息。</span><span class="sxs-lookup"><span data-stu-id="54768-202">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="54768-203">将 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a> 称为 "呼叫开始/结束时间" 和 "响应代码"。</span><span class="sxs-lookup"><span data-stu-id="54768-203">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="54768-p105">该表仅包含 E9-1-1 呼叫的位置 blob。有关呼叫的其他详细信息，请参阅 SessionDetails 表。</span><span class="sxs-lookup"><span data-stu-id="54768-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="54768-206">故障排除表</span><span class="sxs-lookup"><span data-stu-id="54768-206">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54768-207">Table</span><span class="sxs-lookup"><span data-stu-id="54768-207">Table</span></span></th>
<th><span data-ttu-id="54768-208">说明</span><span class="sxs-lookup"><span data-stu-id="54768-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54768-209"><a href="lync-server-2013-application-table.md">Lync Server 2013 中的应用程序表</a></span><span class="sxs-lookup"><span data-stu-id="54768-209"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-210">存储有关在路由和连接中涉及的 Lync Server 2013 中的各种进程的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-210">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-211"><a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-211"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-212">存储有关呼叫类型的信息，例如“音频”、“即时消息”、“音频和视频”以及“应用程序共享”。</span><span class="sxs-lookup"><span data-stu-id="54768-212">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-213"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 中的 ErrorCategory 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-213"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-214">存储每个 Microsoft Lync Server 2013 诊断分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="54768-214">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-215"><a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-215"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-216">存储有关错误类型及其定义的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-216">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-217"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-217"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-218">存储有关发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-218">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-219"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 中的 ProgressReport 表</a></span><span class="sxs-lookup"><span data-stu-id="54768-219"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="54768-220">存储有关 Lync Server 2013 进程中涉及的各种步骤的进度报告的信息。</span><span class="sxs-lookup"><span data-stu-id="54768-220">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="54768-221">以下列表中的表由 Lync Server 内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-221">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="54768-222">本文档不介绍其详细信息。</span><span class="sxs-lookup"><span data-stu-id="54768-222">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="54768-223">供 Lync Server 内部使用的表</span><span class="sxs-lookup"><span data-stu-id="54768-223">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54768-224">Table</span><span class="sxs-lookup"><span data-stu-id="54768-224">Table</span></span></th>
<th><span data-ttu-id="54768-225">说明</span><span class="sxs-lookup"><span data-stu-id="54768-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54768-226"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="54768-226"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-227">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-227">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-228"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="54768-228"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-229">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-229">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-230"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="54768-230"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-231">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-231">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-232"><strong>FrontEnd 表</strong></span><span class="sxs-lookup"><span data-stu-id="54768-232"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-233">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-233">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-234"><strong>MSMQProcessing 表</strong></span><span class="sxs-lookup"><span data-stu-id="54768-234"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-235">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-235">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-236"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="54768-236"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-237">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-237">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-238"><strong>Syndicators 表</strong></span><span class="sxs-lookup"><span data-stu-id="54768-238"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-239">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-239">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-240"><strong>SyndicatorsTenantMap 表</strong></span><span class="sxs-lookup"><span data-stu-id="54768-240"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-241">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-241">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-242"><strong>任务表</strong></span><span class="sxs-lookup"><span data-stu-id="54768-242"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-243">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-243">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-244"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="54768-244"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-245">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-245">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-246"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="54768-246"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-247">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-247">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-248"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="54768-248"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-249">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-249">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-250"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="54768-250"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-251">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-251">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-252"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="54768-252"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-253">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-253">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-254"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="54768-254"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-255">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-255">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-256"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="54768-256"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-257">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-257">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-258"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="54768-258"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-259">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-259">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54768-260"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="54768-260"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-261">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-261">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54768-262"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="54768-262"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="54768-263">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="54768-263">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

