---
title: 'Lync Server 2013: 按类分类的架构属性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes by class
ms:assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398544(v=OCS.15)
ms:contentKeyID: 48184468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09978d9b0cad055b4c3b33976df838ba5543887d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="daec2-102">Lync Server 2013 中按类分类的架构属性</span><span class="sxs-lookup"><span data-stu-id="daec2-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daec2-103">_**主题上次修改时间:** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="daec2-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="daec2-104">此部分列出了可以包含在每个 Lync Server 2013 类中的架构属性以及可以包含在其他类中的类。</span><span class="sxs-lookup"><span data-stu-id="daec2-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="daec2-105">有关所有类及其说明的列表, 请参阅[Lync Server 2013 中的架构类和说明](lync-server-2013-schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="daec2-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="daec2-106">有关所有属性及其说明的列表, 请参阅[Lync Server 2013 中的架构属性和说明](lync-server-2013-schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="daec2-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="daec2-107">按类分类的属性</span><span class="sxs-lookup"><span data-stu-id="daec2-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daec2-108">种类</span><span class="sxs-lookup"><span data-stu-id="daec2-108">Class</span></span></th>
<th><span data-ttu-id="daec2-109">可能包含这些属性</span><span class="sxs-lookup"><span data-stu-id="daec2-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daec2-110">联系人</span><span class="sxs-lookup"><span data-stu-id="daec2-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="daec2-111">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="daec2-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="daec2-112">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="daec2-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="daec2-113">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="daec2-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="daec2-114">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="daec2-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="daec2-115">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="daec2-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="daec2-116">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="daec2-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="daec2-117">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="daec2-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="daec2-118">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="daec2-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="daec2-119">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="daec2-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="daec2-120">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="daec2-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="daec2-121">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="daec2-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="daec2-122">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="daec2-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="daec2-123">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="daec2-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="daec2-124">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="daec2-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="daec2-125">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="daec2-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="daec2-126">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="daec2-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="daec2-127">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="daec2-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="daec2-128">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="daec2-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="daec2-129">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="daec2-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="daec2-130">msRTCSIP-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="daec2-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="daec2-131">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="daec2-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="daec2-132">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="daec2-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="daec2-133">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="daec2-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="daec2-134">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="daec2-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="daec2-135">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="daec2-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="daec2-136">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="daec2-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="daec2-137">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="daec2-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="daec2-138">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="daec2-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="daec2-139">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="daec2-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="daec2-140">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="daec2-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="daec2-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="daec2-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-142">邮件-收件人</span><span class="sxs-lookup"><span data-stu-id="daec2-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="daec2-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="daec2-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="daec2-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="daec2-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-145">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="daec2-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="daec2-146">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="daec2-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-147">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="daec2-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="daec2-148">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="daec2-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="daec2-149">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="daec2-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="daec2-150">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="daec2-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="daec2-151">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-152">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="daec2-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="daec2-153">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="daec2-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="daec2-154">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="daec2-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="daec2-155">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="daec2-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="daec2-156">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="daec2-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-157">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="daec2-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="daec2-158">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="daec2-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="daec2-159">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="daec2-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-160">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="daec2-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="daec2-161">msRTCSIP-默认值</span><span class="sxs-lookup"><span data-stu-id="daec2-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="daec2-162">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="daec2-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="daec2-163">msRTCSIP-域名</span><span class="sxs-lookup"><span data-stu-id="daec2-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-164">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="daec2-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="daec2-165">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="daec2-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="daec2-166">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="daec2-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-167">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="daec2-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="daec2-168">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="daec2-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="daec2-169">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="daec2-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="daec2-170">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-171">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="daec2-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="daec2-172">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="daec2-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="daec2-173">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="daec2-174">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="daec2-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-175">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="daec2-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="daec2-176">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="daec2-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="daec2-177">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="daec2-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="daec2-178">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="daec2-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="daec2-179">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-180">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="daec2-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="daec2-181">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="daec2-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="daec2-182">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="daec2-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="daec2-183">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="daec2-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="daec2-184">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-185">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="daec2-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="daec2-186">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="daec2-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-187">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="daec2-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="daec2-188">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="daec2-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="daec2-189">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="daec2-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="daec2-190">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="daec2-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-191">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="daec2-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="daec2-192">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="daec2-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="daec2-193">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="daec2-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="daec2-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="daec2-195">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="daec2-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="daec2-196">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="daec2-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="daec2-197">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="daec2-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="daec2-198">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="daec2-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="daec2-199">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="daec2-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="daec2-200">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="daec2-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="daec2-201">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-202">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="daec2-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="daec2-203">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="daec2-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-204">msRTCSIP-移动性</span><span class="sxs-lookup"><span data-stu-id="daec2-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="daec2-205">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="daec2-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="daec2-206">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="daec2-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-207">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="daec2-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="daec2-208">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="daec2-208">dnsHostName</span></span></p>
<p><span data-ttu-id="daec2-209">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="daec2-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="daec2-210">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-211">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="daec2-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="daec2-212">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="daec2-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="daec2-213">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="daec2-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="daec2-214">msRTCSIP-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="daec2-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="daec2-215">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="daec2-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="daec2-216">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="daec2-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="daec2-217">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="daec2-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="daec2-218">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="daec2-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="daec2-219">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="daec2-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="daec2-220">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="daec2-221">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="daec2-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-222">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="daec2-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="daec2-223">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="daec2-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-224">msRTCSIP-状态</span><span class="sxs-lookup"><span data-stu-id="daec2-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="daec2-225">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="daec2-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="daec2-226">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="daec2-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-227">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="daec2-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="daec2-228">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="daec2-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="daec2-229">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="daec2-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="daec2-230">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="daec2-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="daec2-231">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="daec2-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="daec2-232">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="daec2-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="daec2-233">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-234">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="daec2-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="daec2-235">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="daec2-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="daec2-236">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="daec2-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="daec2-237">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-238">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="daec2-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="daec2-239">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="daec2-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="daec2-240">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="daec2-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="daec2-241">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-242">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="daec2-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="daec2-243">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="daec2-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="daec2-244">msRTCSIP-可路由</span><span class="sxs-lookup"><span data-stu-id="daec2-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="daec2-245">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="daec2-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="daec2-246">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="daec2-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="daec2-247">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="daec2-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="daec2-248">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="daec2-249">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="daec2-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="daec2-250">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="daec2-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="daec2-251">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="daec2-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-252">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="daec2-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="daec2-253">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="daec2-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="daec2-254">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="daec2-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="daec2-255">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-256">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="daec2-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="daec2-257">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="daec2-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-258">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="daec2-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="daec2-259">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="daec2-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="daec2-260">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="daec2-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="daec2-261">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="daec2-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-262">用户</span><span class="sxs-lookup"><span data-stu-id="daec2-262">User</span></span></p></td>
<td><p><span data-ttu-id="daec2-263">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="daec2-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="daec2-264">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="daec2-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="daec2-265">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="daec2-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="daec2-266">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="daec2-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="daec2-267">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="daec2-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="daec2-268">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="daec2-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="daec2-269">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="daec2-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="daec2-270">msRTCSIP-行</span><span class="sxs-lookup"><span data-stu-id="daec2-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="daec2-271">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="daec2-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="daec2-272">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="daec2-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="daec2-273">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="daec2-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="daec2-274">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="daec2-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="daec2-275">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="daec2-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="daec2-276">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="daec2-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="daec2-277">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="daec2-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="daec2-278">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="daec2-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="daec2-279">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="daec2-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="daec2-280">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="daec2-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="daec2-281">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="daec2-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="daec2-282">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="daec2-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="daec2-283">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="daec2-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="daec2-284">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="daec2-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="daec2-285">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="daec2-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="daec2-286">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="daec2-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="daec2-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="daec2-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="daec2-288">包含在其他类中的类</span><span class="sxs-lookup"><span data-stu-id="daec2-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daec2-289">种类</span><span class="sxs-lookup"><span data-stu-id="daec2-289">Class</span></span></th>
<th><span data-ttu-id="daec2-290">可能包含此类</span><span class="sxs-lookup"><span data-stu-id="daec2-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daec2-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="daec2-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="daec2-292">msRTCSIP-服务器</span><span class="sxs-lookup"><span data-stu-id="daec2-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="daec2-293">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="daec2-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="daec2-294">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="daec2-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="daec2-295">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="daec2-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="daec2-296">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="daec2-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="daec2-297">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="daec2-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="daec2-298">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="daec2-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="daec2-299">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="daec2-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="daec2-300">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="daec2-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="daec2-301">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="daec2-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="daec2-302">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="daec2-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-303">msRTCSIP-服务</span><span class="sxs-lookup"><span data-stu-id="daec2-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="daec2-304">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="daec2-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="daec2-305">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="daec2-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="daec2-306">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="daec2-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="daec2-307">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="daec2-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="daec2-308">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="daec2-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="daec2-309">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="daec2-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="daec2-310">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="daec2-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="daec2-311">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="daec2-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="daec2-312">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="daec2-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="daec2-313">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="daec2-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="daec2-314">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="daec2-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-315">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="daec2-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="daec2-316">msRTCSIP-域</span><span class="sxs-lookup"><span data-stu-id="daec2-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="daec2-317">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="daec2-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="daec2-318">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="daec2-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="daec2-319">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="daec2-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-320">msRTCSIP-池</span><span class="sxs-lookup"><span data-stu-id="daec2-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="daec2-321">msRTCSIP-Pool</span><span class="sxs-lookup"><span data-stu-id="daec2-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-322">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="daec2-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="daec2-323">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="daec2-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-324">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="daec2-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="daec2-325">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="daec2-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-326">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="daec2-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="daec2-327">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="daec2-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-328">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="daec2-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="daec2-329">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="daec2-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-330">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="daec2-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="daec2-331">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="daec2-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-332">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="daec2-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="daec2-333">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="daec2-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daec2-334">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="daec2-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="daec2-335">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="daec2-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daec2-336">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="daec2-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="daec2-337">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="daec2-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
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

