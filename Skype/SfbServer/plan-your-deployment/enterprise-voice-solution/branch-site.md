---
title: Skype for Business 服务器中的分支站点 SIP 中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: 了解 Skype for Business Server 企业版中分支站点的 SIP 中继。
ms.openlocfilehash: 158c1cff28ba0c21f5c995a1fe5b7dfdf2f9f150
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803252"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="0786e-103">Skype for Business 服务器中的分支站点 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="0786e-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="0786e-104">了解 Skype for Business Server 企业版中分支站点的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="0786e-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0786e-105">在某些情况下，你可能需要在选定的分支站点上实施分布式 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="0786e-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="0786e-106">若要确定分支站点是否需要 SIP 主干，以及有关在分支站点中部署 SIP 中继的支持拓扑选项的详细信息，请参阅[Skype For Business 服务器中的 SIP 中继](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="0786e-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="0786e-107">示例分支站点 SIP 中继要求分析</span><span class="sxs-lookup"><span data-stu-id="0786e-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="0786e-108">当您决定部署分支站点 SIP 主干时，您需要执行特定于站点的成本分析。</span><span class="sxs-lookup"><span data-stu-id="0786e-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="0786e-109">例如，在 Redmond、华盛顿和纽约的分支站点中具有中心网站的企业，应执行分析以确定是否要从纽约站点向本地服务提供商实施 SIP 主干。</span><span class="sxs-lookup"><span data-stu-id="0786e-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="0786e-110">为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。</span><span class="sxs-lookup"><span data-stu-id="0786e-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="0786e-111">您可以在中心站点上终止分支站点。</span><span class="sxs-lookup"><span data-stu-id="0786e-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="0786e-112">例如，Redmond 中心网站可以托管纽约分支网站的号码。</span><span class="sxs-lookup"><span data-stu-id="0786e-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="0786e-113">如果实施分布式 SIP 主干的费用低于这些呼叫的费用，请考虑在纽约分支机构实施 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="0786e-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="0786e-114">其他分支站点 SIP 中继要求</span><span class="sxs-lookup"><span data-stu-id="0786e-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="0786e-115">根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。</span><span class="sxs-lookup"><span data-stu-id="0786e-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="0786e-116">如果你部署分支网站 SIP 主干，还需要确定你的恢复性和带宽要求。</span><span class="sxs-lookup"><span data-stu-id="0786e-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="0786e-117">如果分支站点和中心网站之间的链接具有弹性且带宽充足，则可以部署 SIP 主干或网关。</span><span class="sxs-lookup"><span data-stu-id="0786e-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="0786e-118">无需在分支站点上部署 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="0786e-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="0786e-119">如果你的分支站点和中心网站之间的链接不能复原，请部署 Survivable 分支设备，或使用分支站点上的网关或 SIP 中继部署 Survivable 分支服务器。</span><span class="sxs-lookup"><span data-stu-id="0786e-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

