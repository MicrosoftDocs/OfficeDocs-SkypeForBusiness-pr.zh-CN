---
title: 计划紧急呼叫、紧急地址、紧急呼叫路由、动态紧急呼叫
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
description: 了解紧急电话，包括有关紧急地址、紧急呼叫路由和动态紧急呼叫的信息。
ms.openlocfilehash: 85a09880c1eec83851208197c008c8aaafac88f6
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161685"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="3a8d3-103">管理紧急电话</span><span class="sxs-lookup"><span data-stu-id="3a8d3-103">Manage emergency calling</span></span>

<span data-ttu-id="3a8d3-104">本文介绍了管理紧急呼叫的概念，其中包括有关紧急地址、动态紧急地址和紧急呼叫路由的信息。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-104">This article describes concepts you'll need to know to manage emergency calling--it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="3a8d3-105">本文使用以下术语：</span><span class="sxs-lookup"><span data-stu-id="3a8d3-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="3a8d3-106">**紧急地址**-市政地址-您的组织的办公地点的物理地址或街道地址。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-106">**Emergency Address** - A civic address--the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="3a8d3-107">例如，地址 12345 "北卡罗来纳州"、 *"雷德蒙"、"WA" 和 "WA 98052* " 用于将紧急呼叫路由到相应的派遣机构，并帮助查找紧急呼叫方。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="3a8d3-108">**置入**-通常为楼层、建筑物、翼形或办公室号码。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="3a8d3-109">"地点" 与紧急地址相关联，以便在大楼内提供更准确的位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="3a8d3-110">您可以拥有与紧急地址相关联的无限位数。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="3a8d3-111">例如，如果您的组织有多个建筑物，您可能希望在每个建筑物内包括每个建筑物和每个楼层的位置信息。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="3a8d3-112">**紧急地点**-一个位置是市政地址-有一个可选位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-112">**Emergency Location** - A location is a civic address--with an optional place.</span></span> <span data-ttu-id="3a8d3-113">如果您的企业有多个物理位置，则可能需要多个紧急位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="3a8d3-114">创建紧急地址时，系统会自动为此地址创建一个唯一的位置 ID。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="3a8d3-115">如果您向某一 "紧急地址" 添加一个位置，例如，向建筑物地址添加一个楼层时，将为 "紧急地址" 和 "地点" 的组合创建一个位置 ID。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-115">If you add a place to an emergency address--for example, if you add a floor to a building address--a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="3a8d3-116">在此示例中，将有两个位置 Id：一个用于市政地址;一个用于加入的市政地址和关联位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="3a8d3-117">将紧急位置分配给用户或网站时，它是与用户或网站相关联的唯一位置 ID。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="3a8d3-118">**已注册地址**-分配给每个呼叫计划用户的紧急地址;它有时被称为静态紧急地址或记录地址。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="3a8d3-119">（注册的地址不适用于直接路由用户。）</span><span class="sxs-lookup"><span data-stu-id="3a8d3-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="3a8d3-120">使用团队管理中心为呼叫计划用户创建紧急地址。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="3a8d3-121">根据您使用的是电话系统呼叫计划还是适用于 PSTN 连接的电话系统直接路由，您管理紧急呼叫的方式有一些差异。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="3a8d3-122">本文中介绍了这些注意事项。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="3a8d3-123">紧急地址验证</span><span class="sxs-lookup"><span data-stu-id="3a8d3-123">Emergency address validation</span></span>

<span data-ttu-id="3a8d3-124">若要为用户或网络标识符分配紧急地址，必须确保紧急地址标记为 "已验证"。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as “validated.”</span></span>  <span data-ttu-id="3a8d3-125">地址验证可确保地址是合法的，并且在分配后不能被修改。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="3a8d3-126">如果您通过使用 "团队管理中心" 中的地址映射搜索功能来定义紧急地址，则地址会自动标记为 "已验证"。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="3a8d3-127">您不能修改已验证的紧急地址。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="3a8d3-128">因此，如果地址的格式或表示形式发生更改，则必须使用已更新的格式创建新地址。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="3a8d3-129">紧急地址地域代码</span><span class="sxs-lookup"><span data-stu-id="3a8d3-129">Emergency address geo codes</span></span>

<span data-ttu-id="3a8d3-130">每个紧急地址都可以具有与其关联的地域代码（纬度和经度）。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="3a8d3-131">这些地理代码用于某些国家/地区，用动态位置帮助您路由紧急电话。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="3a8d3-132">如果您通过使用 "团队管理中心" 中的地址映射搜索功能来定义紧急地址，则 geo 代码将自动与紧急地址相关联。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="3a8d3-133">如果使用 PowerShell 定义地址，还可以将地域代码与地址相关联。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="3a8d3-134">但是，Microsoft 建议使用团队管理中心中的 "映射搜索" 功能为通话计划创建紧急地址，这将确保地址已设置格式、验证，并具有相应的 geo 代码。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="3a8d3-135">要将紧急位置分配给网络标识符以进行动态紧急呼叫，紧急地址必须包含相应的 geo 代码。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="3a8d3-136">通话计划的注意事项</span><span class="sxs-lookup"><span data-stu-id="3a8d3-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="3a8d3-137">要了解您所在区域是否有通话计划，请参阅[电话计划的国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="3a8d3-138">紧急电话支持</span><span class="sxs-lookup"><span data-stu-id="3a8d3-138">Emergency call enablement</span></span>

<span data-ttu-id="3a8d3-139">每个通话计划用户将自动启用紧急呼叫，并且必须有一个注册的紧急地址与其分配的电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="3a8d3-140">当位置必须与电话号码相关联时，取决于国家/地区：</span><span class="sxs-lookup"><span data-stu-id="3a8d3-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="3a8d3-141">例如，在美国和加拿大，如果向用户分配了一个号码，则需要紧急位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="3a8d3-142">对于其他国家/地区（如欧洲、中东和非洲（EMEA）），当您从 Office 365 获取电话号码或从其他服务提供商或运营商处转移时，需要紧急位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-142">For other countries--such as in Europe, the Middle East, and Africa (EMEA)--an emergency location is required when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="3a8d3-143">动态紧急电话</span><span class="sxs-lookup"><span data-stu-id="3a8d3-143">Dynamic emergency calling</span></span>

<span data-ttu-id="3a8d3-144">Microsoft 通话计划的动态紧急呼叫提供根据团队客户端的当前位置配置和路由紧急呼叫的功能。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="3a8d3-145">自动路由到相应的公共安全应答点（PSAP）或通知安全桌面人员的能力会有所不同，具体取决于团队用户使用的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="3a8d3-146">目前，只有美国的通话计划用户可以利用动态位置来路由紧急呼叫，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3a8d3-146">At this time, only Calling Plan users in the United States can leverage dynamic locations for routing emergency calls as follows:</span></span>

- <span data-ttu-id="3a8d3-147">如果美国呼叫计划的团队客户在美国动态获取紧急地址，则该地址将用于紧急路由，而不是注册地址，并且呼叫将自动路由到 PSAP 中的地址的服务区域。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-147">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="3a8d3-148">如果美国通话计划的团队客户端不会动态获取美国内的紧急地址，则注册的紧急地址将用于帮助屏幕和路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-148">If a Teams client for a United States Calling Plan user doesn’t dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="3a8d3-149">但是，在将呼叫者连接到相应的 PSAP 之前，将对呼叫进行筛选以确定是否需要更新的地址。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-149">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="3a8d3-150">在美国，您必须配置作为分配给网络标识符的紧急位置的一部分的市政地址，并包括相关联的地域代码。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-150">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="3a8d3-151">有关详细信息，请参阅[规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-151">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="3a8d3-152">紧急呼叫路由</span><span class="sxs-lookup"><span data-stu-id="3a8d3-152">Emergency call routing</span></span>

<span data-ttu-id="3a8d3-153">当团队通话计划用户拨打紧急号码时，呼叫如何路由到 PSAP 取决于以下情况：</span><span class="sxs-lookup"><span data-stu-id="3a8d3-153">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="3a8d3-154">紧急地址是否由团队客户端动态确定。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-154">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="3a8d3-155">紧急地址是否是与用户的电话号码相关联的注册地址。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-155">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="3a8d3-156">该国家/地区的紧急电话网络。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-156">The emergency calling network of that country.</span></span>

  <span data-ttu-id="3a8d3-157">**美国：**</span><span class="sxs-lookup"><span data-stu-id="3a8d3-157">**In the United States:**</span></span>

  - <span data-ttu-id="3a8d3-158">如果团队客户端位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫将自动路由到该地理位置的 PSAP 服务。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-158">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="3a8d3-159">如果团队客户端不在租户定义的动态紧急位置，则来自该客户端的紧急呼叫由全国呼叫中心进行筛选，以便在将呼叫转移到该地理位置的 PSAP 服务之前确定呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-159">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="3a8d3-160">如果紧急呼叫方无法将其紧急位置更新到 "筛选中心"，则该呼叫将转到服务于呼叫者的注册地址的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-160">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="3a8d3-161">**在加拿大、爱尔兰和**英国，紧急电话先进行筛选，以便在将呼叫连接到相应的派遣中心之前确定用户的当前位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-161">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="3a8d3-162">**在法国、德国和西班牙**，紧急呼叫直接路由到 PSAP 与号码关联的紧急地址的服务，无论呼叫者的位置如何。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-162">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="3a8d3-163">**在荷兰**，无论呼叫者的位置如何，都可以将紧急呼叫直接路由到号码的本地区号 PSAP。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-163">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="3a8d3-164">**在澳大利亚**，由运营商合作伙伴配置和路由紧急地址。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-164">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="3a8d3-165">**在日本**，不支持紧急通话。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-165">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="3a8d3-166">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="3a8d3-166">For more information, see:</span></span>

- [<span data-ttu-id="3a8d3-167">通话套餐</span><span class="sxs-lookup"><span data-stu-id="3a8d3-167">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="3a8d3-168">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="3a8d3-168">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="3a8d3-169">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="3a8d3-169">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="3a8d3-170">直接路由的注意事项</span><span class="sxs-lookup"><span data-stu-id="3a8d3-170">Considerations for Direct Routing</span></span>

<span data-ttu-id="3a8d3-171">如果您所在区域没有通话计划，或者您想要保留现有运营商，请考虑[直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-171">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="3a8d3-172">有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)和[管理紧急呼叫路由策略](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-172">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="3a8d3-173">紧急电话支持和配置</span><span class="sxs-lookup"><span data-stu-id="3a8d3-173">Emergency call enablement and configuration</span></span>

<span data-ttu-id="3a8d3-174">你必须通过使用 TeamsEmergencyCallRoutingPolicy 定义用于直接路由用户的紧急呼叫策略，以定义紧急号码及其关联的路由目标。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-174">You must define emergency calling policies for Direct Routing users by using the TeamsEmergencyCallRoutingPolicy to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="3a8d3-175">（请注意，直接路由用户不支持注册的紧急位置。）</span><span class="sxs-lookup"><span data-stu-id="3a8d3-175">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="3a8d3-176">你可以将 TeamsEmergencyCallRoutingPolicy 分配给团队直接路由用户帐户和/或网络网站。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-176">You can assign a TeamsEmergencyCallRoutingPolicy to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="3a8d3-177">当团队客户端启动或更改网络连接时，团队将执行客户端所在的网络站点的查找，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3a8d3-177">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="3a8d3-178">如果 TeamsEmergencyCallRoutingPolicy 与网站关联，则使用网站策略配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-178">If a TeamsEmergencyCallRoutingPolicy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="3a8d3-179">如果没有与该网站相关联的 TeamsEmergencyCallRoutingPolicy，或者如果客户在未定义的站点上连接，则将使用与该用户帐户关联的 TeamsEmergencyCallRoutingPolicy 配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-179">If there is no TeamsEmergencyCallRoutingPolicy associated with the site, or if the client is connected at an undefined site, then the TeamsEmergencyCallRoutingPolicy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="3a8d3-180">如果团队客户不能获得 TeamsEmergencyCallRoutingPolicy，则不会为紧急呼叫启用用户。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-180">If the Teams client is unable to obtain an TeamsEmergencyCallRoutingPolicy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="3a8d3-181">动态紧急电话</span><span class="sxs-lookup"><span data-stu-id="3a8d3-181">Dynamic emergency calling</span></span>

<span data-ttu-id="3a8d3-182">直接路由用户的团队客户可以获取动态紧急地址，该地址可用于根据呼叫者的位置动态路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-182">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="3a8d3-183">有关详细信息，请参阅[配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-183">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="3a8d3-184">紧急呼叫路由</span><span class="sxs-lookup"><span data-stu-id="3a8d3-184">Emergency call routing</span></span>

<span data-ttu-id="3a8d3-185">TeamsEmergencyCallRoutingPolicy 引用了一个联机 PSTN 使用，它必须具有适当直接路由配置才能将紧急呼叫正确路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-185">The TeamsEmergencyCallRoutingPolicy references an online PSTN Usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="3a8d3-186">特别是，必须确保紧急拨号字符串有 OnlineVoiceRoute。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-186">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="3a8d3-187">有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-187">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

<span data-ttu-id="3a8d3-188">（注意：团队客户在紧急号码之前预置 "+" 登录，其方式与 Skype for Business 客户端的功能类似，即 + 911。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-188">(Note: Teams clients prepend the “+” sign in front of emergency numbers in a similar manner that Skype for Business client does; that is, +911.</span></span> <span data-ttu-id="3a8d3-189">将在未来的几个月内修改此行为，这样，进行紧急通话的团队将不再发送号码前面的 "+";即911。）</span><span class="sxs-lookup"><span data-stu-id="3a8d3-189">This behavior will be modified in the coming months so that Teams emergency calls will no longer be sending a "+" preceding the number; that is, 911.)</span></span>

<span data-ttu-id="3a8d3-190">为直接路由用户动态路由紧急电话的功能会有所不同，具体取决于给定国家内的紧急呼叫网络。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-190">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="3a8d3-191">提供两种解决方案：</span><span class="sxs-lookup"><span data-stu-id="3a8d3-191">There are two solutions available:</span></span>

- <span data-ttu-id="3a8d3-192">紧急路由服务提供商（仅限美国）</span><span class="sxs-lookup"><span data-stu-id="3a8d3-192">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="3a8d3-193">紧急位置标识号码（ELIN）网关应用程序</span><span class="sxs-lookup"><span data-stu-id="3a8d3-193">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="3a8d3-194">紧急路由服务提供商</span><span class="sxs-lookup"><span data-stu-id="3a8d3-194">Emergency Routing Service Providers</span></span>

<span data-ttu-id="3a8d3-195">在美国，有许多认证的紧急路线服务提供商（ERSPs）可以根据呼叫方的位置自动路由紧急电话。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-195">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="3a8d3-196">如果将紧急路线服务提供商集成到直接路由部署中，则会将带有动态获取位置的紧急呼叫自动路由到服务该位置的公共安全应答点（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-196">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="3a8d3-197">在将呼叫连接到基于更新的位置之前，没有动态获取的位置的紧急电话将首先进行筛选以确定用户的当前位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-197">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="3a8d3-198">有关详细信息，请参阅[为直接路由认证的会话边框控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-198">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="3a8d3-199">紧急位置标识号码（ELIN）应用程序</span><span class="sxs-lookup"><span data-stu-id="3a8d3-199">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="3a8d3-200">会话边框控制器（SBCs）可以包含紧急位置标识号（ELIN）应用程序。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-200">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="3a8d3-201">如果将 SBC ELIN 应用程序集成到直接路由部署，则必须在 ELIN 应用程序中配置紧急地址和关联的电话号码，然后将 ELIN 记录上载到各自 PSTN 中的紧急调用数据库.</span><span class="sxs-lookup"><span data-stu-id="3a8d3-201">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="3a8d3-202">使用 ELIN 标识符的团队紧急位置必须匹配 ELIN 应用程序中的位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-202">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="3a8d3-203">当带有动态获取位置的紧急呼叫被路由到相应的 SBC 时，ELIN 应用程序：</span><span class="sxs-lookup"><span data-stu-id="3a8d3-203">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="3a8d3-204">分析呼叫方的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-204">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="3a8d3-205">将位置与 ELIN 记录相匹配。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-205">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="3a8d3-206">用 ELIN 电话号码替代紧急呼叫方的号码。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-206">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="3a8d3-207">将呼叫路由到该位置的 PSAP 服务，然后调度程序从上载的 ELIN 记录中获取位置。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-207">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="3a8d3-208">在回拨紧急号码后，ELIN 应用程序将对原始紧急呼叫方执行反向拨叫的号码替换。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-208">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="3a8d3-209">有关详细信息，请参阅[为直接路由认证的会话边框控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-209">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="3a8d3-210">安全桌面通知</span><span class="sxs-lookup"><span data-stu-id="3a8d3-210">Security desk notification</span></span>

<span data-ttu-id="3a8d3-211">Microsoft 通话计划和电话系统直接路由都提供了安全桌面通知。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-211">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="3a8d3-212">你可以使用 TeamsEmergencyCallingPolicy 配置应在紧急呼叫期间通知的人员，以及通知方式：仅聊天、conferenced 或已静音，但具有取消静音的功能。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-212">You use the TeamsEmergencyCallingPolicy to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="3a8d3-213">你还可以指定用户或组的外部 PSTN 号码呼叫并加入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-213">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="3a8d3-214">可以向团队用户帐户授予 TeamsEmergencyCallingPolicy，或将其分配给网络网站，或同时授予这两种帐户。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-214">A TeamsEmergencyCallingPolicy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="3a8d3-215">当团队客户端启动或更改网络连接时，团队会执行客户端所在的网络站点的查找：</span><span class="sxs-lookup"><span data-stu-id="3a8d3-215">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="3a8d3-216">如果 TeamsEmergencyCallingPolicy 与网络网站相关联，则使用网站策略配置 security 桌面通知。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-216">If a TeamsEmergencyCallingPolicy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="3a8d3-217">如果没有与该网站相关联的 TeamsEmergencyCallingPolicy，或者客户端连接到了未定义的站点，则将使用与该用户帐户关联的 TeamsEmergencyCallingPolicy 来配置 security 桌面通知。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-217">If there is no TeamsEmergencyCallingPolicy associated with the site, or if the client is connected at an undefined site, then the TeamsEmergencyCallingPolicy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="3a8d3-218">如果团队客户端无法获取 TeamsEmergencyCallingPolicy，则不会为安全桌面通知启用用户。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-218">If the Teams client is unable to obtain an TeamsEmergencyCallingPolicy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="3a8d3-219">在紧急通话期间，安全桌面将 conferenced 到通话中，而安全桌面用户的体验将根据 TeamsEmergencyCallingPolicy 进行控制。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-219">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the TeamsEmergencyCallingPolicy.</span></span> <span data-ttu-id="3a8d3-220">群组聊天已开始于每个 security 书桌成员，紧急呼叫者的位置通过重要消息通知进行共享。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-220">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="3a8d3-221">如果将会议选项配置为 "策略" 的一部分，则每个安全桌面用户还会作为会议的一部分进行调用。</span><span class="sxs-lookup"><span data-stu-id="3a8d3-221">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="3a8d3-222">相关主题</span><span class="sxs-lookup"><span data-stu-id="3a8d3-222">Related topics</span></span>

- [<span data-ttu-id="3a8d3-223">管理紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="3a8d3-223">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="3a8d3-224">管理紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="3a8d3-224">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="3a8d3-225">为你的组织添加、更改或删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="3a8d3-225">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="3a8d3-226">为用户分配或更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="3a8d3-226">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="3a8d3-227">规划和配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="3a8d3-227">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
