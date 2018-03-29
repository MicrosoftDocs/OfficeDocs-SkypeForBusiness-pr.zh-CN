---
title: 在 Skype for Business Server 2015 中部署边缘服务器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 摘要： 了解如何部署到您的业务服务器 2015年环境 Skype 的边缘服务器或边缘池。
ms.openlocfilehash: 38eb0344488512a47f4dc21223d881c15f618e22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-edge-server-in-skype-for-business-server-2015"></a><span data-ttu-id="5e1c1-103">在 Skype for Business Server 2015 中部署边缘服务器</span><span class="sxs-lookup"><span data-stu-id="5e1c1-103">Deploy Edge Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5e1c1-104">**摘要：**了解如何部署到您的业务服务器 2015年环境 Skype 的边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment.</span></span>
  
<span data-ttu-id="5e1c1-105">为什么到您 Skype 业务服务器 2015年环境部署边缘服务器或边缘池？</span><span class="sxs-lookup"><span data-stu-id="5e1c1-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment?</span></span> <span data-ttu-id="5e1c1-106">如果需要不登录到组织内部网络的外部用户能够与内部用户交互，那就有必要这样做。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="5e1c1-107">这些外部用户可能是经过身份验证的远程用户和匿名远程用户、联盟伙伴或其他移动客户端。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server-2015"></a><span data-ttu-id="5e1c1-108">边缘，为业务服务器 2015年的 Skype 的部署清单</span><span class="sxs-lookup"><span data-stu-id="5e1c1-108">Deployment checklist for the Edge, for Skype for Business Server 2015</span></span>

<span data-ttu-id="5e1c1-109">如上文所述、 大量进入边缘服务器部署为 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server 2015.</span></span> <span data-ttu-id="5e1c1-110">此检查表概述您将需要执行操作，任务和链接到更详细的步骤。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="5e1c1-111">我们希望您开始的[边缘服务器部署在 Skype 的业务服务器 2015年计划](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)部分。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="5e1c1-112">如果没有，那里详细介绍了我们提到的很多内容。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="5e1c1-113">部署小节只包含过程，所以如果想知道这些步骤背后的来龙去脉，可以从规划开始。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="5e1c1-114">本文档还假定您已进行基本 Skype 部署了业务服务器 2015年的。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server 2015.</span></span> <span data-ttu-id="5e1c1-115">您可能不齐，执行该部署通过并行但需要第一，遵循这些步骤，然后您将能够为以下所述的边缘进行拓扑的更改。</span><span class="sxs-lookup"><span data-stu-id="5e1c1-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="5e1c1-116">以下是需要遵循的高级步骤，以及可找到这些步骤的位置：</span><span class="sxs-lookup"><span data-stu-id="5e1c1-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="5e1c1-117">边缘服务器的系统要求在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="5e1c1-117">Edge Server system requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="5e1c1-118">边缘服务器环境要求在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="5e1c1-118">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="5e1c1-119">创建业务服务器 2015年的 Skype 边拓扑</span><span class="sxs-lookup"><span data-stu-id="5e1c1-119">Create your Edge topology for Skype for Business Server 2015</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="5e1c1-120">部署边缘服务器在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="5e1c1-120">Deploy Edge Servers in Skype for Business Server 2015</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="5e1c1-121">验证您的边缘部署在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="5e1c1-121">Validate your Edge deployment in Skype for Business Server 2015</span></span>](validate-edge-deployment.md)
    

