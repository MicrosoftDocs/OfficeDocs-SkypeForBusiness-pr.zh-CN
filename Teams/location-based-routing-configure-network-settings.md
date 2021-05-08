---
title: 配置网络设置 - 基于位置的路由
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何为直接路由的路由创建和设置Location-Based、站点和子网。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822942"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="f867a-103">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="f867a-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="f867a-104">如果尚未这样做，请阅读规划直接路由Location-Based路由[](location-based-routing-plan.md)，查看为直接路由配置网络设置之前需要执行的其他Location-Based设置。</span><span class="sxs-lookup"><span data-stu-id="f867a-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="f867a-105">本文介绍如何为网络路由配置Location-Based设置。</span><span class="sxs-lookup"><span data-stu-id="f867a-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="f867a-106">在组织中电话系统直接路由后，接下来的步骤是创建和设置网络区域、网络站点和网络子网。</span><span class="sxs-lookup"><span data-stu-id="f867a-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="f867a-107">定义网络区域</span><span class="sxs-lookup"><span data-stu-id="f867a-107">Define network regions</span></span>

<span data-ttu-id="f867a-108">网络区域包含一组网络站点，跨多个地理区域互连网络的各个部分。</span><span class="sxs-lookup"><span data-stu-id="f867a-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="f867a-109">有关配置网络区域的步骤，请转到管理云功能的网络拓扑[Teams。](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="f867a-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="f867a-110">定义网络站点</span><span class="sxs-lookup"><span data-stu-id="f867a-110">Define network sites</span></span>

<span data-ttu-id="f867a-111">网络网站表示组织具有物理场所的位置，例如办公室、一组建筑物或校园。</span><span class="sxs-lookup"><span data-stu-id="f867a-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="f867a-112">必须将拓扑中的每个网络站点与网络区域关联。</span><span class="sxs-lookup"><span data-stu-id="f867a-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="f867a-113">有关配置网络站点的步骤，请参阅[管理](manage-your-network-topology.md)云功能的网络拓扑Teams。</span><span class="sxs-lookup"><span data-stu-id="f867a-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="f867a-114">路由路由Location-Based为每个具有唯一 PSTN 连接的位置创建单独的网站。</span><span class="sxs-lookup"><span data-stu-id="f867a-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="f867a-115">可以创建为路由启用的站点Location-Based未启用路由路由Location-Based站点。</span><span class="sxs-lookup"><span data-stu-id="f867a-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="f867a-116">例如，你可能想要创建未为 Location-Based 路由启用的网站，以允许启用了 Location-Based 路由的用户在漫游到该网站时进行 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="f867a-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="f867a-117">定义网络子网</span><span class="sxs-lookup"><span data-stu-id="f867a-117">Define network subnets</span></span>

<span data-ttu-id="f867a-118">每个子网必须与特定的网络站点相关联。</span><span class="sxs-lookup"><span data-stu-id="f867a-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="f867a-119">可以将多个子网与同一网络站点关联，但不能将多个站点与同一子网关联。</span><span class="sxs-lookup"><span data-stu-id="f867a-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="f867a-120">有关配置网络子网的步骤，请转到管理云功能的网络拓扑[，Teams。](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="f867a-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="f867a-121">对于Location-Based路由，必须定义终结点Teams位置的 IP 子网，并关联到定义的网络，以强制绕过收费。</span><span class="sxs-lookup"><span data-stu-id="f867a-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="f867a-122">子网的这种关联Location-Based路由在地理上查找终结点，确定是否应允许给定的 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="f867a-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="f867a-123">支持 IPv6 和 IPv4 子网。</span><span class="sxs-lookup"><span data-stu-id="f867a-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="f867a-124">确定终结点是否Teams站点时，Location-Based路由首先检查匹配的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="f867a-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="f867a-125">如果不存在 IPv6 地址，Location-Based路由检查 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="f867a-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="f867a-126">定义外部子网 (受信任的 IP) </span><span class="sxs-lookup"><span data-stu-id="f867a-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="f867a-127">受信任的 IP 地址是企业网络的 Internet 外部 IP 地址，用于确定用户的终结点是否在企业网络中。</span><span class="sxs-lookup"><span data-stu-id="f867a-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="f867a-128">若要了解如何配置受信任的 IP 地址，请转到管理云功能的网络[](manage-your-network-topology.md)拓扑，Teams。</span><span class="sxs-lookup"><span data-stu-id="f867a-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="f867a-129">如果用户的外部 IP 地址与受信任的 IP 地址列表中的 IP 地址匹配，Location-Based路由检查以确定用户终结点所在的内部子网。</span><span class="sxs-lookup"><span data-stu-id="f867a-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="f867a-130">如果用户的外部 IP 地址与受信任的 IP 地址列表中定义的任何 IP 地址不匹配，则终结点被分类为位于未知位置，并且阻止与启用了 Location-Based 路由的用户之间的任何 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="f867a-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f867a-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f867a-131">Next steps</span></span>

<span data-ttu-id="f867a-132">转到"[为直接Location-Based启用路由"。](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="f867a-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f867a-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="f867a-133">Related topics</span></span>

- [<span data-ttu-id="f867a-134">云语音功能的网络设置Teams</span><span class="sxs-lookup"><span data-stu-id="f867a-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
