---
title: 基于位置的路由术语
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解与直接路由的基于位置的路由相关的术语和概念。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d35b42453ac0eb9d9ae4a3f4c71f4452943a3b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245091"
---
# <a name="location-based-routing-terminology"></a><span data-ttu-id="38299-103">基于位置的路由术语</span><span class="sxs-lookup"><span data-stu-id="38299-103">Location-Based Routing terminology</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="38299-104">下面是在整个基于位置的路由文档中使用的一些术语和概念。</span><span class="sxs-lookup"><span data-stu-id="38299-104">Here are some terms and concepts that are used throughout the Location-Based Routing documentation.</span></span> <span data-ttu-id="38299-105">在深入了解文档之前, 最好先熟悉这些条款和概念。</span><span class="sxs-lookup"><span data-stu-id="38299-105">It's a good idea to be familiar with these terms and concepts before you get deeper into the documentation.</span></span>

|<span data-ttu-id="38299-106">术语</span><span class="sxs-lookup"><span data-stu-id="38299-106">Term</span></span>  |<span data-ttu-id="38299-107">说明</span><span class="sxs-lookup"><span data-stu-id="38299-107">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="38299-108">网络区域</span><span class="sxs-lookup"><span data-stu-id="38299-108">Network regions</span></span>     | <span data-ttu-id="38299-109">网络区域包含网络站点的集合。</span><span class="sxs-lookup"><span data-stu-id="38299-109">A network region contains a collection of network sites.</span></span> <span data-ttu-id="38299-110">例如, 如果您的组织具有多个位于印度的网站, 您可以选择将 "印度" 指定为网络区域。</span><span class="sxs-lookup"><span data-stu-id="38299-110">For example, if your organization has many sites located in India, you may choose to designate “India” as a network region.</span></span>        |
|<span data-ttu-id="38299-111">网络站点</span><span class="sxs-lookup"><span data-stu-id="38299-111">Network sites</span></span>    | <span data-ttu-id="38299-112">网络站点表示您的组织有物理场所的位置, 如办公室、一组建筑物或校园。</span><span class="sxs-lookup"><span data-stu-id="38299-112">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="38299-113">网络站点定义为 IP 子网的集合。</span><span class="sxs-lookup"><span data-stu-id="38299-113">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="38299-114">基于位置的路由的最佳做法是为每个具有唯一 PSTN 连接的位置创建单独的网站。</span><span class="sxs-lookup"><span data-stu-id="38299-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span>  <span data-ttu-id="38299-115">每个网络站点都必须与一个网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="38299-115">Each network site must be associated with a network region.</span></span> <span data-ttu-id="38299-116">你可以创建为基于位置的路由或未启用基于位置的路由的网站启用的网站。</span><span class="sxs-lookup"><span data-stu-id="38299-116">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="38299-117">例如, 你可能希望创建一个未启用基于位置的路由的网站, 以便允许启用了基于位置的路由的用户在漫游到该站点时进行 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="38299-117">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span> <span data-ttu-id="38299-118">请注意, 网络站点也可以用于启用和配置紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="38299-118">Note that network sites may also be used to enable and configure emergency calling.</span></span>        |
|<span data-ttu-id="38299-119">网络子网</span><span class="sxs-lookup"><span data-stu-id="38299-119">Network subnets</span></span>     |<span data-ttu-id="38299-120">必须定义团队终结点可以连接到网络的位置的 IP 子网, 并将其关联到已定义的网络以强制使用免费功能。</span><span class="sxs-lookup"><span data-stu-id="38299-120">IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="38299-121">多个子网可能与同一网络站点相关联, 但是多个站点可能未与同一子网关联。</span><span class="sxs-lookup"><span data-stu-id="38299-121">Multiple subnets may be associated with the same network site, but multiple sites may not be associated with a same subnet.</span></span> <span data-ttu-id="38299-122">这种子网的关联使基于位置的路由能够在地理位置找到终结点, 以确定是否应允许给定的 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="38299-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="38299-123">IPv6 和 IPv4 子网均受支持。</span><span class="sxs-lookup"><span data-stu-id="38299-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="38299-124">确定团队终结点是否位于某个网站时, 基于位置的路由首先检查匹配的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="38299-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="38299-125">如果不存在 IPv6 地址, 则基于位置的路由检查 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="38299-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span> <br><br>
|<span data-ttu-id="38299-126">受信任的外部 IP 地址</span><span class="sxs-lookup"><span data-stu-id="38299-126">Trusted external IP addresses</span></span>    |<span data-ttu-id="38299-127">受信任的外部 IP 地址是企业网络的 Internet 外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="38299-127">Trusted external IP addresses are the Internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="38299-128">它们确定用户的终结点是否位于企业网络内, 然后再检查特定网站匹配项。</span><span class="sxs-lookup"><span data-stu-id="38299-128">They determine whether the user’s endpoint is inside the corporate network before checking for a specific site match.</span></span> <span data-ttu-id="38299-129">如果用户的外部 IP 与受信任列表中定义的 IP 地址匹配, 则基于位置的路由检查以确定用户终结点所在的内部子网。</span><span class="sxs-lookup"><span data-stu-id="38299-129">If the user’s external IP matches an IP address that's defined in the trusted list, Location-Based Routing checks to determine the internal subnet where the user’s endpoint is located.</span></span> <span data-ttu-id="38299-130">如果用户的外部 IP 地址与受信任列表中定义的任何 IP 地址不匹配, 则终结点将被归为未知位置, 并且对启用了基于位置的路由的用户的任何 PSTN 呼叫都将被阻止。</span><span class="sxs-lookup"><span data-stu-id="38299-130">If the user’s external IP address doesn’t match any IP address that's defined in the trusted list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>          |

### <a name="related-topics"></a><span data-ttu-id="38299-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="38299-131">Related topics</span></span>
- [<span data-ttu-id="38299-132">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="38299-132">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="38299-133">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="38299-133">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="38299-134">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="38299-134">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
