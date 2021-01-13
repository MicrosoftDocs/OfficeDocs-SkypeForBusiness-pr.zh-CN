---
title: 在 Skype for Business Server 中部署边缘服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 摘要：了解如何将边缘服务器或边缘池部署到 Skype for Business Server 环境中。
ms.openlocfilehash: edd2ff501320c4252b8032d1528ede7b83b8fcd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804382"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="a45b4-103">在 Skype for Business Server 中部署边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a45b4-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="a45b4-104">**摘要：** 了解如何将边缘服务器或边缘池部署到 Skype for Business Server 环境中。</span><span class="sxs-lookup"><span data-stu-id="a45b4-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="a45b4-105">为什么要将边缘服务器或边缘池部署到 Skype for Business Server 环境？</span><span class="sxs-lookup"><span data-stu-id="a45b4-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="a45b4-106">如果需要未登录到组织内部网络的外部用户能够与内部用户进行交互，则有必要。</span><span class="sxs-lookup"><span data-stu-id="a45b4-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="a45b4-107">这些外部用户可能是经过身份验证的匿名远程用户、联盟伙伴或其他移动客户端。</span><span class="sxs-lookup"><span data-stu-id="a45b4-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="a45b4-108">适用于 Skype for Business Server 的边缘部署清单</span><span class="sxs-lookup"><span data-stu-id="a45b4-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="a45b4-109">如上所述，Skype for Business Server 的边缘服务器部署有许多方面。</span><span class="sxs-lookup"><span data-stu-id="a45b4-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="a45b4-110">此清单概述了需要执行的任务，以及指向更详细步骤的链接。</span><span class="sxs-lookup"><span data-stu-id="a45b4-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="a45b4-111">我们希望你已开始在 [Skype for Business Server 中规划边缘服务器部署](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) 部分。</span><span class="sxs-lookup"><span data-stu-id="a45b4-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="a45b4-112">如果没有，我们将在其中详细介绍我们引用的许多内容。</span><span class="sxs-lookup"><span data-stu-id="a45b4-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="a45b4-113">部署部分仅包含过程，因此，如果您想了解这些步骤背后的原因，可以开始规划。</span><span class="sxs-lookup"><span data-stu-id="a45b4-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="a45b4-114">本文档还基于你已完成 Skype for Business Server 的基本部署。</span><span class="sxs-lookup"><span data-stu-id="a45b4-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="a45b4-115">你可能正在与边缘并行执行该部署，但你需要先执行这些步骤，然后你将能够对此处记录的边缘进行拓扑更改。</span><span class="sxs-lookup"><span data-stu-id="a45b4-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="a45b4-116">这些是需要遵循的高级别步骤，以及您将找到这些步骤的位置：</span><span class="sxs-lookup"><span data-stu-id="a45b4-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="a45b4-117">Skype for Business Server 中的边缘服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="a45b4-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="a45b4-118">Skype for Business Server 中的边缘服务器环境要求</span><span class="sxs-lookup"><span data-stu-id="a45b4-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="a45b4-119">为 Skype for Business Server 创建边缘拓扑</span><span class="sxs-lookup"><span data-stu-id="a45b4-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="a45b4-120">在 Skype for Business Server 中部署边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a45b4-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="a45b4-121">在 Skype for Business Server 中验证边缘部署</span><span class="sxs-lookup"><span data-stu-id="a45b4-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

