---
title: 配置动态紧急呼叫
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: 配置动态紧急呼叫
appliesto:
- Microsoft Teams
ms.openlocfilehash: 006f131183fe75b8246f0d2fa2d0ae28575e9e1d
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396466"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="2da32-103">规划和配置通话计划的动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="2da32-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="2da32-104">Microsoft 通话计划的动态紧急呼叫提供根据团队客户端的当前位置配置和路由紧急呼叫的功能。</span><span class="sxs-lookup"><span data-stu-id="2da32-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="2da32-105">自动路由到相应的公共安全应答点（PSAP）或通知安全桌面人员的能力会有所不同，具体取决于团队用户使用的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="2da32-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="2da32-106">动态紧急呼叫目前仅在美国可用。</span><span class="sxs-lookup"><span data-stu-id="2da32-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="2da32-107">但是，安全桌面通知在国家边界内受支持。</span><span class="sxs-lookup"><span data-stu-id="2da32-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="2da32-108">在**美国**，您可以配置动态紧急呼叫路由，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2da32-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="2da32-109">如果团队客户端位于租户定义的动态紧急位置，则来自该客户端的紧急呼叫将自动路由到该地理位置的 PSAP 服务。</span><span class="sxs-lookup"><span data-stu-id="2da32-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="2da32-110">如果团队客户端不在租户定义的动态紧急位置，则来自该客户端的紧急呼叫由全国呼叫中心进行筛选，以便在将呼叫转移到该地理位置的 PSAP 服务之前确定呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="2da32-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="2da32-111">您可以配置安全桌面通知，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2da32-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="2da32-112">如果团队客户端位于租户定义的网络网站上，则为该网站配置的安全组成员将收到通知。</span><span class="sxs-lookup"><span data-stu-id="2da32-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="2da32-113">如果团队客户端不在租户定义的网络网站上，将通知为该用户配置的安全组成员。</span><span class="sxs-lookup"><span data-stu-id="2da32-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="2da32-114">**在美国以外**，紧急电话将被路由到映射到分配给用户的电话号码的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="2da32-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="2da32-115">某些国家/地区（如英国和加拿大）在将呼叫者转移到相应的 PSAP 之前调用国内长途，而其他国家或地区直接路由到 PSAP，无论用户当前位于何处。</span><span class="sxs-lookup"><span data-stu-id="2da32-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="2da32-116">请注意，您可以为所有呼叫计划用户配置动态安全桌面通知。</span><span class="sxs-lookup"><span data-stu-id="2da32-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="2da32-117">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="2da32-117">Supported clients</span></span>

<span data-ttu-id="2da32-118">目前支持下列客户端。</span><span class="sxs-lookup"><span data-stu-id="2da32-118">The following clients are currently supported.</span></span>  <span data-ttu-id="2da32-119">经常回来查看此列表的更新。</span><span class="sxs-lookup"><span data-stu-id="2da32-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="2da32-120">适用于 Windows 的团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="2da32-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="2da32-121">适用于 Mac 的团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="2da32-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="2da32-122">配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="2da32-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="2da32-123">要配置动态紧急呼叫，您需要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2da32-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="2da32-124">配置紧急地址</span><span class="sxs-lookup"><span data-stu-id="2da32-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="2da32-125">配置网络设置</span><span class="sxs-lookup"><span data-stu-id="2da32-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="2da32-126">配置位置信息服务</span><span class="sxs-lookup"><span data-stu-id="2da32-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="2da32-127">配置紧急策略</span><span class="sxs-lookup"><span data-stu-id="2da32-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="2da32-128">启用用户和网站</span><span class="sxs-lookup"><span data-stu-id="2da32-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="2da32-129">测试紧急电话</span><span class="sxs-lookup"><span data-stu-id="2da32-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="2da32-130">配置紧急地址</span><span class="sxs-lookup"><span data-stu-id="2da32-130">Configure emergency addresses</span></span>

<span data-ttu-id="2da32-131">若要支持美国的自动路由，必须完全配置分配给网络标识符的紧急位置部分的市政地址，并包括相关联的地域代码。</span><span class="sxs-lookup"><span data-stu-id="2da32-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="2da32-132">（不能将没有地理代码的紧急地址分配给动态位置所需的网络标识符。）</span><span class="sxs-lookup"><span data-stu-id="2da32-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="2da32-133">如果通过 Microsoft 团队管理中心输入紧急地址，则如果找到匹配项，将自动包含 geo 代码。</span><span class="sxs-lookup"><span data-stu-id="2da32-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="2da32-134">如果未自动找到匹配项，您将有机会手动创建紧急地址。</span><span class="sxs-lookup"><span data-stu-id="2da32-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="2da32-135">这意味着，如果为紧急呼叫配置了现有的紧急地址，则需要重新创建相同的地址以包括 geo 代码。</span><span class="sxs-lookup"><span data-stu-id="2da32-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="2da32-136">若要区分这两个地址，应包含不同的说明。</span><span class="sxs-lookup"><span data-stu-id="2da32-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="2da32-137">新的紧急地址可以分配给具有旧地址的用户。</span><span class="sxs-lookup"><span data-stu-id="2da32-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="2da32-138">完全迁移时，可以删除旧地址。</span><span class="sxs-lookup"><span data-stu-id="2da32-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="2da32-139">有关配置紧急地址的详细信息，请参阅[什么是紧急位置、位置和呼叫路由？](what-are-emergency-locations-addresses-and-call-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="2da32-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="2da32-140">配置网络设置</span><span class="sxs-lookup"><span data-stu-id="2da32-140">Configure network settings</span></span>

<span data-ttu-id="2da32-141">你需要配置网络设置以动态获取用于路由紧急呼叫的紧急位置，还可以选择提供安全桌面通知的动态配置。</span><span class="sxs-lookup"><span data-stu-id="2da32-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="2da32-142">所需的紧急呼叫体验将规定需要配置的网络设置。</span><span class="sxs-lookup"><span data-stu-id="2da32-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="2da32-143">请记住以下定义：</span><span class="sxs-lookup"><span data-stu-id="2da32-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="2da32-144">受信任的 IP 包含企业网络的 Internet 外部 Ip 的集合，用于确定用户的终结点是否位于企业网络内。</span><span class="sxs-lookup"><span data-stu-id="2da32-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="2da32-145">仅当用户的外部 IP 与受信任的 IP 集合中的 IP 匹配时，才会启用动态位置。</span><span class="sxs-lookup"><span data-stu-id="2da32-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="2da32-146">可以针对 IPv4 或 IPv6 IP 地址进行匹配，取决于发送到网络设置的 IP 数据包的格式。</span><span class="sxs-lookup"><span data-stu-id="2da32-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="2da32-147">网络区域包含网络站点的集合。</span><span class="sxs-lookup"><span data-stu-id="2da32-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="2da32-148">网络站点表示您的组织具有物理价值（如办公室、一组建筑物或校园）的位置。</span><span class="sxs-lookup"><span data-stu-id="2da32-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="2da32-149">这些网站定义为 IP 子网的集合。</span><span class="sxs-lookup"><span data-stu-id="2da32-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="2da32-150">网络子网必须与特定的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="2da32-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="2da32-151">根据网络子网和关联的网络站点确定客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="2da32-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="2da32-152">对于呼叫计划用户：</span><span class="sxs-lookup"><span data-stu-id="2da32-152">For Calling Plan users:</span></span>

- <span data-ttu-id="2da32-153">如果需要对 security 办公桌通知进行动态配置，则必须同时配置受信任的 IP 地址和网络站点。</span><span class="sxs-lookup"><span data-stu-id="2da32-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="2da32-154">如果仅需要动态位置，则必须仅配置受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2da32-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="2da32-155">如果两者都不是必需的，则不需要配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="2da32-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="2da32-156">有关详细信息，请参阅[配置基于位置的路由的网络设置](location-based-routing-configure-network-settings.md)，它介绍了如何配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="2da32-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="2da32-157">（本文中的信息既适用于通话计划，也适用于直接路由。）</span><span class="sxs-lookup"><span data-stu-id="2da32-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="2da32-158">配置位置信息服务</span><span class="sxs-lookup"><span data-stu-id="2da32-158">Configure Location Information Service</span></span>

<span data-ttu-id="2da32-159">团队客户端从与不同网络标识符关联的紧急位置获取紧急地址。</span><span class="sxs-lookup"><span data-stu-id="2da32-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="2da32-160">子网和无线访问点均受支持。</span><span class="sxs-lookup"><span data-stu-id="2da32-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="2da32-161">（对以太网交换机/端口的支持已挂起。）</span><span class="sxs-lookup"><span data-stu-id="2da32-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="2da32-162">要使用网络标识符和紧急位置配置位置信息服务（.LIS），请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2da32-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="2da32-163">获取、设置、删除 CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="2da32-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="2da32-164">获取、设置、删除 CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="2da32-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="2da32-165">获取、设置、删除 CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="2da32-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="2da32-166">获取、设置、删除 CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="2da32-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="2da32-167">如果子网用作网络站点的一部分，则必须在位置信息服务中重新定义它们以呈现动态位置。</span><span class="sxs-lookup"><span data-stu-id="2da32-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="2da32-168">配置紧急策略</span><span class="sxs-lookup"><span data-stu-id="2da32-168">Configure emergency policies</span></span>

<span data-ttu-id="2da32-169">紧急策略确定当组织中的用户进行紧急呼叫时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="2da32-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="2da32-170">你可以设置通知人以及当用户呼叫紧急服务时如何通知他们。</span><span class="sxs-lookup"><span data-stu-id="2da32-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="2da32-171">例如，您可以将策略设置配置为自动通知组织的安全桌面，并让他们在紧急电话上侦听。</span><span class="sxs-lookup"><span data-stu-id="2da32-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="2da32-172">你可以使用新的、Set 和 Grant CsTeamsEmergencyCalling 策略 cmdlet 管理紧急策略。</span><span class="sxs-lookup"><span data-stu-id="2da32-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="2da32-173">有关详细信息，请参阅[管理团队中的紧急呼叫策略](manage-emergency-calling-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2da32-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="2da32-174">启用用户和网站</span><span class="sxs-lookup"><span data-stu-id="2da32-174">Enable users and sites</span></span>

<span data-ttu-id="2da32-175">当通话计划用户自动启用紧急呼叫时，您必须通过配置紧急呼叫策略来为用户启用安全桌面通知，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="2da32-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="2da32-176">您也可以将紧急呼叫策略分配给网络站点，如以下示例所示，它将名为 "Contoso 紧急呼叫策略 1" 的策略分配给站点1：</span><span class="sxs-lookup"><span data-stu-id="2da32-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="2da32-177">如果你为网络网站和用户分配了紧急呼叫策略，并且如果该用户位于该网络站点，则分配给网络网站的策略将覆盖分配给该用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2da32-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="2da32-178">测试紧急电话</span><span class="sxs-lookup"><span data-stu-id="2da32-178">Test emergency calling</span></span>

<span data-ttu-id="2da32-179">要测试美国的紧急电话，请使用预定义的测试紧急号码933。</span><span class="sxs-lookup"><span data-stu-id="2da32-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="2da32-180">此号码将路由到 bot，然后回显呼叫者电话号码（呼叫线路 ID）、紧急地址或位置，以及是否首先将呼叫自动路由到 PSAP 或筛选。</span><span class="sxs-lookup"><span data-stu-id="2da32-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  