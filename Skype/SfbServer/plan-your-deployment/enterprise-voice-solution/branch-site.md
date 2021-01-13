---
title: Skype for Business Server 中的分支站点 SIP 中继
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 了解 Skype for Business Server 服务中的分支站点中的 SIP 中继企业语音。
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813712"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="79675-103">Skype for Business Server 中的分支站点 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="79675-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="79675-104">了解 Skype for Business Server 服务中的分支站点中的 SIP 中继企业语音。</span><span class="sxs-lookup"><span data-stu-id="79675-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="79675-105">在某些情况下，您可能需要在选定的分支站点实施分布式 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="79675-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="79675-106">若要确定分支站点是否需要 SIP 中继，以及有关在分支站点中部署 SIP 中继的受支持的拓扑选项的详细信息，请参阅 Skype for [Business Server 中的 SIP](sip-trunking.md)中继。</span><span class="sxs-lookup"><span data-stu-id="79675-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="79675-107">示例分支站点 SIP 中继要求分析</span><span class="sxs-lookup"><span data-stu-id="79675-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="79675-108">当您决定部署分支站点 SIP 中继时，您需要执行特定于站点的成本分析。</span><span class="sxs-lookup"><span data-stu-id="79675-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="79675-109">例如，具有位于华盛顿州雷德蒙德的中央站点和纽约分支站点的企业应进行分析，以确定是否实现从纽约站点到本地服务提供商的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="79675-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="79675-110">为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。</span><span class="sxs-lookup"><span data-stu-id="79675-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="79675-111">可以在中央站点对分支站点进行 DID 终止。</span><span class="sxs-lookup"><span data-stu-id="79675-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="79675-112">例如，Redmond 中央站点可以承载纽约分支站点的 DID 号码。</span><span class="sxs-lookup"><span data-stu-id="79675-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="79675-113">如果实现分布式 SIP 中继的成本低于这些呼叫的成本，请考虑在纽约分支站点实施 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="79675-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="79675-114">其他分支站点 SIP 中继要求</span><span class="sxs-lookup"><span data-stu-id="79675-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="79675-115">根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。</span><span class="sxs-lookup"><span data-stu-id="79675-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="79675-116">如果部署分支站点 SIP 中继，则还需要确定恢复能力和带宽要求。</span><span class="sxs-lookup"><span data-stu-id="79675-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="79675-117">如果分支站点和中央站点之间的链路具有弹性且具有足够的带宽，您可以部署 SIP 中继或网关。</span><span class="sxs-lookup"><span data-stu-id="79675-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="79675-118">无需在分支站点部署 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="79675-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="79675-119">如果分支站点和中央站点之间的链路无法恢复，请部署 Survivable Branch Appliance，或在分支站点部署具有网关或 SIP 中继的 Survivable Branch Server。</span><span class="sxs-lookup"><span data-stu-id="79675-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

