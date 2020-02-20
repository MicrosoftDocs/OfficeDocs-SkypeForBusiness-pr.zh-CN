---
title: Lync Server 2013： CDR 表的列表
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
ms.openlocfilehash: b2792988c24ad412c80c18a4c334d1af54bbcf3a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="1bb35-102">Lync Server 2013 中的 CDR 表的列表</span><span class="sxs-lookup"><span data-stu-id="1bb35-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bb35-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1bb35-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1bb35-104">呼叫详细信息记录 (CDR) 数据库架构由以下表组成。</span><span class="sxs-lookup"><span data-stu-id="1bb35-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="1bb35-105">静态表</span><span class="sxs-lookup"><span data-stu-id="1bb35-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bb35-106">Table</span><span class="sxs-lookup"><span data-stu-id="1bb35-106">Table</span></span></th>
<th><span data-ttu-id="1bb35-107">说明</span><span class="sxs-lookup"><span data-stu-id="1bb35-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-108"><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-109">存储可能的呼叫优先级（例如紧急、紧迫、普通、非紧迫等）列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-111">存储会议加入时间摘要报表所使用的分类边界。</span><span class="sxs-lookup"><span data-stu-id="1bb35-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-112"><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-113">存储可能的用户取消注册原因&quot;的列表，如客户端启动、&quot; &quot;注册过期、&quot; &quot;客户端崩溃&quot;等。</span><span class="sxs-lookup"><span data-stu-id="1bb35-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-114"><a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-115">存储可生成数据库条目的媒体类型（例如，IM、音频、视频和文件传输）列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-116"><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 中的 PurgeSettings 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-117">存储指定是否（以及何时）从 CDR 数据库自动删除过时的呼叫详细信息记录的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-118"><a href="lync-server-2013-roles-table.md">Lync Server 2013 中的 Roles 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-119">存储可能的会议角色（例如，与会者和演示者）列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 中的 SIPResponseMetaData 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-121">存储 SIP 响应代码列表以及每个代码的分类和定义。</span><span class="sxs-lookup"><span data-stu-id="1bb35-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="1bb35-122">支持表</span><span class="sxs-lookup"><span data-stu-id="1bb35-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bb35-123">Table</span><span class="sxs-lookup"><span data-stu-id="1bb35-123">Table</span></span></th>
<th><span data-ttu-id="1bb35-124">说明</span><span class="sxs-lookup"><span data-stu-id="1bb35-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-125"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-126">存储呼叫中涉及的每个客户端的客户端信息（客户端类型和版本号）以及在此数据库中捕获的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-127"><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-128">存储用于会议相关呼叫的 ConferenceURI 列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-129"><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-130">存储用于点对点呼叫和会议呼叫的会话初始协议 (SIP) 内容类型列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-131"><a href="lync-server-2013-devices-table.md">Lync Server 2013 中的 "设备" 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-132">存储设备列表，包括其制造商、硬件版本和 MAC 地址。</span><span class="sxs-lookup"><span data-stu-id="1bb35-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-133"><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-134">存储有关数据库中每个会话的对话 ID 的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-135"><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-136">存储用于外部呼叫的边缘服务器列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-137"><a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-138">存储用于 IP 语音 (VoIP) 呼叫的网关列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-139"><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-140">存储设备（桌面电话）的硬件版本列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-141"><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 "制造商" 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-142">存储设备（桌面电话）的制造商列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-143"><a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 mcu 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-144">存储有关各种 A/V 会议服务器及其 URI 的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-145"><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-146">存储用于 VoIP 呼叫的中介服务器列表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-147"><a href="lync-server-2013-phones-table.md">Lync Server 2013 中的电话表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-148">存储已存档的或已记录其呼叫详细信息的 VoIP 呼叫使用的所有电话号码。</span><span class="sxs-lookup"><span data-stu-id="1bb35-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-149"><a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-150">存储在其中捕获 IM 消息的池的名称。</span><span class="sxs-lookup"><span data-stu-id="1bb35-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-151"><a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 "服务器" 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-152">存储呼叫涉及的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="1bb35-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-153"><a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-154">存储当前部署支持的租户。</span><span class="sxs-lookup"><span data-stu-id="1bb35-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="1bb35-155">其中包含企业用户、联盟用户、公共 IM 连接用户和匿名用户的某些内置租户。</span><span class="sxs-lookup"><span data-stu-id="1bb35-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-156"><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-157">将用户代理标识符映射到代理的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="1bb35-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-158"><a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-159">存储已参与此数据库中记录或存档的会话的用户的用户 URI。</span><span class="sxs-lookup"><span data-stu-id="1bb35-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-160"><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 中的 UserStatistics 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-161">存储有关单个用户的系统使用情况的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="1bb35-162">特定于会议 CDR 记录的表</span><span class="sxs-lookup"><span data-stu-id="1bb35-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bb35-163">Table</span><span class="sxs-lookup"><span data-stu-id="1bb35-163">Table</span></span></th>
<th><span data-ttu-id="1bb35-164">说明</span><span class="sxs-lookup"><span data-stu-id="1bb35-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-165"><a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的 "会议" 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-166">存储有关已存档的或已记录其详细信息的所有会议的信息，包括 ConferenceURI 以及开始时间和结束时间。</span><span class="sxs-lookup"><span data-stu-id="1bb35-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 中的 ConferenceSessionDetails 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-168">存储有关每个基于 SIP 的会议会话的信息，包括每个会话的开始时间和结束时间、用户 ID、响应代码以及诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="1bb35-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 中的 FocusJoinsAndLeaves 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-170">存储有关会议加入和离开的信息，包括用户的角色和客户端版本。</span><span class="sxs-lookup"><span data-stu-id="1bb35-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 中的 McuJoinsAndLeaves 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-172">存储有关会议涉及的 A/V 会议服务器以及用户加入和离开时间的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="1bb35-173">IM 会议的消息表</span><span class="sxs-lookup"><span data-stu-id="1bb35-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bb35-174">Table</span><span class="sxs-lookup"><span data-stu-id="1bb35-174">Table</span></span></th>
<th><span data-ttu-id="1bb35-175">说明</span><span class="sxs-lookup"><span data-stu-id="1bb35-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-176"><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 中的 ConferenceMessageCount 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-177">对于每个 IM 会议，存储每个用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="1bb35-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-178"><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 中的 IMReportSummary 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-179">提供有关组织内进行的即时消息会话的全面报告。</span><span class="sxs-lookup"><span data-stu-id="1bb35-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="1bb35-180">点对点会话表</span><span class="sxs-lookup"><span data-stu-id="1bb35-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bb35-181">Table</span><span class="sxs-lookup"><span data-stu-id="1bb35-181">Table</span></span></th>
<th><span data-ttu-id="1bb35-182">说明</span><span class="sxs-lookup"><span data-stu-id="1bb35-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-183"><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-184">存储有关每个点对点会话的信息，包括每个用户的开始时间和结束时间、用户 ID、响应代码以及消息计数。</span><span class="sxs-lookup"><span data-stu-id="1bb35-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-185"><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 中的 FileTransfers 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-186">存储有关文件传输会话的信息，包括文件名和结果（接受、拒绝或取消）。</span><span class="sxs-lookup"><span data-stu-id="1bb35-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-187"><a href="lync-server-2013-media-table.md">Lync Server 2013 中的媒体表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-188">存储有关点对点会话涉及的不同媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="1bb35-189">VoIP 呼叫详细信息表</span><span class="sxs-lookup"><span data-stu-id="1bb35-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bb35-190">Table</span><span class="sxs-lookup"><span data-stu-id="1bb35-190">Table</span></span></th>
<th><span data-ttu-id="1bb35-191">说明</span><span class="sxs-lookup"><span data-stu-id="1bb35-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-192"><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 中的 VoipDetails 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-193">对于每个双方 VoIP/PSTN 呼叫，存储有关呼叫的信息，例如 VoIP 电话的电话 ID、使用的网关以及断开连接方。</span><span class="sxs-lookup"><span data-stu-id="1bb35-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="1bb35-194">将<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a>称为 "呼叫开始/结束时间" 和 "响应代码"。</span><span class="sxs-lookup"><span data-stu-id="1bb35-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1bb35-195">如果呼叫的一方是 VoIP 用户，或者呼叫涉及中介服务器，则会在此表中创建一个记录。</span><span class="sxs-lookup"><span data-stu-id="1bb35-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="1bb35-196">在<A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 的 SessionDetails 表</A>中捕获有关不涉及公用电话交换网（PSTN）电话的 VoIP/voip 呼叫的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="1bb35-197">E9-1-1 呼叫审核表</span><span class="sxs-lookup"><span data-stu-id="1bb35-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bb35-198">Table</span><span class="sxs-lookup"><span data-stu-id="1bb35-198">Table</span></span></th>
<th><span data-ttu-id="1bb35-199">说明</span><span class="sxs-lookup"><span data-stu-id="1bb35-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-200"><a href="lync-server-2013-locations-table.md">Lync Server 2013 中的位置表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-201">对于每个紧急呼叫（例如增强型 9-1-1 (E9-1-1) 呼叫），存储有关该呼叫的位置信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="1bb35-202">将<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a>称为 "呼叫开始/结束时间" 和 "响应代码"。</span><span class="sxs-lookup"><span data-stu-id="1bb35-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1bb35-p105">该表仅包含 E9-1-1 呼叫的位置 blob。有关呼叫的其他详细信息，请参阅 SessionDetails 表。</span><span class="sxs-lookup"><span data-stu-id="1bb35-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="1bb35-205">故障排除表</span><span class="sxs-lookup"><span data-stu-id="1bb35-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bb35-206">Table</span><span class="sxs-lookup"><span data-stu-id="1bb35-206">Table</span></span></th>
<th><span data-ttu-id="1bb35-207">说明</span><span class="sxs-lookup"><span data-stu-id="1bb35-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-208"><a href="lync-server-2013-application-table.md">Lync Server 2013 中的应用程序表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-209">存储有关在路由和连接中涉及的 Lync Server 2013 中的各种进程的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-210"><a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-211">存储有关呼叫类型的信息，例如“音频”、“即时消息”、“音频和视频”以及“应用程序共享”。</span><span class="sxs-lookup"><span data-stu-id="1bb35-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-212"><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 中的 ErrorCategory 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-213">存储每个 Microsoft Lync Server 2013 诊断分类的友好名称。</span><span class="sxs-lookup"><span data-stu-id="1bb35-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-214"><a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-215">存储有关错误类型及其定义的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-216"><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-217">存储有关发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-218"><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 中的 ProgressReport 表</a></span><span class="sxs-lookup"><span data-stu-id="1bb35-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1bb35-219">存储有关 Lync Server 2013 进程中涉及的各种步骤的进度报告的信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1bb35-220">以下列表中的表由 Lync Server 内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="1bb35-221">本文档不介绍其详细信息。</span><span class="sxs-lookup"><span data-stu-id="1bb35-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="1bb35-222">供 Lync Server 内部使用的表</span><span class="sxs-lookup"><span data-stu-id="1bb35-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bb35-223">Table</span><span class="sxs-lookup"><span data-stu-id="1bb35-223">Table</span></span></th>
<th><span data-ttu-id="1bb35-224">说明</span><span class="sxs-lookup"><span data-stu-id="1bb35-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-226">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-228">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-230">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-231"><strong>FrontEnd 表</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-232">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-233"><strong>MSMQProcessing 表</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-234">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-236">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-237"><strong>Syndicators 表</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-238">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-239"><strong>SyndicatorsTenantMap 表</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-240">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-241"><strong>任务表</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-242">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-244">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-246">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-248">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-250">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-252">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-254">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-256">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-258">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bb35-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-260">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bb35-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="1bb35-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="1bb35-262">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1bb35-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

