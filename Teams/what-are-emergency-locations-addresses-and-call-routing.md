---
title: 计划和管理紧急呼叫
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: 了解紧急呼叫，包括有关紧急地址、紧急呼叫路由和动态紧急呼叫的信息。
ms.openlocfilehash: 4f2ef86d05537a147a459fd6bc121f0680b534bd
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031598"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="21066-103">管理紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="21066-103">Manage emergency calling</span></span>

<span data-ttu-id="21066-104">本文介绍管理紧急呼叫时需要知道的概念，其中包括有关紧急地址、动态紧急地址和紧急 &mdash; 呼叫路由的信息。</span><span class="sxs-lookup"><span data-stu-id="21066-104">This article describes concepts you'll need to know to manage emergency calling&mdash;it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="21066-105">本文使用以下术语：</span><span class="sxs-lookup"><span data-stu-id="21066-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="21066-106">**紧急地址** - 一个街道地址，用于组织的业务 &mdash; 地点的物理地址或街道地址。</span><span class="sxs-lookup"><span data-stu-id="21066-106">**Emergency address** - A civic address&mdash;the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="21066-107">例如，地址  *12345 North Main Street， Redmond， WA 98052* 用于将紧急呼叫路由到相应的调度机构，以及帮助定位紧急呼叫者。</span><span class="sxs-lookup"><span data-stu-id="21066-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="21066-108">**地点** - 通常是楼层、建筑物、楼层或办公室号码。</span><span class="sxs-lookup"><span data-stu-id="21066-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="21066-109">位置与紧急地址相关联，以在建筑物内提供更精确的位置。</span><span class="sxs-lookup"><span data-stu-id="21066-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="21066-110">你可以将无限数量的地点与紧急地址相关联。</span><span class="sxs-lookup"><span data-stu-id="21066-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="21066-111">例如，如果组织有多个建筑物，可能需要包括每个建筑物和每个建筑物内每个楼层的位置信息。</span><span class="sxs-lookup"><span data-stu-id="21066-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="21066-112">**紧急位置** - 位置是具有可选位置 &mdash; 的市政地址。</span><span class="sxs-lookup"><span data-stu-id="21066-112">**Emergency location** - A location is a civic address&mdash;with an optional place.</span></span> <span data-ttu-id="21066-113">如果你的企业具有多个物理位置，则你可能需要多个紧急位置。</span><span class="sxs-lookup"><span data-stu-id="21066-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="21066-114">创建紧急地址时，会自动为此地址创建唯一的位置 ID。</span><span class="sxs-lookup"><span data-stu-id="21066-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="21066-115">例如，如果向紧急地址添加位置，则向建筑物地址添加楼层时，将创建一个位置 ID，用于组合使用紧急地址 &mdash; &mdash; 和位置。</span><span class="sxs-lookup"><span data-stu-id="21066-115">If you add a place to an emergency address&mdash;for example, if you add a floor to a building address&mdash;a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="21066-116">本示例将存在两个位置 ID：一个针对市/区地址;一个地址用于已加入的市政地址和关联位置。</span><span class="sxs-lookup"><span data-stu-id="21066-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="21066-117">向用户或网站分配紧急位置时，这是与用户或网站关联的此唯一位置 ID。</span><span class="sxs-lookup"><span data-stu-id="21066-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="21066-118">**已注册** 的地址 - 分配给每个呼叫计划用户的紧急地址;它有时称为静态紧急地址或记录地址。</span><span class="sxs-lookup"><span data-stu-id="21066-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="21066-119"> (注册的地址不适用于直接路由用户.) </span><span class="sxs-lookup"><span data-stu-id="21066-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="21066-120">使用管理中心为呼叫计划用户创建Teams地址。</span><span class="sxs-lookup"><span data-stu-id="21066-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="21066-121">管理紧急呼叫方式存在一些差异，具体取决于你使用的是电话系统呼叫计划电话系统 PSTN 连接直接路由。</span><span class="sxs-lookup"><span data-stu-id="21066-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="21066-122">本文中介绍了这些注意事项。</span><span class="sxs-lookup"><span data-stu-id="21066-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="21066-123">紧急地址验证</span><span class="sxs-lookup"><span data-stu-id="21066-123">Emergency address validation</span></span>

<span data-ttu-id="21066-124">若要向用户或网络标识符分配紧急地址，必须确保紧急地址标记为"已验证"。</span><span class="sxs-lookup"><span data-stu-id="21066-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as "validated."</span></span>  <span data-ttu-id="21066-125">地址验证可确保地址是合法的，并且分配后无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="21066-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="21066-126">如果使用地址管理中心中的地址映射搜索功能Teams紧急地址，该地址会自动标记为已验证。</span><span class="sxs-lookup"><span data-stu-id="21066-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="21066-127">无法修改已验证的紧急地址。</span><span class="sxs-lookup"><span data-stu-id="21066-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="21066-128">因此，如果地址的格式或表示形式发生更改，则必须使用更新的格式创建新地址。</span><span class="sxs-lookup"><span data-stu-id="21066-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="21066-129">紧急地址地理代码</span><span class="sxs-lookup"><span data-stu-id="21066-129">Emergency address geo codes</span></span>

<span data-ttu-id="21066-130">每个紧急地址可以具有与 (和经度) 地理代码。</span><span class="sxs-lookup"><span data-stu-id="21066-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="21066-131">这些国家/地区使用这些地理代码来帮助通过动态位置路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21066-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="21066-132">如果使用紧急管理中心中的地址映射搜索功能定义Teams地址，则地理代码会自动与紧急地址相关联。</span><span class="sxs-lookup"><span data-stu-id="21066-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="21066-133">如果使用 PowerShell 定义地址，还可以将地理代码与地址关联。</span><span class="sxs-lookup"><span data-stu-id="21066-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="21066-134">但是，Microsoft 建议使用 Teams 管理中心中的地图搜索功能为呼叫计划创建紧急地址，这将确保地址经过格式设置、验证并拥有适当的地理代码。</span><span class="sxs-lookup"><span data-stu-id="21066-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="21066-135">若要为网络标识符分配紧急位置以用于动态紧急呼叫，紧急地址必须包含相应的地理代码。</span><span class="sxs-lookup"><span data-stu-id="21066-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="21066-136">通话套餐注意事项</span><span class="sxs-lookup"><span data-stu-id="21066-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="21066-137">若要了解呼叫计划在你的区域中是否可用，请参阅通话套餐[的"国家/地区"和"区域可用性"。](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="21066-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="21066-138">紧急呼叫启用</span><span class="sxs-lookup"><span data-stu-id="21066-138">Emergency call enablement</span></span>

<span data-ttu-id="21066-139">每个呼叫计划用户都将自动启用紧急呼叫，并且需要具有与其分配的电话号码相关联的已注册紧急地址。</span><span class="sxs-lookup"><span data-stu-id="21066-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="21066-140">当位置必须与电话号码关联时，取决于国家/地区：</span><span class="sxs-lookup"><span data-stu-id="21066-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="21066-141">例如，在美国和加拿大，向用户分配号码时需要紧急位置。</span><span class="sxs-lookup"><span data-stu-id="21066-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="21066-142">对于其他国家/地区（例如欧洲、中东和非洲 (EMEA) ）来说，从 Microsoft 365 或 Office 365 获取电话号码或者从另一服务提供商或运营商转移电话号码时，需要紧急位置。</span><span class="sxs-lookup"><span data-stu-id="21066-142">For other countries--such as in Europe, the Middle East, and Africa (EMEA)--an emergency location is required when you get the phone number from Microsoft 365 or Office 365, or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="21066-143">动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="21066-143">Dynamic emergency calling</span></span>

<span data-ttu-id="21066-144">Microsoft 呼叫计划的动态紧急呼叫提供根据客户端的当前位置配置和路由Teams呼叫的功能。</span><span class="sxs-lookup"><span data-stu-id="21066-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="21066-145">自动路由到相应的公共安全应答点 (PSAP) 或通知安全服务台人员的能力因使用安全Teams国家/地区而异。</span><span class="sxs-lookup"><span data-stu-id="21066-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="21066-146">对于呼叫计划用户，仅美国支持用于路由紧急呼叫的动态位置，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21066-146">For Calling Plan users, dynamic location for routing emergency calls is only supported in the United States as follows.</span></span> <span data-ttu-id="21066-147"> (有关动态紧急呼叫和直接路由的信息，请参阅 [直接路由注意事项](#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="21066-147">(For information about dynamic emergency calling and Direct Routing, see [Considerations for Direct Routing](#considerations-for-direct-routing).</span></span>

- <span data-ttu-id="21066-148">如果美国Teams计划的客户端动态获取美国内的紧急地址，该地址将用于紧急路由，而不是注册的地址，并且该呼叫将自动路由到地址服务区域中的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="21066-148">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="21066-149">如果Teams呼叫计划用户的用户客户端未在美国动态获取紧急地址，则注册的紧急地址用于帮助筛选和路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="21066-149">If a Teams client for a United States Calling Plan user doesn't dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="21066-150">但是，在将呼叫方连接到相应的 PSAP 之前，将筛选呼叫以确定是否要求更新的地址。</span><span class="sxs-lookup"><span data-stu-id="21066-150">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="21066-151">在美国，必须配置属于分配给网络标识符的紧急位置的一部分的市政地址，并 &mdash; 包含关联的地理代码。</span><span class="sxs-lookup"><span data-stu-id="21066-151">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers&mdash;and include the associated geo codes.</span></span> <span data-ttu-id="21066-152">有关详细信息，请参阅 [计划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="21066-152">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="21066-153">紧急呼叫路由</span><span class="sxs-lookup"><span data-stu-id="21066-153">Emergency call routing</span></span>

<span data-ttu-id="21066-154">当Teams呼叫计划用户拨打紧急号码时，呼叫路由到 PSAP 的方式取决于以下条件：</span><span class="sxs-lookup"><span data-stu-id="21066-154">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="21066-155">紧急地址是否由客户端动态Teams确定。</span><span class="sxs-lookup"><span data-stu-id="21066-155">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="21066-156">紧急地址是否是与用户电话号码关联的已注册地址。</span><span class="sxs-lookup"><span data-stu-id="21066-156">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="21066-157">该国家/地区紧急呼叫网络。</span><span class="sxs-lookup"><span data-stu-id="21066-157">The emergency calling network of that country.</span></span>

  <span data-ttu-id="21066-158">**在美国：**</span><span class="sxs-lookup"><span data-stu-id="21066-158">**In the United States:**</span></span>

  - <span data-ttu-id="21066-159">如果Teams位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫会自动路由到该地理位置服务的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="21066-159">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="21066-160">如果Teams客户端未位于租户定义的动态紧急位置，则国家/地区呼叫中心将筛选来自该客户端的紧急呼叫，以确定呼叫者的位置，然后再将呼叫转接到为该地理位置服务的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="21066-160">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="21066-161">如果紧急呼叫者无法将其紧急位置更新到筛选中心，呼叫将转接到 PSAP，为呼叫者注册的地址提供。</span><span class="sxs-lookup"><span data-stu-id="21066-161">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="21066-162">**加拿大、爱尔兰** 和英国将首先筛选紧急呼叫，以确定用户的当前位置，然后再将呼叫连接到相应的调度中心。</span><span class="sxs-lookup"><span data-stu-id="21066-162">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="21066-163">**法国、德国以及** 西班牙的紧急呼叫将直接路由到 PSAP，为与号码关联的紧急地址提供紧急地址，而不考虑呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="21066-163">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="21066-164">**在荷兰，** 紧急呼叫直接路由到 PSAP，该号码的本地区号与呼叫者的位置不同。</span><span class="sxs-lookup"><span data-stu-id="21066-164">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="21066-165">**在澳大利亚**，紧急地址由运营商合作伙伴配置和路由。</span><span class="sxs-lookup"><span data-stu-id="21066-165">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="21066-166">**在日本**，不支持紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21066-166">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="21066-167">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="21066-167">For more information, see:</span></span>

- [<span data-ttu-id="21066-168">通话套餐</span><span class="sxs-lookup"><span data-stu-id="21066-168">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="21066-169">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="21066-169">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="21066-170">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="21066-170">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="21066-171">直接路由注意事项</span><span class="sxs-lookup"><span data-stu-id="21066-171">Considerations for Direct Routing</span></span>

<span data-ttu-id="21066-172">如果呼叫计划在你的区域中不可用，或者你想要保留你的现有运营商，请考虑直接 [路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="21066-172">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="21066-173">有关详细信息，请参阅配置[直接路由和管理](direct-routing-configure.md)[紧急呼叫路由策略](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="21066-173">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="21066-174">紧急呼叫启用和配置</span><span class="sxs-lookup"><span data-stu-id="21066-174">Emergency call enablement and configuration</span></span>

<span data-ttu-id="21066-175">必须使用 Teams 紧急呼叫路由策略 (TeamsEmergencyCallRoutingPolicy) 来定义紧急号码及其关联的路由目标，为直接路由用户定义紧急呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="21066-175">You must define emergency calling policies for Direct Routing users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="21066-176"> (请注意，直接路由用户.) </span><span class="sxs-lookup"><span data-stu-id="21066-176">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="21066-177">可以将紧急呼叫路由策略Teams直接路由用户帐户和网络站点。</span><span class="sxs-lookup"><span data-stu-id="21066-177">You can assign an emergency call routing policy  to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="21066-178">当Teams客户端启动或更改网络连接时，Teams将执行客户端所在的网络站点的查找，如下所示：</span><span class="sxs-lookup"><span data-stu-id="21066-178">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="21066-179">如果紧急呼叫路由策略与站点关联，则站点策略用于配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21066-179">If an emergency call routing policy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="21066-180">如果没有与站点关联的紧急呼叫路由策略，或者客户端在未定义的站点连接，则使用与用户帐户关联的紧急呼叫路由策略来配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21066-180">If there is no emergency call routing policy associated with the site, or if the client is connected at an undefined site, then the emergency call routing policy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="21066-181">如果Teams客户端无法获取紧急呼叫路由策略，则用户未启用紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21066-181">If the Teams client is unable to obtain an emergency call routing policy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="21066-182">动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="21066-182">Dynamic emergency calling</span></span>

<span data-ttu-id="21066-183">Teams路由的用户客户端可以获取动态紧急地址，该地址可用于根据调用方的位置动态路由调用。</span><span class="sxs-lookup"><span data-stu-id="21066-183">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="21066-184">有关详细信息，请参阅 [配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="21066-184">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="21066-185">紧急呼叫路由</span><span class="sxs-lookup"><span data-stu-id="21066-185">Emergency call routing</span></span>

<span data-ttu-id="21066-186">紧急呼叫路由策略引用联机 PSTN 使用情况，该策略必须具有适当的直接路由配置，以正确将紧急呼叫路由到 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="21066-186">The emergency call routing policy references an online PSTN usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="21066-187">具体而言，必须确保紧急拨号字符串有 OnlineVoiceRoute。</span><span class="sxs-lookup"><span data-stu-id="21066-187">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="21066-188">有关详细信息，请参阅配置 [直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="21066-188">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

<span data-ttu-id="21066-189"> (：Teams客户端在紧急号码前面加"+"登录，其方式与Skype for Business类似;即 +911。</span><span class="sxs-lookup"><span data-stu-id="21066-189">(Note: Teams clients prepend the "+" sign in front of emergency numbers in a similar manner that Skype for Business client does; that is, +911.</span></span> <span data-ttu-id="21066-190">这将在几个月内修改此行为，Teams紧急呼叫不再发送号码前面的"+";即 911.) </span><span class="sxs-lookup"><span data-stu-id="21066-190">This behavior will be modified in the coming months so that Teams emergency calls will no longer be sending a "+" preceding the number; that is, 911.)</span></span>

<span data-ttu-id="21066-191">根据给定国家/地区内的紧急呼叫网络，为直接路由用户动态路由紧急呼叫的能力有所不同。</span><span class="sxs-lookup"><span data-stu-id="21066-191">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="21066-192">有两种可用的解决方案：</span><span class="sxs-lookup"><span data-stu-id="21066-192">There are two solutions available:</span></span>

- <span data-ttu-id="21066-193">紧急路由服务提供商 (美国) </span><span class="sxs-lookup"><span data-stu-id="21066-193">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="21066-194">紧急位置标识号 (ELIN) 网关应用程序</span><span class="sxs-lookup"><span data-stu-id="21066-194">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="21066-195">紧急路由服务提供商</span><span class="sxs-lookup"><span data-stu-id="21066-195">Emergency Routing Service Providers</span></span>

<span data-ttu-id="21066-196">在美国，有许多经过认证的紧急路由服务提供商 (ERSP) 根据呼叫者的位置自动路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21066-196">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="21066-197">如果将紧急路由服务提供商集成到直接路由部署中，具有动态获取位置的紧急呼叫将自动路由到提供该位置的公共安全应答点 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="21066-197">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="21066-198">没有动态获取位置的紧急呼叫首先经过筛选，以确定用户的当前位置，然后根据更新的位置将呼叫连接到相应的调度中心。</span><span class="sxs-lookup"><span data-stu-id="21066-198">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="21066-199">有关详细信息，请参阅通过 [直接路由 认证的会话边界控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="21066-199">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="21066-200">紧急位置标识号 (ELIN) 应用程序</span><span class="sxs-lookup"><span data-stu-id="21066-200">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="21066-201">会话边界控制器 (SBC) ELIN 应用程序 (紧急位置标识) 编号。</span><span class="sxs-lookup"><span data-stu-id="21066-201">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="21066-202">如果 SBC ELIN 应用程序集成到直接路由部署中，则必须在 ELIN 应用程序中配置紧急地址和关联的电话号码，然后将 ELIN 记录上传到相应 PSTN 中的紧急呼叫数据库。</span><span class="sxs-lookup"><span data-stu-id="21066-202">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="21066-203">Teams ELIN 标识符的紧急位置必须与 ELIN 应用程序中的位置匹配。</span><span class="sxs-lookup"><span data-stu-id="21066-203">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="21066-204">将具有动态获取位置的紧急呼叫路由到相应的 SBC 时，ELIN 应用程序：</span><span class="sxs-lookup"><span data-stu-id="21066-204">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="21066-205">分析调用方的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="21066-205">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="21066-206">将位置与 ELIN 记录匹配。</span><span class="sxs-lookup"><span data-stu-id="21066-206">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="21066-207">将紧急呼叫者的电话号码替换为 ELIN 电话号码。</span><span class="sxs-lookup"><span data-stu-id="21066-207">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="21066-208">将调用路由到提供该位置的 PSAP，然后调度程序从上传的 ELIN 记录获取位置。</span><span class="sxs-lookup"><span data-stu-id="21066-208">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="21066-209">呼叫回紧急号码后，ELIN 应用程序将执行与原始紧急呼叫者相反的呼叫号码替换。</span><span class="sxs-lookup"><span data-stu-id="21066-209">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="21066-210">有关详细信息，请参阅通过 [直接路由 认证的会话边界控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="21066-210">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="21066-211">安全服务台通知</span><span class="sxs-lookup"><span data-stu-id="21066-211">Security desk notification</span></span>

<span data-ttu-id="21066-212">安全服务台通知可用于 Microsoft 呼叫计划和 电话系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="21066-212">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="21066-213">使用 Teams 紧急呼叫策略 (TeamsEmergencyCallingPolicy) 来配置在紧急呼叫期间应通知哪些人以及如何通知他们：仅聊天、参加会议和静音，或者已进入和静音但能够取消静音。</span><span class="sxs-lookup"><span data-stu-id="21066-213">You use a Teams emergency calling policy (TeamsEmergencyCallingPolicy) to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="21066-214">您还可以指定要呼叫和加入紧急呼叫的用户或组的外部 PSTN 号码。</span><span class="sxs-lookup"><span data-stu-id="21066-214">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="21066-215">紧急呼叫策略可以授予用户Teams或分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="21066-215">An emergency calling policy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="21066-216">当Teams客户端启动或更改网络连接时，Teams将执行客户端所在的网络站点的查找：</span><span class="sxs-lookup"><span data-stu-id="21066-216">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="21066-217">如果紧急呼叫策略与网络站点相关联，则站点策略用于配置安全服务台通知。</span><span class="sxs-lookup"><span data-stu-id="21066-217">If an emergency calling policy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="21066-218">如果没有与站点关联的紧急呼叫策略，或者客户端在未定义的站点连接，则与用户帐户关联的紧急呼叫策略用于配置安全服务台通知。</span><span class="sxs-lookup"><span data-stu-id="21066-218">If there is no emergency calling policy associated with the site, or if the client is connected at an undefined site, then the emergency calling policy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="21066-219">如果Teams客户端无法获取紧急呼叫策略，则用户未启用安全服务台通知。</span><span class="sxs-lookup"><span data-stu-id="21066-219">If the Teams client is unable to obtain an emergency calling policy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="21066-220">在紧急呼叫期间，安全服务台将参加会议，安全服务台用户的体验根据紧急呼叫Teams控制。</span><span class="sxs-lookup"><span data-stu-id="21066-220">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the Teams emergency calling policy.</span></span> <span data-ttu-id="21066-221">与每个安全服务台成员开始群组聊天，紧急呼叫者的位置通过重要消息通知共享。</span><span class="sxs-lookup"><span data-stu-id="21066-221">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="21066-222">如果将会议选项配置为策略的一部分，则额外调用每个安全服务台用户作为会议的一部分。</span><span class="sxs-lookup"><span data-stu-id="21066-222">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="21066-223">相关主题</span><span class="sxs-lookup"><span data-stu-id="21066-223">Related topics</span></span>

- [<span data-ttu-id="21066-224">管理紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="21066-224">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="21066-225">管理紧急呼叫路由策略 </span><span class="sxs-lookup"><span data-stu-id="21066-225">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="21066-226">为你的组织添加、更改或删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="21066-226">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="21066-227">为用户分配或更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="21066-227">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="21066-228">规划和配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="21066-228">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
