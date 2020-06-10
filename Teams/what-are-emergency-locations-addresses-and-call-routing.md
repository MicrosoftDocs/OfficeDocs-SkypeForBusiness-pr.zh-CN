---
title: 规划和管理紧急呼叫
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
- seo-marvel-mar2020
description: 了解紧急电话，包括有关紧急地址、紧急呼叫路由和动态紧急呼叫的信息。
ms.openlocfilehash: b41b7e9b4442e10cf3ca352a9d6460f2d537b43e
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665154"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="f7de2-103">管理紧急电话</span><span class="sxs-lookup"><span data-stu-id="f7de2-103">Manage emergency calling</span></span>

<span data-ttu-id="f7de2-104">本文介绍管理紧急呼叫时需要了解的概念 &mdash; ，其中包括有关紧急地址、动态紧急地址和紧急呼叫路由的信息。</span><span class="sxs-lookup"><span data-stu-id="f7de2-104">This article describes concepts you'll need to know to manage emergency calling&mdash;it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="f7de2-105">本文使用以下术语：</span><span class="sxs-lookup"><span data-stu-id="f7de2-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="f7de2-106">**紧急地址**-市政地址您的组织中的 &mdash; 企业位置的物理地址或街道地址。</span><span class="sxs-lookup"><span data-stu-id="f7de2-106">**Emergency address** - A civic address&mdash;the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="f7de2-107">例如，地址 12345 "北卡罗来纳州"、 *"雷德蒙"、"WA" 和 "WA 98052* " 用于将紧急呼叫路由到相应的派遣机构，并帮助查找紧急呼叫方。</span><span class="sxs-lookup"><span data-stu-id="f7de2-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="f7de2-108">**置入**-通常为楼层、建筑物、翼形或办公室号码。</span><span class="sxs-lookup"><span data-stu-id="f7de2-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="f7de2-109">"地点" 与紧急地址相关联，以便在大楼内提供更准确的位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="f7de2-110">您可以拥有与紧急地址相关联的无限位数。</span><span class="sxs-lookup"><span data-stu-id="f7de2-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="f7de2-111">例如，如果您的组织有多个建筑物，您可能希望在每个建筑物内包括每个建筑物和每个楼层的位置信息。</span><span class="sxs-lookup"><span data-stu-id="f7de2-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="f7de2-112">**紧急位置**-位置是 &mdash; 带有可选位置的市政地址。</span><span class="sxs-lookup"><span data-stu-id="f7de2-112">**Emergency location** - A location is a civic address&mdash;with an optional place.</span></span> <span data-ttu-id="f7de2-113">如果您的企业有多个物理位置，则可能需要多个紧急位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="f7de2-114">创建紧急地址时，系统会自动为此地址创建一个唯一的位置 ID。</span><span class="sxs-lookup"><span data-stu-id="f7de2-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="f7de2-115">如果向建筑物地址添加一个位置 &mdash; ，例如，如果将楼层添加到建筑物地址，则会为 " &mdash; 紧急地址" 和 "地点" 的组合创建一个 "位置 ID"。</span><span class="sxs-lookup"><span data-stu-id="f7de2-115">If you add a place to an emergency address&mdash;for example, if you add a floor to a building address&mdash;a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="f7de2-116">在此示例中，将有两个位置 Id：一个用于市政地址;一个用于加入的市政地址和关联位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="f7de2-117">将紧急位置分配给用户或网站时，它是与用户或网站相关联的唯一位置 ID。</span><span class="sxs-lookup"><span data-stu-id="f7de2-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="f7de2-118">**已注册地址**-分配给每个呼叫计划用户的紧急地址;它有时被称为静态紧急地址或记录地址。</span><span class="sxs-lookup"><span data-stu-id="f7de2-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="f7de2-119">（注册的地址不适用于直接路由用户。）</span><span class="sxs-lookup"><span data-stu-id="f7de2-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="f7de2-120">使用团队管理中心为呼叫计划用户创建紧急地址。</span><span class="sxs-lookup"><span data-stu-id="f7de2-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="f7de2-121">根据您使用的是电话系统呼叫计划还是适用于 PSTN 连接的电话系统直接路由，您管理紧急呼叫的方式有一些差异。</span><span class="sxs-lookup"><span data-stu-id="f7de2-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="f7de2-122">本文中介绍了这些注意事项。</span><span class="sxs-lookup"><span data-stu-id="f7de2-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="f7de2-123">紧急地址验证</span><span class="sxs-lookup"><span data-stu-id="f7de2-123">Emergency address validation</span></span>

<span data-ttu-id="f7de2-124">若要为用户或网络标识符分配紧急地址，必须确保紧急地址标记为 "已验证"。</span><span class="sxs-lookup"><span data-stu-id="f7de2-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as "validated."</span></span>  <span data-ttu-id="f7de2-125">地址验证可确保地址是合法的，并且在分配后不能被修改。</span><span class="sxs-lookup"><span data-stu-id="f7de2-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="f7de2-126">如果您通过使用 "团队管理中心" 中的地址映射搜索功能来定义紧急地址，则地址会自动标记为 "已验证"。</span><span class="sxs-lookup"><span data-stu-id="f7de2-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="f7de2-127">您不能修改已验证的紧急地址。</span><span class="sxs-lookup"><span data-stu-id="f7de2-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="f7de2-128">因此，如果地址的格式或表示形式发生更改，则必须使用已更新的格式创建新地址。</span><span class="sxs-lookup"><span data-stu-id="f7de2-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="f7de2-129">紧急地址地域代码</span><span class="sxs-lookup"><span data-stu-id="f7de2-129">Emergency address geo codes</span></span>

<span data-ttu-id="f7de2-130">每个紧急地址都可以具有与其关联的地域代码（纬度和经度）。</span><span class="sxs-lookup"><span data-stu-id="f7de2-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="f7de2-131">这些地理代码用于某些国家/地区，用动态位置帮助您路由紧急电话。</span><span class="sxs-lookup"><span data-stu-id="f7de2-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="f7de2-132">如果您通过使用 "团队管理中心" 中的地址映射搜索功能来定义紧急地址，则 geo 代码将自动与紧急地址相关联。</span><span class="sxs-lookup"><span data-stu-id="f7de2-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="f7de2-133">如果使用 PowerShell 定义地址，还可以将地域代码与地址相关联。</span><span class="sxs-lookup"><span data-stu-id="f7de2-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="f7de2-134">但是，Microsoft 建议使用团队管理中心中的 "映射搜索" 功能为通话计划创建紧急地址，这将确保地址已设置格式、验证，并具有相应的 geo 代码。</span><span class="sxs-lookup"><span data-stu-id="f7de2-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="f7de2-135">要将紧急位置分配给网络标识符以进行动态紧急呼叫，紧急地址必须包含相应的 geo 代码。</span><span class="sxs-lookup"><span data-stu-id="f7de2-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="f7de2-136">通话计划的注意事项</span><span class="sxs-lookup"><span data-stu-id="f7de2-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="f7de2-137">要了解您所在区域是否有通话计划，请参阅[电话计划的国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="f7de2-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="f7de2-138">紧急电话支持</span><span class="sxs-lookup"><span data-stu-id="f7de2-138">Emergency call enablement</span></span>

<span data-ttu-id="f7de2-139">每个通话计划用户将自动启用紧急呼叫，并且必须有一个注册的紧急地址与其分配的电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="f7de2-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="f7de2-140">当位置必须与电话号码相关联时，取决于国家/地区：</span><span class="sxs-lookup"><span data-stu-id="f7de2-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="f7de2-141">例如，在美国和加拿大，如果向用户分配了一个号码，则需要紧急位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="f7de2-142">对于其他国家/地区（例如在欧洲、中东和非洲（EMEA）），当您获得来自 Microsoft 365 或 Office 365 的电话号码时，或者从另一个服务提供商或运营商处转移电话号码时，需要紧急位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-142">For other countries--such as in Europe, the Middle East, and Africa (EMEA)--an emergency location is required when you get the phone number from Microsoft 365 or Office 365, or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="f7de2-143">动态紧急电话</span><span class="sxs-lookup"><span data-stu-id="f7de2-143">Dynamic emergency calling</span></span>

<span data-ttu-id="f7de2-144">Microsoft 通话计划的动态紧急呼叫提供根据团队客户端的当前位置配置和路由紧急呼叫的功能。</span><span class="sxs-lookup"><span data-stu-id="f7de2-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="f7de2-145">自动路由到相应的公共安全应答点（PSAP）或通知安全桌面人员的能力会有所不同，具体取决于团队用户使用的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="f7de2-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="f7de2-146">对于呼叫计划用户，仅在美国才支持用于路由紧急呼叫的动态位置，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f7de2-146">For Calling Plan users, dynamic location for routing emergency calls is only supported in the United States as follows.</span></span> <span data-ttu-id="f7de2-147">（有关动态紧急呼叫和直接路由的信息，请参阅[直接路由的注意事项](#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="f7de2-147">(For information about dynamic emergency calling and Direct Routing, see [Considerations for Direct Routing](#considerations-for-direct-routing).</span></span>

- <span data-ttu-id="f7de2-148">如果美国呼叫计划的团队客户在美国动态获取紧急地址，则该地址将用于紧急路由，而不是注册地址，并且呼叫将自动路由到地址的服务区域中的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="f7de2-148">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="f7de2-149">如果美国通话计划的团队客户端不会动态获取美国内的紧急地址，则注册的紧急地址将用于帮助屏幕和路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="f7de2-149">If a Teams client for a United States Calling Plan user doesn't dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="f7de2-150">但是，在将呼叫者连接到相应的 PSAP 之前，将对呼叫进行筛选以确定是否需要更新的地址。</span><span class="sxs-lookup"><span data-stu-id="f7de2-150">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="f7de2-151">在美国，您必须配置属于紧急位置的市政地址，该地址是分配给网络标识符的紧急位置的一部分， &mdash; 并包含相关联的地域代码。</span><span class="sxs-lookup"><span data-stu-id="f7de2-151">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers&mdash;and include the associated geo codes.</span></span> <span data-ttu-id="f7de2-152">有关详细信息，请参阅[规划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="f7de2-152">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="f7de2-153">紧急呼叫路由</span><span class="sxs-lookup"><span data-stu-id="f7de2-153">Emergency call routing</span></span>

<span data-ttu-id="f7de2-154">当团队通话计划用户拨打紧急号码时，呼叫如何路由到 PSAP 取决于以下情况：</span><span class="sxs-lookup"><span data-stu-id="f7de2-154">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="f7de2-155">紧急地址是否由团队客户端动态确定。</span><span class="sxs-lookup"><span data-stu-id="f7de2-155">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="f7de2-156">紧急地址是否是与用户的电话号码相关联的注册地址。</span><span class="sxs-lookup"><span data-stu-id="f7de2-156">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="f7de2-157">该国家/地区的紧急电话网络。</span><span class="sxs-lookup"><span data-stu-id="f7de2-157">The emergency calling network of that country.</span></span>

  <span data-ttu-id="f7de2-158">**美国：**</span><span class="sxs-lookup"><span data-stu-id="f7de2-158">**In the United States:**</span></span>

  - <span data-ttu-id="f7de2-159">如果团队客户端位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫将自动路由到该地理位置的 PSAP 服务。</span><span class="sxs-lookup"><span data-stu-id="f7de2-159">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="f7de2-160">如果团队客户端不在租户定义的动态紧急位置，则来自该客户端的紧急呼叫由全国呼叫中心进行筛选，以便在将呼叫转移到该地理位置的 PSAP 服务之前确定呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-160">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="f7de2-161">如果紧急呼叫方无法将其紧急位置更新到 "筛选中心"，则该呼叫将转到服务于呼叫者的注册地址的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="f7de2-161">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="f7de2-162">**在加拿大、爱尔兰和**英国，紧急电话先进行筛选，以便在将呼叫连接到相应的派遣中心之前确定用户的当前位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-162">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="f7de2-163">**在法国、德国和西班牙**，紧急呼叫直接路由到 PSAP 与号码关联的紧急地址的服务，无论呼叫者的位置如何。</span><span class="sxs-lookup"><span data-stu-id="f7de2-163">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="f7de2-164">**在荷兰**，无论呼叫者的位置如何，都可以将紧急呼叫直接路由到号码的本地区号 PSAP。</span><span class="sxs-lookup"><span data-stu-id="f7de2-164">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="f7de2-165">**在澳大利亚**，由运营商合作伙伴配置和路由紧急地址。</span><span class="sxs-lookup"><span data-stu-id="f7de2-165">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="f7de2-166">**在日本**，不支持紧急通话。</span><span class="sxs-lookup"><span data-stu-id="f7de2-166">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="f7de2-167">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="f7de2-167">For more information, see:</span></span>

- [<span data-ttu-id="f7de2-168">通话套餐</span><span class="sxs-lookup"><span data-stu-id="f7de2-168">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="f7de2-169">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="f7de2-169">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="f7de2-170">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="f7de2-170">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="f7de2-171">直接路由的注意事项</span><span class="sxs-lookup"><span data-stu-id="f7de2-171">Considerations for Direct Routing</span></span>

<span data-ttu-id="f7de2-172">如果您所在区域没有通话计划，或者您想要保留现有运营商，请考虑[直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="f7de2-172">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="f7de2-173">有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)和[管理紧急呼叫路由策略](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f7de2-173">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="f7de2-174">紧急电话支持和配置</span><span class="sxs-lookup"><span data-stu-id="f7de2-174">Emergency call enablement and configuration</span></span>

<span data-ttu-id="f7de2-175">你必须使用团队紧急呼叫路由策略（TeamsEmergencyCallRoutingPolicy）为直接路由用户定义紧急呼叫策略，以定义紧急号码及其关联的路由目标。</span><span class="sxs-lookup"><span data-stu-id="f7de2-175">You must define emergency calling policies for Direct Routing users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="f7de2-176">（请注意，直接路由用户不支持注册的紧急位置。）</span><span class="sxs-lookup"><span data-stu-id="f7de2-176">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="f7de2-177">您可以将紧急呼叫路由策略分配给团队直接路由用户帐户和/或网络网站。</span><span class="sxs-lookup"><span data-stu-id="f7de2-177">You can assign an emergency call routing policy  to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="f7de2-178">当团队客户端启动或更改网络连接时，团队将执行客户端所在的网络站点的查找，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7de2-178">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="f7de2-179">如果紧急呼叫路由策略与该站点相关联，则使用网站策略配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="f7de2-179">If an emergency call routing policy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="f7de2-180">如果没有与该站点关联的紧急呼叫路由策略，或者客户在未定义的站点上连接，则将使用与该用户帐户相关联的紧急呼叫路由策略来配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="f7de2-180">If there is no emergency call routing policy associated with the site, or if the client is connected at an undefined site, then the emergency call routing policy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="f7de2-181">如果团队客户不能获得紧急呼叫路由策略，则不会为用户启用紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="f7de2-181">If the Teams client is unable to obtain an emergency call routing policy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="f7de2-182">动态紧急电话</span><span class="sxs-lookup"><span data-stu-id="f7de2-182">Dynamic emergency calling</span></span>

<span data-ttu-id="f7de2-183">直接路由用户的团队客户可以获取动态紧急地址，该地址可用于根据呼叫者的位置动态路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="f7de2-183">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="f7de2-184">有关详细信息，请参阅[配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="f7de2-184">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="f7de2-185">紧急呼叫路由</span><span class="sxs-lookup"><span data-stu-id="f7de2-185">Emergency call routing</span></span>

<span data-ttu-id="f7de2-186">"紧急呼叫路由策略" 将引用联机 PSTN 使用，它必须具有适当的直接路由配置，才能将紧急呼叫正确路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="f7de2-186">The emergency call routing policy references an online PSTN usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="f7de2-187">特别是，必须确保紧急拨号字符串有 OnlineVoiceRoute。</span><span class="sxs-lookup"><span data-stu-id="f7de2-187">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="f7de2-188">有关详细信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="f7de2-188">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

<span data-ttu-id="f7de2-189">（注意：团队客户在紧急号码之前预置 "+" 登录，其方式与 Skype for Business 客户端的功能类似，即 + 911。</span><span class="sxs-lookup"><span data-stu-id="f7de2-189">(Note: Teams clients prepend the "+" sign in front of emergency numbers in a similar manner that Skype for Business client does; that is, +911.</span></span> <span data-ttu-id="f7de2-190">将在未来的几个月内修改此行为，这样，进行紧急通话的团队将不再发送号码前面的 "+";即911。）</span><span class="sxs-lookup"><span data-stu-id="f7de2-190">This behavior will be modified in the coming months so that Teams emergency calls will no longer be sending a "+" preceding the number; that is, 911.)</span></span>

<span data-ttu-id="f7de2-191">为直接路由用户动态路由紧急电话的功能会有所不同，具体取决于给定国家内的紧急呼叫网络。</span><span class="sxs-lookup"><span data-stu-id="f7de2-191">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="f7de2-192">提供两种解决方案：</span><span class="sxs-lookup"><span data-stu-id="f7de2-192">There are two solutions available:</span></span>

- <span data-ttu-id="f7de2-193">紧急路由服务提供商（仅限美国）</span><span class="sxs-lookup"><span data-stu-id="f7de2-193">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="f7de2-194">紧急位置标识号码（ELIN）网关应用程序</span><span class="sxs-lookup"><span data-stu-id="f7de2-194">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="f7de2-195">紧急路由服务提供商</span><span class="sxs-lookup"><span data-stu-id="f7de2-195">Emergency Routing Service Providers</span></span>

<span data-ttu-id="f7de2-196">在美国，有许多认证的紧急路线服务提供商（ERSPs）可以根据呼叫方的位置自动路由紧急电话。</span><span class="sxs-lookup"><span data-stu-id="f7de2-196">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="f7de2-197">如果将紧急路线服务提供商集成到直接路由部署中，则会将带有动态获取位置的紧急呼叫自动路由到服务该位置的公共安全应答点（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="f7de2-197">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="f7de2-198">在将呼叫连接到基于更新的位置之前，没有动态获取的位置的紧急电话将首先进行筛选以确定用户的当前位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-198">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="f7de2-199">有关详细信息，请参阅[为直接路由认证的会话边框控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="f7de2-199">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="f7de2-200">紧急位置标识号码（ELIN）应用程序</span><span class="sxs-lookup"><span data-stu-id="f7de2-200">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="f7de2-201">会话边框控制器（SBCs）可以包含紧急位置标识号（ELIN）应用程序。</span><span class="sxs-lookup"><span data-stu-id="f7de2-201">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="f7de2-202">如果将 SBC ELIN 应用程序集成到直接路由部署，则必须在 ELIN 应用程序中配置紧急地址和关联的电话号码，然后将 ELIN 记录上载到各自 PSTN 中的紧急调用数据库。</span><span class="sxs-lookup"><span data-stu-id="f7de2-202">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="f7de2-203">使用 ELIN 标识符的团队紧急位置必须匹配 ELIN 应用程序中的位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-203">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="f7de2-204">当带有动态获取位置的紧急呼叫被路由到相应的 SBC 时，ELIN 应用程序：</span><span class="sxs-lookup"><span data-stu-id="f7de2-204">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="f7de2-205">分析呼叫方的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-205">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="f7de2-206">将位置与 ELIN 记录相匹配。</span><span class="sxs-lookup"><span data-stu-id="f7de2-206">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="f7de2-207">用 ELIN 电话号码替代紧急呼叫方的号码。</span><span class="sxs-lookup"><span data-stu-id="f7de2-207">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="f7de2-208">将呼叫路由到该位置的 PSAP 服务，然后调度程序从上载的 ELIN 记录中获取位置。</span><span class="sxs-lookup"><span data-stu-id="f7de2-208">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="f7de2-209">在回拨紧急号码后，ELIN 应用程序将对原始紧急呼叫方执行反向拨叫的号码替换。</span><span class="sxs-lookup"><span data-stu-id="f7de2-209">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="f7de2-210">有关详细信息，请参阅[为直接路由认证的会话边框控制器](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="f7de2-210">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="f7de2-211">安全桌面通知</span><span class="sxs-lookup"><span data-stu-id="f7de2-211">Security desk notification</span></span>

<span data-ttu-id="f7de2-212">Microsoft 通话计划和电话系统直接路由都提供了安全桌面通知。</span><span class="sxs-lookup"><span data-stu-id="f7de2-212">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="f7de2-213">使用团队紧急呼叫政策（TeamsEmergencyCallingPolicy）来配置应在紧急呼叫期间收到通知的人员，以及通知方式：仅聊天、conferenced 或静音，以及取消静音的功能。</span><span class="sxs-lookup"><span data-stu-id="f7de2-213">You use a Teams emergency calling policy (TeamsEmergencyCallingPolicy) to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="f7de2-214">你还可以指定用户或组的外部 PSTN 号码呼叫并加入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="f7de2-214">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="f7de2-215">紧急呼叫策略可授予团队用户帐户、分配给网络站点或两者。</span><span class="sxs-lookup"><span data-stu-id="f7de2-215">An emergency calling policy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="f7de2-216">当团队客户端启动或更改网络连接时，团队会执行客户端所在的网络站点的查找：</span><span class="sxs-lookup"><span data-stu-id="f7de2-216">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="f7de2-217">如果紧急呼叫策略与网络站点相关联，则网站策略用于配置 security 桌面通知。</span><span class="sxs-lookup"><span data-stu-id="f7de2-217">If an emergency calling policy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="f7de2-218">如果没有与该站点相关联的紧急呼叫策略，或者客户在未定义的站点上连接，则与该用户帐户相关联的紧急呼叫策略将用于配置安全桌面通知。</span><span class="sxs-lookup"><span data-stu-id="f7de2-218">If there is no emergency calling policy associated with the site, or if the client is connected at an undefined site, then the emergency calling policy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="f7de2-219">如果团队客户端无法获取紧急呼叫策略，则不会为安全桌面通知启用用户。</span><span class="sxs-lookup"><span data-stu-id="f7de2-219">If the Teams client is unable to obtain an emergency calling policy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="f7de2-220">在紧急通话期间，安全桌面将 conferenced 到呼叫中，而安全桌面用户的体验将基于团队紧急呼叫政策进行控制。</span><span class="sxs-lookup"><span data-stu-id="f7de2-220">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the Teams emergency calling policy.</span></span> <span data-ttu-id="f7de2-221">群组聊天已开始于每个 security 书桌成员，紧急呼叫者的位置通过重要消息通知进行共享。</span><span class="sxs-lookup"><span data-stu-id="f7de2-221">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="f7de2-222">如果将会议选项配置为 "策略" 的一部分，则每个安全桌面用户还会作为会议的一部分进行调用。</span><span class="sxs-lookup"><span data-stu-id="f7de2-222">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="f7de2-223">相关主题</span><span class="sxs-lookup"><span data-stu-id="f7de2-223">Related topics</span></span>

- [<span data-ttu-id="f7de2-224">管理紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="f7de2-224">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="f7de2-225">管理紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="f7de2-225">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="f7de2-226">为你的组织添加、更改或删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="f7de2-226">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="f7de2-227">为用户分配或更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="f7de2-227">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="f7de2-228">规划和配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="f7de2-228">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
