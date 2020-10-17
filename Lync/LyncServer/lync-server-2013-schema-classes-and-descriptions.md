---
title: Lync Server 2013：架构类和说明
description: Lync Server 2013：架构类和说明。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec27c2e00a7f969dbc13c91b06313c8045894a9e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557098"
---
# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="1509f-103">Lync Server 2013 中的架构类和说明</span><span class="sxs-lookup"><span data-stu-id="1509f-103">Schema classes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1509f-104">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="1509f-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="1509f-105">本节介绍 Lync Server 2013 使用的所有架构类。</span><span class="sxs-lookup"><span data-stu-id="1509f-105">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="1509f-106">架构类和说明</span><span class="sxs-lookup"><span data-stu-id="1509f-106">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1509f-107">类</span><span class="sxs-lookup"><span data-stu-id="1509f-107">Class</span></span></th>
<th><span data-ttu-id="1509f-108">说明</span><span class="sxs-lookup"><span data-stu-id="1509f-108">Description</span></span></th>
<th><span data-ttu-id="1509f-109">Comments</span><span class="sxs-lookup"><span data-stu-id="1509f-109">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1509f-110">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="1509f-110">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="1509f-111">Exchange 统一消息 (UM) 电子邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="1509f-111">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="1509f-112">此辅助类与 Exchange UM 共享。</span><span class="sxs-lookup"><span data-stu-id="1509f-112">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-113">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="1509f-113">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="1509f-114">此类是多个应用程序联系人的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-114">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-115">Microsoft Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-115">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-116">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="1509f-116">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="1509f-117">此类包含统一通信应用程序服务 (UCAS) 实例的服务控制点的相应项。</span><span class="sxs-lookup"><span data-stu-id="1509f-117">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="1509f-118">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-118">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-119">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="1509f-119">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="1509f-120">此类提供从特定池到其应用程序服务的关联。</span><span class="sxs-lookup"><span data-stu-id="1509f-120">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="1509f-121">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-121">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-122">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="1509f-122">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="1509f-123">此辅助类到 msRTCSIP-ApplicationServer 包含表示应用程序服务实例的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-123">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="1509f-124">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-124">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-125">msRTCSIP-Archive（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-125">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-126">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与存档相关的所有设置。</span><span class="sxs-lookup"><span data-stu-id="1509f-126">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="1509f-127">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-127">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-128">msRTCSIP-ArchivingServer（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-128">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-p101">此类表示单个即时消息存档服务器。将计算机作为即时消息存档服务器（如安装了即时消息存档服务的计算机）激活时将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="1509f-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="1509f-131">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-131">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-132">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="1509f-132">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="1509f-133">此类是会议目录的多个实例的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-133">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-134">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-134">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-135">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="1509f-135">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="1509f-136">此类包含表示特定会议目录的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-136">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="1509f-137">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-137">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-138">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="1509f-138">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="1509f-139"> (SCP) 将计算机指定为运行 Lync Server 的服务器的通用服务控制点。</span><span class="sxs-lookup"><span data-stu-id="1509f-139">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="1509f-140">Lync 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-140">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-141">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="1509f-141">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="1509f-142">此辅助类保存 Microsoft Lync Web App bank 的设置。</span><span class="sxs-lookup"><span data-stu-id="1509f-142">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="1509f-143">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-143">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-144">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="1509f-144">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="1509f-145">此类包含定义 SIP 注册器的已配置域的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-145">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-146">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="1509f-146">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="1509f-147">此类容器表示单个访问边缘服务。</span><span class="sxs-lookup"><span data-stu-id="1509f-147">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="1509f-148">由于在外围网络中部署了访问边缘服务，并且客户通常不允许从外围网络进行 Active Directory 域服务访问，因此 Access Edge 服务的实例未加入 intranet 的 Active Directory 网络。</span><span class="sxs-lookup"><span data-stu-id="1509f-148">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="1509f-149">这样，访问代理就不会在 AD DS 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="1509f-149">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="1509f-150">管理员必须手动配置 AD DS 中的每个 Access Edge 服务实例的存在。</span><span class="sxs-lookup"><span data-stu-id="1509f-150">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-151">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="1509f-151">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="1509f-152">这是 msRTCSIP-MCU 的辅助类，其中包含表示会议服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-152">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="1509f-153">Microsoft Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-153">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-154">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="1509f-154">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="1509f-155">这是 msRTCSIP-MediationServer 的辅助类，其中包含表示中介服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-155">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="1509f-156">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-156">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-157">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="1509f-157">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="1509f-158">这是 msRTCSIP-Server 的辅助类，其中包含表示 SIP 服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-158">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-159">msRTCSIP-联合</span><span class="sxs-lookup"><span data-stu-id="1509f-159">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="1509f-160">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与联盟相关的所有设置。</span><span class="sxs-lookup"><span data-stu-id="1509f-160">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-161">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="1509f-161">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="1509f-162">此类包含适用于所有在 Lync Server 部署中的设置。</span><span class="sxs-lookup"><span data-stu-id="1509f-162">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-163">msRTCSIP-GlobalUserPolicy（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-163">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-164">此类表示单个 Office 通信服务器会议策略。</span><span class="sxs-lookup"><span data-stu-id="1509f-164">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="1509f-165">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-165">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-166">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="1509f-166">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="1509f-167">本地全局拓扑设置对象。</span><span class="sxs-lookup"><span data-stu-id="1509f-167">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="1509f-168">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-168">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-169">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="1509f-169">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="1509f-170">包含全局拓扑设置对象的容器。</span><span class="sxs-lookup"><span data-stu-id="1509f-170">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="1509f-171">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-171">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-172">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="1509f-172">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="1509f-173">此类是表示位置规范化规则的实例的容器。</span><span class="sxs-lookup"><span data-stu-id="1509f-173">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-174">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="1509f-174">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="1509f-175">此类由会议助理应用程序创建，并保留用于按地区对会议电话号码进行分类的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-175">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="1509f-176">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-176">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-177">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="1509f-177">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="1509f-178">此类是位置联系人映射的多个实例的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-178">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-179">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-179">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-180">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="1509f-180">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="1509f-181">此类是表示特定位置配置文件的容器。</span><span class="sxs-lookup"><span data-stu-id="1509f-181">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-182">msRTCSIP-LocationProfiles（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-182">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-183">此类是多个位置配置文件的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-183">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-184">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-184">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-185">msRTCSIP-LocalNormalizations（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-185">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-186">此类是多个本地规范化规则的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-186">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-187">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-187">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-188">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="1509f-188">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="1509f-189">此类表示单个会议服务器。</span><span class="sxs-lookup"><span data-stu-id="1509f-189">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="1509f-190">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-190">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-191">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="1509f-191">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="1509f-192">此类包含多个 msRTCSIP-MCUFactory 类，并且自身没有任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-192">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-193">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-193">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="1509f-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="1509f-p103">此类是表示单个媒体类型的会议服务器中心的容器。当激活对应于此特定类型和供应商的第一台会议服务器时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="1509f-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="1509f-197">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-197">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-198">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="1509f-198">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="1509f-199">此类提供从特定池到其会议服务器中心的关联。</span><span class="sxs-lookup"><span data-stu-id="1509f-199">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="1509f-200">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-200">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-201">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="1509f-201">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="1509f-202">此类包含中介服务器的服务控制点的相应项。</span><span class="sxs-lookup"><span data-stu-id="1509f-202">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="1509f-203">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-203">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-204">msRTCSIP-Meeting（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-204">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-205">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含表示可配置会议设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-205">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="1509f-206">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-206">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-207">msRTCSIP-移动性</span><span class="sxs-lookup"><span data-stu-id="1509f-207">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="1509f-208">存储全局移动性设置的容器。</span><span class="sxs-lookup"><span data-stu-id="1509f-208">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-209">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="1509f-209">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="1509f-210">此类包含表示单个监视服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-210">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="1509f-211">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-211">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-212">msRTCSIP-PhoneRoute（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-212">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-p104">此类是表示到一个网关或一组网关的最低成本路由的实例的容器。所有企业版池或运行 Standard Edition 的服务器使用此信息，以最经济有效的方式将传出呼叫路由至公用电话交换网 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="1509f-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="1509f-215">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-215">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-216">msRTCSIP-PhoneRoutes（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-216">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-217">此类是多个最低成本路由的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-217">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-218">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-218">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-219">msRTCSIP-Policies（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-219">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-220">此类保存多个 Lync Server 策略类，并且没有任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="1509f-220">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-221">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-221">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-222">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="1509f-222">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="1509f-223">此类表示单个 Lync Server 池。</span><span class="sxs-lookup"><span data-stu-id="1509f-223">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-224">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="1509f-224">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="1509f-225">此类保存多个 Lync Server 池，并且没有任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="1509f-225">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-226">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="1509f-226">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="1509f-p105">此类表示池的服务控制点。如果用户承载于池中，其 msRTCSIP-PrimaryHomeServer 属性将指向此类的实例。</span><span class="sxs-lookup"><span data-stu-id="1509f-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-229">msRTCSIP-状态</span><span class="sxs-lookup"><span data-stu-id="1509f-229">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="1509f-230">存储全局状态设置的容器。</span><span class="sxs-lookup"><span data-stu-id="1509f-230">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-231">msRTCSIP-注册器</span><span class="sxs-lookup"><span data-stu-id="1509f-231">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="1509f-232">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含表示由 SIP 注册器服务器维护的用户设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-232">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-233">msRTCSIP-RouteUsage（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-233">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-p106">此类是表示电话路由用法的实例的容器。电话路由用法类由一个属性字段和一个说明字段组成。属性字段定义用法类型。通过说明字段，管理员可以描述此属性在电话路由中的用法。</span><span class="sxs-lookup"><span data-stu-id="1509f-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="1509f-238">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-238">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-239">msRTCSIP-RouteUsages（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-239">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-240">此类包含 msRTCSIP-RouteUsage 类的多个实例，并且自身没有任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-240">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-241">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-242">msRTCSIP-搜索</span><span class="sxs-lookup"><span data-stu-id="1509f-242">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="1509f-243">这是 msRTCSIP-GlobalContainer 的辅助类，它包含用于限定和控制搜索结果范围的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-243">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-244">msRTCSIP-服务器</span><span class="sxs-lookup"><span data-stu-id="1509f-244">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="1509f-245">此类表示运行 Lync Server 的单个服务器。</span><span class="sxs-lookup"><span data-stu-id="1509f-245">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-246">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="1509f-246">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="1509f-247">此类包含全局设置容器和 msRTCSIP-Domain 对象。</span><span class="sxs-lookup"><span data-stu-id="1509f-247">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-248">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="1509f-248">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="1509f-249">此类包含表示受信任会议服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-249">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="1509f-250">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-250">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-251">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="1509f-251">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="1509f-252">此类包含 msRTCSIP-TrustedMCU 类的多个实例，并且自身没有任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-252">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-253">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-253">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-254">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="1509f-254">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="1509f-255">此类包含多个 msRTCSIP-TrustedProxy 类，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-255">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-256">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-256">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-257">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="1509f-257">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="1509f-p107">此类是表示运行代理服务器的服务器的容器。在加入 AD DS 的计算机上激活新的代理服务器时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="1509f-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="1509f-260">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-260">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-261">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="1509f-261">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="1509f-262">此类包含表示受信任服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-262">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-263">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="1509f-263">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="1509f-264">此类是表示可使用全局可路由用户代理 URI (GRUU) 地址进行路由的受信任服务的容器。</span><span class="sxs-lookup"><span data-stu-id="1509f-264">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="1509f-265">当激活由 Lync Server 信任的新服务器时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="1509f-265">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="1509f-266">此受信任服务器必须加入 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="1509f-266">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="1509f-267">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-267">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-268">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="1509f-268">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="1509f-269">此类是多个 GRUU 服务器的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-269">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-270">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-270">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-271">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="1509f-271">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="1509f-272">此类包含表示受信任 Web 组件的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-272">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="1509f-273">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-273">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-274">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="1509f-274">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="1509f-275">此类包含 msRTCSIP-TrustedWebComponentServer 类的多个实例，并且自身没有任何属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-275">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="1509f-276">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-276">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-277">msRTCSIP-UnifiedCommunications（作废）</span><span class="sxs-lookup"><span data-stu-id="1509f-277">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1509f-278">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与统一通信相关的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-278">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="1509f-279">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="1509f-279">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-280">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="1509f-280">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="1509f-p109">此类包含 Internet Information Server (IIS) 的服务控制点。它将服务器标识为 Web 组件服务器。</span><span class="sxs-lookup"><span data-stu-id="1509f-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="1509f-283">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-283">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1509f-284">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="1509f-284">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="1509f-285">此类提供从特定池到该池将使用的 Web 组件的关联。</span><span class="sxs-lookup"><span data-stu-id="1509f-285">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="1509f-286">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-286">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1509f-287">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="1509f-287">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="1509f-288">这是 msRTCSIP-WebComponents 的辅助类，其中包含表示 Web 组件的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1509f-288">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="1509f-289">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="1509f-289">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

