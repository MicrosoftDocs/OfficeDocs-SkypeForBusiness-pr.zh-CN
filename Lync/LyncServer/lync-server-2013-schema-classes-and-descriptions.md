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
ms.openlocfilehash: 5080af0977457f5c4a75d2f121e75560b0f24524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="c2bff-102">Lync Server 2013 中的架构类和说明</span><span class="sxs-lookup"><span data-stu-id="c2bff-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2bff-103">_**主题上次修改时间：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c2bff-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c2bff-104">本部分介绍 Lync Server 2013 使用的所有架构类。</span><span class="sxs-lookup"><span data-stu-id="c2bff-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="c2bff-105">架构类和说明</span><span class="sxs-lookup"><span data-stu-id="c2bff-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2bff-106">种类</span><span class="sxs-lookup"><span data-stu-id="c2bff-106">Class</span></span></th>
<th><span data-ttu-id="c2bff-107">说明</span><span class="sxs-lookup"><span data-stu-id="c2bff-107">Description</span></span></th>
<th><span data-ttu-id="c2bff-108">备注</span><span class="sxs-lookup"><span data-stu-id="c2bff-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-109">邮件-收件人</span><span class="sxs-lookup"><span data-stu-id="c2bff-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="c2bff-110">Exchange 统一消息（UM）电子邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="c2bff-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-111">此辅助类与 Exchange UM 共享。</span><span class="sxs-lookup"><span data-stu-id="c2bff-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-112">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="c2bff-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="c2bff-113">此类是多个应用程序联系人的容器，并且不包含任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-114">Microsoft Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-115">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="c2bff-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="c2bff-116">此类包含统一通信应用程序服务（UCAS）实例的服务控制点的条目。</span><span class="sxs-lookup"><span data-stu-id="c2bff-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="c2bff-117">Office 通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-118">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="c2bff-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="c2bff-119">此类提供从特定池到其应用程序服务的关联。</span><span class="sxs-lookup"><span data-stu-id="c2bff-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-120">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-121">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="c2bff-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="c2bff-122">此辅助类到 msRTCSIP-ApplicationServer 保留表示应用程序服务实例的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-123">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-124">msRTCSIP-存档（已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-125">此辅助类到 msRTCSIP-GlobalContainer 保存与存档相关的所有设置。</span><span class="sxs-lookup"><span data-stu-id="c2bff-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-126">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-127">msRTCSIP-ArchivingServer （已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-128">此类表示单个即时消息存档服务器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-128">This class represents a single instant messaging Archiving Server.</span></span> <span data-ttu-id="c2bff-129">在将计算机激活为即时消息存档服务器（如安装了即时消息存档服务的计算机）时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c2bff-129">An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-130">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-131">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="c2bff-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="c2bff-132">此类是多个会议目录实例的容器，并且不包含任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-133">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-134">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="c2bff-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="c2bff-135">此类包含表示特定会议目录的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-136">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-137">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="c2bff-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="c2bff-138">通用服务控制点（SCP）将计算机指定为运行 Lync Server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-139">Lync 2010 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-140">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="c2bff-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="c2bff-141">此辅助类保留 Microsoft Lync Web App bank 的设置。</span><span class="sxs-lookup"><span data-stu-id="c2bff-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-142">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-143">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="c2bff-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="c2bff-144">此类包含用于定义 SIP 注册机构配置的域的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-145">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="c2bff-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="c2bff-146">此类容器表示单个访问边缘服务。</span><span class="sxs-lookup"><span data-stu-id="c2bff-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="c2bff-147">由于在外围网络中部署了 Access Edge 服务，并且客户通常不允许从外围网络访问 Active Directory 域服务，因此 Access Edge 服务的实例未联接到 intranet 的 Active Directory 网络。</span><span class="sxs-lookup"><span data-stu-id="c2bff-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="c2bff-148">因此，访问代理服务器不会自动在 AD DS 中注册。</span><span class="sxs-lookup"><span data-stu-id="c2bff-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="c2bff-149">管理员必须手动配置 AD DS 中的每个 Access Edge 服务实例的存在。</span><span class="sxs-lookup"><span data-stu-id="c2bff-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-150">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="c2bff-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="c2bff-151">MsRTCSIP 的此辅助类保留表示会议服务器设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-152">Microsoft Office 通信服务器2007中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="c2bff-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-153">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="c2bff-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="c2bff-154">此辅助类到 msRTCSIP-MediationServer 包含表示中介服务器设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-155">Office 通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-156">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="c2bff-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="c2bff-157">此辅助类到 msRTCSIP-服务器保留表示 SIP 服务器设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-158">msRTCSIP-联合</span><span class="sxs-lookup"><span data-stu-id="c2bff-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="c2bff-159">此辅助类到 msRTCSIP-GlobalContainer 保存与联盟相关的所有设置。</span><span class="sxs-lookup"><span data-stu-id="c2bff-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-160">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="c2bff-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="c2bff-161">此类包含适用于整个 Lync Server 部署的所有设置。</span><span class="sxs-lookup"><span data-stu-id="c2bff-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-162">msRTCSIP-GlobalUserPolicy （已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-163">此类表示单个 Office 通信服务器会议策略。</span><span class="sxs-lookup"><span data-stu-id="c2bff-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-164">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-165">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="c2bff-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="c2bff-166">本地全局拓扑设置对象。</span><span class="sxs-lookup"><span data-stu-id="c2bff-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-167">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="c2bff-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-168">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="c2bff-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="c2bff-169">用于保存全局拓扑设置对象的容器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-170">Lync Server 2010 中的新增新增服务。</span><span class="sxs-lookup"><span data-stu-id="c2bff-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-171">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="c2bff-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="c2bff-172">此类是表示位置规范化规则的实例的容器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-173">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="c2bff-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="c2bff-174">此类由会议助理应用程序创建，并保留用于按地区对会议电话号码进行分类的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-175">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-176">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="c2bff-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="c2bff-177">此类是位置联系人映射的多个实例的容器，并且不包含任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-178">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-179">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="c2bff-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="c2bff-180">此类是一个表示特定位置配置文件的容器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-181">msRTCSIP-LocationProfiles （已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-182">此类是多个位置配置文件的容器，并且不包含任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-183">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-184">msRTCSIP-LocalNormalizations （已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-185">此类是多个本地规范化规则的容器，并且不包含任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-186">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-187">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="c2bff-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="c2bff-188">此类表示单个会议服务器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-189">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-190">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="c2bff-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="c2bff-191">此类保存多个 msRTCSIP MCUFactory 类，并且没有属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-192">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-193">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="c2bff-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="c2bff-194">此类是一个容器，表示适用于单个媒体类型的会议服务器工厂。</span><span class="sxs-lookup"><span data-stu-id="c2bff-194">This class is a container representing a Conferencing Server Factory for a single medium type.</span></span> <span data-ttu-id="c2bff-195">当激活此特定类型和供应商的第一个会议服务器时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c2bff-195">An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-196">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-197">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="c2bff-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="c2bff-198">此类提供从特定池到其会议服务器工厂的关联。</span><span class="sxs-lookup"><span data-stu-id="c2bff-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-199">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-200">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="c2bff-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="c2bff-201">此类包含用于中介服务器的服务控制点的条目。</span><span class="sxs-lookup"><span data-stu-id="c2bff-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-202">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-203">msRTCSIP-会议（已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-204">此辅助类到 msRTCSIP-GlobalContainer 包含表示可配置的会议设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-205">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-206">msRTCSIP-移动性</span><span class="sxs-lookup"><span data-stu-id="c2bff-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="c2bff-207">存储全局移动设置的容器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-208">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="c2bff-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="c2bff-209">此类包含表示单个监视服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-210">通信服务器 2007 R2 中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-211">msRTCSIP-PhoneRoute （已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-212">此类是一个容器，表示指向网关或网关集的最低成本路线的实例。</span><span class="sxs-lookup"><span data-stu-id="c2bff-212">This class is a container representing an instance of a least cost route to a gateway or set of gateways.</span></span> <span data-ttu-id="c2bff-213">此信息由运行标准版的所有企业池或服务器使用，以最经济高效的方式将传出呼叫路由到公共交换电话网络（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="c2bff-213">This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-214">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-215">msRTCSIP-PhoneRoutes （已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-216">此类是多个最少的成本路由的容器，并且不包含任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-217">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-218">msRTCSIP-政策（已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-219">此类包含多个 Lync 服务器策略类，并且没有任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-220">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-221">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="c2bff-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="c2bff-222">此类表示单个 Lync 服务器池。</span><span class="sxs-lookup"><span data-stu-id="c2bff-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-223">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="c2bff-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="c2bff-224">此类包含多个 Lync 服务器池，并且没有任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-225">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="c2bff-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="c2bff-226">此类表示池的服务控制 pointservice 控制点。</span><span class="sxs-lookup"><span data-stu-id="c2bff-226">This class represents the service control pointservice control point of a pool.</span></span> <span data-ttu-id="c2bff-227">托管在池中的用户将其 msRTCSIP-PrimaryHomeServer 属性指向此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c2bff-227">Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-228">msRTCSIP-状态</span><span class="sxs-lookup"><span data-stu-id="c2bff-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="c2bff-229">存储全局状态设置的容器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-230">msRTCSIP-注册机构</span><span class="sxs-lookup"><span data-stu-id="c2bff-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="c2bff-231">此辅助类到 msRTCSIP-GlobalContainer 包含表示 SIP 注册机构维护的用户设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-232">msRTCSIP-RouteUsage （已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-233">此类是一个容器，表示手机路线使用情况的实例。</span><span class="sxs-lookup"><span data-stu-id="c2bff-233">This class is a container representing an instance of a phone route usage.</span></span> <span data-ttu-id="c2bff-234">电话路由使用类包含一个属性字段和一个说明字段。</span><span class="sxs-lookup"><span data-stu-id="c2bff-234">A phone route usage class consists of an attribute field and a description field.</span></span> <span data-ttu-id="c2bff-235">属性字段定义使用类型。</span><span class="sxs-lookup"><span data-stu-id="c2bff-235">The attribute field defines a usage type.</span></span> <span data-ttu-id="c2bff-236">"说明" 域允许管理员在手机路线中描述此属性的用法。</span><span class="sxs-lookup"><span data-stu-id="c2bff-236">The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-237">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-238">msRTCSIP-RouteUsages （已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-239">此类保留 msRTCSIP 类的多个实例，并且没有任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-240">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-241">msRTCSIP-搜索</span><span class="sxs-lookup"><span data-stu-id="c2bff-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="c2bff-242">此辅助类到 msRTCSIP-GlobalContainer 包含限制和控制搜索结果范围的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-243">msRTCSIP-服务器</span><span class="sxs-lookup"><span data-stu-id="c2bff-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="c2bff-244">此类表示运行 Lync Server 的单个服务器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-245">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="c2bff-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="c2bff-246">此类包含全局设置容器和 msRTCSIP 域对象。</span><span class="sxs-lookup"><span data-stu-id="c2bff-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-247">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="c2bff-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="c2bff-248">此类包含表示受信任的会议服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-249">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-250">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="c2bff-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="c2bff-251">此类保留 msRTCSIP 类的多个实例，并且没有任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-252">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-253">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="c2bff-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="c2bff-254">此类包含多个 msRTCSIP TrustedProxy 类，并且不包含任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-255">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-256">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="c2bff-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="c2bff-257">此类是一个容器，表示运行代理服务器的服务器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-257">This class is a container representing a server running Proxy Server.</span></span> <span data-ttu-id="c2bff-258">在加入到 AD DS 的计算机上激活新的代理服务器时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c2bff-258">An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-259">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-260">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="c2bff-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="c2bff-261">此类包含表示受信任服务器的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-262">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="c2bff-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="c2bff-263">此类是一个容器，表示可通过全局可路由用户代理 URI （GRUU）地址进行路由的受信任的服务。</span><span class="sxs-lookup"><span data-stu-id="c2bff-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="c2bff-264">当激活由 Lync Server 信任的新服务器时，将创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c2bff-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="c2bff-265">此受信任服务器必须加入 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="c2bff-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-266">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-267">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="c2bff-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="c2bff-268">此类是多个 GRUU 服务器的容器，并且不包含任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-269">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-270">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="c2bff-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="c2bff-271">此类包含表示受信任 web 组件的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-272">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-273">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="c2bff-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="c2bff-274">此类保留 msRTCSIP 类的多个实例，并且没有任何属性本身。</span><span class="sxs-lookup"><span data-stu-id="c2bff-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-275">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-276">msRTCSIP-UnifiedCommunications （已过时）</span><span class="sxs-lookup"><span data-stu-id="c2bff-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c2bff-277">此辅助类到 msRTCSIP-GlobalContainer 保存与统一通信相关的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-278">在 Lync Server 2010 中已过时。</span><span class="sxs-lookup"><span data-stu-id="c2bff-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-279">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="c2bff-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="c2bff-280">此类包含 Internet information Server （IIS）的服务控制 pointservice 控制点。</span><span class="sxs-lookup"><span data-stu-id="c2bff-280">This class holds the service control pointservice control point for Internet Information Server (IIS).</span></span> <span data-ttu-id="c2bff-281">它将服务器标识为 web 组件服务器。</span><span class="sxs-lookup"><span data-stu-id="c2bff-281">It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-282">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2bff-283">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="c2bff-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="c2bff-284">此类提供从特定池到该池将使用的 web 组件的关联。</span><span class="sxs-lookup"><span data-stu-id="c2bff-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-285">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2bff-286">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="c2bff-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="c2bff-287">此辅助类到 msRTCSIP-WebComponents 包含表示 web 组件的设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c2bff-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="c2bff-288">通信服务器2007中的新增项。</span><span class="sxs-lookup"><span data-stu-id="c2bff-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

