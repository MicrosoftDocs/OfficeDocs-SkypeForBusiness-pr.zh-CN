---
title: 在 Skype for Business 服务器中部署 Edge 服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: '摘要: 了解如何将 Edge 服务器或边缘池部署到 Skype for business 服务器环境中。'
ms.openlocfilehash: bcb6f7fdd7b322411e793fe3466418db1dd00894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306949"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="a67fd-103">在 Skype for Business 服务器中部署 Edge 服务器</span><span class="sxs-lookup"><span data-stu-id="a67fd-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="a67fd-104">**摘要:** 了解如何将 Edge 服务器或边缘池部署到 Skype for business 服务器环境中。</span><span class="sxs-lookup"><span data-stu-id="a67fd-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="a67fd-105">为什么要将 Edge 服务器或边缘池部署到 Skype for Business 服务器环境中？</span><span class="sxs-lookup"><span data-stu-id="a67fd-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="a67fd-106">如果需要不登录到组织内部网络的外部用户能够与内部用户交互，那就有必要这样做。</span><span class="sxs-lookup"><span data-stu-id="a67fd-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="a67fd-107">这些外部用户可能是经过身份验证的远程用户和匿名远程用户、联盟伙伴或其他移动客户端。</span><span class="sxs-lookup"><span data-stu-id="a67fd-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="a67fd-108">适用于 Skype for business 服务器的边缘部署核对清单</span><span class="sxs-lookup"><span data-stu-id="a67fd-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="a67fd-109">如上所述, 许多 Skype for business 服务器的边缘服务器部署非常如此。</span><span class="sxs-lookup"><span data-stu-id="a67fd-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="a67fd-110">此清单概括介绍了你需要执行的任务, 以及指向更详细的步骤的链接。</span><span class="sxs-lookup"><span data-stu-id="a67fd-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="a67fd-111">我们希望你已经开始在[Skype For Business server 部分中的 Edge 服务器部署计划](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)中开始。</span><span class="sxs-lookup"><span data-stu-id="a67fd-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="a67fd-112">如果没有，那里详细介绍了我们提到的很多内容。</span><span class="sxs-lookup"><span data-stu-id="a67fd-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="a67fd-113">部署小节只包含过程，所以如果想知道这些步骤背后的来龙去脉，可以从规划开始。</span><span class="sxs-lookup"><span data-stu-id="a67fd-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="a67fd-114">本文档还假定你已经完成了 Skype for Business 服务器的基本部署。</span><span class="sxs-lookup"><span data-stu-id="a67fd-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="a67fd-115">你可能会与边缘并排执行部署, 但你需要先关注这些步骤, 然后你将能够对此处所述的边缘进行拓扑更改。</span><span class="sxs-lookup"><span data-stu-id="a67fd-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="a67fd-116">以下是需要遵循的高级步骤，以及可找到这些步骤的位置：</span><span class="sxs-lookup"><span data-stu-id="a67fd-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="a67fd-117">Skype for Business Server 中的边缘服务器系统要求</span><span class="sxs-lookup"><span data-stu-id="a67fd-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="a67fd-118">Skype for Business Server 中的边缘服务器环境要求</span><span class="sxs-lookup"><span data-stu-id="a67fd-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="a67fd-119">为 Skype for Business 服务器创建边缘拓扑</span><span class="sxs-lookup"><span data-stu-id="a67fd-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="a67fd-120">在 Skype for Business 服务器中部署边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a67fd-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="a67fd-121">在 Skype for Business 服务器中验证 Edge 部署</span><span class="sxs-lookup"><span data-stu-id="a67fd-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

