---
title: 云语音功能的网络设置
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解您必须为直接路由和增强的紧急服务的基于位置的路由配置的网络设置。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bc2694760e93579a78cb849cc054d70a65431724
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139061"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="6a624-103">Microsoft 团队中云语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="6a624-103">Network settings for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="6a624-104">了解网络区域、网络站点、网络子网和受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6a624-104">Learn about network regions, network sites, network subnets, and trusted IP addresses.</span></span> <span data-ttu-id="6a624-105">这些条款和概念在所有云语音文档中用于直接路由和[动态紧急呼叫](configure-dynamic-emergency-calling.md)的[基于位置的路由](location-based-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="6a624-105">These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan.md) and [dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span> <span data-ttu-id="6a624-106">如果你要在你的组织中部署这些云功能，则必须配置用于 Microsoft 团队中的这些功能的网络设置。</span><span class="sxs-lookup"><span data-stu-id="6a624-106">If you're deploying these cloud features in your organization, you must configure network settings for use with these features in Microsoft Teams.</span></span>

<span data-ttu-id="6a624-107">本文简要介绍了基于位置的路由和动态紧急呼叫的常见网络设置。</span><span class="sxs-lookup"><span data-stu-id="6a624-107">This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="6a624-108">你可以配置部分或所有这些设置，具体取决于你部署的云语音功能和功能。</span><span class="sxs-lookup"><span data-stu-id="6a624-108">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="6a624-109">有关如何配置这些设置的步骤，请参阅[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="6a624-109">For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6a624-110">针对网络设置的任何特定于功能的要求将记录在该功能的配置主题中。</span><span class="sxs-lookup"><span data-stu-id="6a624-110">Any feature-specific requirements for network settings are documented in the configuration topics for that feature.</span></span>

## <a name="network-region"></a><span data-ttu-id="6a624-111">网络区域</span><span class="sxs-lookup"><span data-stu-id="6a624-111">Network region</span></span>

<span data-ttu-id="6a624-112">网络区域包含网络站点的集合。</span><span class="sxs-lookup"><span data-stu-id="6a624-112">A network region contains a collection of network sites.</span></span> <span data-ttu-id="6a624-113">它跨多个地理区域互连网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="6a624-113">It interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="6a624-114">例如，如果您的组织具有多个位于印度的网站，您可以选择将 "印度" 指定为网络区域。</span><span class="sxs-lookup"><span data-stu-id="6a624-114">For example, if your organization has many sites located in India, you may choose to designate "India" as a network region.</span></span> <span data-ttu-id="6a624-115">每个网络站点都必须与一个网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="6a624-115">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="6a624-116">相同的网络区域由直接路由和增强的紧急服务的基于位置的路由共享。</span><span class="sxs-lookup"><span data-stu-id="6a624-116">The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services.</span></span> <span data-ttu-id="6a624-117">如果已为一个功能创建了网络区域，则不必为其他功能创建新的网络区域。</span><span class="sxs-lookup"><span data-stu-id="6a624-117">If you already created network regions for one feature, you don't have to create new network regions for the other feature.</span></span>

## <a name="network-site"></a><span data-ttu-id="6a624-118">网络站点</span><span class="sxs-lookup"><span data-stu-id="6a624-118">Network site</span></span>

<span data-ttu-id="6a624-119">网络站点表示您的组织有物理场所的位置，如办公室、一组建筑物或校园。</span><span class="sxs-lookup"><span data-stu-id="6a624-119">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="6a624-120">网络站点定义为 IP 子网的集合。</span><span class="sxs-lookup"><span data-stu-id="6a624-120">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="6a624-121">每个网络站点都必须与一个网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="6a624-121">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="6a624-122">您也可以使用 "网络站点" 启用和配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="6a624-122">You can also use network sites to enable and configure emergency calling.</span></span>

## <a name="network-subnet"></a><span data-ttu-id="6a624-123">网络子网</span><span class="sxs-lookup"><span data-stu-id="6a624-123">Network subnet</span></span>

<span data-ttu-id="6a624-124">每个子网都必须与特定的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="6a624-124">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="6a624-125">根据网络子网和关联的网络站点确定客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="6a624-125">A client's location is determined based on the network subnet and the associated network site.</span></span> <span data-ttu-id="6a624-126">你可以将多个子网与同一网络站点关联，但不能将多个站点与同一子网相关联。</span><span class="sxs-lookup"><span data-stu-id="6a624-126">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span>

<span data-ttu-id="6a624-127">子网信息用于确定启动新会话时终结点所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="6a624-127">Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated.</span></span> <span data-ttu-id="6a624-128">当会话中每个方的位置已知时，云语音功能可以应用该信息来确定如何处理呼叫设置或路由。</span><span class="sxs-lookup"><span data-stu-id="6a624-128">When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.</span></span>

<span data-ttu-id="6a624-129">对于每个网络站点，请与您的网络管理员协作，确定哪些 IP 子网分配给每个网络站点。</span><span class="sxs-lookup"><span data-stu-id="6a624-129">For each network site, work with your network admin to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="6a624-130">例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。</span><span class="sxs-lookup"><span data-stu-id="6a624-130">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="6a624-131">如果 Bob 通常在底特律中工作，在中传播到纽约的 office 进行培训，然后在其计算机上连接到网络，他的计算机将在分配给纽约的四个区域之一（例如172.29.80.103）中获取 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6a624-131">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York, for example, 172.29.80.103.</span></span>

## <a name="trusted-ip-address"></a><span data-ttu-id="6a624-132">受信任的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="6a624-132">Trusted IP address</span></span>

<span data-ttu-id="6a624-133">"受信任的 IP 地址" 是企业网络的 internet 外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="6a624-133">Trusted IP addresses are the internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="6a624-134">它们确定用户的终结点是否位于企业网络内，然后再检查特定网站匹配项。</span><span class="sxs-lookup"><span data-stu-id="6a624-134">They determine whether the user's endpoint is inside the corporate network before checking for a specific site match.</span></span>

<span data-ttu-id="6a624-135">如果用户的外部 IP 地址与 "信任的 IP 地址" 列表中的 IP 地址相匹配，则云语音功能将检查以确定用户终结点所在的内部子网。</span><span class="sxs-lookup"><span data-stu-id="6a624-135">If the user's external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="6a624-136">可以针对 IPv4 或 IPv6 IP 地址进行匹配，取决于发送到网络设置的 IP 数据包的格式。</span><span class="sxs-lookup"><span data-stu-id="6a624-136">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span> <span data-ttu-id="6a624-137">（如果公共 IP 地址同时具有 IPv4 和 IPv6，则必须将两者都添加为受信任的 IP 地址。）</span><span class="sxs-lookup"><span data-stu-id="6a624-137">(If a public IP address has both IPv4 and IPv6, you must add both as trusted IP addresses.)</span></span>

<span data-ttu-id="6a624-138">如果用户的外部 IP 地址与 "受信任的 IP 地址" 列表中的 IP 地址不匹配，则终结点将被分类为未知位置。</span><span class="sxs-lookup"><span data-stu-id="6a624-138">If the user's external IP address doesn't match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.</span></span>
