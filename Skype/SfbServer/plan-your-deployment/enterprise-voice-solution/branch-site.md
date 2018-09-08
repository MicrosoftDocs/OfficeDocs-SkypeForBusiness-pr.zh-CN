---
title: Skype 业务服务器中的分支站点 SIP 中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: 了解有关在 Skype 中的分支站点 SIP 中继的业务 Server 企业语音。
ms.openlocfilehash: 17b387a0aec3498aa6ff15890ef39c94f1d68f60
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883856"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="61eb3-103">Skype 业务服务器中的分支站点 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="61eb3-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="61eb3-104">了解有关在 Skype 中的分支站点 SIP 中继的业务 Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="61eb3-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="61eb3-105">在某些情况下，您可能需要实现选定的分支站点上的分布式的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="61eb3-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="61eb3-106">若要确定是否对 SIP 中继所需的分支站点，以及有关支持的拓扑选项用于部署中的分支站点 SIP 中继的详细信息，请参阅[Skype 业务服务器中的 SIP 中继](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="61eb3-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="61eb3-107">示例分支站点 SIP 中继要求分析</span><span class="sxs-lookup"><span data-stu-id="61eb3-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="61eb3-108">如果您决定部署分支站点 SIP 中继，您需要执行的特定于站点的成本分析。</span><span class="sxs-lookup"><span data-stu-id="61eb3-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="61eb3-109">例如，企业已在华盛顿州雷德蒙德，中央站点和分支站点纽约，应执行分析，以确定是否实现从纽约站点 SIP 中继到本地服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="61eb3-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="61eb3-110">为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。</span><span class="sxs-lookup"><span data-stu-id="61eb3-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="61eb3-111">您可以为分支站点的 DID 终止在中央站点。</span><span class="sxs-lookup"><span data-stu-id="61eb3-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="61eb3-112">例如，Redmond 中央站点还可以承载纽约分支站点的 DID 号码。</span><span class="sxs-lookup"><span data-stu-id="61eb3-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="61eb3-113">如果实施分布式的 SIP 中继的成本小于这些呼叫的成本，请考虑实现纽约分支站点 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="61eb3-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="61eb3-114">其他分支站点 SIP 中继要求</span><span class="sxs-lookup"><span data-stu-id="61eb3-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="61eb3-115">根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。</span><span class="sxs-lookup"><span data-stu-id="61eb3-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="61eb3-116">如果您部署分支站点 SIP 中继，您还需要确定您的恢复能力和带宽要求。</span><span class="sxs-lookup"><span data-stu-id="61eb3-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="61eb3-117">如果您的分支站点和中央站点之间的链接弹性并且具有足够带宽，则可以部署 SIP 中继或网关。</span><span class="sxs-lookup"><span data-stu-id="61eb3-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="61eb3-118">不需要部署 Survivable Branch Appliance 分支站点。</span><span class="sxs-lookup"><span data-stu-id="61eb3-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="61eb3-119">如果您的分支站点和中央站点之间的链接不可恢复，部署 Survivable Branch Appliance，或部署 Survivable Branch Server 与网关或 SIP 中继，在分支站点。</span><span class="sxs-lookup"><span data-stu-id="61eb3-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

