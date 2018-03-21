---
title: "什么是紧急位置、地址和呼叫路由？"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 35553da49cbaffde1a960ce83550b6fc4ce3ef07
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a><span data-ttu-id="a00cc-103">什么是紧急位置、地址和呼叫路由？</span><span class="sxs-lookup"><span data-stu-id="a00cc-103">What are emergency locations, addresses and call routing?</span></span>

<span data-ttu-id="a00cc-104">当在 Office 365 中配置调用计划时，要求每个电话号码配给一个紧急的地址，或您可以得到的电话号码时指派给用户以支持紧急电话。</span><span class="sxs-lookup"><span data-stu-id="a00cc-104">When you are configuring Calling Plans in Office 365, it's required that an emergency address be assigned to each telephone number when you either get the phone number or when its assigned to a user to support emergency calling.</span></span> <span data-ttu-id="a00cc-105">将紧急的地址分配给一个电话号码之前, 必须创建并验证一个紧急的地址。</span><span class="sxs-lookup"><span data-stu-id="a00cc-105">Before assigning an emergency address to a phone number, an emergency address must be created and validated.</span></span> <span data-ttu-id="a00cc-106">验证可确保紧急通讯被识别并且是可供紧急响应服务的正确格式。</span><span class="sxs-lookup"><span data-stu-id="a00cc-106">Validation ensures that the emergency address is recognized and that it is in a correct format that can be used by emergency response services.</span></span> <span data-ttu-id="a00cc-107">（可选） 可以添加紧急通讯中的位置提供更具体的用户位置。</span><span class="sxs-lookup"><span data-stu-id="a00cc-107">Optionally, a location within the emergency address can be added to provide a more specific location for the user.</span></span> <span data-ttu-id="a00cc-108">例如，紧急位置可能是地板、 翼形或链接到特定的紧急通讯的办公室。</span><span class="sxs-lookup"><span data-stu-id="a00cc-108">For example, the emergency location could be a floor, wing, or office that is linked to a specific emergency address.</span></span> <span data-ttu-id="a00cc-109">即使紧急地址进行验证，并不是位置。</span><span class="sxs-lookup"><span data-stu-id="a00cc-109">Even though emergency address are validated, locations aren't.</span></span>
  
## <a name="what-are-emergency-addresses"></a><span data-ttu-id="a00cc-110">什么是紧急地址？</span><span class="sxs-lookup"><span data-stu-id="a00cc-110">What are emergency addresses?</span></span>

<span data-ttu-id="a00cc-111">活动的电话号码，需要紧急的地址，但当它是必需是取决于国家/地区。</span><span class="sxs-lookup"><span data-stu-id="a00cc-111">An emergency address is required for active telephone numbers, but when it's required is dependent on the country/region.</span></span> <span data-ttu-id="a00cc-112">在美国，紧急通讯时**需要**大量分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a00cc-112">In the United States, an emergency address is **required** when a number is assigned to a user.</span></span> <span data-ttu-id="a00cc-113">对于其他国家或地区，如欧洲、 中东和非洲 (EMEA) 紧急通讯时**需要**从 Office 365 或另一个服务提供商或运营商传输收到的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a00cc-113">For other countries, such as in Europe, the Middle East, and Africa (EMEA), an emergency address is **required** when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.</span></span>
  
<span data-ttu-id="a00cc-114">紧急通讯可能称为市政地址、 街道地址或物理地址。</span><span class="sxs-lookup"><span data-stu-id="a00cc-114">An emergency address may be referred to as a civic address, street address, or a physical address.</span></span> <span data-ttu-id="a00cc-115">它是你的组织业务经营场所的街道或市镇地址。</span><span class="sxs-lookup"><span data-stu-id="a00cc-115">It is the street or civic address of a place of business for your organization.</span></span> <span data-ttu-id="a00cc-116">例如， *12345 北主街道，雷蒙德，WA 98052*用于路由到相应派遣机构的紧急电话，并以帮助定位紧急调用方的地址。</span><span class="sxs-lookup"><span data-stu-id="a00cc-116">For example, the address  *12345 North Main Street, Redmond, WA 98052*  is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span> <span data-ttu-id="a00cc-117">如果你的企业有多个物理位置，你可能需要多个紧急地址。</span><span class="sxs-lookup"><span data-stu-id="a00cc-117">It's likely that you will need more than one emergency address if your business has more than one physical business location.</span></span>
  
<span data-ttu-id="a00cc-118">验证应急通讯涉及确保它合法且紧急响应服务的格式正确。</span><span class="sxs-lookup"><span data-stu-id="a00cc-118">Validating an emergency address involves making sure that it is legitimate and correctly formatted for emergency response services.</span></span> <span data-ttu-id="a00cc-119">可以创建并保存紧急地址未验证，但只有经过验证的地址可以是与用户相关联。</span><span class="sxs-lookup"><span data-stu-id="a00cc-119">It's possible to create and save an emergency address that isn't validated, but only validated addresses can be associated to a user.</span></span> <span data-ttu-id="a00cc-120">验证和保存紧急地址后，即可将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a00cc-120">Once an emergency address is validated and saved, it can be assigned to a user.</span></span> <span data-ttu-id="a00cc-121">如果需要更改保存的已验证紧急地址，你需要创建一个新紧急地址。</span><span class="sxs-lookup"><span data-stu-id="a00cc-121">If you need to change a saved validated emergency address, you will need to create a new one.</span></span>
  
## <a name="what-are-emergency-locations"></a><span data-ttu-id="a00cc-122">什么是紧急位置？</span><span class="sxs-lookup"><span data-stu-id="a00cc-122">What are emergency locations?</span></span>

<span data-ttu-id="a00cc-123">紧急位置是使建筑物内的更精确位置紧急地址相关联。</span><span class="sxs-lookup"><span data-stu-id="a00cc-123">Emergency locations are associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="a00cc-124">紧急位置通常是用户所在的楼层、侧楼或办公室编号。</span><span class="sxs-lookup"><span data-stu-id="a00cc-124">An emergency location is typically a floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="a00cc-125">可以有无限个紧急地址相关联的位置。</span><span class="sxs-lookup"><span data-stu-id="a00cc-125">You can have an unlimited number of locations associated with an emergency address.</span></span> 
  
<span data-ttu-id="a00cc-126">向用户分配紧急地址，实际上是分配地址时引用的位置 ID。</span><span class="sxs-lookup"><span data-stu-id="a00cc-126">When assigning a user an emergency address, it is actually a location ID that is referenced when you assign the address.</span></span> <span data-ttu-id="a00cc-127">位置 ID 包含被引用的紧急地址 （街道或市政地址）。</span><span class="sxs-lookup"><span data-stu-id="a00cc-127">The location ID includes the referenced emergency address (the street or civic address).</span></span> <span data-ttu-id="a00cc-128">如果不需要建筑内的位置，则紧急地址将包括默认紧急位置。</span><span class="sxs-lookup"><span data-stu-id="a00cc-128">A default emergency location is included with an emergency address for the case when in-building locations aren't needed.</span></span> 
  
## <a name="what-is-emergency-call-routing"></a><span data-ttu-id="a00cc-129">什么是紧急呼叫路由？</span><span class="sxs-lookup"><span data-stu-id="a00cc-129">What is emergency call routing?</span></span>

<span data-ttu-id="a00cc-130">紧急的地址和位置路由到相应的派单中心的紧急电话的过程时使用调度紧急的第一反应。</span><span class="sxs-lookup"><span data-stu-id="a00cc-130">Emergency addresses and locations are used during the process of routing emergency calls to the appropriate dispatch center when dispatching emergency first responders.</span></span> <span data-ttu-id="a00cc-131">当业务用户的 Skype 拨叫紧急号码时，如何将呼叫路由到服务公共安全应答点 (PSAP) 会因国家/地区。</span><span class="sxs-lookup"><span data-stu-id="a00cc-131">When a Skype for Business user dials an emergency number, how the call is routed to the serving Public Safety Answering Point (PSAP) will vary by country/region.</span></span> <span data-ttu-id="a00cc-132">在某些国家，如美国和英国，该调用将第一次进行检查，以连接到相应调度中心电话之前确定当前用户的位置。</span><span class="sxs-lookup"><span data-stu-id="a00cc-132">In some countries, such as the United States and the United Kingdom, the calls will first be screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> <span data-ttu-id="a00cc-133">在其他国家/地区，调用将被直接路由到调度中心服务的关联与紧急呼叫的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a00cc-133">In other countries/regions, calls will be routed directly to the dispatch center serving the phone number associated with the emergency caller.</span></span>
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a><span data-ttu-id="a00cc-134">创建、 添加和将紧急位置和地址分配给您的用户</span><span class="sxs-lookup"><span data-stu-id="a00cc-134">Creating, adding, and assigning emergency locations and addresses to your users</span></span>

1. <span data-ttu-id="a00cc-135">**规划对于紧急的位置**第一步是安排紧急的位置。</span><span class="sxs-lookup"><span data-stu-id="a00cc-135">**Plan for emergency locations** The first step is to plan for your emergency locations.</span></span> <span data-ttu-id="a00cc-136">您需要列出所有您的物理地址。</span><span class="sxs-lookup"><span data-stu-id="a00cc-136">You need to list all of your physical addresses.</span></span> <span data-ttu-id="a00cc-137">然后，此基础，确定是否需要紧急地址的位置，如果出现这种情况，它们是什么。</span><span class="sxs-lookup"><span data-stu-id="a00cc-137">Then, based on that, determine whether locations for the emergency addresses are needed and if so, what they are.</span></span> <span data-ttu-id="a00cc-138">例如，如果企业具有 3 办公楼每 4 厂用，很可能，必须有 3 个紧急地址，与 1-4 的位置列出每个楼层。</span><span class="sxs-lookup"><span data-stu-id="a00cc-138">For example, if a business has 3 office buildings each with 4 floors, it is likely that there need to be 3 emergency addresses, with floors 1-4 listed as a location for each.</span></span>
    
2. <span data-ttu-id="a00cc-139">**创建并验证紧急位置** 下一步是创建和验证紧急地址。</span><span class="sxs-lookup"><span data-stu-id="a00cc-139">**Create and validate your emergency locations** The next step is to create and validate your emergency addresses.</span></span> <span data-ttu-id="a00cc-140">当你创建紧急地址时，可以验证它。</span><span class="sxs-lookup"><span data-stu-id="a00cc-140">When you create an emergency address, you can validate it.</span></span> <span data-ttu-id="a00cc-141">若要创建一个紧急的地址，请参阅[添加或删除为您的组织满足紧急情况](add-or-remove-an-emergency-address-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="a00cc-141">To create an emergency address, see [Add or remove an emergency address for your organization](add-or-remove-an-emergency-address-for-your-organization.md).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a00cc-142">[!重要信息] 验证街道或市镇地址涉及确保该地址是合法的并且格式设置正确。</span><span class="sxs-lookup"><span data-stu-id="a00cc-142">Validating a street or civic address involves making sure that it is legitimate and correctly formatted.</span></span> <span data-ttu-id="a00cc-143">可能存在不完全正确的紧急地址（例如，城市的名称有错）可能仍会通过验证。</span><span class="sxs-lookup"><span data-stu-id="a00cc-143">It is possible that a partially correct emergency address, such as a mistyped name of the city, may pass still pass validation.</span></span> <span data-ttu-id="a00cc-144">验证过程使用给定的地址的所有部分，确定它是否包含足够的信息来将呼叫路由到适当的紧急派遣中心。</span><span class="sxs-lookup"><span data-stu-id="a00cc-144">The validation process uses all parts of a given address to determine if it contains enough information to route the call to the appropriate emergency dispatch center.</span></span> <span data-ttu-id="a00cc-145">如果是这样，它会返回验证，然后可以分配到一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="a00cc-145">If so, it will be returned as validated and then can be assigned to a phone number.</span></span> 
  
3. <span data-ttu-id="a00cc-146">**获取电话号码**下一步是获取用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a00cc-146">**Get phone numbers** The next step is to get phone numbers for your users.</span></span> <span data-ttu-id="a00cc-147">你可以通过从 Office 365 获取新的电话号码或通过将现有电话号码"转网"或转移到 Office 365 来获取号码。</span><span class="sxs-lookup"><span data-stu-id="a00cc-147">You can do this by getting new phone numbers from Office 365 or by "porting" or transferring your existing phone numbers over to Office 365.</span></span> <span data-ttu-id="a00cc-148">若要查看完整的步骤，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a00cc-148">To see the complete steps, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
    
4. <span data-ttu-id="a00cc-149">**分配电话号码** 最后一步是让用户拨打和接听电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="a00cc-149">**Assign phone numbers** The last step is to enable users to make and receive phone calls.</span></span> <span data-ttu-id="a00cc-150">要执行此操作，你必须为每个用户分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="a00cc-150">To do this, you must assign a phone number to each user.</span></span> <span data-ttu-id="a00cc-151">请参阅[指派、 更改或删除的用户的电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)分配的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a00cc-151">See [Assign, change, or remove a phone number for a user](assign-change-or-remove-a-phone-number-for-a-user.md) to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="a00cc-152">如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="a00cc-152">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="a00cc-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="a00cc-153">Related topics</span></span>
[<span data-ttu-id="a00cc-154">什么是地址验证？</span><span class="sxs-lookup"><span data-stu-id="a00cc-154">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="a00cc-155">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="a00cc-155">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="a00cc-156">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="a00cc-156">Emergency calling terms and conditions</span></span>](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="a00cc-157">Skype for Business Online：紧急呼叫免责声明标签</span><span class="sxs-lookup"><span data-stu-id="a00cc-157">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
