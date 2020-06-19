---
title: 团队语音 Contoso 个案研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785976"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="64006-103">Contoso 案例研究：紧急电话</span><span class="sxs-lookup"><span data-stu-id="64006-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="64006-104">要了解紧急呼叫的可用性以及与紧急呼叫 &mdash; 紧急地址、地点、紧急位置和注册地址相关的术语， &mdash; Contoso 已查看[管理紧急呼叫](what-are-emergency-locations-addresses-and-call-routing.md)和[计划和配置动态紧急呼叫](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="64006-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="64006-105">在 Office 365 中，通话计划用户将自动启用以进行紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="64006-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="64006-106">但只有美国的通话计划用户才可以使用动态位置路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="64006-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="64006-107">对于直接路由，Contoso 发现，需要进行额外的配置来路由紧急呼叫，并且可能需要进行合作伙伴连接。</span><span class="sxs-lookup"><span data-stu-id="64006-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="64006-108">管理员必须配置与紧急路由服务提供商（ERSP）（美国）的连接，或为紧急位置识别号码（ELIN）应用程序配置会话边界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="64006-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="64006-109">Contoso 拥有美国和美国境外的办事处：</span><span class="sxs-lookup"><span data-stu-id="64006-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="64006-110">在美国，Contoso 通话计划用户可以使用动态位置路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="64006-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="64006-111">在美国以外，Contoso 拥有一些使用呼叫计划的网站，以及通过直接路由连接到手机系统的某些网站。</span><span class="sxs-lookup"><span data-stu-id="64006-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="64006-112">紧急呼叫使用案例</span><span class="sxs-lookup"><span data-stu-id="64006-112">Emergency calling use cases</span></span>

<span data-ttu-id="64006-113">确定 Contoso 将如何连接到手机系统后，Contoso 识别出以下紧急呼叫使用案例：</span><span class="sxs-lookup"><span data-stu-id="64006-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="64006-114">美国的通话计划用户</span><span class="sxs-lookup"><span data-stu-id="64006-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="64006-115">美国境外的通话计划用户</span><span class="sxs-lookup"><span data-stu-id="64006-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="64006-116">通过直接路由连接到手机系统的用户</span><span class="sxs-lookup"><span data-stu-id="64006-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="64006-117">美国的通话计划用户</span><span class="sxs-lookup"><span data-stu-id="64006-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="64006-118">需要与紧急位置相关联的电话号码的要求。</span><span class="sxs-lookup"><span data-stu-id="64006-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="64006-119">若要了解这些要求，Contoso 检查[了通话计划的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="64006-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="64006-120">根据这些要求，当将号码分配给美国的用户时，Contoso 决定将位置与电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="64006-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="64006-121">美国境外的通话计划用户</span><span class="sxs-lookup"><span data-stu-id="64006-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="64006-122">若要了解需要与紧急位置相关联的电话号码，Contoso 检查[了通话计划的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="64006-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="64006-123">根据要求，Contoso 确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="64006-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="64006-124">当将号码分配给加拿大的用户时，Contoso 会将该位置与电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="64006-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="64006-125">当从 Office 365 获取电话号码时，或者从另一个服务提供商或运营商处转移号码时，Contoso 将分配紧急地点。</span><span class="sxs-lookup"><span data-stu-id="64006-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="64006-126">通过直接路由连接到手机系统的用户</span><span class="sxs-lookup"><span data-stu-id="64006-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="64006-127">要为此使用案例规划紧急路由，Contoso 已检查[直接路由的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="64006-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="64006-128">由于直接路由用户没有像呼叫计划用户那样接收紧急呼叫，因此，Contoso 必须决定如何提供紧急电话。</span><span class="sxs-lookup"><span data-stu-id="64006-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="64006-129">直接路由可以连接到紧急路由服务提供商（ERSP）。</span><span class="sxs-lookup"><span data-stu-id="64006-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="64006-130">直接路由还可以有一个包含紧急位置识别号（ELIN）的 SBC。</span><span class="sxs-lookup"><span data-stu-id="64006-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="64006-131">紧急路由服务提供商（ERSP）注意事项</span><span class="sxs-lookup"><span data-stu-id="64006-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="64006-132">紧急路由服务提供商（ERSPs）可以根据呼叫方的位置自动路由紧急电话。</span><span class="sxs-lookup"><span data-stu-id="64006-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="64006-133">如果将紧急路线服务提供商集成到直接路由部署中，则会将带有动态获取位置的紧急呼叫自动路由到服务该位置的公共安全应答点（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="64006-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="64006-134">在将呼叫连接到基于更新的位置之前，没有动态获取的位置的紧急电话将首先进行筛选以确定用户的当前位置。</span><span class="sxs-lookup"><span data-stu-id="64006-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="64006-135">ELIN 注意事项</span><span class="sxs-lookup"><span data-stu-id="64006-135">ELIN considerations</span></span>

<span data-ttu-id="64006-136">如果 SBC ELIN 应用程序集成到直接路由部署中，则需要执行其他配置步骤以将紧急地址与电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="64006-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="64006-137">Contoso 决定使用包含紧急位置标识号（ELIN）应用程序的会话边框控制器。</span><span class="sxs-lookup"><span data-stu-id="64006-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="64006-138">安全桌面通知</span><span class="sxs-lookup"><span data-stu-id="64006-138">Security desk notification</span></span>

<span data-ttu-id="64006-139">可用于 Microsoft 通话计划和电话系统直接路由，以便在紧急呼叫被置入时通知安全桌面。</span><span class="sxs-lookup"><span data-stu-id="64006-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="64006-140">Contoso 已查看安全桌面通知中的详细信息，以确定是否应在其办公室配置此信息</span><span class="sxs-lookup"><span data-stu-id="64006-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="64006-141">Contoso 决定使用安全桌面通知。</span><span class="sxs-lookup"><span data-stu-id="64006-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="64006-142">配置</span><span class="sxs-lookup"><span data-stu-id="64006-142">Configuration</span></span> 

<span data-ttu-id="64006-143">Contoso 按照[配置动态紧急呼叫](configure-dynamic-emergency-calling.md)的步骤执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="64006-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="64006-144">分配紧急地址</span><span class="sxs-lookup"><span data-stu-id="64006-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="64006-145">配置网络设置</span><span class="sxs-lookup"><span data-stu-id="64006-145">Configure network settings</span></span> 

- <span data-ttu-id="64006-146">配置位置信息服务</span><span class="sxs-lookup"><span data-stu-id="64006-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="64006-147">配置紧急策略</span><span class="sxs-lookup"><span data-stu-id="64006-147">Configure emergency policies</span></span> 

- <span data-ttu-id="64006-148">启用用户和网站</span><span class="sxs-lookup"><span data-stu-id="64006-148">Enable users and sites</span></span> 

- <span data-ttu-id="64006-149">测试紧急电话</span><span class="sxs-lookup"><span data-stu-id="64006-149">Test emergency calling</span></span> 

<span data-ttu-id="64006-150">配置动态紧急呼叫后，Contoso 需要将位置分配给相应的用户。</span><span class="sxs-lookup"><span data-stu-id="64006-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="64006-151">若要为你的组织添加、更改或删除紧急位置，Contoso 按照[添加、更改或删除你的组织的紧急位置](add-change-remove-emergency-location-organization.md)中的步骤进行操作</span><span class="sxs-lookup"><span data-stu-id="64006-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="64006-152">要创建建筑物、楼层和办事处的位置，Contoso 按照[为紧急位置添加、更改或删除位置](add-change-remove-emergency-place-organization.md)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="64006-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="64006-153">要分配紧急位置，Contoso 按照[为用户分配或更改紧急位置](assign-change-emergency-location-user.md)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="64006-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 