---
title: 什么是紧急位置、 地址和呼叫路由？
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
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: d552fe5599a9c1189b20a3efa69f659333d80166
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30352839"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a><span data-ttu-id="8ee62-103">什么是紧急位置、 地址和呼叫路由？</span><span class="sxs-lookup"><span data-stu-id="8ee62-103">What are emergency locations, addresses, and call routing?</span></span>

<span data-ttu-id="8ee62-104">配置时调用计划在 Office 365 中，您必须将紧急地址分配给每个电话号码，获取电话号码或将其分配给用户支持紧急呼叫时。</span><span class="sxs-lookup"><span data-stu-id="8ee62-104">When you are configuring Calling Plans in Office 365, you have to assign an emergency address to each telephone number when you either get the phone number or assign it to a user to support emergency calling.</span></span> <span data-ttu-id="8ee62-105">您可以为紧急地址分配电话号码之前，必须创建和验证紧急地址。</span><span class="sxs-lookup"><span data-stu-id="8ee62-105">And before you can assign an emergency address to a phone number, you must create and validate the emergency address.</span></span> <span data-ttu-id="8ee62-106">验证可以确保紧急地址被识别，并且是可由紧急响应 services 使用正确的格式。</span><span class="sxs-lookup"><span data-stu-id="8ee62-106">Validation ensures that the emergency address is recognized and that it is in a correct format that can be used by emergency response services.</span></span> <span data-ttu-id="8ee62-107">或者，您可以添加内提供用户的更多特定位置的紧急地址的位置。</span><span class="sxs-lookup"><span data-stu-id="8ee62-107">Optionally, you can add a location within the emergency address to provide a more specific location for the user.</span></span> <span data-ttu-id="8ee62-108">例如，floor、 wing 或链接到特定的紧急地址的 office，无法为紧急位置。</span><span class="sxs-lookup"><span data-stu-id="8ee62-108">For example, the emergency location could be a floor, wing, or office that is linked to a specific emergency address.</span></span> <span data-ttu-id="8ee62-109">验证紧急地址，尽管不位置。</span><span class="sxs-lookup"><span data-stu-id="8ee62-109">Although emergency address are validated, locations aren't.</span></span>
  
## <a name="what-are-emergency-addresses"></a><span data-ttu-id="8ee62-110">什么是紧急地址？</span><span class="sxs-lookup"><span data-stu-id="8ee62-110">What are emergency addresses?</span></span>

<span data-ttu-id="8ee62-111">紧急地址需要活动的电话号码，但需要时取决于国家/地区。</span><span class="sxs-lookup"><span data-stu-id="8ee62-111">An emergency address is required for active telephone numbers, but when it's required depends on the country/region.</span></span> <span data-ttu-id="8ee62-112">在美国，紧急地址时需要一个号码分配给用户。</span><span class="sxs-lookup"><span data-stu-id="8ee62-112">In the United States, an emergency address is required when a number is assigned to a user.</span></span> <span data-ttu-id="8ee62-113">其他国家/地区，如欧洲、 中东和非洲 (EMEA) 中的紧急地址时需要您要从 Office 365 或从其他服务提供商或运营商传输获取电话号码。</span><span class="sxs-lookup"><span data-stu-id="8ee62-113">For other countries, such as in Europe, the Middle East, and Africa (EMEA), an emergency address is required when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.</span></span>
  
<span data-ttu-id="8ee62-114">紧急地址可能称为市政地址、 街道地址或物理地址。</span><span class="sxs-lookup"><span data-stu-id="8ee62-114">An emergency address may be referred to as a civic address, street address, or a physical address.</span></span> <span data-ttu-id="8ee62-115">它是你的组织业务经营场所的街道或市镇地址。</span><span class="sxs-lookup"><span data-stu-id="8ee62-115">It is the street or civic address of a place of business for your organization.</span></span> <span data-ttu-id="8ee62-116">例如， *12345 北美 Main Street，Redmond，WA 98052*用于紧急呼叫路由到相应派遣机构和帮助查找紧急呼叫者的地址。</span><span class="sxs-lookup"><span data-stu-id="8ee62-116">For example, the address  *12345 North Main Street, Redmond, WA 98052*  is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span> <span data-ttu-id="8ee62-117">如果你的企业有多个物理位置，你可能需要多个紧急地址。</span><span class="sxs-lookup"><span data-stu-id="8ee62-117">It's likely that you will need more than one emergency address if your business has more than one physical business location.</span></span>
  
<span data-ttu-id="8ee62-118">验证紧急地址涉及确保它合法和格式正确的应急响应服务。</span><span class="sxs-lookup"><span data-stu-id="8ee62-118">Validating an emergency address involves making sure that it is legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="8ee62-119">可以创建并保存紧急地址不验证，但仅验证的地址可与用户相关联。</span><span class="sxs-lookup"><span data-stu-id="8ee62-119">It's possible to create and save an emergency address that isn't validated, but only validated addresses can be associated with a user.</span></span> <span data-ttu-id="8ee62-120">验证和保存紧急地址后，即可将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="8ee62-120">Once an emergency address is validated and saved, it can be assigned to a user.</span></span> <span data-ttu-id="8ee62-121">如果需要更改保存的已验证紧急地址，你需要创建一个新紧急地址。</span><span class="sxs-lookup"><span data-stu-id="8ee62-121">If you need to change a saved validated emergency address, you will need to create a new one.</span></span>
  
## <a name="what-are-emergency-locations"></a><span data-ttu-id="8ee62-122">什么是紧急位置？</span><span class="sxs-lookup"><span data-stu-id="8ee62-122">What are emergency locations?</span></span>

<span data-ttu-id="8ee62-123">紧急位置相关联的紧急的地址，以提供大厦内的更精确位置。</span><span class="sxs-lookup"><span data-stu-id="8ee62-123">An emergency location is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="8ee62-124">紧急位置通常是用户所在的楼层、侧楼或办公室编号。</span><span class="sxs-lookup"><span data-stu-id="8ee62-124">An emergency location is typically a floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="8ee62-125">您可以数量不限与紧急地址关联的位置。</span><span class="sxs-lookup"><span data-stu-id="8ee62-125">You can have an unlimited number of locations associated with an emergency address.</span></span> 
  
<span data-ttu-id="8ee62-126">为用户分配的紧急地址，时，实际上引用时指定地址的位置 ID。</span><span class="sxs-lookup"><span data-stu-id="8ee62-126">When you assign an emergency address to a user, it is actually a location ID that is referenced when you assign the address.</span></span> <span data-ttu-id="8ee62-127">位置 ID 包括的引用的紧急地址 （街道或市政地址）。</span><span class="sxs-lookup"><span data-stu-id="8ee62-127">The location ID includes the referenced emergency address (the street or civic address).</span></span> <span data-ttu-id="8ee62-128">默认紧急位置随中构建位置不所需的情况下紧急地址。</span><span class="sxs-lookup"><span data-stu-id="8ee62-128">A default emergency location is included with an emergency address for cases in which in-building locations aren't needed.</span></span> 
  
## <a name="what-is-emergency-call-routing"></a><span data-ttu-id="8ee62-129">什么是紧急呼叫路由？</span><span class="sxs-lookup"><span data-stu-id="8ee62-129">What is emergency call routing?</span></span>

<span data-ttu-id="8ee62-130">紧急地址和位置的紧急呼叫路由至相应派遣中心过程时使用派遣紧急的第一个响应者。</span><span class="sxs-lookup"><span data-stu-id="8ee62-130">Emergency addresses and locations are used during the process of routing emergency calls to the appropriate dispatch center when dispatching emergency first responders.</span></span> <span data-ttu-id="8ee62-131">当工作组或业务用户的 Skype 拨打紧急号码，如何将该呼叫路由到公共安全应答点 (PSAP) 提供不同的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="8ee62-131">When a Teams or Skype for Business user dials an emergency number, how the call is routed to the serving Public Safety Answering Point (PSAP) will vary by country/region.</span></span> <span data-ttu-id="8ee62-132">在某些国家/地区，如美国和英国，呼叫将先进行检查，以连接到相应派遣中心呼叫之前确定当前用户的位置。</span><span class="sxs-lookup"><span data-stu-id="8ee62-132">In some countries, such as the United States and the United Kingdom, the calls will first be screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> <span data-ttu-id="8ee62-133">在其他国家/地区，呼叫将路由到调度中心提供紧急呼叫者与关联的电话号码直接。</span><span class="sxs-lookup"><span data-stu-id="8ee62-133">In other countries/regions, calls will be routed directly to the dispatch center serving the phone number associated with the emergency caller.</span></span>
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a><span data-ttu-id="8ee62-134">创建、 添加和将紧急位置和地址分配给您的用户</span><span class="sxs-lookup"><span data-stu-id="8ee62-134">Create, add, and assign emergency locations and addresses to your users</span></span>

1. <span data-ttu-id="8ee62-135">**规划紧急位置**。</span><span class="sxs-lookup"><span data-stu-id="8ee62-135">**Plan for emergency locations**.</span></span> <span data-ttu-id="8ee62-136">第一步是规划您的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="8ee62-136">The first step is to plan for your emergency locations.</span></span> <span data-ttu-id="8ee62-137">您需要的所有您的物理地址列表。</span><span class="sxs-lookup"><span data-stu-id="8ee62-137">You need to list all of your physical addresses.</span></span> <span data-ttu-id="8ee62-138">然后，此基础，确定是否需要紧急地址的位置，如果是这样，它们是什么。</span><span class="sxs-lookup"><span data-stu-id="8ee62-138">Then, based on that, determine whether locations for the emergency addresses are needed and if so, what they are.</span></span> <span data-ttu-id="8ee62-139">例如，如果企业具有 3 办公楼每个与 4 楼层，很可能有需要 3 紧急地址，1-4 为位置列出每个楼层。</span><span class="sxs-lookup"><span data-stu-id="8ee62-139">For example, if a business has 3 office buildings each with 4 floors, it is likely that there need to be 3 emergency addresses, with floors 1-4 listed as a location for each.</span></span>
    
2. <span data-ttu-id="8ee62-140">**创建和验证您紧急位置**。</span><span class="sxs-lookup"><span data-stu-id="8ee62-140">**Create and validate your emergency locations**.</span></span> <span data-ttu-id="8ee62-141">下一步是创建和验证您紧急地址。</span><span class="sxs-lookup"><span data-stu-id="8ee62-141">The next step is to create and validate your emergency addresses.</span></span> <span data-ttu-id="8ee62-142">当你创建紧急地址时，可以验证它。</span><span class="sxs-lookup"><span data-stu-id="8ee62-142">When you create an emergency address, you can validate it.</span></span> <span data-ttu-id="8ee62-143">若要创建紧急地址，请参阅[添加或删除紧急情况地址为您的组织](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="8ee62-143">To create an emergency address, see [Add or remove an emergency address for your organization](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ee62-144">[!重要信息] 验证街道或市镇地址涉及确保该地址是合法的并且格式设置正确。</span><span class="sxs-lookup"><span data-stu-id="8ee62-144">Validating a street or civic address involves making sure that it is legitimate and correctly formatted.</span></span> <span data-ttu-id="8ee62-145">则可能部分正确的紧急地址，例如键入错误市/县的名称可能仍通过验证。</span><span class="sxs-lookup"><span data-stu-id="8ee62-145">It is possible that a partially correct emergency address, such as a mistyped name of the city, may still pass validation.</span></span> <span data-ttu-id="8ee62-146">验证过程使用给定的地址的所有部分，确定它是否包含足够的信息来将呼叫路由到适当的紧急派遣中心。</span><span class="sxs-lookup"><span data-stu-id="8ee62-146">The validation process uses all parts of a given address to determine if it contains enough information to route the call to the appropriate emergency dispatch center.</span></span> <span data-ttu-id="8ee62-147">如果是这样，它将返回为已验证，并且然后可以分配给电话号码。</span><span class="sxs-lookup"><span data-stu-id="8ee62-147">If so, it will be returned as validated and then can be assigned to a phone number.</span></span> 
  
3. <span data-ttu-id="8ee62-148">**获取电话号码**。</span><span class="sxs-lookup"><span data-stu-id="8ee62-148">**Get phone numbers**.</span></span> <span data-ttu-id="8ee62-149">下一步是为用户获取电话号码。</span><span class="sxs-lookup"><span data-stu-id="8ee62-149">The next step is to get phone numbers for your users.</span></span> <span data-ttu-id="8ee62-150">你可以通过从 Office 365 获取新的电话号码或通过将现有电话号码"转网"或转移到 Office 365 来获取号码。</span><span class="sxs-lookup"><span data-stu-id="8ee62-150">You can do this by getting new phone numbers from Office 365 or by "porting" or transferring your existing phone numbers over to Office 365.</span></span> <span data-ttu-id="8ee62-151">若要查看的完整步骤，请参阅[转接到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8ee62-151">To see the complete steps, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
    
4. <span data-ttu-id="8ee62-152">**分配电话号码**。</span><span class="sxs-lookup"><span data-stu-id="8ee62-152">**Assign phone numbers**.</span></span> <span data-ttu-id="8ee62-153">最后一步是使用户可以发起和接收电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="8ee62-153">The last step is to enable users to make and receive phone calls.</span></span> <span data-ttu-id="8ee62-154">要执行此操作，你必须为每个用户分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="8ee62-154">To do this, you must assign a phone number to each user.</span></span> <span data-ttu-id="8ee62-155">请参阅[分配、 更改或删除的用户的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user)分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="8ee62-155">See [Assign, change, or remove a phone number for a user](/SkypeForBusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user) to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="8ee62-156">如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="8ee62-156">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="8ee62-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="8ee62-157">Related topics</span></span>
[<span data-ttu-id="8ee62-158">什么是地址验证？</span><span class="sxs-lookup"><span data-stu-id="8ee62-158">What is address validation?</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[<span data-ttu-id="8ee62-159">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="8ee62-159">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="8ee62-160">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="8ee62-160">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="8ee62-161">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8ee62-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

