---
title: 云语音功能的网络设置
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解必须为直接路由和增强型紧急Location-Based路由配置的网络设置。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97ddf7f6b7410e83a5e2257d7df6ae2ad27cb7f
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096279"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="595f5-103">云语音功能的网络设置Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="595f5-103">Network settings for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="595f5-104">了解网络区域、网络站点、网络子网和受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="595f5-104">Learn about network regions, network sites, network subnets, and trusted IP addresses.</span></span> <span data-ttu-id="595f5-105">这些术语和概念将在整个云语音文档中用于 [直接](location-based-routing-plan.md) 路由和动态紧急呼叫的基于位置 [的路由](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="595f5-105">These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan.md) and [dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span> <span data-ttu-id="595f5-106">如果要在组织中部署这些云功能，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="595f5-106">If you're deploying these cloud features in your organization, you must configure network settings for use with these features in Microsoft Teams.</span></span>

<span data-ttu-id="595f5-107">本文概述了路由和动态紧急呼叫Location-Based网络设置。</span><span class="sxs-lookup"><span data-stu-id="595f5-107">This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="595f5-108">根据要部署的云语音功能，可以配置其中一些或所有设置。</span><span class="sxs-lookup"><span data-stu-id="595f5-108">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="595f5-109">有关配置这些设置的步骤，请参阅[管理](manage-your-network-topology.md)云功能的网络拓扑Teams。</span><span class="sxs-lookup"><span data-stu-id="595f5-109">For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

> [!NOTE]
> <span data-ttu-id="595f5-110">该功能的配置主题中记录了网络设置的任何特定于功能的要求。</span><span class="sxs-lookup"><span data-stu-id="595f5-110">Any feature-specific requirements for network settings are documented in the configuration topics for that feature.</span></span>

## <a name="network-region"></a><span data-ttu-id="595f5-111">网络区域</span><span class="sxs-lookup"><span data-stu-id="595f5-111">Network region</span></span>

<span data-ttu-id="595f5-112">网络区域包含网络站点的集合。</span><span class="sxs-lookup"><span data-stu-id="595f5-112">A network region contains a collection of network sites.</span></span> <span data-ttu-id="595f5-113">它跨多个地理区域互连网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="595f5-113">It interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="595f5-114">例如，如果您的组织有许多位于印度的网站，您可以选择将"印度"指定为网络区域。</span><span class="sxs-lookup"><span data-stu-id="595f5-114">For example, if your organization has many sites located in India, you may choose to designate "India" as a network region.</span></span> <span data-ttu-id="595f5-115">每个网络站点必须与网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="595f5-115">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="595f5-116">同一网络区域由直接路由Location-Based增强型紧急服务的路由共享。</span><span class="sxs-lookup"><span data-stu-id="595f5-116">The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services.</span></span> <span data-ttu-id="595f5-117">如果已针对一项功能创建了网络区域，则不必为另一项功能创建新的网络区域。</span><span class="sxs-lookup"><span data-stu-id="595f5-117">If you already created network regions for one feature, you don't have to create new network regions for the other feature.</span></span>

## <a name="network-site"></a><span data-ttu-id="595f5-118">网络站点</span><span class="sxs-lookup"><span data-stu-id="595f5-118">Network site</span></span>

<span data-ttu-id="595f5-119">网络网站表示组织具有物理场所的位置，例如办公室、一组建筑物或校园。</span><span class="sxs-lookup"><span data-stu-id="595f5-119">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="595f5-120">网络站点定义为 IP 子网的集合。</span><span class="sxs-lookup"><span data-stu-id="595f5-120">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="595f5-121">每个网络站点必须与网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="595f5-121">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="595f5-122">您也可以使用网络站点来启用和配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="595f5-122">You can also use network sites to enable and configure emergency calling.</span></span>

## <a name="network-subnet"></a><span data-ttu-id="595f5-123">网络子网</span><span class="sxs-lookup"><span data-stu-id="595f5-123">Network subnet</span></span>

<span data-ttu-id="595f5-124">每个子网必须与特定的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="595f5-124">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="595f5-125">根据网络子网和关联的网络站点确定客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="595f5-125">A client's location is determined based on the network subnet and the associated network site.</span></span> <span data-ttu-id="595f5-126">可以将多个子网与同一网络站点关联，但不能将多个站点与同一子网关联。</span><span class="sxs-lookup"><span data-stu-id="595f5-126">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span>

<span data-ttu-id="595f5-127">子网信息用于确定启动新会话时终结点所在的网络站点。</span><span class="sxs-lookup"><span data-stu-id="595f5-127">Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated.</span></span> <span data-ttu-id="595f5-128">当知道会话中每一方的位置时，云语音功能可以应用该信息来确定如何处理呼叫设置或路由。</span><span class="sxs-lookup"><span data-stu-id="595f5-128">When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.</span></span>

<span data-ttu-id="595f5-129">对于每个网络站点，请与网络管理员合作，确定哪些 IP 子网分配给每个网络站点。</span><span class="sxs-lookup"><span data-stu-id="595f5-129">For each network site, work with your network admin to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="595f5-130">例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。</span><span class="sxs-lookup"><span data-stu-id="595f5-130">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="595f5-131">如果常在 Office 中工作的 Bob 前往纽约办公室接受培训，打开他的计算机并连接到网络，则他的计算机将在分配给纽约四个范围之一（例如 172.29.80.103）中获取 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="595f5-131">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York, for example, 172.29.80.103.</span></span>

## <a name="trusted-ip-address"></a><span data-ttu-id="595f5-132">受信任的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="595f5-132">Trusted IP address</span></span>

<span data-ttu-id="595f5-133">受信任的 IP 地址是企业网络的 Internet 外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="595f5-133">Trusted IP addresses are the internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="595f5-134">在检查特定站点匹配之前，确定用户的终结点是否位于企业网络内部。</span><span class="sxs-lookup"><span data-stu-id="595f5-134">They determine whether the user's endpoint is inside the corporate network before checking for a specific site match.</span></span>

<span data-ttu-id="595f5-135">如果用户的外部 IP 地址与受信任的 IP 地址列表中的 IP 地址匹配，云语音功能会检查以确定用户终结点所在的内部子网。</span><span class="sxs-lookup"><span data-stu-id="595f5-135">If the user's external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="595f5-136">可以针对 IPv4 或 IPv6 IP 地址进行匹配，并且取决于发送到网络设置的 IP 数据包的格式。</span><span class="sxs-lookup"><span data-stu-id="595f5-136">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span> <span data-ttu-id="595f5-137"> (如果公共 IP 地址同时具有 IPv4 和 IPv6，则必须将两者添加为受信任的 IP 地址.) </span><span class="sxs-lookup"><span data-stu-id="595f5-137">(If a public IP address has both IPv4 and IPv6, you must add both as trusted IP addresses.)</span></span>

<span data-ttu-id="595f5-138">如果用户的外部 IP 地址与受信任的 IP 地址列表中的 IP 地址不匹配，则终结点被分类为位于未知位置。</span><span class="sxs-lookup"><span data-stu-id="595f5-138">If the user's external IP address doesn't match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.</span></span>

> [!Important]
> <span data-ttu-id="595f5-139">修改源 IP 地址的云代理服务部署不支持网络配置设置查找Teams客户端。</span><span class="sxs-lookup"><span data-stu-id="595f5-139">Network configuration setting lookups are not supported with cloud proxy service deployments that modify the source IP addresses from Teams clients.</span></span>
