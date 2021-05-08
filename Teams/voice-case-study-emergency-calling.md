---
title: Teams Contoso 案例研究
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
description: Teams多语言公司语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785976"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="ec27e-103">Contoso 案例研究：紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="ec27e-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="ec27e-104">若要了解紧急呼叫的可用性以及与紧急呼叫相关的术语，请拨打紧急地址、地点、紧急位置和已注册地址 &mdash; &mdash; ，Contoso[](what-are-emergency-locations-addresses-and-call-routing.md)查看管理紧急呼叫和[计划和](configure-dynamic-emergency-calling.md)配置动态紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="ec27e-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="ec27e-105">在Office 365，呼叫计划用户会自动启用紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="ec27e-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="ec27e-106">但是，只有美国的呼叫计划用户才能使用动态位置路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="ec27e-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="ec27e-107">对于直接路由，Contoso 了解到，路由紧急呼叫和合作伙伴连接可能需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="ec27e-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="ec27e-108">管理员必须配置与紧急路由服务提供商 (ERSP)  (美国) 的连接，或者为紧急位置标识号 (ELIN) 应用程序配置会话边界控制器 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="ec27e-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="ec27e-109">Contoso 在美国和美国以外设有办公室：</span><span class="sxs-lookup"><span data-stu-id="ec27e-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="ec27e-110">在美国，Contoso 呼叫计划用户可以使用动态位置路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="ec27e-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="ec27e-111">在美国以外，Contoso 拥有一些使用呼叫计划的站点，以及一些通过直接路由电话系统连接的站点。</span><span class="sxs-lookup"><span data-stu-id="ec27e-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="ec27e-112">紧急呼叫用例</span><span class="sxs-lookup"><span data-stu-id="ec27e-112">Emergency calling use cases</span></span>

<span data-ttu-id="ec27e-113">确定 Contoso 如何连接到电话后，Contoso 确定了以下紧急呼叫用例：</span><span class="sxs-lookup"><span data-stu-id="ec27e-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="ec27e-114">呼叫美国计划用户</span><span class="sxs-lookup"><span data-stu-id="ec27e-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="ec27e-115">呼叫美国以外的计划用户</span><span class="sxs-lookup"><span data-stu-id="ec27e-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="ec27e-116">通过直接路由电话系统用户</span><span class="sxs-lookup"><span data-stu-id="ec27e-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="ec27e-117">呼叫美国计划用户</span><span class="sxs-lookup"><span data-stu-id="ec27e-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="ec27e-118">电话号码何时需要与紧急位置关联有要求。</span><span class="sxs-lookup"><span data-stu-id="ec27e-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="ec27e-119">为了了解这些要求，Contoso 查看了 [调用计划的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="ec27e-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="ec27e-120">根据这些要求，Contoso 决定在将号码分配给美国用户时，将位置与电话号码关联。</span><span class="sxs-lookup"><span data-stu-id="ec27e-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="ec27e-121">呼叫美国以外的计划用户</span><span class="sxs-lookup"><span data-stu-id="ec27e-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="ec27e-122">为了了解电话号码何时需要与紧急位置关联，Contoso 查看了呼叫  [计划的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="ec27e-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="ec27e-123">Contoso 根据要求决定以下事项：</span><span class="sxs-lookup"><span data-stu-id="ec27e-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="ec27e-124">当向加拿大的用户分配号码时，Contoso 将位置与电话号码关联。</span><span class="sxs-lookup"><span data-stu-id="ec27e-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="ec27e-125">从提供商处获取电话号码时，或者从另一服务提供商或运营商Office 365号码时，Contoso 将分配紧急位置。</span><span class="sxs-lookup"><span data-stu-id="ec27e-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="ec27e-126">通过直接路由电话系统用户</span><span class="sxs-lookup"><span data-stu-id="ec27e-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="ec27e-127">为了针对此用例规划紧急路由，Contoso 查看了 [直接路由的注意事项](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="ec27e-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="ec27e-128">由于直接路由用户接收紧急呼叫的方式与呼叫计划用户不同，Contoso 必须决定如何提供紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="ec27e-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="ec27e-129">直接路由可以连接到紧急路由服务提供商 (ERSP) 。</span><span class="sxs-lookup"><span data-stu-id="ec27e-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="ec27e-130">直接路由还可以有一个 SBC，其中包含紧急位置标识号 (ELIN) 。</span><span class="sxs-lookup"><span data-stu-id="ec27e-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="ec27e-131">紧急路由服务提供商 (ERSP) 注意事项</span><span class="sxs-lookup"><span data-stu-id="ec27e-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="ec27e-132">紧急路由服务提供商 (ERSP) 根据呼叫者的位置自动路由紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="ec27e-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="ec27e-133">如果将紧急路由服务提供商集成到直接路由部署中，具有动态获取位置的紧急呼叫将自动路由到提供该位置的公共安全应答点 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="ec27e-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="ec27e-134">没有动态获取位置的紧急呼叫首先经过筛选，以确定用户的当前位置，然后根据更新的位置将呼叫连接到相应的调度中心。</span><span class="sxs-lookup"><span data-stu-id="ec27e-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="ec27e-135">ELIN 注意事项</span><span class="sxs-lookup"><span data-stu-id="ec27e-135">ELIN considerations</span></span>

<span data-ttu-id="ec27e-136">如果将 SBC ELIN 应用程序集成到直接路由部署中，则需要执行其他配置步骤，将紧急地址与电话号码关联。</span><span class="sxs-lookup"><span data-stu-id="ec27e-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="ec27e-137">Contoso 决定使用包含紧急位置标识号的会话边界控制器 (ELIN) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec27e-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="ec27e-138">安全服务台通知</span><span class="sxs-lookup"><span data-stu-id="ec27e-138">Security desk notification</span></span>

<span data-ttu-id="ec27e-139">在拨打紧急呼叫时通知安全服务台的能力适用于 Microsoft 呼叫计划和直接电话系统路由。</span><span class="sxs-lookup"><span data-stu-id="ec27e-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="ec27e-140">Contoso 查看了安全服务台通知中的详细信息，确定是否应在其办公室进行配置</span><span class="sxs-lookup"><span data-stu-id="ec27e-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="ec27e-141">Contoso 决定使用安全服务台通知。</span><span class="sxs-lookup"><span data-stu-id="ec27e-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="ec27e-142">配置</span><span class="sxs-lookup"><span data-stu-id="ec27e-142">Configuration</span></span> 

<span data-ttu-id="ec27e-143">Contoso 遵循配置动态紧急 [呼叫中的步骤](configure-dynamic-emergency-calling.md) 来：</span><span class="sxs-lookup"><span data-stu-id="ec27e-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="ec27e-144">分配紧急地址</span><span class="sxs-lookup"><span data-stu-id="ec27e-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="ec27e-145">配置网络设置</span><span class="sxs-lookup"><span data-stu-id="ec27e-145">Configure network settings</span></span> 

- <span data-ttu-id="ec27e-146">配置位置信息服务</span><span class="sxs-lookup"><span data-stu-id="ec27e-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="ec27e-147">配置紧急策略</span><span class="sxs-lookup"><span data-stu-id="ec27e-147">Configure emergency policies</span></span> 

- <span data-ttu-id="ec27e-148">启用用户和网站</span><span class="sxs-lookup"><span data-stu-id="ec27e-148">Enable users and sites</span></span> 

- <span data-ttu-id="ec27e-149">测试紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="ec27e-149">Test emergency calling</span></span> 

<span data-ttu-id="ec27e-150">配置动态紧急呼叫后，Contoso 需要将位置分配给相应的用户。</span><span class="sxs-lookup"><span data-stu-id="ec27e-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="ec27e-151">若要为组织添加、更改或删除紧急位置，Contoso 按照为组织添加、更改或删除紧急位置中的 [步骤操作](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="ec27e-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="ec27e-152">为了创建建筑物、楼层和办公室的位置，Contoso 按照添加、更改或删除紧急位置 [中的步骤操作](add-change-remove-emergency-place-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="ec27e-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="ec27e-153">为了分配紧急位置，Contoso 按照为用户分配或更改紧急 [位置中的步骤操作](assign-change-emergency-location-user.md)。</span><span class="sxs-lookup"><span data-stu-id="ec27e-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 