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
description: 了解如何配置 Microsoft 呼叫计划和电话系统直接路由动态紧急呼叫功能。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 73b894b0eb02b8f860a3486251dab002832f4d46
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122326"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="13c69-103">规划和配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="13c69-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="13c69-104">Microsoft 呼叫计划和电话系统直接路由的动态紧急呼叫提供配置和路由紧急呼叫以及根据 Teams 客户端的当前位置通知安全人员的功能。</span><span class="sxs-lookup"><span data-stu-id="13c69-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="13c69-105">根据租户管理员定义的网络拓扑，Teams 客户端在向位置信息服务请求中提供网络连接信息 (LIS) 。</span><span class="sxs-lookup"><span data-stu-id="13c69-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span> <span data-ttu-id="13c69-106">如果存在匹配项，LIS 会向客户端返回一个位置。</span><span class="sxs-lookup"><span data-stu-id="13c69-106">If there's a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="13c69-107">此位置数据将传输回客户端。</span><span class="sxs-lookup"><span data-stu-id="13c69-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="13c69-108">Teams 客户端在紧急呼叫中包括位置数据。</span><span class="sxs-lookup"><span data-stu-id="13c69-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="13c69-109">然后，紧急服务提供机构会使用这些数据来确定适当的公共安全应答点 (PSAP) ，然后将呼叫路由到该 PSAP，以便 PSAP 调度程序获取调用方的位置。</span><span class="sxs-lookup"><span data-stu-id="13c69-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="13c69-110">对于动态紧急呼叫，必须发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="13c69-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="13c69-111">网络管理员配置网络设置和 LIS 以创建网络/紧急位置地图。</span><span class="sxs-lookup"><span data-stu-id="13c69-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="13c69-112">对于直接路由，路由紧急呼叫可能需要其他配置，并且合作伙伴连接可能需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="13c69-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="13c69-113">管理员必须配置与紧急路由服务 (ERS) 提供商 (美国) **的连接，或者** 为紧急位置标识号 (ELIN) 应用程序配置会话边界控制器 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="13c69-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="13c69-114">在启动期间和之后定期，或者当网络连接发生更改时，Teams 客户端会向网络设置和 LIS 发送包含其网络连接信息的位置请求。</span><span class="sxs-lookup"><span data-stu-id="13c69-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="13c69-115">如果存在网络设置站点匹配 ，则紧急呼叫策略会从该网站返回到 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="13c69-115">If there's a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="13c69-116"> (有关策略详细信息，请参阅配置 [紧急](#configure-emergency-policies)) 。</span><span class="sxs-lookup"><span data-stu-id="13c69-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="13c69-117">如果存在 LIS 匹配，Teams 客户端连接到的网络元素中的紧急位置将返回到 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="13c69-117">If there's an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span> <span data-ttu-id="13c69-118">按以下顺序执行匹配，并返回第一个匹配的结果：</span><span class="sxs-lookup"><span data-stu-id="13c69-118">The match is performed in the following order with the first matched result being returned:</span></span>
       - <span data-ttu-id="13c69-119">WAP</span><span class="sxs-lookup"><span data-stu-id="13c69-119">WAP</span></span>
       - <span data-ttu-id="13c69-120">以太网交换机/端口</span><span class="sxs-lookup"><span data-stu-id="13c69-120">Ethernet switch/port</span></span>
       - <span data-ttu-id="13c69-121">以太网交换机</span><span class="sxs-lookup"><span data-stu-id="13c69-121">Ethernet switch</span></span>
       - <span data-ttu-id="13c69-122">子网</span><span class="sxs-lookup"><span data-stu-id="13c69-122">Subnet</span></span>

3. <span data-ttu-id="13c69-123">当 Teams 客户端进行紧急呼叫时，紧急位置将传达给 PSTN 网络。</span><span class="sxs-lookup"><span data-stu-id="13c69-123">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="13c69-124">对于直接路由，管理员必须将 SBC 配置为向 ERS 提供程序发送紧急呼叫，或配置 SBC ELIN 应用程序。</span><span class="sxs-lookup"><span data-stu-id="13c69-124">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="13c69-125">本文包含以下部分。</span><span class="sxs-lookup"><span data-stu-id="13c69-125">This article contains the following sections.</span></span>

- [<span data-ttu-id="13c69-126">配置紧急地址</span><span class="sxs-lookup"><span data-stu-id="13c69-126">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="13c69-127">配置网络设置</span><span class="sxs-lookup"><span data-stu-id="13c69-127">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="13c69-128">配置位置信息服务</span><span class="sxs-lookup"><span data-stu-id="13c69-128">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="13c69-129">配置紧急策略</span><span class="sxs-lookup"><span data-stu-id="13c69-129">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="13c69-130">启用用户和网站</span><span class="sxs-lookup"><span data-stu-id="13c69-130">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="13c69-131">测试紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="13c69-131">Test emergency calling</span></span>](#test-emergency-calling)

<span data-ttu-id="13c69-132">PSAP (PSAP) 自动路由的能力因 Teams 用户的使用国家/地区而异。</span><span class="sxs-lookup"><span data-stu-id="13c69-132">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span>

<span data-ttu-id="13c69-133">有关紧急呼叫的信息，包括有关紧急地址和紧急呼叫路由的信息、特定于国家/地区的信息，以及有关网络设置和网络拓扑的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="13c69-133">For more information about emergency calling, including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology, see the following:</span></span>

- [<span data-ttu-id="13c69-134">管理紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="13c69-134">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="13c69-135">管理云语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="13c69-135">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="13c69-136">管理云语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="13c69-136">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)

<span data-ttu-id="13c69-137">有关政府云中可用的功能详细信息 [，请参阅本文](#government-support) 末尾的"政府支持"。</span><span class="sxs-lookup"><span data-stu-id="13c69-137">For more information about which features are available in the government clouds, see [Government support](#government-support) at the end of this article.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="13c69-138">支持的客户端</span><span class="sxs-lookup"><span data-stu-id="13c69-138">Supported clients</span></span>

<span data-ttu-id="13c69-139">目前支持以下客户端。</span><span class="sxs-lookup"><span data-stu-id="13c69-139">The following clients are currently supported.</span></span>  <span data-ttu-id="13c69-140">请经常返回查看此列表的更新。</span><span class="sxs-lookup"><span data-stu-id="13c69-140">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="13c69-141">适用于 Microsoft Windows 的 Teams 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="13c69-141">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="13c69-142">适用于 Apple macOS 的 Teams 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="13c69-142">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="13c69-143">适用于 Apple iOS 客户端版本 1.0.92.2019121004 和 App Store 1.0.92 及更高的 Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="13c69-143">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="13c69-144">Android 客户端和 Google Play 应用商店版本 1416/1.0.0.2019121201 及更高的 Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="13c69-144">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="13c69-145">Teams 手机版本 1449/1.0.94.2019110802 及更高</span><span class="sxs-lookup"><span data-stu-id="13c69-145">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>
- <span data-ttu-id="13c69-146">Teams 会议室版本 4.4.25.0 及更高</span><span class="sxs-lookup"><span data-stu-id="13c69-146">Teams Rooms version 4.4.25.0 and greater</span></span>

> [!NOTE]
> <span data-ttu-id="13c69-147">Teams Web 客户端不支持动态紧急呼叫，包括安全服务台通知。</span><span class="sxs-lookup"><span data-stu-id="13c69-147">Dynamic emergency calling including security desk notification isn't supported on the Teams web client.</span></span> <span data-ttu-id="13c69-148">若要防止用户使用 Teams Web 客户端呼叫 PSTN 号码，可以设置 Teams 呼叫策略并关闭"允许 **Web PSTN 呼叫"** 设置。</span><span class="sxs-lookup"><span data-stu-id="13c69-148">To prevent users from using the Teams web client to call PSTN numbers, you can set a Teams calling policy and turn off the **Allow web PSTN calling** setting.</span></span> <span data-ttu-id="13c69-149">有关详细信息，请参阅在[Teams 中调用策略](teams-calling-policy.md)和[Set-CsTeamsCallingPolicy。](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="13c69-149">To learn more, see [Calling policies in Teams](teams-calling-policy.md) and [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="13c69-150">分配紧急地址</span><span class="sxs-lookup"><span data-stu-id="13c69-150">Assign emergency addresses</span></span>

<span data-ttu-id="13c69-151">可以将紧急地址分配给呼叫计划用户以及动态获取位置所需的网络标识符。</span><span class="sxs-lookup"><span data-stu-id="13c69-151">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="13c69-152"> (子网和 WiFi AP。</span><span class="sxs-lookup"><span data-stu-id="13c69-152">(Subnet and WiFi AP are supported.</span></span> <span data-ttu-id="13c69-153">Windows 8.1 和更高版本目前支持以太网交换机/) 。</span><span class="sxs-lookup"><span data-stu-id="13c69-153">Ethernet switch/port is supported on Windows 8.1 and later at this time).</span></span>

<span data-ttu-id="13c69-154">若要支持美国境内紧急呼叫的自动路由，必须确保分配给网络标识符的紧急位置包含关联的地理代码。</span><span class="sxs-lookup"><span data-stu-id="13c69-154">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="13c69-155"> (没有地理代码的紧急地址不能分配给动态位置.) </span><span class="sxs-lookup"><span data-stu-id="13c69-155">(Emergency addresses without geo codes can't be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="13c69-156">Azure Maps 用于基于位置的服务。</span><span class="sxs-lookup"><span data-stu-id="13c69-156">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="13c69-157">使用 Microsoft Teams 管理中心输入紧急地址时，Teams 会检查 Azure Maps 中的地址：</span><span class="sxs-lookup"><span data-stu-id="13c69-157">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="13c69-158">如果找到匹配项，则会自动包含地理代码。</span><span class="sxs-lookup"><span data-stu-id="13c69-158">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="13c69-159">如果未找到匹配项，你将有机会手动创建紧急地址。</span><span class="sxs-lookup"><span data-stu-id="13c69-159">If a match isn't found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="13c69-160">可以使用 PIN 拖放功能来这样做。</span><span class="sxs-lookup"><span data-stu-id="13c69-160">You can use the PIN drop feature to do this.</span></span> 

<span data-ttu-id="13c69-161">这意味着，如果为分配给呼叫计划用户而创建的现有紧急位置适用于动态位置，需要重新创建相同的地址以包含地理代码。</span><span class="sxs-lookup"><span data-stu-id="13c69-161">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="13c69-162">若要区分这两个位置，应包含不同的说明。</span><span class="sxs-lookup"><span data-stu-id="13c69-162">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="13c69-163">可以将新的紧急位置分配给具有旧位置的用户。</span><span class="sxs-lookup"><span data-stu-id="13c69-163">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="13c69-164">完全迁移后，可以删除旧位置。</span><span class="sxs-lookup"><span data-stu-id="13c69-164">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="13c69-165">在 Microsoft Teams 管理中心或通过使用 PowerShell 添加和分配紧急地址。</span><span class="sxs-lookup"><span data-stu-id="13c69-165">You add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="13c69-166">有关详细信息，请参阅 [为组织添加紧急](add-change-remove-emergency-location-organization.md) 位置和 [为用户分配紧急位置](assign-change-emergency-location-user.md)。</span><span class="sxs-lookup"><span data-stu-id="13c69-166">For more information, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for a user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="13c69-167">配置网络设置</span><span class="sxs-lookup"><span data-stu-id="13c69-167">Configure network settings</span></span>

<span data-ttu-id="13c69-168">网络设置用于确定 Teams 客户端的位置，以及动态获取紧急呼叫策略和紧急位置。</span><span class="sxs-lookup"><span data-stu-id="13c69-168">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="13c69-169">你可以根据组织希望紧急呼叫如何工作来配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="13c69-169">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="13c69-170">网络设置包括包含子网集合的站点，这些子网专门用于向用户动态分配策略。</span><span class="sxs-lookup"><span data-stu-id="13c69-170">Network settings include sites that include a collection of subnets and these are used exclusively for dynamic policy assignment to users.</span></span> <span data-ttu-id="13c69-171">例如，紧急呼叫策略和紧急呼叫路由策略可能分配给"雷德蒙德站点"，以便从家里或其他 Microsoft 位置漫游的任何用户都配置了特定于雷德蒙德的紧急号码、路由和安全服务台。</span><span class="sxs-lookup"><span data-stu-id="13c69-171">For example, an emergency calling policy and an emergency call routing policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="13c69-172">子网还可以在 LIS 中定义，并可以与紧急位置相关联。</span><span class="sxs-lookup"><span data-stu-id="13c69-172">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="13c69-173">请记住以下定义。</span><span class="sxs-lookup"><span data-stu-id="13c69-173">Keep the following definitions in mind.</span></span> <span data-ttu-id="13c69-174">有关详细信息，请参阅 [云语音功能的网络设置](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="13c69-174">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

- <span data-ttu-id="13c69-175">受信任的 IP 地址包含企业网络的 Internet 外部 IP 地址的集合，用于确定用户的终结点是否位于企业网络中。</span><span class="sxs-lookup"><span data-stu-id="13c69-175">Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="13c69-176">只有在用户的外部 IP 地址与受信任的 IP 地址中的 IP 地址匹配时，才尝试获取动态策略或位置。</span><span class="sxs-lookup"><span data-stu-id="13c69-176">An attempt to obtain a dynamic policy or location will only be made if the user's external IP address matches an IP address in the trusted IP address.</span></span> <span data-ttu-id="13c69-177">可以针对 IPv4 或 IPv6 IP 地址进行匹配，并且取决于发送到网络设置的 IP 数据包的格式。</span><span class="sxs-lookup"><span data-stu-id="13c69-177">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="13c69-178"> (如果公共 IP 地址同时具有 IPv4 和 IPv6，则需要将两者添加为受信任的 IP 地址.) </span><span class="sxs-lookup"><span data-stu-id="13c69-178">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="13c69-179">网络区域包含网络站点的集合。</span><span class="sxs-lookup"><span data-stu-id="13c69-179">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="13c69-180">网络网站表示组织具有物理值的位置，例如办公室、一组建筑物或校园。</span><span class="sxs-lookup"><span data-stu-id="13c69-180">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="13c69-181">这些站点定义为 IP 子网的集合。</span><span class="sxs-lookup"><span data-stu-id="13c69-181">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="13c69-182">网络子网必须与特定网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="13c69-182">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="13c69-183">根据网络子网和关联的网络站点确定客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="13c69-183">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="13c69-184">在 Microsoft Teams 管理中心或 PowerShell 中配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="13c69-184">You configure network settings in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="13c69-185">有关详细信息，请参阅 [管理云语音功能的网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="13c69-185">To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="13c69-186">请注意，可能需要一些时间 () 才能对网络设置进行一些更改 (例如新地址、网络标识符等) 才能传播并可供 Teams 客户端使用。</span><span class="sxs-lookup"><span data-stu-id="13c69-186">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="13c69-187">**对于调用计划用户：**</span><span class="sxs-lookup"><span data-stu-id="13c69-187">**For Calling Plan users:**</span></span>

- <span data-ttu-id="13c69-188">如果需要动态配置安全服务台通知，则必须同时配置受信任的 IP 地址和网络站点。</span><span class="sxs-lookup"><span data-stu-id="13c69-188">If dynamic configuration of security desk notification is required, you must configure both trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="13c69-189">如果只需要动态位置，则必须仅配置受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="13c69-189">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="13c69-190">如果两者都不需要，则不需要配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="13c69-190">If neither are required, configuring network settings isn't required.</span></span> 

<span data-ttu-id="13c69-191">**对于直接路由用户：**</span><span class="sxs-lookup"><span data-stu-id="13c69-191">**For Direct Routing users:**</span></span>

- <span data-ttu-id="13c69-192">如果需要动态启用紧急呼叫或安全服务台通知的动态配置，则必须同时配置受信任的 IP 地址和网络站点。</span><span class="sxs-lookup"><span data-stu-id="13c69-192">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="13c69-193">如果只需要动态位置，则必须仅配置受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="13c69-193">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="13c69-194">如果两者都不需要，则不需要配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="13c69-194">If neither are required, configuring network settings isn't required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="13c69-195">配置位置信息服务</span><span class="sxs-lookup"><span data-stu-id="13c69-195">Configure Location Information Service</span></span>

<span data-ttu-id="13c69-196">Teams 客户端从与不同网络标识符关联的位置获取紧急地址。</span><span class="sxs-lookup"><span data-stu-id="13c69-196">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="13c69-197">支持子网和无线接入点 () WAN。</span><span class="sxs-lookup"><span data-stu-id="13c69-197">Both subnets and wireless access points (WAPs) are supported.</span></span> <span data-ttu-id="13c69-198">Windows 8.1 和更高版本目前支持以太网交换机/端口。</span><span class="sxs-lookup"><span data-stu-id="13c69-198">Ethernet switch/port is supported on Windows 8.1 and later at this time.</span></span>

<span data-ttu-id="13c69-199">若要让客户端获取位置，必须使用子网、 (、交换机、端口和紧急位置的网络标识符) LIS。</span><span class="sxs-lookup"><span data-stu-id="13c69-199">For a client to obtain a location, you must populate the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations.</span></span> <span data-ttu-id="13c69-200">可以在 Microsoft Teams 管理中心或 PowerShell 中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="13c69-200">You can do this in the Microsoft Teams admin center or by using PowerShell.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="13c69-201">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="13c69-201">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="13c69-202">在左侧导航栏中，转到 **"位置**  >  **""网络&位置"。**</span><span class="sxs-lookup"><span data-stu-id="13c69-202">In the left navigation, go to **Locations** > **Networks & locations**.</span></span>
2. <span data-ttu-id="13c69-203">单击表示要添加的网络标识符的选项卡。</span><span class="sxs-lookup"><span data-stu-id="13c69-203">Click the tab that represents the network identifier that you want to add.</span></span> <span data-ttu-id="13c69-204">例如，单击 **"子网\*\*\*\*、Wi-Fi 接入点**、交换机"或"**端口"。**</span><span class="sxs-lookup"><span data-stu-id="13c69-204">For example, click **Subnets**, **Wi-Fi access points**, **Switches**, or **Ports**.</span></span> <span data-ttu-id="13c69-205">然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="13c69-205">Then click **Add**.</span></span>
3. <span data-ttu-id="13c69-206">填写字段，添加紧急位置，然后单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="13c69-206">Complete the fields, add an emergency location, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="13c69-207">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="13c69-207">Using PowerShell</span></span>

<span data-ttu-id="13c69-208">使用以下 cmdlet 将端口、交换机、子网和 WAP 添加到 LIS。</span><span class="sxs-lookup"><span data-stu-id="13c69-208">Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.</span></span>

- <span data-ttu-id="13c69-209">[获取](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="13c69-209">[Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="13c69-210">[获取](/powershell/module/skype/get-csonlinelisport?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlinelisport?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="13c69-210">[Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="13c69-211">[获取](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="13c69-211">[Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span></span>
- <span data-ttu-id="13c69-212">[获取](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps)、 [设置](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps)、 [删除](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="13c69-212">[Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>

>[!Important]
><span data-ttu-id="13c69-213">如果将子网用作网络网站的一部分，则必须在位置信息服务中重新定义子网，以呈现动态位置。</span><span class="sxs-lookup"><span data-stu-id="13c69-213">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>

## <a name="configure-emergency-policies"></a><span data-ttu-id="13c69-214">配置紧急策略</span><span class="sxs-lookup"><span data-stu-id="13c69-214">Configure emergency policies</span></span>

<span data-ttu-id="13c69-215">使用以下策略配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="13c69-215">Use the following policies to configure emergency calling.</span></span> <span data-ttu-id="13c69-216">可以在 Microsoft Teams 管理中心或 PowerShell 中管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="13c69-216">You can manage these policies in the Microsoft Teams admin center or by using PowerShell.</span></span>

- <span data-ttu-id="13c69-217">**紧急呼叫路由策略** - 仅适用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="13c69-217">**Emergency call routing policy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="13c69-218">此策略配置紧急号码、每个号码的掩码（如果需要）和每个号码的 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="13c69-218">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="13c69-219">可以将此策略分配给用户、网络站点或两者。</span><span class="sxs-lookup"><span data-stu-id="13c69-219">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="13c69-220"> (呼叫计划 Teams 客户端基于其 Microsoft 365 或 Office 365 使用位置自动启用紧急呼叫，其紧急号码来自国家/地区。) 若要了解有关详细信息，请参阅管理直接路由的紧急呼叫路由 [策略](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="13c69-220">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Microsoft 365 or Office 365 usage location.)  To  learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>

- <span data-ttu-id="13c69-221">**紧急呼叫策略** - 适用于呼叫计划和直接路由。</span><span class="sxs-lookup"><span data-stu-id="13c69-221">**Emergency calling policy** - Applies to Calling Plans and Direct Routing.</span></span> <span data-ttu-id="13c69-222">此策略配置进行紧急呼叫时的安全服务台通知体验。</span><span class="sxs-lookup"><span data-stu-id="13c69-222">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="13c69-223">可以设置要通知谁以及如何通知他们。</span><span class="sxs-lookup"><span data-stu-id="13c69-223">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="13c69-224">例如，自动通知组织的安全服务台，让他们接听紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="13c69-224">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="13c69-225">可以将此策略分配给用户或网络站点，也可以同时分配给这两者。</span><span class="sxs-lookup"><span data-stu-id="13c69-225">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="13c69-226">有关详细信息，请参阅在 [Teams 中管理紧急呼叫策略](manage-emergency-calling-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="13c69-226">To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>

## <a name="enable-users-and-sites"></a><span data-ttu-id="13c69-227">启用用户和网站</span><span class="sxs-lookup"><span data-stu-id="13c69-227">Enable users and sites</span></span>

<span data-ttu-id="13c69-228">可以将紧急呼叫路由策略和紧急呼叫策略分配给用户和站点。</span><span class="sxs-lookup"><span data-stu-id="13c69-228">You can assign emergency call routing policies and emergency calling policies to users and to sites.</span></span> <span data-ttu-id="13c69-229">请记住，紧急呼叫路由策略仅适用于直接路由。</span><span class="sxs-lookup"><span data-stu-id="13c69-229">Keep in mind that emergency call routing policies apply to Direct Routing only.</span></span> <span data-ttu-id="13c69-230"> (尽管可以将此策略分配给呼叫计划用户，但该策略将不起作用。) </span><span class="sxs-lookup"><span data-stu-id="13c69-230">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="13c69-231">在 Microsoft Teams 管理中心中分配策略，或者使用 PowerShell 分配策略。</span><span class="sxs-lookup"><span data-stu-id="13c69-231">You assign policies in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="13c69-232">若要了解详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="13c69-232">To learn more, see:</span></span>

- [<span data-ttu-id="13c69-233">管理直接路由的紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="13c69-233">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="13c69-234">在 Teams 中管理紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="13c69-234">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

<span data-ttu-id="13c69-235">下面是一些 PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="13c69-235">Here's some PowerShell examples.</span></span>

<span data-ttu-id="13c69-236">若要为安全服务台通知启用特定用户，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="13c69-236">To enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="13c69-237">若要将名为"Contoso 紧急呼叫策略 1"的策略分配到站点 1，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="13c69-237">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="13c69-238">若要为特定的直接路由用户启用紧急呼叫，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="13c69-238">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="13c69-239">若要将名为"Contoso New York 紧急呼叫路由"的策略分配到站点 1，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="13c69-239">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="13c69-240">如果将紧急呼叫策略分配给网络站点和用户，并且该用户位于该网络站点，则分配给网络站点的策略将覆盖分配给用户的策略。</span><span class="sxs-lookup"><span data-stu-id="13c69-240">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="test-emergency-calling"></a><span data-ttu-id="13c69-241">测试紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="13c69-241">Test emergency calling</span></span>

<span data-ttu-id="13c69-242">美国某些紧急路由 (ERSP) 提供紧急呼叫测试机器人。</span><span class="sxs-lookup"><span data-stu-id="13c69-242">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="13c69-243">**美国呼叫计划用户可以使用** 预定义的测试紧急号码 933 来验证其紧急呼叫配置。</span><span class="sxs-lookup"><span data-stu-id="13c69-243">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="13c69-244">此号码将路由到机器人，机器人随后回显呼叫方电话号码 (呼叫线路 ID) 、紧急地址或位置，以及呼叫是自动路由到 PSAP 还是先进行筛选。</span><span class="sxs-lookup"><span data-stu-id="13c69-244">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="13c69-245">**美国直接路由客户应** 协调其 ERSP 以测试服务。</span><span class="sxs-lookup"><span data-stu-id="13c69-245">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

## <a name="government-support"></a><span data-ttu-id="13c69-246">政府支持</span><span class="sxs-lookup"><span data-stu-id="13c69-246">Government support</span></span>

<span data-ttu-id="13c69-247">下表显示了对政府云中的动态紧急呼叫的支持：</span><span class="sxs-lookup"><span data-stu-id="13c69-247">The following table shows support for dynamic emergency calling in the government clouds:</span></span>

| <span data-ttu-id="13c69-248">云</span><span class="sxs-lookup"><span data-stu-id="13c69-248">Cloud</span></span> | <span data-ttu-id="13c69-249">可用性</span><span class="sxs-lookup"><span data-stu-id="13c69-249">Availability</span></span> |
| :------------|:-------|
| <span data-ttu-id="13c69-250">万维多租户</span><span class="sxs-lookup"><span data-stu-id="13c69-250">World Wide Multi Tenant</span></span> | <span data-ttu-id="13c69-251">完全可用</span><span class="sxs-lookup"><span data-stu-id="13c69-251">Fully available</span></span> |
| <span data-ttu-id="13c69-252">GCC</span><span class="sxs-lookup"><span data-stu-id="13c69-252">GCC</span></span> | <span data-ttu-id="13c69-253">除 Teams IP 电话外的所有客户端上均可用</span><span class="sxs-lookup"><span data-stu-id="13c69-253">Available on all clients except Teams IP phones</span></span> |
| <span data-ttu-id="13c69-254">GCCH</span><span class="sxs-lookup"><span data-stu-id="13c69-254">GCCH</span></span> | <span data-ttu-id="13c69-255">Pending</span><span class="sxs-lookup"><span data-stu-id="13c69-255">Pending</span></span> |
| <span data-ttu-id="13c69-256">DoD</span><span class="sxs-lookup"><span data-stu-id="13c69-256">DoD</span></span> | <span data-ttu-id="13c69-257">Pending</span><span class="sxs-lookup"><span data-stu-id="13c69-257">Pending</span></span> |

 ## <a name="related-topics"></a><span data-ttu-id="13c69-258">相关主题</span><span class="sxs-lookup"><span data-stu-id="13c69-258">Related topics</span></span>

- [<span data-ttu-id="13c69-259">管理紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="13c69-259">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="13c69-260">管理紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="13c69-260">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="13c69-261">管理紧急呼叫路由策略 </span><span class="sxs-lookup"><span data-stu-id="13c69-261">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="13c69-262">为你的组织添加、更改或删除紧急位置</span><span class="sxs-lookup"><span data-stu-id="13c69-262">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="13c69-263">为用户分配或更改紧急位置</span><span class="sxs-lookup"><span data-stu-id="13c69-263">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="13c69-264">云语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="13c69-264">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="13c69-265">管理云语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="13c69-265">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)