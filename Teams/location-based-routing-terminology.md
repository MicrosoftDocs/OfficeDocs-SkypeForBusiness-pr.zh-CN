---
title: 基于位置的路由术语
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 了解术语和概念的直接路由与基于位置的路由相关联。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34ec6558873da0db3537f6c5ae82b6624a3af369
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462393"
---
# <a name="location-based-routing-terminology"></a><span data-ttu-id="461f2-103">基于位置的路由术语</span><span class="sxs-lookup"><span data-stu-id="461f2-103">Location-Based Routing terminology</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="461f2-104">下面是一些术语和概念用于整个基于位置的路由文档的。</span><span class="sxs-lookup"><span data-stu-id="461f2-104">Here are some terms and concepts that are used throughout the Location-Based Routing documentation.</span></span> <span data-ttu-id="461f2-105">最好之前插入文档获取更深入地介绍要熟悉这些术语和概念。</span><span class="sxs-lookup"><span data-stu-id="461f2-105">It's a good idea to be familiar with these terms and concepts before you get deeper into the documentation.</span></span>

|<span data-ttu-id="461f2-106">术语</span><span class="sxs-lookup"><span data-stu-id="461f2-106">Term</span></span>  |<span data-ttu-id="461f2-107">说明</span><span class="sxs-lookup"><span data-stu-id="461f2-107">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="461f2-108">网络区域</span><span class="sxs-lookup"><span data-stu-id="461f2-108">Network regions</span></span>     | <span data-ttu-id="461f2-109">网络区域包含网络站点的集合。</span><span class="sxs-lookup"><span data-stu-id="461f2-109">A network region contains a collection of network sites.</span></span> <span data-ttu-id="461f2-110">例如，如果您的组织具有位于印度的多个网站，您可以选择将"印度"指定为网络区域。</span><span class="sxs-lookup"><span data-stu-id="461f2-110">For example, if your organization has many sites located in India, you may choose to designate “India” as a network region.</span></span>        |
|<span data-ttu-id="461f2-111">网络站点</span><span class="sxs-lookup"><span data-stu-id="461f2-111">Network sites</span></span>    | <span data-ttu-id="461f2-112">网络站点表示您的组织其中有物理定义位置，如 office、 一组建筑或一所高校的位置。</span><span class="sxs-lookup"><span data-stu-id="461f2-112">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="461f2-113">网络站点定义为 IP 子网的集合。</span><span class="sxs-lookup"><span data-stu-id="461f2-113">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="461f2-114">基于位置的路由的最佳做法是创建单独的网站的每个具有唯一的 PSTN 连接的位置。</span><span class="sxs-lookup"><span data-stu-id="461f2-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span>  <span data-ttu-id="461f2-115">每个网络站点必须与网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="461f2-115">Each network site must be associated with a network region.</span></span> <span data-ttu-id="461f2-116">您可以创建基于位置的路由启用网站或网站的未启用基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="461f2-116">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="461f2-117">例如，您可能想要创建基于位置的路由，以便为基于位置的路由，以便 PSTN 呼叫，它们漫游到该网站时启用的用户未启用网站。</span><span class="sxs-lookup"><span data-stu-id="461f2-117">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span> <span data-ttu-id="461f2-118">请注意，网络站点可能还使用启用和配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="461f2-118">Note that network sites may also be used to enable and configure emergency calling.</span></span>        |
|<span data-ttu-id="461f2-119">网络子网</span><span class="sxs-lookup"><span data-stu-id="461f2-119">Network subnets</span></span>     |<span data-ttu-id="461f2-120">其中团队终结点可以连接到网络位置的 IP 子网必须定义，并定义网络强制实施收费绕过关联。</span><span class="sxs-lookup"><span data-stu-id="461f2-120">IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="461f2-121">多个子网可能的相同的网络站点相关联，但可能不与同一子网关联多个站点。</span><span class="sxs-lookup"><span data-stu-id="461f2-121">Multiple subnets may be associated with the same network site, but multiple sites may not be associated with a same subnet.</span></span> <span data-ttu-id="461f2-122">此关联的子网启用基于位置的路由来查找地理位置以确定是否应允许给定的 PSTN 呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="461f2-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="461f2-123">支持 IPv6 和 IPv4 子网。</span><span class="sxs-lookup"><span data-stu-id="461f2-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="461f2-124">在确定是否团队终结点所处的网站时，基于位置的路由首先检查匹配的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="461f2-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="461f2-125">如果 IPv6 地址不存在，基于位置的路由检查 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="461f2-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span> <br><br><span data-ttu-id="461f2-126">IPv6 支持正在进行，可通过常规可用性 (GA) 的基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="461f2-126">Support for IPv6 is in progress and will be available by General Availability (GA) of Location-Based Routing.</span></span>          |
|<span data-ttu-id="461f2-127">受信任的外部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="461f2-127">Trusted external IP addresses</span></span>    |<span data-ttu-id="461f2-128">受信任的外部 IP 地址是企业网络的 Internet 外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="461f2-128">Trusted external IP addresses are the Internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="461f2-129">决定是否用户的终结点位于企业网络内部之前检查的特定网站匹配项。</span><span class="sxs-lookup"><span data-stu-id="461f2-129">They determine whether the user’s endpoint is inside the corporate network before checking for a specific site match.</span></span> <span data-ttu-id="461f2-130">如果用户的外部 IP 与受信任列表中定义的 IP 地址相匹配，基于位置的路由检查以确定用户的终结点所在的内部子网。</span><span class="sxs-lookup"><span data-stu-id="461f2-130">If the user’s external IP matches an IP address that's defined in the trusted list, Location-Based Routing checks to determine the internal subnet where the user’s endpoint is located.</span></span> <span data-ttu-id="461f2-131">如果用户的外部 IP 地址不匹配的受信任列表中定义的任意 IP 地址，终结点分类为未知位置，或从基于位置的路由启用的用户的所有 PSTN 呼叫被都阻止。</span><span class="sxs-lookup"><span data-stu-id="461f2-131">If the user’s external IP address doesn’t match any IP address that's defined in the trusted list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>          |

### <a name="related-topics"></a><span data-ttu-id="461f2-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="461f2-132">Related topics</span></span>
- [<span data-ttu-id="461f2-133">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="461f2-133">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="461f2-134">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="461f2-134">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="461f2-135">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="461f2-135">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
