---
title: 配置动态紧急呼叫
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft 通话计划和电话系统直接路由动态紧急呼叫功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06153eccd343ef8731af38ff4e3b45cea334fcb2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031008"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="67088-103">规划和配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="67088-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="67088-104">Microsoft 通话计划和电话系统直接路由的动态紧急呼叫提供了配置和路由紧急呼叫的功能，并根据团队客户的当前位置通知安全人员。</span><span class="sxs-lookup"><span data-stu-id="67088-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="67088-105">根据租户管理员定义的网络拓扑，团队客户端在 (.LIS) 位置的位置信息服务请求中提供网络连接信息。</span><span class="sxs-lookup"><span data-stu-id="67088-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span> <span data-ttu-id="67088-106">如果存在匹配项，则 IIS 将向客户端返回一个位置。</span><span class="sxs-lookup"><span data-stu-id="67088-106">If there's a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="67088-107">此位置数据将传回客户端。</span><span class="sxs-lookup"><span data-stu-id="67088-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="67088-108">团队客户端包括作为紧急呼叫的一部分的位置数据。</span><span class="sxs-lookup"><span data-stu-id="67088-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="67088-109">这些数据随后由紧急服务提供商用于确定相应的公共安全应答点 (PSAP) 并将呼叫路由到该 PSAP，从而允许 PSAP dispatcher 获取呼叫者的位置。</span><span class="sxs-lookup"><span data-stu-id="67088-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="67088-110">对于动态紧急呼叫，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="67088-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="67088-111">网络管理员配置网络设置和 .LIS 以创建网络/紧急位置映射。</span><span class="sxs-lookup"><span data-stu-id="67088-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="67088-112">对于直接路由，需要进行额外的配置来路由紧急呼叫，并且可能需要进行合作伙伴连接。</span><span class="sxs-lookup"><span data-stu-id="67088-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="67088-113">管理员必须将连接配置为紧急路由服务 (ERS) 提供商 (美国) **或** 为紧急位置标识号 (ELIN) 应用程序配置会话边界控制器 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="67088-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="67088-114">在启动和以后定期，或者当网络连接更改时，团队客户端会将包含其网络连接信息的位置请求发送到网络设置和 .LIS。</span><span class="sxs-lookup"><span data-stu-id="67088-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="67088-115">如果存在网络设置网站匹配项，则会将紧急呼叫策略从该网站返回到团队客户端。</span><span class="sxs-lookup"><span data-stu-id="67088-115">If there's a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="67088-116"> (有关策略的详细信息，请参阅 [配置紧急策略](#configure-emergency-policies)) 。</span><span class="sxs-lookup"><span data-stu-id="67088-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="67088-117">如果存在一个 .LIS 匹配项-来自团队客户端连接到的网络元素的紧急位置将返回到团队客户端。</span><span class="sxs-lookup"><span data-stu-id="67088-117">If there's an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span> <span data-ttu-id="67088-118">按以下顺序执行匹配，并返回第一个匹配的结果：</span><span class="sxs-lookup"><span data-stu-id="67088-118">The match is performed in the following order with the first matched result being returned:</span></span>
       - <span data-ttu-id="67088-119">WAP</span><span class="sxs-lookup"><span data-stu-id="67088-119">WAP</span></span>
       - <span data-ttu-id="67088-120">以太网交换机/端口</span><span class="sxs-lookup"><span data-stu-id="67088-120">Ethernet switch/port</span></span>
       - <span data-ttu-id="67088-121">以太网交换机</span><span class="sxs-lookup"><span data-stu-id="67088-121">Ethernet switch</span></span>
       - <span data-ttu-id="67088-122">子网</span><span class="sxs-lookup"><span data-stu-id="67088-122">Subnet</span></span>

3. <span data-ttu-id="67088-123">当团队客户端进行紧急呼叫时，会将紧急位置传达给 PSTN 网络。</span><span class="sxs-lookup"><span data-stu-id="67088-123">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="67088-124">对于直接路由，管理员必须将 SBC 配置为向 ERS 提供商发送紧急呼叫或配置 SBC ELIN 应用程序。</span><span class="sxs-lookup"><span data-stu-id="67088-124">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="67088-125">本文包含以下部分。</span><span class="sxs-lookup"><span data-stu-id="67088-125">This article contains the following sections.</span></span>

- [<span data-ttu-id="67088-126">配置紧急地址</span><span class="sxs-lookup"><span data-stu-id="67088-126">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="67088-127">配置网络设置</span><span class="sxs-lookup"><span data-stu-id="67088-127">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="67088-128">配置位置信息服务</span><span class="sxs-lookup"><span data-stu-id="67088-128">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="67088-129">配置紧急策略</span><span class="sxs-lookup"><span data-stu-id="67088-129">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="67088-130">启用用户和网站</span><span class="sxs-lookup"><span data-stu-id="67088-130">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="67088-131">测试紧急电话</span><span class="sxs-lookup"><span data-stu-id="67088-131">Test emergency calling</span></span>](#test-emergency-calling)

<span data-ttu-id="67088-132">自动路由到相应的公共安全应答点的能力 (PSAP) 根据团队用户的使用情况的不同而有所不同。</span><span class="sxs-lookup"><span data-stu-id="67088-132">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span>

<span data-ttu-id="67088-133">有关紧急呼叫的详细信息，包括有关紧急地址和紧急呼叫路由的信息、特定于国家/地区的信息以及有关网络设置和网络拓扑的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="67088-133">For more information about emergency calling, including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology, see the following:</span></span>

- [<span data-ttu-id="67088-134">管理紧急电话</span><span class="sxs-lookup"><span data-stu-id="67088-134">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="67088-135">管理云语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="67088-135">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="67088-136">管理云语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="67088-136">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)

## <a name="supported-clients"></a><span data-ttu-id="67088-137">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="67088-137">Supported clients</span></span>

<span data-ttu-id="67088-138">目前支持下列客户端。</span><span class="sxs-lookup"><span data-stu-id="67088-138">The following clients are currently supported.</span></span>  <span data-ttu-id="67088-139">经常回来查看此列表的更新。</span><span class="sxs-lookup"><span data-stu-id="67088-139">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="67088-140">适用于 Microsoft Windows 的团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="67088-140">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="67088-141">Apple macOS 的团队桌面客户端</span><span class="sxs-lookup"><span data-stu-id="67088-141">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="67088-142">Apple iOS 客户端版本1.0.92.2019121004 和应用商店版本1.0.92 及更高版本的团队移动客户端</span><span class="sxs-lookup"><span data-stu-id="67088-142">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="67088-143">适用于 Android 客户端和 Google Play 版的团队移动客户端和 Google Play store 版本 1416/1.0.0.2019121201 及更高</span><span class="sxs-lookup"><span data-stu-id="67088-143">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="67088-144">工作组电话版本 1449/1.0.94.2019110802 及更高版本</span><span class="sxs-lookup"><span data-stu-id="67088-144">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>
- <span data-ttu-id="67088-145">团队聊天室版本4.4.25.0 及更高版本</span><span class="sxs-lookup"><span data-stu-id="67088-145">Teams Rooms version 4.4.25.0 and greater</span></span>

> [!NOTE]
> <span data-ttu-id="67088-146">不支持团队 web 客户端上的动态紧急呼叫（包括安全桌面通知）。</span><span class="sxs-lookup"><span data-stu-id="67088-146">Dynamic emergency calling including security desk notification isn't supported on the Teams web client.</span></span> <span data-ttu-id="67088-147">若要防止用户使用团队 web 客户端调用 PSTN 号码，您可以设置团队呼叫策略并关闭 " **允许 WEB PSTN 呼叫** " 设置。</span><span class="sxs-lookup"><span data-stu-id="67088-147">To prevent users from using the Teams web client to call PSTN numbers, you can set a Teams calling policy and turn off the **Allow web PSTN calling** setting.</span></span> <span data-ttu-id="67088-148">若要了解详细信息，请参阅 [在团队中调用策略](teams-calling-policy.md) 和 [设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="67088-148">To learn more, see [Calling policies in Teams](teams-calling-policy.md) and [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="67088-149">分配紧急地址</span><span class="sxs-lookup"><span data-stu-id="67088-149">Assign emergency addresses</span></span>

<span data-ttu-id="67088-150">你可以将紧急地址分配给呼叫计划用户和动态获取位置所需的网络标识符。</span><span class="sxs-lookup"><span data-stu-id="67088-150">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="67088-151">支持 (子网和 WiFi AP。</span><span class="sxs-lookup"><span data-stu-id="67088-151">(Subnet and WiFi AP are supported.</span></span> <span data-ttu-id="67088-152">在 Windows 8.1 和更高版本) 上支持以太网交换机/端口。</span><span class="sxs-lookup"><span data-stu-id="67088-152">Ethernet switch/port is supported on Windows 8.1 and later at this time).</span></span>

<span data-ttu-id="67088-153">若要支持在美国的紧急呼叫自动路由，必须确保分配给网络标识符的紧急位置包括关联的地域代码。</span><span class="sxs-lookup"><span data-stu-id="67088-153">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="67088-154">不能将没有地域代码的紧急地址分配给动态位置所需的网络标识符。 )  (</span><span class="sxs-lookup"><span data-stu-id="67088-154">(Emergency addresses without geo codes can't be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="67088-155">Azure 映射用于基于位置的服务。</span><span class="sxs-lookup"><span data-stu-id="67088-155">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="67088-156">使用 Microsoft 团队管理中心输入紧急地址时，团队会检查该地址的 Azure 映射：</span><span class="sxs-lookup"><span data-stu-id="67088-156">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="67088-157">如果找到匹配项，则自动包括 geo 代码。</span><span class="sxs-lookup"><span data-stu-id="67088-157">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="67088-158">如果找不到匹配项，您将有机会手动创建紧急地址。</span><span class="sxs-lookup"><span data-stu-id="67088-158">If a match isn't found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="67088-159">你可以使用 "固定放置" 功能执行此操作。</span><span class="sxs-lookup"><span data-stu-id="67088-159">You can use the PIN drop feature to do this.</span></span> 

<span data-ttu-id="67088-160">这意味着，如果为分配给呼叫计划用户而创建的现有紧急位置适用于动态位置，则需要重新创建相同的地址以包括 geo 代码。</span><span class="sxs-lookup"><span data-stu-id="67088-160">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="67088-161">若要区分这两个位置，应包含不同的说明。</span><span class="sxs-lookup"><span data-stu-id="67088-161">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="67088-162">新的紧急位置可分配给具有旧位置的用户。</span><span class="sxs-lookup"><span data-stu-id="67088-162">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="67088-163">完全迁移时，可以删除旧位置。</span><span class="sxs-lookup"><span data-stu-id="67088-163">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="67088-164">在 Microsoft 团队管理中心或使用 PowerShell 中添加和分配紧急地址。</span><span class="sxs-lookup"><span data-stu-id="67088-164">You add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="67088-165">有关详细信息，请参阅为 [你的组织添加紧急位置](add-change-remove-emergency-location-organization.md) 和为 [用户分配紧急位置](assign-change-emergency-location-user.md)。</span><span class="sxs-lookup"><span data-stu-id="67088-165">For more information, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for a user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="67088-166">配置网络设置</span><span class="sxs-lookup"><span data-stu-id="67088-166">Configure network settings</span></span>

<span data-ttu-id="67088-167">网络设置用于确定团队客户端的位置，并动态获取紧急呼叫策略和紧急位置。</span><span class="sxs-lookup"><span data-stu-id="67088-167">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="67088-168">您可以根据组织希望的紧急呼叫功能来配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="67088-168">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="67088-169">网络设置包括包含子网集合的网站，这些网站专门用于向用户分配动态策略。</span><span class="sxs-lookup"><span data-stu-id="67088-169">Network settings include sites that include a collection of subnets and these are used exclusively for dynamic policy assignment to users.</span></span> <span data-ttu-id="67088-170">例如，紧急呼叫策略和紧急呼叫路由策略可能会分配给 "雷德蒙" 网站，以便从家里或其他 Microsoft 位置漫游的任何用户都使用特定于 Redmond 的紧急号码、路线和安全桌面进行配置。</span><span class="sxs-lookup"><span data-stu-id="67088-170">For example, an emergency calling policy and an emergency call routing policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="67088-171">子网也可以在 .LIS 中定义，并且可以与紧急位置相关联。</span><span class="sxs-lookup"><span data-stu-id="67088-171">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="67088-172">请记住以下定义。</span><span class="sxs-lookup"><span data-stu-id="67088-172">Keep the following definitions in mind.</span></span> <span data-ttu-id="67088-173">有关详细信息，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="67088-173">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

- <span data-ttu-id="67088-174">"受信任的 IP 地址" 包含企业网络的 internet 外部 IP 地址的集合，用于确定用户的终结点是否位于企业网络内。</span><span class="sxs-lookup"><span data-stu-id="67088-174">Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="67088-175">仅当用户的外部 IP 地址与受信任的 IP 地址中的 IP 地址匹配时，才会尝试获取动态策略或位置。</span><span class="sxs-lookup"><span data-stu-id="67088-175">An attempt to obtain a dynamic policy or location will only be made if the user's external IP address matches an IP address in the trusted IP address.</span></span> <span data-ttu-id="67088-176">可以针对 IPv4 或 IPv6 IP 地址进行匹配，取决于发送到网络设置的 IP 数据包的格式。</span><span class="sxs-lookup"><span data-stu-id="67088-176">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="67088-177"> (如果公共 IP 地址同时具有 IPv4 和 IPv6，则需要将两者都添加为受信任的 IP 地址。 ) </span><span class="sxs-lookup"><span data-stu-id="67088-177">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="67088-178">网络区域包含网络站点的集合。</span><span class="sxs-lookup"><span data-stu-id="67088-178">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="67088-179">网络站点表示您的组织具有物理价值（如办公室、一组建筑物或校园）的位置。</span><span class="sxs-lookup"><span data-stu-id="67088-179">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="67088-180">这些网站定义为 IP 子网的集合。</span><span class="sxs-lookup"><span data-stu-id="67088-180">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="67088-181">网络子网必须与特定的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="67088-181">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="67088-182">根据网络子网和关联的网络站点确定客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="67088-182">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="67088-183">在 Microsoft 团队管理中心或通过使用 PowerShell 配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="67088-183">You configure network settings in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="67088-184">若要了解详细信息，请参阅 [管理云语音功能的网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="67088-184">To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="67088-185">请注意，可能需要一段时间 (几个小时，) 对网络设置的某些更改 (如新地址、网络标识符等) 传播并供团队客户端使用。</span><span class="sxs-lookup"><span data-stu-id="67088-185">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="67088-186">**对于呼叫计划用户：**</span><span class="sxs-lookup"><span data-stu-id="67088-186">**For Calling Plan users:**</span></span>

- <span data-ttu-id="67088-187">如果需要对 security 办公桌通知进行动态配置，则必须同时配置受信任的 IP 地址和网络站点。</span><span class="sxs-lookup"><span data-stu-id="67088-187">If dynamic configuration of security desk notification is required, you must configure both trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="67088-188">如果仅需要动态位置，则必须仅配置受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="67088-188">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="67088-189">如果两者都不是必需的，则不需要配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="67088-189">If neither are required, configuring network settings isn't required.</span></span> 

<span data-ttu-id="67088-190">**对于直接路由用户：**</span><span class="sxs-lookup"><span data-stu-id="67088-190">**For Direct Routing users:**</span></span>

- <span data-ttu-id="67088-191">如果需要动态启用紧急呼叫或安全桌面通知的动态配置，则必须同时配置受信任的 IP 地址和网络站点。</span><span class="sxs-lookup"><span data-stu-id="67088-191">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="67088-192">如果仅需要动态位置，则必须仅配置受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="67088-192">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="67088-193">如果两者都不是必需的，则不需要配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="67088-193">If neither are required, configuring network settings isn't required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="67088-194">配置位置信息服务</span><span class="sxs-lookup"><span data-stu-id="67088-194">Configure Location Information Service</span></span>

<span data-ttu-id="67088-195">团队客户端从与不同网络标识符关联的位置获取紧急地址。</span><span class="sxs-lookup"><span data-stu-id="67088-195">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="67088-196">子网和无线访问点 (WAPs) 均受支持。</span><span class="sxs-lookup"><span data-stu-id="67088-196">Both subnets and wireless access points (WAPs) are supported.</span></span> <span data-ttu-id="67088-197">目前在 Windows 8.1 和更高版本上支持以太网交换机/端口。</span><span class="sxs-lookup"><span data-stu-id="67088-197">Ethernet switch/port is supported on Windows 8.1 and later at this time.</span></span>

<span data-ttu-id="67088-198">若要获取某个位置的客户端，你必须使用网络标识符（ (子网、WAPs、交换机、端口) 和紧急位置）填充 IIS。</span><span class="sxs-lookup"><span data-stu-id="67088-198">For a client to obtain a location, you must populate the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations.</span></span> <span data-ttu-id="67088-199">可以在 Microsoft 团队管理中心或使用 PowerShell 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="67088-199">You can do this in the Microsoft Teams admin center or by using PowerShell.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="67088-200">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="67088-200">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="67088-201">在左侧导航中，转到 " **位置**  >  **网络" & 位置** 。</span><span class="sxs-lookup"><span data-stu-id="67088-201">In the left navigation, go to **Locations** > **Networks & locations**.</span></span>
2. <span data-ttu-id="67088-202">单击表示要添加的网络标识符的选项卡。</span><span class="sxs-lookup"><span data-stu-id="67088-202">Click the tab that represents the network identifier that you want to add.</span></span> <span data-ttu-id="67088-203">例如，单击 " **子网** "、" **wi-fi 访问点** "、" **交换机** " 或 " **端口** "。</span><span class="sxs-lookup"><span data-stu-id="67088-203">For example, click **Subnets** , **Wi-Fi access points** , **Switches** , or **Ports**.</span></span> <span data-ttu-id="67088-204">然后单击 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="67088-204">Then click **Add**.</span></span>
3. <span data-ttu-id="67088-205">填写字段，添加紧急位置，然后单击 " **应用** "。</span><span class="sxs-lookup"><span data-stu-id="67088-205">Complete the fields, add an emergency location, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="67088-206">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="67088-206">Using PowerShell</span></span>

<span data-ttu-id="67088-207">使用以下 cmdlet 将端口、开关、子网和 WAPs 添加到 .LIS。</span><span class="sxs-lookup"><span data-stu-id="67088-207">Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.</span></span>

- <span data-ttu-id="67088-208">[获取](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [设置](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [删除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="67088-208">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="67088-209">[获取](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [设置](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [删除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="67088-209">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="67088-210">[获取](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [设置](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [删除](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="67088-210">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span></span>
- <span data-ttu-id="67088-211">[获取](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [设置](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [删除](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="67088-211">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>

>[!Important]
><span data-ttu-id="67088-212">如果子网用作网络站点的一部分，则必须在位置信息服务中重新定义它们以呈现动态位置。</span><span class="sxs-lookup"><span data-stu-id="67088-212">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>

## <a name="configure-emergency-policies"></a><span data-ttu-id="67088-213">配置紧急策略</span><span class="sxs-lookup"><span data-stu-id="67088-213">Configure emergency policies</span></span>

<span data-ttu-id="67088-214">使用以下策略配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="67088-214">Use the following policies to configure emergency calling.</span></span> <span data-ttu-id="67088-215">你可以在 Microsoft 团队管理中心或通过使用 PowerShell 管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="67088-215">You can manage these policies in the Microsoft Teams admin center or by using PowerShell.</span></span>

- <span data-ttu-id="67088-216">**紧急呼叫路由策略** -仅适用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="67088-216">**Emergency call routing policy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="67088-217">此政策配置紧急号码、每个号码的掩码（如果需要），以及每个号码的 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="67088-217">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="67088-218">你可以将此策略分配给用户和/或网络站点。</span><span class="sxs-lookup"><span data-stu-id="67088-218">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="67088-219"> (通话计划团队客户将使用基于其 Microsoft 365 或 Office 365 使用位置的紧急电话自动启用紧急呼叫。 ) 了解详细信息，请参阅 [管理直接路由的紧急呼叫路由策略](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="67088-219">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Microsoft 365 or Office 365 usage location.)  To  learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>

- <span data-ttu-id="67088-220">**紧急呼叫政策** -适用于通话计划和直接路由。</span><span class="sxs-lookup"><span data-stu-id="67088-220">**Emergency calling policy** - Applies to Calling Plans and Direct Routing.</span></span> <span data-ttu-id="67088-221">此策略配置在进行紧急呼叫时的安全桌面通知体验。</span><span class="sxs-lookup"><span data-stu-id="67088-221">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="67088-222">可以设置要通知的人员以及通知的方式。</span><span class="sxs-lookup"><span data-stu-id="67088-222">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="67088-223">例如，自动通知组织的安全桌面并让他们在紧急电话上侦听。</span><span class="sxs-lookup"><span data-stu-id="67088-223">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="67088-224">此策略既可以分配给用户，也可以同时分配给用户或网络站点。</span><span class="sxs-lookup"><span data-stu-id="67088-224">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="67088-225">若要了解详细信息，请参阅 [管理团队中的紧急呼叫策略](manage-emergency-calling-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="67088-225">To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>

## <a name="enable-users-and-sites"></a><span data-ttu-id="67088-226">启用用户和网站</span><span class="sxs-lookup"><span data-stu-id="67088-226">Enable users and sites</span></span>

<span data-ttu-id="67088-227">您可以为用户和网站分配紧急呼叫路由策略和紧急呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="67088-227">You can assign emergency call routing policies and emergency calling policies to users and to sites.</span></span> <span data-ttu-id="67088-228">请记住，紧急呼叫路由策略仅适用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="67088-228">Keep in mind that emergency call routing policies apply to Direct Routing only.</span></span> <span data-ttu-id="67088-229"> (尽管可以将此策略分配给通话计划用户，但该策略不会有任何影响。 ) </span><span class="sxs-lookup"><span data-stu-id="67088-229">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="67088-230">在 Microsoft 团队管理中心或通过使用 PowerShell 分配策略。</span><span class="sxs-lookup"><span data-stu-id="67088-230">You assign policies in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="67088-231">要了解详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="67088-231">To learn more, see:</span></span>

- [<span data-ttu-id="67088-232">管理直接路由的紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="67088-232">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="67088-233">管理团队中的紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="67088-233">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

<span data-ttu-id="67088-234">下面是一些 PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="67088-234">Here's some PowerShell examples.</span></span>

<span data-ttu-id="67088-235">若要为安全桌面通知启用特定用户，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="67088-235">To enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="67088-236">若要将名为 "Contoso 紧急呼叫策略 1" 的策略分配给站点1，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="67088-236">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="67088-237">若要启用特定直接路由用户进行紧急呼叫，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="67088-237">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="67088-238">若要将名为 "Contoso 纽约紧急呼叫路由" 的策略分配给站点1，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="67088-238">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="67088-239">如果你为网络网站和用户分配了紧急呼叫策略，并且如果该用户位于该网络站点，则分配给网络网站的策略将覆盖分配给该用户的策略。</span><span class="sxs-lookup"><span data-stu-id="67088-239">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="test-emergency-calling"></a><span data-ttu-id="67088-240">测试紧急电话</span><span class="sxs-lookup"><span data-stu-id="67088-240">Test emergency calling</span></span>

<span data-ttu-id="67088-241">某些紧急路线服务提供商 (ERSPs) 在美国提供紧急呼叫测试机器人。</span><span class="sxs-lookup"><span data-stu-id="67088-241">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="67088-242">**美国的通话计划用户** 可以使用预定义的测试紧急号码933验证紧急呼叫配置。</span><span class="sxs-lookup"><span data-stu-id="67088-242">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="67088-243">此号码将路由到一个 bot，然后将回显呼叫者电话号码 (呼叫线路 ID) 、紧急地址或位置，以及是否会首先自动将呼叫路由到 PSAP 或筛选。</span><span class="sxs-lookup"><span data-stu-id="67088-243">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="67088-244">**美国直接路由客户** 应与他们的 ERSP 进行测试服务协调。</span><span class="sxs-lookup"><span data-stu-id="67088-244">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="67088-245">相关主题</span><span class="sxs-lookup"><span data-stu-id="67088-245">Related topics</span></span>

- [<span data-ttu-id="67088-246">管理紧急电话</span><span class="sxs-lookup"><span data-stu-id="67088-246">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="67088-247">管理紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="67088-247">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="67088-248">管理紧急呼叫路由策略 </span><span class="sxs-lookup"><span data-stu-id="67088-248">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="67088-249">为你的组织添加、更改或删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="67088-249">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="67088-250">为用户分配或更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="67088-250">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="67088-251">云语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="67088-251">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="67088-252">管理云语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="67088-252">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
