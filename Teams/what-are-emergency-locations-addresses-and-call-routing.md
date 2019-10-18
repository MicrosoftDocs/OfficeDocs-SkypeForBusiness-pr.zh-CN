---
title: 什么是紧急位置、地点和呼叫路由？
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
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: '了解紧急地点、地点和紧急呼叫路由的定义，以及如何规划和为用户分配。 '
ms.openlocfilehash: a6f3051c4902d9fda2f20ca17e4aa501a8922264
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568549"
---
# <a name="what-are-emergency-locations-places-and-call-routing"></a><span data-ttu-id="ad852-103">什么是紧急位置、地点和呼叫路由？</span><span class="sxs-lookup"><span data-stu-id="ad852-103">What are emergency locations, places, and call routing?</span></span>

<span data-ttu-id="ad852-104">配置呼叫计划时，当您获取电话号码或将其分配给用户以支持紧急呼叫时，您必须为每个电话号码分配紧急位置。</span><span class="sxs-lookup"><span data-stu-id="ad852-104">When you configure Calling Plans, you have to assign an emergency location to each phone number when you either get the phone number or assign it to a user to support emergency calling.</span></span> <span data-ttu-id="ad852-105">您必须先添加并验证紧急位置，然后才能将紧急地点分配给电话号码。</span><span class="sxs-lookup"><span data-stu-id="ad852-105">Before you can assign an emergency location to a phone number, you must add and validate an emergency location.</span></span> <span data-ttu-id="ad852-106">验证可确保已识别紧急位置，并且该位置采用紧急响应服务可以使用的正确格式。</span><span class="sxs-lookup"><span data-stu-id="ad852-106">Validation ensures that the emergency location is recognized and that it's in a correct format that can be used by emergency response services.</span></span> <span data-ttu-id="ad852-107">或者，您可以在紧急位置中添加一个位置，以便为用户提供更具体的位置。</span><span class="sxs-lookup"><span data-stu-id="ad852-107">Optionally, you can add a place within the emergency location to provide a more specific location for the user.</span></span> <span data-ttu-id="ad852-108">例如，位置可以是链接到特定紧急位置的楼层、翼形或办公室。</span><span class="sxs-lookup"><span data-stu-id="ad852-108">For example, the place could be a floor, wing, or office that's linked to a specific emergency location.</span></span> <span data-ttu-id="ad852-109">虽然紧急位置已经过验证，但不会出现任何地方。</span><span class="sxs-lookup"><span data-stu-id="ad852-109">Although emergency locations are validated, places aren't.</span></span>
  
## <a name="what-are-emergency-locations"></a><span data-ttu-id="ad852-110">什么是紧急位置？</span><span class="sxs-lookup"><span data-stu-id="ad852-110">What are emergency locations?</span></span>

<span data-ttu-id="ad852-111">有效电话号码需要紧急位置，并且在需要时取决于国家/地区。</span><span class="sxs-lookup"><span data-stu-id="ad852-111">An emergency location is required for active telephone numbers and when it's required depends on the country/region.</span></span> <span data-ttu-id="ad852-112">在美国，如果向用户分配了一个号码，则需要紧急位置。</span><span class="sxs-lookup"><span data-stu-id="ad852-112">In the United States, an emergency location is required when a number is assigned to a user.</span></span> <span data-ttu-id="ad852-113">对于其他国家或地区（如欧洲、中东和非洲（EMEA）），当您从 Office 365 获取电话号码或从其他服务提供商或运营商处转移时，需要紧急位置。</span><span class="sxs-lookup"><span data-stu-id="ad852-113">For other countries, such as in Europe, the Middle East, and Africa (EMEA), an emergency location is required when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.</span></span>
  
<span data-ttu-id="ad852-114">紧急地点可能称为市政地址、街道地址或物理地址。</span><span class="sxs-lookup"><span data-stu-id="ad852-114">An emergency location may be referred to as a civic address, street address, or a physical address.</span></span> <span data-ttu-id="ad852-115">这是您的组织的公司位置的街道或市政地址。</span><span class="sxs-lookup"><span data-stu-id="ad852-115">It's the street or civic address of a place of business for your organization.</span></span> <span data-ttu-id="ad852-116">例如，地址 12345 "北卡罗来纳州"、 *"雷德蒙"、"WA" 和 "WA 98052* " 用于将紧急呼叫路由到相应的派遣机构，并帮助查找紧急呼叫方。</span><span class="sxs-lookup"><span data-stu-id="ad852-116">For example, the address  *12345 North Main Street, Redmond, WA 98052*  is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span> <span data-ttu-id="ad852-117">如果您的企业有多个物理业务位置，则很可能需要多个紧急位置。</span><span class="sxs-lookup"><span data-stu-id="ad852-117">It's likely that you'll need more than one emergency location if your business has more than one physical business location.</span></span>
  
<span data-ttu-id="ad852-118">验证紧急位置涉及确保它具有合法且格式正确的紧急响应服务。</span><span class="sxs-lookup"><span data-stu-id="ad852-118">Validating an emergency location involves making sure that it's legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="ad852-119">可以添加和保存未验证的紧急位置，但只能将已验证的位置与用户相关联。</span><span class="sxs-lookup"><span data-stu-id="ad852-119">It's possible to add and save an emergency location that isn't validated, but only validated locations can be associated with a user.</span></span> <span data-ttu-id="ad852-120">验证并保存紧急位置后，您可以将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="ad852-120">After an emergency location is validated and saved, you can assign it to a user.</span></span> <span data-ttu-id="ad852-121">要更改已保存和验证的紧急位置，您需要创建一个新的。</span><span class="sxs-lookup"><span data-stu-id="ad852-121">To change an emergency location that's saved and validated, you'll need to create a new one.</span></span>
  
## <a name="what-are-places"></a><span data-ttu-id="ad852-122">有什么地方？</span><span class="sxs-lookup"><span data-stu-id="ad852-122">What are places?</span></span>

<span data-ttu-id="ad852-123">一个位置与紧急位置相关联，以便在大楼内提供更准确的位置。</span><span class="sxs-lookup"><span data-stu-id="ad852-123">A place is associated with an emergency location to give a more exact location within a building.</span></span> <span data-ttu-id="ad852-124">一个位置通常是用户所在的楼层、建筑物的翼形或办公室号码。</span><span class="sxs-lookup"><span data-stu-id="ad852-124">A place is typically a floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="ad852-125">您可以拥有与紧急位置相关联的无限位数。</span><span class="sxs-lookup"><span data-stu-id="ad852-125">You can have an unlimited number of places associated with an emergency location.</span></span> 
  
<span data-ttu-id="ad852-126">向用户分配紧急位置时，它实际上是分配位置时引用的位置 ID。</span><span class="sxs-lookup"><span data-stu-id="ad852-126">When you assign an emergency location to a user, it's actually a location ID that's referenced when you assign the location.</span></span> <span data-ttu-id="ad852-127">位置 ID 包括引用的紧急位置（街道或市政地址）。</span><span class="sxs-lookup"><span data-stu-id="ad852-127">The location ID includes the referenced emergency location (the street or civic address).</span></span> <span data-ttu-id="ad852-128">对于不需要内部部署位置的情况，将在紧急位置附带一个默认位置。</span><span class="sxs-lookup"><span data-stu-id="ad852-128">A default place is included with an emergency location for cases in which in-building places aren't needed.</span></span>
  
## <a name="what-is-emergency-call-routing"></a><span data-ttu-id="ad852-129">什么是紧急呼叫路由？</span><span class="sxs-lookup"><span data-stu-id="ad852-129">What is emergency call routing?</span></span>

<span data-ttu-id="ad852-130">紧急位置和地点在将紧急呼叫发送到相应的派遣中心时，在向相应的派遣中心发出紧急响应的过程中使用。</span><span class="sxs-lookup"><span data-stu-id="ad852-130">Emergency locations and places are used during the process of routing emergency calls to the appropriate dispatch center when dispatching emergency first responders.</span></span> <span data-ttu-id="ad852-131">当团队用户拨打紧急号码时，呼叫如何路由到服务公共安全应答点（PSAP）因国家和地区而异。</span><span class="sxs-lookup"><span data-stu-id="ad852-131">When a Teams user dials an emergency number, how the call is routed to the serving Public Safety Answering Point (PSAP) varies by country and region.</span></span> <span data-ttu-id="ad852-132">在某些国家/地区（如美国和英国），在将呼叫连接到相应的派遣中心之前，将首先筛选呼叫以确定用户的当前位置。</span><span class="sxs-lookup"><span data-stu-id="ad852-132">In some countries, such as the United States and the United Kingdom, the calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> <span data-ttu-id="ad852-133">在其他国家和地区，呼叫直接路由到派遣中心，为与紧急呼叫方相关联的电话号码提供服务。</span><span class="sxs-lookup"><span data-stu-id="ad852-133">In other countries and regions, calls are routed directly to the dispatch center serving the phone number associated with the emergency caller.</span></span>
  
## <a name="create-add-and-assign-emergency-locations-and-places-to-your-users"></a><span data-ttu-id="ad852-134">为您的用户创建、添加和分配紧急位置和位置</span><span class="sxs-lookup"><span data-stu-id="ad852-134">Create, add, and assign emergency locations and places to your users</span></span>

1. <span data-ttu-id="ad852-135">**计划紧急地点**。</span><span class="sxs-lookup"><span data-stu-id="ad852-135">**Plan for emergency locations**.</span></span> <span data-ttu-id="ad852-136">第一步是为紧急位置进行规划。</span><span class="sxs-lookup"><span data-stu-id="ad852-136">The first step is to plan for your emergency locations.</span></span> <span data-ttu-id="ad852-137">列出所有物理地址。</span><span class="sxs-lookup"><span data-stu-id="ad852-137">List all your physical addresses.</span></span> <span data-ttu-id="ad852-138">然后，根据这一点，确定是否需要紧急位置的位置以及是否需要这些位置（如果有）。</span><span class="sxs-lookup"><span data-stu-id="ad852-138">Then, based on that, determine whether places for the emergency locations are needed and if so, what they are.</span></span> <span data-ttu-id="ad852-139">例如，如果一位企业有三个办公楼，每个都有四个楼层，则可能需要有三个紧急位置，其中第一到四个是第一和第四个。</span><span class="sxs-lookup"><span data-stu-id="ad852-139">For example, if a business has three office buildings each with four floors, it's likely that there needs to be three emergency locations, with floors one to four listed as a place for each.</span></span>
    
2. <span data-ttu-id="ad852-140">**添加紧急位置**。</span><span class="sxs-lookup"><span data-stu-id="ad852-140">**Add your emergency locations**.</span></span> <span data-ttu-id="ad852-141">下一步是添加紧急位置。</span><span class="sxs-lookup"><span data-stu-id="ad852-141">The next step is to add your emergency locations.</span></span> <span data-ttu-id="ad852-142">若要了解详细信息，请参阅为[你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ad852-142">To learn more, see [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ad852-143">验证街道或市政地址涉及确保其合法且格式正确。</span><span class="sxs-lookup"><span data-stu-id="ad852-143">Validating a street or civic address involves making sure that it's legitimate and correctly formatted.</span></span> <span data-ttu-id="ad852-144">部分正确的紧急地址（如城市名称）可能仍然通过验证。</span><span class="sxs-lookup"><span data-stu-id="ad852-144">It's possible that a partially correct emergency address, such as a mistyped name of the city, may still pass validation.</span></span> <span data-ttu-id="ad852-145">验证过程使用给定地址的所有部分来确定它是否包含足够的信息，以将呼叫路由到相应的紧急派遣中心。</span><span class="sxs-lookup"><span data-stu-id="ad852-145">The validation process uses all parts of a given address to determine whether it contains enough information to route the call to the appropriate emergency dispatch center.</span></span> <span data-ttu-id="ad852-146">如果是这样，它将按验证返回，然后可以分配给电话号码。</span><span class="sxs-lookup"><span data-stu-id="ad852-146">If so, it will be returned as validated and then can be assigned to a phone number.</span></span>
  
3. <span data-ttu-id="ad852-147">**获取电话号码**。</span><span class="sxs-lookup"><span data-stu-id="ad852-147">**Get phone numbers**.</span></span> <span data-ttu-id="ad852-148">下一步是为你的用户获取电话号码。</span><span class="sxs-lookup"><span data-stu-id="ad852-148">The next step is to get phone numbers for your users.</span></span> <span data-ttu-id="ad852-149">你可以通过从 Office 365 获取新的电话号码或通过将现有电话号码"转网"或转移到 Office 365 来获取号码。</span><span class="sxs-lookup"><span data-stu-id="ad852-149">You can do this by getting new phone numbers from Office 365 or by "porting" or transferring your existing phone numbers over to Office 365.</span></span> <span data-ttu-id="ad852-150">若要查看完整步骤，请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="ad852-150">To see the complete steps, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
    
4. <span data-ttu-id="ad852-151">**分配电话号码**。</span><span class="sxs-lookup"><span data-stu-id="ad852-151">**Assign phone numbers**.</span></span> <span data-ttu-id="ad852-152">最后一步是使用户能够拨打和接听电话。</span><span class="sxs-lookup"><span data-stu-id="ad852-152">The last step is to enable users to make and receive phone calls.</span></span> <span data-ttu-id="ad852-153">要执行此操作，你必须为每个用户分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="ad852-153">To do this, you must assign a phone number to each user.</span></span> <span data-ttu-id="ad852-154">请参阅为[用户分配、更改或删除电话](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)号码以分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="ad852-154">See [Assign, change, or remove a phone number for a user](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="ad852-155">如果您需要获得比这更多的电话号码，[请与 PSTN 服务支持人员联系](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。</span><span class="sxs-lookup"><span data-stu-id="ad852-155">If you need to get more phone numbers than this, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="ad852-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="ad852-156">Related topics</span></span>

[<span data-ttu-id="ad852-157">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="ad852-157">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="ad852-158">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="ad852-158">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)