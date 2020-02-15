---
title: Lync Server 2013：架构类和说明
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
ms.openlocfilehash: 3063e0dd6288f4b9248c93de57a6182a7ab20a8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="c496b-102">Lync Server 2013 中的架构类和说明</span><span class="sxs-lookup"><span data-stu-id="c496b-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c496b-103">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c496b-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c496b-104">本节介绍 Lync Server 2013 使用的所有架构类。</span><span class="sxs-lookup"><span data-stu-id="c496b-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="c496b-105">架构类和说明</span><span class="sxs-lookup"><span data-stu-id="c496b-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c496b-106">类</span><span class="sxs-lookup"><span data-stu-id="c496b-106">Class</span></span></th>
<th><span data-ttu-id="c496b-107">说明</span><span class="sxs-lookup"><span data-stu-id="c496b-107">Description</span></span></th>
<th><span data-ttu-id="c496b-108">注释</span><span class="sxs-lookup"><span data-stu-id="c496b-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c496b-109">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="c496b-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="c496b-110">Exchange 统一消息（UM）电子邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="c496b-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="c496b-111">此辅助类与 Exchange UM 共享。</span><span class="sxs-lookup"><span data-stu-id="c496b-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-112">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="c496b-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="c496b-113">此类是多个应用程序联系人的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-114">Microsoft Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-115">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="c496b-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="c496b-116">此类包含统一通信应用程序服务 (UCAS) 实例的服务控制点的相应项。</span><span class="sxs-lookup"><span data-stu-id="c496b-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="c496b-117">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-118">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="c496b-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="c496b-119">此类提供从特定池到其应用程序服务的关联。</span><span class="sxs-lookup"><span data-stu-id="c496b-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="c496b-120">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-121">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="c496b-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="c496b-122">此辅助类到 msRTCSIP-ApplicationServer 包含表示应用程序服务实例的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="c496b-123">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-124">msRTCSIP-Archive（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-125">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与存档相关的所有设置。</span><span class="sxs-lookup"><span data-stu-id="c496b-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="c496b-126">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-127">msRTCSIP-ArchivingServer（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-p101">此类表示单个即时消息存档服务器。将计算机作为即时消息存档服务器（如安装了即时消息存档服务的计算机）激活时将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c496b-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="c496b-130">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-131">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="c496b-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="c496b-132">此类是会议目录的多个实例的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-133">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-134">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="c496b-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="c496b-135">此类包含表示特定会议目录的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="c496b-136">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-137">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="c496b-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="c496b-138">将计算机指定为运行 Lync Server 的服务器的通用服务控制点（SCP）。</span><span class="sxs-lookup"><span data-stu-id="c496b-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="c496b-139">Lync 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-140">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="c496b-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="c496b-141">此辅助类保存 Microsoft Lync Web App bank 的设置。</span><span class="sxs-lookup"><span data-stu-id="c496b-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="c496b-142">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-143">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="c496b-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="c496b-144">此类包含定义 SIP 注册器的已配置域的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-145">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="c496b-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="c496b-146">此类容器表示单个访问边缘服务。</span><span class="sxs-lookup"><span data-stu-id="c496b-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="c496b-147">由于在外围网络中部署了访问边缘服务，并且客户通常不允许从外围网络进行 Active Directory 域服务访问，因此 Access Edge 服务的实例未加入 intranet 的 Active Directory 网络。</span><span class="sxs-lookup"><span data-stu-id="c496b-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="c496b-148">这样，访问代理就不会在 AD DS 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="c496b-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="c496b-149">管理员必须手动配置 AD DS 中的每个 Access Edge 服务实例的存在。</span><span class="sxs-lookup"><span data-stu-id="c496b-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-150">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="c496b-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="c496b-151">这是 msRTCSIP-MCU 的辅助类，其中包含表示会议服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="c496b-152">Microsoft Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-153">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="c496b-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="c496b-154">这是 msRTCSIP-MediationServer 的辅助类，其中包含表示中介服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="c496b-155">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-156">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="c496b-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="c496b-157">这是 msRTCSIP-Server 的辅助类，其中包含表示 SIP 服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-158">msRTCSIP-联合</span><span class="sxs-lookup"><span data-stu-id="c496b-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="c496b-159">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与联盟相关的所有设置。</span><span class="sxs-lookup"><span data-stu-id="c496b-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-160">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="c496b-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="c496b-161">此类包含适用于所有在 Lync Server 部署中的设置。</span><span class="sxs-lookup"><span data-stu-id="c496b-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-162">msRTCSIP-GlobalUserPolicy（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-163">此类表示单个 Office 通信服务器会议策略。</span><span class="sxs-lookup"><span data-stu-id="c496b-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="c496b-164">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-165">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="c496b-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="c496b-166">本地全局拓扑设置对象。</span><span class="sxs-lookup"><span data-stu-id="c496b-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="c496b-167">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-168">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="c496b-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="c496b-169">包含全局拓扑设置对象的容器。</span><span class="sxs-lookup"><span data-stu-id="c496b-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="c496b-170">Lync Server 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-171">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="c496b-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="c496b-172">此类是表示位置规范化规则的实例的容器。</span><span class="sxs-lookup"><span data-stu-id="c496b-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-173">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="c496b-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="c496b-174">此类由会议助理应用程序创建，并保留用于按地区对会议电话号码进行分类的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="c496b-175">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-176">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="c496b-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="c496b-177">此类是位置联系人映射的多个实例的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-178">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-179">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="c496b-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="c496b-180">此类是表示特定位置配置文件的容器。</span><span class="sxs-lookup"><span data-stu-id="c496b-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-181">msRTCSIP-LocationProfiles（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-182">此类是多个位置配置文件的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-183">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-184">msRTCSIP-LocalNormalizations（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-185">此类是多个本地规范化规则的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-186">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-187">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="c496b-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="c496b-188">此类表示单个会议服务器。</span><span class="sxs-lookup"><span data-stu-id="c496b-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="c496b-189">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-190">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="c496b-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="c496b-191">此类包含多个 msRTCSIP-MCUFactory 类，并且自身没有任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-192">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-193">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="c496b-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="c496b-p103">此类是表示单个媒体类型的会议服务器中心的容器。当激活对应于此特定类型和供应商的第一台会议服务器时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c496b-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="c496b-196">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-197">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="c496b-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="c496b-198">此类提供从特定池到其会议服务器中心的关联。</span><span class="sxs-lookup"><span data-stu-id="c496b-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="c496b-199">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-200">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="c496b-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="c496b-201">此类包含中介服务器的服务控制点的相应项。</span><span class="sxs-lookup"><span data-stu-id="c496b-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="c496b-202">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-203">msRTCSIP-Meeting（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-204">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含表示可配置会议设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="c496b-205">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-206">msRTCSIP-移动性</span><span class="sxs-lookup"><span data-stu-id="c496b-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="c496b-207">存储全局移动性设置的容器。</span><span class="sxs-lookup"><span data-stu-id="c496b-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-208">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="c496b-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="c496b-209">此类包含表示单个监视服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="c496b-210">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-211">msRTCSIP-PhoneRoute（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-p104">此类是表示到一个网关或一组网关的最低成本路由的实例的容器。所有企业版池或运行 Standard Edition 的服务器使用此信息，以最经济有效的方式将传出呼叫路由至公用电话交换网 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="c496b-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="c496b-214">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-215">msRTCSIP-PhoneRoutes（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-216">此类是多个最低成本路由的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-217">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-218">msRTCSIP-Policies（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-219">此类保存多个 Lync Server 策略类，并且没有任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c496b-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-220">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-221">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="c496b-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="c496b-222">此类表示单个 Lync Server 池。</span><span class="sxs-lookup"><span data-stu-id="c496b-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-223">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="c496b-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="c496b-224">此类保存多个 Lync Server 池，并且没有任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c496b-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-225">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="c496b-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="c496b-p105">此类表示池的服务控制点。如果用户承载于池中，其 msRTCSIP-PrimaryHomeServer 属性将指向此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c496b-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-228">msRTCSIP-状态</span><span class="sxs-lookup"><span data-stu-id="c496b-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="c496b-229">存储全局状态设置的容器。</span><span class="sxs-lookup"><span data-stu-id="c496b-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-230">msRTCSIP-注册器</span><span class="sxs-lookup"><span data-stu-id="c496b-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="c496b-231">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含表示由 SIP 注册器服务器维护的用户设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-232">msRTCSIP-RouteUsage（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-p106">此类是表示电话路由用法的实例的容器。电话路由用法类由一个属性字段和一个说明字段组成。属性字段定义用法类型。通过说明字段，管理员可以描述此属性在电话路由中的用法。</span><span class="sxs-lookup"><span data-stu-id="c496b-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="c496b-237">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-238">msRTCSIP-RouteUsages（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-239">此类包含 msRTCSIP-RouteUsage 类的多个实例，并且自身没有任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-240">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-241">msRTCSIP-搜索</span><span class="sxs-lookup"><span data-stu-id="c496b-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="c496b-242">这是 msRTCSIP-GlobalContainer 的辅助类，它包含用于限定和控制搜索结果范围的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-243">msRTCSIP-服务器</span><span class="sxs-lookup"><span data-stu-id="c496b-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="c496b-244">此类表示运行 Lync Server 的单个服务器。</span><span class="sxs-lookup"><span data-stu-id="c496b-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-245">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="c496b-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="c496b-246">此类包含全局设置容器和 msRTCSIP-Domain 对象。</span><span class="sxs-lookup"><span data-stu-id="c496b-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-247">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="c496b-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="c496b-248">此类包含表示受信任会议服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="c496b-249">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-250">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="c496b-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="c496b-251">此类包含 msRTCSIP-TrustedMCU 类的多个实例，并且自身没有任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-252">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-253">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="c496b-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="c496b-254">此类包含多个 msRTCSIP-TrustedProxy 类，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-255">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-256">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="c496b-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="c496b-p107">此类是表示运行代理服务器的服务器的容器。在加入 AD DS 的计算机上激活新的代理服务器时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c496b-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="c496b-259">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-260">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="c496b-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="c496b-261">此类包含表示受信任服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-262">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="c496b-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="c496b-263">此类是表示可使用全局可路由用户代理 URI (GRUU) 地址进行路由的受信任服务的容器。</span><span class="sxs-lookup"><span data-stu-id="c496b-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="c496b-264">当激活由 Lync Server 信任的新服务器时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c496b-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="c496b-265">此受信任服务器必须加入 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="c496b-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="c496b-266">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-267">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="c496b-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="c496b-268">此类是多个 GRUU 服务器的容器，并且自身不包含任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-269">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-270">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="c496b-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="c496b-271">此类包含表示受信任 Web 组件的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="c496b-272">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-273">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="c496b-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="c496b-274">此类包含 msRTCSIP-TrustedWebComponentServer 类的多个实例，并且自身没有任何属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c496b-275">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-276">msRTCSIP-UnifiedCommunications（作废）</span><span class="sxs-lookup"><span data-stu-id="c496b-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c496b-277">这是 msRTCSIP-GlobalContainer 的辅助类，其中包含与统一通信相关的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="c496b-278">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c496b-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-279">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="c496b-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="c496b-p109">此类包含 Internet Information Server (IIS) 的服务控制点。它将服务器标识为 Web 组件服务器。</span><span class="sxs-lookup"><span data-stu-id="c496b-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="c496b-282">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c496b-283">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="c496b-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="c496b-284">此类提供从特定池到该池将使用的 Web 组件的关联。</span><span class="sxs-lookup"><span data-stu-id="c496b-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="c496b-285">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c496b-286">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="c496b-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="c496b-287">这是 msRTCSIP-WebComponents 的辅助类，其中包含表示 Web 组件的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c496b-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="c496b-288">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c496b-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

