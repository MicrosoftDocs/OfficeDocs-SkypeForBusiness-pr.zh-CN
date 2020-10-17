---
title: Lync Server 2013：按类分类的架构属性
description: Lync Server 2013：按类的架构属性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes by class
ms:assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398544(v=OCS.15)
ms:contentKeyID: 48184468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cd31e42ce825049903310d6021e13086fe07afd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557168"
---
# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="3bbfb-103">Lync Server 2013 中按类分类的架构属性</span><span class="sxs-lookup"><span data-stu-id="3bbfb-103">Schema attributes by class in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bbfb-104">_**上次修改的主题：** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="3bbfb-104">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="3bbfb-105">本节列出了可包含在每个 Lync Server 2013 类和可包含在其他类中的类中的架构属性。</span><span class="sxs-lookup"><span data-stu-id="3bbfb-105">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="3bbfb-106">有关所有类及其说明的列表，请参阅 [Lync Server 2013 中的架构类和说明](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="3bbfb-106">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="3bbfb-107">有关所有属性及其说明的列表，请参阅 [Lync Server 2013 中的架构属性和说明](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="3bbfb-107">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="3bbfb-108">按类分组的属性</span><span class="sxs-lookup"><span data-stu-id="3bbfb-108">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3bbfb-109">Class</span><span class="sxs-lookup"><span data-stu-id="3bbfb-109">Class</span></span></th>
<th><span data-ttu-id="3bbfb-110">可包含以下属性</span><span class="sxs-lookup"><span data-stu-id="3bbfb-110">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-111">Contact</span><span class="sxs-lookup"><span data-stu-id="3bbfb-111">Contact</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-112">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-112">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="3bbfb-113">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="3bbfb-113">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="3bbfb-114">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="3bbfb-114">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="3bbfb-115">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="3bbfb-115">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="3bbfb-116">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="3bbfb-116">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="3bbfb-117">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="3bbfb-117">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="3bbfb-118">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="3bbfb-118">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="3bbfb-119">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="3bbfb-119">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="3bbfb-120">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="3bbfb-120">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="3bbfb-121">msRTCSIP-Msrtcsip-groupingid</span><span class="sxs-lookup"><span data-stu-id="3bbfb-121">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="3bbfb-122">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="3bbfb-122">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="3bbfb-123">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="3bbfb-123">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="3bbfb-124">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-124">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="3bbfb-125">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="3bbfb-125">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="3bbfb-126">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="3bbfb-126">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="3bbfb-127">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="3bbfb-127">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="3bbfb-128">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-128">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="3bbfb-129">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="3bbfb-129">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="3bbfb-130">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="3bbfb-130">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="3bbfb-131">msRTCSIP-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3bbfb-131">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="3bbfb-132">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="3bbfb-132">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="3bbfb-133">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-133">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="3bbfb-134">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="3bbfb-134">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="3bbfb-135">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="3bbfb-135">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="3bbfb-136">msRTCSIP-Msrtcsip-userenabled</span><span class="sxs-lookup"><span data-stu-id="3bbfb-136">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="3bbfb-137">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="3bbfb-137">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="3bbfb-138">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="3bbfb-138">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="3bbfb-139">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="3bbfb-139">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="3bbfb-140">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="3bbfb-140">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="3bbfb-141">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="3bbfb-141">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="3bbfb-142">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3bbfb-142">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-143">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="3bbfb-143">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-144">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-144">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="3bbfb-145">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="3bbfb-145">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-146">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-146">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-147">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="3bbfb-147">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-148">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-148">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-149">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="3bbfb-149">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="3bbfb-150">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="3bbfb-150">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="3bbfb-151">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-151">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="3bbfb-152">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-152">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-153">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="3bbfb-153">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-154">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="3bbfb-154">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="3bbfb-155">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="3bbfb-155">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="3bbfb-156">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="3bbfb-156">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="3bbfb-157">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-157">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-158">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="3bbfb-158">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-159">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="3bbfb-159">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="3bbfb-160">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="3bbfb-160">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-161">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="3bbfb-161">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-162">msRTCSIP-默认值</span><span class="sxs-lookup"><span data-stu-id="3bbfb-162">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="3bbfb-163">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-163">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="3bbfb-164">msRTCSIP-域名</span><span class="sxs-lookup"><span data-stu-id="3bbfb-164">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-165">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="3bbfb-165">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-166">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-166">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="3bbfb-167">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-167">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-168">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-168">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-169">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-169">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="3bbfb-170">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="3bbfb-170">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="3bbfb-171">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-171">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-172">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-172">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-173">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-173">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="3bbfb-174">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-174">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="3bbfb-175">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="3bbfb-175">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-176">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-176">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-177">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="3bbfb-177">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="3bbfb-178">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="3bbfb-178">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="3bbfb-179">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-179">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="3bbfb-180">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-180">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-181">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="3bbfb-181">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-182">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-182">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="3bbfb-183">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-183">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="3bbfb-184">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-184">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="3bbfb-185">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-185">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-186">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="3bbfb-186">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-187">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="3bbfb-187">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-188">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="3bbfb-188">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-189">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-189">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="3bbfb-190">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="3bbfb-190">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="3bbfb-191">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="3bbfb-191">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-192">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="3bbfb-192">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-193">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="3bbfb-193">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="3bbfb-194">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="3bbfb-194">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-195">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="3bbfb-195">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-196">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-196">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="3bbfb-197">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="3bbfb-197">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="3bbfb-198">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="3bbfb-198">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="3bbfb-199">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="3bbfb-199">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="3bbfb-200">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="3bbfb-200">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="3bbfb-201">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="3bbfb-201">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="3bbfb-202">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-202">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-203">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-203">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-204">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="3bbfb-204">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-205">msRTCSIP-移动性</span><span class="sxs-lookup"><span data-stu-id="3bbfb-205">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-206">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="3bbfb-206">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="3bbfb-207">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="3bbfb-207">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-208">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-209">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="3bbfb-209">dnsHostName</span></span></p>
<p><span data-ttu-id="3bbfb-210">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-210">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="3bbfb-211">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-211">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-212">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="3bbfb-212">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-213">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="3bbfb-213">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="3bbfb-214">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-214">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="3bbfb-215">msRTCSIP-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="3bbfb-215">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="3bbfb-216">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-216">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="3bbfb-217">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="3bbfb-217">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="3bbfb-218">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-218">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="3bbfb-219">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="3bbfb-219">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="3bbfb-220">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="3bbfb-220">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="3bbfb-221">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-221">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="3bbfb-222">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="3bbfb-222">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-223">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-223">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-224">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="3bbfb-224">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-225">msRTCSIP-状态</span><span class="sxs-lookup"><span data-stu-id="3bbfb-225">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-226">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="3bbfb-226">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="3bbfb-227">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="3bbfb-227">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-228">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="3bbfb-228">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-229">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="3bbfb-229">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="3bbfb-230">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="3bbfb-230">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="3bbfb-231">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-231">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="3bbfb-232">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-232">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="3bbfb-233">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-233">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="3bbfb-234">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-234">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-235">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="3bbfb-235">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-236">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-236">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="3bbfb-237">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-237">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="3bbfb-238">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-238">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-239">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-239">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-240">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-240">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="3bbfb-241">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-241">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="3bbfb-242">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-242">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-243">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-243">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-244">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-244">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="3bbfb-245">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="3bbfb-245">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="3bbfb-246">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-246">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="3bbfb-247">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="3bbfb-247">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="3bbfb-248">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-248">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="3bbfb-249">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-249">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="3bbfb-250">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="3bbfb-250">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="3bbfb-251">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="3bbfb-251">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="3bbfb-252">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="3bbfb-252">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-253">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-253">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-254">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-254">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="3bbfb-255">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="3bbfb-255">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="3bbfb-256">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-256">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-257">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-257">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-258">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="3bbfb-258">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-259">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-259">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-260">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="3bbfb-260">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="3bbfb-261">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="3bbfb-261">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="3bbfb-262">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3bbfb-262">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-263">用户</span><span class="sxs-lookup"><span data-stu-id="3bbfb-263">User</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-264">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="3bbfb-264">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="3bbfb-265">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="3bbfb-265">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="3bbfb-266">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="3bbfb-266">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="3bbfb-267">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="3bbfb-267">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="3bbfb-268">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="3bbfb-268">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="3bbfb-269">msRTCSIP-Msrtcsip-groupingid</span><span class="sxs-lookup"><span data-stu-id="3bbfb-269">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="3bbfb-270">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="3bbfb-270">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="3bbfb-271">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="3bbfb-271">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="3bbfb-272">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-272">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="3bbfb-273">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="3bbfb-273">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="3bbfb-274">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="3bbfb-274">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="3bbfb-275">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="3bbfb-275">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="3bbfb-276">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-276">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="3bbfb-277">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="3bbfb-277">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="3bbfb-278">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="3bbfb-278">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="3bbfb-279">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-279">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="3bbfb-280">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="3bbfb-280">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="3bbfb-281">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="3bbfb-281">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="3bbfb-282">msRTCSIP-Msrtcsip-userenabled</span><span class="sxs-lookup"><span data-stu-id="3bbfb-282">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="3bbfb-283">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="3bbfb-283">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="3bbfb-284">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="3bbfb-284">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="3bbfb-285">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="3bbfb-285">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="3bbfb-286">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="3bbfb-286">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="3bbfb-287">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="3bbfb-287">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="3bbfb-288">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3bbfb-288">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="3bbfb-289">包含在其他类中的类</span><span class="sxs-lookup"><span data-stu-id="3bbfb-289">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3bbfb-290">Class</span><span class="sxs-lookup"><span data-stu-id="3bbfb-290">Class</span></span></th>
<th><span data-ttu-id="3bbfb-291">可包含以下类</span><span class="sxs-lookup"><span data-stu-id="3bbfb-291">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-292">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="3bbfb-292">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-293">msRTCSIP-服务器</span><span class="sxs-lookup"><span data-stu-id="3bbfb-293">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="3bbfb-294">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-294">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="3bbfb-295">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="3bbfb-295">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="3bbfb-296">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-296">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="3bbfb-297">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="3bbfb-297">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="3bbfb-298">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-298">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="3bbfb-299">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-299">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="3bbfb-300">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="3bbfb-300">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="3bbfb-301">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="3bbfb-301">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="3bbfb-302">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-302">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="3bbfb-303">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-303">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-304">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="3bbfb-304">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-305">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-305">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="3bbfb-306">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="3bbfb-306">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="3bbfb-307">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="3bbfb-307">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="3bbfb-308">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="3bbfb-308">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="3bbfb-309">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="3bbfb-309">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="3bbfb-310">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="3bbfb-310">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="3bbfb-311">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="3bbfb-311">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="3bbfb-312">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="3bbfb-312">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="3bbfb-313">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-313">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="3bbfb-314">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="3bbfb-314">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="3bbfb-315">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-315">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-316">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-316">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-317">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="3bbfb-317">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="3bbfb-318">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-318">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="3bbfb-319">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="3bbfb-319">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="3bbfb-320">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-320">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-321">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="3bbfb-321">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-322">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="3bbfb-322">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-323">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="3bbfb-323">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-324">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="3bbfb-324">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-325">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="3bbfb-325">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-326">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="3bbfb-326">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-327">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="3bbfb-327">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-328">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="3bbfb-328">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-329">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="3bbfb-329">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-330">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="3bbfb-330">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-331">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="3bbfb-331">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-332">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="3bbfb-332">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-333">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-333">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-334">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="3bbfb-334">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bbfb-335">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="3bbfb-335">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-336">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="3bbfb-336">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bbfb-337">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="3bbfb-337">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="3bbfb-338">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="3bbfb-338">msRTCSIP-GlobalTopologySetting</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

