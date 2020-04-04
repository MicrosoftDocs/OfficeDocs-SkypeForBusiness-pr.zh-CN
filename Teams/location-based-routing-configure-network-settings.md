---
title: 配置网络设置-基于位置的路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何创建和设置用于直接路由的基于位置的路由的网络区域、站点和子网。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f63ff0191518acf72fd3e4c33abe80b819c3db28
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141275"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="e04e9-103">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="e04e9-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="e04e9-104">如果尚未执行此操作，请阅读[基于计划位置的路由，直接路由](location-based-routing-plan.md)以查看在为基于位置的路由配置网络设置之前需要执行的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="e04e9-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="e04e9-105">本文介绍如何为基于位置的路由配置网络设置。</span><span class="sxs-lookup"><span data-stu-id="e04e9-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="e04e9-106">在组织中部署手机系统直接路由后，下一步是创建和设置网络区域、网络网站和网络子网。</span><span class="sxs-lookup"><span data-stu-id="e04e9-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="e04e9-107">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="e04e9-107">Define network regions</span></span>

<span data-ttu-id="e04e9-108">网络区域包含网络站点集合，并跨多个地理区域互连网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="e04e9-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e04e9-109">有关如何配置网络区域的步骤，请转到[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="e04e9-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="e04e9-110">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="e04e9-110">Define network sites</span></span>

<span data-ttu-id="e04e9-111">网络站点表示您的组织有物理场所的位置，如办公室、一组建筑物或校园。</span><span class="sxs-lookup"><span data-stu-id="e04e9-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="e04e9-112">您必须将拓扑中的每个网络站点与网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="e04e9-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="e04e9-113">有关如何配置网络网站的步骤，请参阅[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="e04e9-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="e04e9-114">基于位置的路由的最佳做法是为每个具有唯一 PSTN 连接的位置创建单独的网站。</span><span class="sxs-lookup"><span data-stu-id="e04e9-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="e04e9-115">你可以创建为基于位置的路由或未启用基于位置的路由的网站启用的网站。</span><span class="sxs-lookup"><span data-stu-id="e04e9-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="e04e9-116">例如，你可能希望创建一个未启用基于位置的路由的网站，以便允许启用了基于位置的路由的用户在漫游到该站点时进行 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="e04e9-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="e04e9-117">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="e04e9-117">Define network subnets</span></span>

<span data-ttu-id="e04e9-118">每个子网都必须与特定的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="e04e9-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="e04e9-119">你可以将多个子网与同一网络站点关联，但不能将多个站点与同一子网相关联。</span><span class="sxs-lookup"><span data-stu-id="e04e9-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="e04e9-120">有关如何配置网络子网的步骤，请转到[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="e04e9-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="e04e9-121">对于基于位置的路由，团队终结点可以连接到网络的位置上的 IP 子网必须定义并关联到已定义的网络，才能强制使用收费旁路。</span><span class="sxs-lookup"><span data-stu-id="e04e9-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="e04e9-122">这种子网的关联使基于位置的路由能够在地理位置找到终结点，以确定是否应允许给定的 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="e04e9-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="e04e9-123">IPv6 和 IPv4 子网均受支持。</span><span class="sxs-lookup"><span data-stu-id="e04e9-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="e04e9-124">确定团队终结点是否位于某个网站时，基于位置的路由首先检查匹配的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="e04e9-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="e04e9-125">如果不存在 IPv6 地址，则基于位置的路由检查 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="e04e9-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="e04e9-126">定义受信任的 IP 地址（外部子网）</span><span class="sxs-lookup"><span data-stu-id="e04e9-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="e04e9-127">"受信任的 IP 地址" 是企业网络的 internet 外部 IP 地址，用于确定用户的终结点是否位于企业网络内。</span><span class="sxs-lookup"><span data-stu-id="e04e9-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="e04e9-128">有关如何配置受信任 IP 地址的步骤，请转到[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="e04e9-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="e04e9-129">如果用户的外部 IP 地址与 "受信任的 IP 地址" 列表中的 IP 地址匹配，则基于位置的路由检查以确定用户终结点所在的内部子网。</span><span class="sxs-lookup"><span data-stu-id="e04e9-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="e04e9-130">如果用户的外部 IP 地址不匹配在 "信任的 IP 地址" 列表中定义的任何 IP 地址，终结点将被归类为处于未知位置，并且对启用了基于位置的路由的用户的任何 PSTN 呼叫都将被阻止。</span><span class="sxs-lookup"><span data-stu-id="e04e9-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e04e9-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e04e9-131">Next steps</span></span>

<span data-ttu-id="e04e9-132">转到 "为[直接路由启用基于位置的路由](location-based-routing-enable.md)"。</span><span class="sxs-lookup"><span data-stu-id="e04e9-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e04e9-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="e04e9-133">Related topics</span></span>

- [<span data-ttu-id="e04e9-134">团队中云语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="e04e9-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
