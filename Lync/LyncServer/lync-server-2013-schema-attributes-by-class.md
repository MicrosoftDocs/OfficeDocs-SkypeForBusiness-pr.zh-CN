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
ms.openlocfilehash: 160a148705ececfcbe105dcbc3fca819d4790a0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="58182-102">Lync Server 2013 中按类分类的架构属性</span><span class="sxs-lookup"><span data-stu-id="58182-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58182-103">_**主题上次修改时间：** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="58182-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="58182-104">此部分列出了可以包含在每个 Lync Server 2013 类中的架构属性以及可以包含在其他类中的类。</span><span class="sxs-lookup"><span data-stu-id="58182-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="58182-105">有关所有类及其说明的列表，请参阅[Lync Server 2013 中的架构类和说明](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="58182-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="58182-106">有关所有属性及其说明的列表，请参阅[Lync Server 2013 中的架构属性和说明](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="58182-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="58182-107">按类分类的属性</span><span class="sxs-lookup"><span data-stu-id="58182-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58182-108">种类</span><span class="sxs-lookup"><span data-stu-id="58182-108">Class</span></span></th>
<th><span data-ttu-id="58182-109">可能包含这些属性</span><span class="sxs-lookup"><span data-stu-id="58182-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58182-110">联系人</span><span class="sxs-lookup"><span data-stu-id="58182-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="58182-111">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="58182-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="58182-112">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="58182-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="58182-113">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="58182-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="58182-114">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="58182-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="58182-115">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="58182-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="58182-116">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="58182-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="58182-117">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="58182-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="58182-118">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="58182-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="58182-119">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="58182-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="58182-120">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="58182-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="58182-121">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="58182-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="58182-122">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="58182-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="58182-123">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="58182-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="58182-124">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="58182-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="58182-125">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="58182-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="58182-126">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="58182-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="58182-127">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="58182-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="58182-128">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="58182-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="58182-129">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="58182-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="58182-130">msRTCSIP-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="58182-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="58182-131">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="58182-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="58182-132">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="58182-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="58182-133">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="58182-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="58182-134">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="58182-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="58182-135">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="58182-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="58182-136">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="58182-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="58182-137">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="58182-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="58182-138">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="58182-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="58182-139">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="58182-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="58182-140">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="58182-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="58182-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="58182-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-142">邮件-收件人</span><span class="sxs-lookup"><span data-stu-id="58182-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="58182-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="58182-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="58182-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="58182-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-145">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="58182-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="58182-146">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="58182-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-147">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="58182-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="58182-148">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="58182-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="58182-149">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="58182-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="58182-150">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="58182-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="58182-151">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-152">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="58182-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="58182-153">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="58182-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="58182-154">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="58182-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="58182-155">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="58182-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="58182-156">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="58182-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-157">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="58182-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="58182-158">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="58182-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="58182-159">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="58182-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-160">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="58182-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="58182-161">msRTCSIP-默认值</span><span class="sxs-lookup"><span data-stu-id="58182-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="58182-162">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="58182-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="58182-163">msRTCSIP-域名</span><span class="sxs-lookup"><span data-stu-id="58182-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-164">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="58182-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="58182-165">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="58182-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="58182-166">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="58182-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-167">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="58182-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="58182-168">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="58182-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="58182-169">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="58182-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="58182-170">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-171">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="58182-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="58182-172">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="58182-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="58182-173">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="58182-174">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="58182-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-175">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="58182-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="58182-176">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="58182-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="58182-177">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="58182-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="58182-178">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="58182-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="58182-179">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-180">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="58182-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="58182-181">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="58182-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="58182-182">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="58182-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="58182-183">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="58182-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="58182-184">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-185">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="58182-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="58182-186">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="58182-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-187">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="58182-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="58182-188">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="58182-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="58182-189">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="58182-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="58182-190">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="58182-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-191">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="58182-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="58182-192">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="58182-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="58182-193">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="58182-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="58182-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="58182-195">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="58182-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="58182-196">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="58182-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="58182-197">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="58182-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="58182-198">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="58182-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="58182-199">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="58182-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="58182-200">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="58182-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="58182-201">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-202">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="58182-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="58182-203">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="58182-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-204">msRTCSIP-移动性</span><span class="sxs-lookup"><span data-stu-id="58182-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="58182-205">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="58182-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="58182-206">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="58182-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-207">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="58182-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="58182-208">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="58182-208">dnsHostName</span></span></p>
<p><span data-ttu-id="58182-209">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="58182-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="58182-210">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-211">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="58182-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="58182-212">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="58182-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="58182-213">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="58182-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="58182-214">msRTCSIP-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="58182-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="58182-215">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="58182-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="58182-216">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="58182-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="58182-217">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="58182-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="58182-218">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="58182-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="58182-219">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="58182-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="58182-220">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="58182-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="58182-221">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="58182-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-222">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="58182-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="58182-223">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="58182-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-224">msRTCSIP-状态</span><span class="sxs-lookup"><span data-stu-id="58182-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="58182-225">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="58182-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="58182-226">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="58182-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-227">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="58182-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="58182-228">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="58182-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="58182-229">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="58182-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="58182-230">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="58182-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="58182-231">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="58182-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="58182-232">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="58182-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="58182-233">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-234">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="58182-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="58182-235">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="58182-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="58182-236">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="58182-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="58182-237">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-238">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="58182-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="58182-239">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="58182-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="58182-240">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="58182-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="58182-241">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-242">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="58182-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="58182-243">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="58182-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="58182-244">msRTCSIP-可路由</span><span class="sxs-lookup"><span data-stu-id="58182-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="58182-245">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="58182-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="58182-246">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="58182-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="58182-247">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="58182-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="58182-248">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="58182-249">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="58182-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="58182-250">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="58182-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="58182-251">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="58182-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-252">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="58182-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="58182-253">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="58182-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="58182-254">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="58182-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="58182-255">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-256">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="58182-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="58182-257">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="58182-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-258">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="58182-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="58182-259">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="58182-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="58182-260">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="58182-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="58182-261">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="58182-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-262">用户</span><span class="sxs-lookup"><span data-stu-id="58182-262">User</span></span></p></td>
<td><p><span data-ttu-id="58182-263">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="58182-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="58182-264">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="58182-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="58182-265">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="58182-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="58182-266">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="58182-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="58182-267">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="58182-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="58182-268">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="58182-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="58182-269">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="58182-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="58182-270">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="58182-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="58182-271">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="58182-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="58182-272">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="58182-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="58182-273">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="58182-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="58182-274">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="58182-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="58182-275">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="58182-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="58182-276">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="58182-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="58182-277">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="58182-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="58182-278">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="58182-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="58182-279">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="58182-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="58182-280">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="58182-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="58182-281">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="58182-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="58182-282">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="58182-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="58182-283">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="58182-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="58182-284">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="58182-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="58182-285">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="58182-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="58182-286">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="58182-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="58182-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="58182-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="58182-288">包含在其他类中的类</span><span class="sxs-lookup"><span data-stu-id="58182-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58182-289">种类</span><span class="sxs-lookup"><span data-stu-id="58182-289">Class</span></span></th>
<th><span data-ttu-id="58182-290">可能包含此类</span><span class="sxs-lookup"><span data-stu-id="58182-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58182-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="58182-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="58182-292">msRTCSIP-服务器</span><span class="sxs-lookup"><span data-stu-id="58182-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="58182-293">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="58182-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="58182-294">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="58182-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="58182-295">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="58182-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="58182-296">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="58182-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="58182-297">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="58182-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="58182-298">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="58182-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="58182-299">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="58182-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="58182-300">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="58182-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="58182-301">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="58182-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="58182-302">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="58182-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-303">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="58182-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="58182-304">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="58182-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="58182-305">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="58182-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="58182-306">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="58182-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="58182-307">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="58182-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="58182-308">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="58182-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="58182-309">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="58182-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="58182-310">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="58182-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="58182-311">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="58182-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="58182-312">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="58182-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="58182-313">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="58182-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="58182-314">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="58182-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-315">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="58182-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="58182-316">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="58182-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="58182-317">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="58182-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="58182-318">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="58182-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="58182-319">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="58182-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-320">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="58182-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="58182-321">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="58182-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-322">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="58182-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="58182-323">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="58182-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-324">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="58182-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="58182-325">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="58182-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-326">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="58182-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="58182-327">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="58182-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-328">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="58182-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="58182-329">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="58182-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-330">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="58182-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="58182-331">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="58182-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-332">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="58182-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="58182-333">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="58182-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58182-334">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="58182-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="58182-335">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="58182-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58182-336">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="58182-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="58182-337">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="58182-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
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

