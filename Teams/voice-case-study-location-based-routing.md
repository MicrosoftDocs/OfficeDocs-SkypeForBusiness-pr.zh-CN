---
title: 团队语音 Contoso 个案研究
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
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785952"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="08c8d-103">Contoso 个案研究：基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="08c8d-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="08c8d-104">基于位置的路由（LBR）是一种功能，可在发出或接收呼叫时限制基于策略和用户的物理位置的收费旁路。</span><span class="sxs-lookup"><span data-stu-id="08c8d-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="08c8d-105">概述</span><span class="sxs-lookup"><span data-stu-id="08c8d-105">Overview</span></span>

<span data-ttu-id="08c8d-106">Contoso 在一个国家/地区有两个办事处，在这种情况下，不能绕过公共交换电话网络（PSTN）提供程序来减少长途通话成本。</span><span class="sxs-lookup"><span data-stu-id="08c8d-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="08c8d-107">主 office 具有由主办公室和第二个 office 使用的 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="08c8d-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="08c8d-108">每个 office 都有自己的会话边界控制器（SBC）连接到 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="08c8d-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="08c8d-109">在此国家/地区，Contoso 已针对其 Skype for Business 部署配置了 LBR。</span><span class="sxs-lookup"><span data-stu-id="08c8d-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="08c8d-110">若要确定如何为团队配置 LBR，请按 Contoso 读取[计划位置直接路由选择](location-based-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="08c8d-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="08c8d-111">Contoso 确定团队和 Skype for business 在可以进行呼叫时，如果可以接收到当 PSTN 呼叫可以转到团队用户，并且可以将其他团队用户转移到 PSTN 呼叫时，请遵循相同的方案。</span><span class="sxs-lookup"><span data-stu-id="08c8d-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="08c8d-112">对于 Skype for Business，LBR 已配置有会话边界控制器（SBC） SIP Trunk 连接到 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="08c8d-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="08c8d-113">对于此 SBC，Contoso 检查了已[认证的 SBCs 列表](direct-routing-border-controllers.md)，并确定 SBC 部署的 SBC 已验证为直接路由，但未针对媒体旁路进行验证。</span><span class="sxs-lookup"><span data-stu-id="08c8d-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="08c8d-114">为了支持 LBR，直接路由需要配置到 SBC 现场，需要有本地 Internet 出口，并且需要为媒体旁路配置 SBC。</span><span class="sxs-lookup"><span data-stu-id="08c8d-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="08c8d-115">根据此信息，Contoso 确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="08c8d-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="08c8d-116">若要延迟团队 LBR 的启用，直到现有 SBC 验证了媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="08c8d-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="08c8d-117">Contoso 决定使用主站点 SBC 直接前往 Office 365。</span><span class="sxs-lookup"><span data-stu-id="08c8d-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="08c8d-118">主站点 SBC 将是远程站点的代理 SBC。</span><span class="sxs-lookup"><span data-stu-id="08c8d-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="08c8d-119">Contoso 使用基于印度的第三方顾问来协助 LBR 配置与国家/地区的电话公司的认证。</span><span class="sxs-lookup"><span data-stu-id="08c8d-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="08c8d-120">为了支持从办公室外部工作以进行 PSTN 呼叫，公司颁发的移动电话已提供给其员工。</span><span class="sxs-lookup"><span data-stu-id="08c8d-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="08c8d-121">下图显示了具有需要基于位置路由的电话服务的国家/地区的部署之前和之后的情况：</span><span class="sxs-lookup"><span data-stu-id="08c8d-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="08c8d-122">**原始部署**</span><span class="sxs-lookup"><span data-stu-id="08c8d-122">**Original deployment**</span></span>

![状态之前显示的图表](media/voice-case-study-5.png)

<span data-ttu-id="08c8d-124">**直接路由的部署**</span><span class="sxs-lookup"><span data-stu-id="08c8d-124">**Deployment with Direct Routing**</span></span>

![状态之前显示的图表](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="08c8d-126">配置</span><span class="sxs-lookup"><span data-stu-id="08c8d-126">Configuration:</span></span> 

<span data-ttu-id="08c8d-127">若要配置团队中的网络组件，Contoso 按照[管理云语音功能的网络拓扑](manage-your-network-topology.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="08c8d-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="08c8d-128">Contoso 已完成以下步骤来配置基于位置的路由：</span><span class="sxs-lookup"><span data-stu-id="08c8d-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="08c8d-129">定义网络区域-已定义一个网络区域。</span><span class="sxs-lookup"><span data-stu-id="08c8d-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="08c8d-130">定义网络站点-定义了两个网络站点。</span><span class="sxs-lookup"><span data-stu-id="08c8d-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="08c8d-131">区域中每个办公位置的一个网站。</span><span class="sxs-lookup"><span data-stu-id="08c8d-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="08c8d-132">定义网络子网-办公室位置内的每个楼层都有其自己的用于有线和无线网络的子网。</span><span class="sxs-lookup"><span data-stu-id="08c8d-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="08c8d-133">此配置为 Contoso 产生了20个子网。</span><span class="sxs-lookup"><span data-stu-id="08c8d-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="08c8d-134">定义受信任的 IP 地址-将 SBC 的面向外部的 IP 地址添加到受信任的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="08c8d-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

