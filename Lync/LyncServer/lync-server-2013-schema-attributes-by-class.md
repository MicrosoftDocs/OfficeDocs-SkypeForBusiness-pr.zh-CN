---
title: Lync Server 2013：按类分类的架构属性
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
ms.openlocfilehash: 8394a1333cff66b076612ed197fa2a6a7af12ec6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="bdc53-102">Lync Server 2013 中按类分类的架构属性</span><span class="sxs-lookup"><span data-stu-id="bdc53-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdc53-103">_**上次修改的主题：** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="bdc53-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="bdc53-104">本节列出了可包含在每个 Lync Server 2013 类和可包含在其他类中的类中的架构属性。</span><span class="sxs-lookup"><span data-stu-id="bdc53-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="bdc53-105">有关所有类及其说明的列表，请参阅[Lync Server 2013 中的架构类和说明](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="bdc53-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="bdc53-106">有关所有属性及其说明的列表，请参阅[Lync Server 2013 中的架构属性和说明](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="bdc53-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="bdc53-107">按类分组的属性</span><span class="sxs-lookup"><span data-stu-id="bdc53-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdc53-108">Class</span><span class="sxs-lookup"><span data-stu-id="bdc53-108">Class</span></span></th>
<th><span data-ttu-id="bdc53-109">可包含以下属性</span><span class="sxs-lookup"><span data-stu-id="bdc53-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-110">Contact</span><span class="sxs-lookup"><span data-stu-id="bdc53-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="bdc53-111">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="bdc53-112">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="bdc53-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="bdc53-113">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="bdc53-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="bdc53-114">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="bdc53-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="bdc53-115">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="bdc53-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="bdc53-116">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="bdc53-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="bdc53-117">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="bdc53-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="bdc53-118">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="bdc53-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="bdc53-119">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="bdc53-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="bdc53-120">msRTCSIP-Msrtcsip-groupingid</span><span class="sxs-lookup"><span data-stu-id="bdc53-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="bdc53-121">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="bdc53-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="bdc53-122">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="bdc53-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="bdc53-123">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="bdc53-124">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="bdc53-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="bdc53-125">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="bdc53-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="bdc53-126">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="bdc53-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="bdc53-127">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="bdc53-128">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="bdc53-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="bdc53-129">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="bdc53-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="bdc53-130">msRTCSIP-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="bdc53-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="bdc53-131">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="bdc53-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="bdc53-132">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="bdc53-133">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="bdc53-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="bdc53-134">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="bdc53-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="bdc53-135">msRTCSIP-Msrtcsip-userenabled</span><span class="sxs-lookup"><span data-stu-id="bdc53-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="bdc53-136">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="bdc53-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="bdc53-137">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="bdc53-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="bdc53-138">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="bdc53-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="bdc53-139">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="bdc53-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="bdc53-140">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="bdc53-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="bdc53-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="bdc53-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-142">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="bdc53-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="bdc53-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="bdc53-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="bdc53-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="bdc53-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-145">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="bdc53-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="bdc53-146">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="bdc53-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-147">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="bdc53-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="bdc53-148">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="bdc53-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="bdc53-149">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="bdc53-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="bdc53-150">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="bdc53-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="bdc53-151">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-152">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="bdc53-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="bdc53-153">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="bdc53-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="bdc53-154">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="bdc53-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="bdc53-155">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="bdc53-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="bdc53-156">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="bdc53-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-157">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="bdc53-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="bdc53-158">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="bdc53-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="bdc53-159">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="bdc53-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-160">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="bdc53-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="bdc53-161">msRTCSIP-默认值</span><span class="sxs-lookup"><span data-stu-id="bdc53-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="bdc53-162">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="bdc53-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="bdc53-163">msRTCSIP-域名</span><span class="sxs-lookup"><span data-stu-id="bdc53-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-164">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="bdc53-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="bdc53-165">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="bdc53-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="bdc53-166">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-167">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="bdc53-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="bdc53-168">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="bdc53-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="bdc53-169">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="bdc53-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="bdc53-170">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-171">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="bdc53-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="bdc53-172">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="bdc53-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="bdc53-173">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="bdc53-174">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="bdc53-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-175">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="bdc53-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="bdc53-176">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="bdc53-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="bdc53-177">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="bdc53-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="bdc53-178">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="bdc53-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="bdc53-179">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-180">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="bdc53-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="bdc53-181">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="bdc53-182">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="bdc53-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="bdc53-183">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="bdc53-184">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-185">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="bdc53-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="bdc53-186">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="bdc53-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-187">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="bdc53-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="bdc53-188">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="bdc53-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="bdc53-189">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="bdc53-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="bdc53-190">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="bdc53-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-191">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="bdc53-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="bdc53-192">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="bdc53-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="bdc53-193">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="bdc53-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="bdc53-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="bdc53-195">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="bdc53-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="bdc53-196">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="bdc53-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="bdc53-197">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="bdc53-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="bdc53-198">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="bdc53-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="bdc53-199">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="bdc53-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="bdc53-200">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="bdc53-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="bdc53-201">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-202">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="bdc53-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="bdc53-203">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="bdc53-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-204">msRTCSIP-移动性</span><span class="sxs-lookup"><span data-stu-id="bdc53-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="bdc53-205">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="bdc53-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="bdc53-206">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="bdc53-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-207">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="bdc53-208">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="bdc53-208">dnsHostName</span></span></p>
<p><span data-ttu-id="bdc53-209">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="bdc53-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="bdc53-210">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-211">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="bdc53-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="bdc53-212">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="bdc53-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="bdc53-213">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="bdc53-214">msRTCSIP-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="bdc53-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="bdc53-215">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="bdc53-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="bdc53-216">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="bdc53-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="bdc53-217">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="bdc53-218">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="bdc53-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="bdc53-219">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="bdc53-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="bdc53-220">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="bdc53-221">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="bdc53-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-222">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="bdc53-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="bdc53-223">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="bdc53-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-224">msRTCSIP-状态</span><span class="sxs-lookup"><span data-stu-id="bdc53-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="bdc53-225">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="bdc53-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="bdc53-226">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="bdc53-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-227">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="bdc53-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="bdc53-228">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="bdc53-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="bdc53-229">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="bdc53-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="bdc53-230">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="bdc53-231">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="bdc53-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="bdc53-232">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="bdc53-233">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-234">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="bdc53-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="bdc53-235">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="bdc53-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="bdc53-236">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="bdc53-237">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-238">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="bdc53-239">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="bdc53-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="bdc53-240">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="bdc53-241">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-242">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="bdc53-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="bdc53-243">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="bdc53-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="bdc53-244">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="bdc53-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="bdc53-245">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="bdc53-246">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="bdc53-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="bdc53-247">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="bdc53-248">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="bdc53-249">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="bdc53-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="bdc53-250">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="bdc53-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="bdc53-251">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="bdc53-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-252">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="bdc53-253">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="bdc53-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="bdc53-254">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="bdc53-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="bdc53-255">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-256">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="bdc53-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="bdc53-257">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="bdc53-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-258">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="bdc53-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="bdc53-259">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="bdc53-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="bdc53-260">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="bdc53-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="bdc53-261">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="bdc53-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-262">用户</span><span class="sxs-lookup"><span data-stu-id="bdc53-262">User</span></span></p></td>
<td><p><span data-ttu-id="bdc53-263">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="bdc53-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="bdc53-264">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="bdc53-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="bdc53-265">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="bdc53-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="bdc53-266">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="bdc53-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="bdc53-267">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="bdc53-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="bdc53-268">msRTCSIP-Msrtcsip-groupingid</span><span class="sxs-lookup"><span data-stu-id="bdc53-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="bdc53-269">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="bdc53-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="bdc53-270">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="bdc53-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="bdc53-271">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="bdc53-272">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="bdc53-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="bdc53-273">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="bdc53-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="bdc53-274">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="bdc53-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="bdc53-275">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="bdc53-276">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="bdc53-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="bdc53-277">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="bdc53-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="bdc53-278">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="bdc53-279">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="bdc53-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="bdc53-280">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="bdc53-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="bdc53-281">msRTCSIP-Msrtcsip-userenabled</span><span class="sxs-lookup"><span data-stu-id="bdc53-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="bdc53-282">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="bdc53-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="bdc53-283">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="bdc53-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="bdc53-284">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="bdc53-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="bdc53-285">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="bdc53-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="bdc53-286">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="bdc53-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="bdc53-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="bdc53-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="bdc53-288">包含在其他类中的类</span><span class="sxs-lookup"><span data-stu-id="bdc53-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdc53-289">Class</span><span class="sxs-lookup"><span data-stu-id="bdc53-289">Class</span></span></th>
<th><span data-ttu-id="bdc53-290">可包含以下类</span><span class="sxs-lookup"><span data-stu-id="bdc53-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="bdc53-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="bdc53-292">msRTCSIP-服务器</span><span class="sxs-lookup"><span data-stu-id="bdc53-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="bdc53-293">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="bdc53-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="bdc53-294">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="bdc53-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="bdc53-295">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="bdc53-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="bdc53-296">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="bdc53-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="bdc53-297">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="bdc53-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="bdc53-298">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="bdc53-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="bdc53-299">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="bdc53-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="bdc53-300">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="bdc53-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="bdc53-301">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="bdc53-302">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-303">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="bdc53-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="bdc53-304">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="bdc53-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="bdc53-305">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="bdc53-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="bdc53-306">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="bdc53-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="bdc53-307">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="bdc53-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="bdc53-308">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="bdc53-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="bdc53-309">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="bdc53-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="bdc53-310">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="bdc53-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="bdc53-311">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="bdc53-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="bdc53-312">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="bdc53-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="bdc53-313">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="bdc53-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="bdc53-314">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="bdc53-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-315">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="bdc53-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="bdc53-316">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="bdc53-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="bdc53-317">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="bdc53-318">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="bdc53-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="bdc53-319">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-320">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="bdc53-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="bdc53-321">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="bdc53-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-322">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="bdc53-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="bdc53-323">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="bdc53-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-324">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="bdc53-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="bdc53-325">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="bdc53-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-326">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="bdc53-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="bdc53-327">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="bdc53-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-328">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="bdc53-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="bdc53-329">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="bdc53-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-330">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="bdc53-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="bdc53-331">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="bdc53-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-332">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="bdc53-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="bdc53-333">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="bdc53-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc53-334">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="bdc53-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="bdc53-335">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="bdc53-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc53-336">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="bdc53-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="bdc53-337">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="bdc53-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
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

