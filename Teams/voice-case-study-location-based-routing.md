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
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785952"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="002bc-103">Contoso 案例研究：Location-Based路由</span><span class="sxs-lookup"><span data-stu-id="002bc-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="002bc-104">Location-Based LBR (路由) 是一项功能，它基于发出或接收呼叫时的策略和用户的物理位置限制通行费绕过。</span><span class="sxs-lookup"><span data-stu-id="002bc-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="002bc-105">概述</span><span class="sxs-lookup"><span data-stu-id="002bc-105">Overview</span></span>

<span data-ttu-id="002bc-106">Contoso 在一个国家/地区有两个办公室，其中绕过公共电话交换网 (PSTN 提供商) 降低远程呼叫成本非法。</span><span class="sxs-lookup"><span data-stu-id="002bc-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="002bc-107">主办公室具有由主办公室和第二个办公室使用的 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="002bc-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="002bc-108">每个办公室都有自己的会话边界控制器 (SBC) PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="002bc-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="002bc-109">在此国家/地区，Contoso 已针对其用户部署Skype for Business LBR。</span><span class="sxs-lookup"><span data-stu-id="002bc-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="002bc-110">若要确定如何为直接路由配置 LBR Teams，Contoso 请阅读规划Location-Based[直接路由的路由](location-based-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="002bc-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="002bc-111">Contoso 确定 Teams 和 Skype for Business 在何时可以拨打呼叫、何时可以接收呼叫、PSTN 呼叫何时可以转接到 Teams 用户以及何时可以将另一个 Teams 用户转接到 PSTN 呼叫上遵循相同的方案。</span><span class="sxs-lookup"><span data-stu-id="002bc-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="002bc-112">对于Skype for Business，LBR 配置了会话边界控制器 (SBC) 连接到 PSTN 运营商的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="002bc-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="002bc-113">对于此 SBC，Contoso 查看[](direct-routing-border-controllers.md)了经过认证的 SBC 列表，确定部署的 SBC 已通过直接路由认证，但没有通过媒体旁路认证。</span><span class="sxs-lookup"><span data-stu-id="002bc-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="002bc-114">若要支持 LBR，需要将直接路由配置为本地 SBC，需要有本地 Internet 出口，并且需要为媒体旁路配置 SBC。</span><span class="sxs-lookup"><span data-stu-id="002bc-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="002bc-115">Contoso 根据此信息决定以下事项：</span><span class="sxs-lookup"><span data-stu-id="002bc-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="002bc-116">若要延迟启用 Teams LBR，直到现有 SBC 通过媒体旁路认证。</span><span class="sxs-lookup"><span data-stu-id="002bc-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="002bc-117">Contoso 决定使用主站点 SBC 作为直接路由来Office 365。</span><span class="sxs-lookup"><span data-stu-id="002bc-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="002bc-118">主站点 SBC 将是远程站点的代理 SBC。</span><span class="sxs-lookup"><span data-stu-id="002bc-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="002bc-119">Contoso 使用一位印度的第三方顾问协助国内电话公司进行 LBR 配置认证。</span><span class="sxs-lookup"><span data-stu-id="002bc-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="002bc-120">为了支持从办公室外工作以拨打 PSTN 呼叫的用户，公司向员工提供了公司颁发的移动电话。</span><span class="sxs-lookup"><span data-stu-id="002bc-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="002bc-121">下图显示了在部署之前和之后，对于有电话法规要求使用路由Location-Based国家/地区：</span><span class="sxs-lookup"><span data-stu-id="002bc-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="002bc-122">**原始部署**</span><span class="sxs-lookup"><span data-stu-id="002bc-122">**Original deployment**</span></span>

![显示状态前的图表](media/voice-case-study-5.png)

<span data-ttu-id="002bc-124">**使用直接路由进行部署**</span><span class="sxs-lookup"><span data-stu-id="002bc-124">**Deployment with Direct Routing**</span></span>

![显示状态前的图表](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="002bc-126">配置：</span><span class="sxs-lookup"><span data-stu-id="002bc-126">Configuration:</span></span> 

<span data-ttu-id="002bc-127">为了在云中配置网络Teams，Contoso 按照管理云语音功能的网络拓扑[中的说明进行操作](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="002bc-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="002bc-128">Contoso 已完成以下步骤来配置Location-Based路由：</span><span class="sxs-lookup"><span data-stu-id="002bc-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="002bc-129">定义网络区域 - 定义了一个网络区域。</span><span class="sxs-lookup"><span data-stu-id="002bc-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="002bc-130">定义网络站点 - 定义了两个网络站点。</span><span class="sxs-lookup"><span data-stu-id="002bc-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="002bc-131">该区域中每个办公室位置都有一个网站。</span><span class="sxs-lookup"><span data-stu-id="002bc-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="002bc-132">定义网络子网 - 办公室位置内的每个楼层都有自己的有线和无线网络子网。</span><span class="sxs-lookup"><span data-stu-id="002bc-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="002bc-133">此配置导致 Contoso 有 20 个子网。</span><span class="sxs-lookup"><span data-stu-id="002bc-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="002bc-134">定义受信任的 IP 地址 - SBC 面向外部的 IP 地址已添加到受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="002bc-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

