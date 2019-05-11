---
title: 部署边缘服务器在 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 摘要： 了解如何为您 Skype 业务服务器环境中部署边缘服务器或边缘池。
ms.openlocfilehash: 4968f11b14b21308ab731cffbc68d67337afa564
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893236"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="f5911-103">部署边缘服务器在 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="f5911-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f5911-104">**摘要：** 了解如何为您 Skype 业务服务器环境中部署边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="f5911-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="f5911-105">为什么到您 Skype 业务服务器环境中部署边缘服务器或边缘池？</span><span class="sxs-lookup"><span data-stu-id="f5911-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="f5911-106">如果需要不登录到组织内部网络的外部用户能够与内部用户交互，那就有必要这样做。</span><span class="sxs-lookup"><span data-stu-id="f5911-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="f5911-107">这些外部用户可能是经过身份验证的远程用户和匿名远程用户、联盟伙伴或其他移动客户端。</span><span class="sxs-lookup"><span data-stu-id="f5911-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="f5911-108">为边缘的企业服务器的 Skype 的部署清单</span><span class="sxs-lookup"><span data-stu-id="f5911-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="f5911-109">如上所述、 大量转到边缘服务器部署的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="f5911-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="f5911-110">此检查表为您提供了概述您需要执行操作，这些任务并链接到更详细的步骤。</span><span class="sxs-lookup"><span data-stu-id="f5911-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="f5911-111">我们希望在[规划边缘服务器部署中的业务服务器 Skype](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)部分已经开始。</span><span class="sxs-lookup"><span data-stu-id="f5911-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="f5911-112">如果没有，那里详细介绍了我们提到的很多内容。</span><span class="sxs-lookup"><span data-stu-id="f5911-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="f5911-113">部署小节只包含过程，所以如果想知道这些步骤背后的来龙去脉，可以从规划开始。</span><span class="sxs-lookup"><span data-stu-id="f5911-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="f5911-114">本文档还假定您已进行基本 Skype 部署了业务服务器。</span><span class="sxs-lookup"><span data-stu-id="f5911-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="f5911-115">您可能与边缘，执行该部署-并行但需要首先，请按照这些步骤，然后您将能够使此处介绍的边缘拓扑的更改。</span><span class="sxs-lookup"><span data-stu-id="f5911-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="f5911-116">以下是需要遵循的高级步骤，以及可找到这些步骤的位置：</span><span class="sxs-lookup"><span data-stu-id="f5911-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="f5911-117">为业务服务器中 Skype 边缘服务器的系统要求</span><span class="sxs-lookup"><span data-stu-id="f5911-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="f5911-118">边缘服务器环境要求中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="f5911-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="f5911-119">为 Business Server Skype 创建边缘拓扑</span><span class="sxs-lookup"><span data-stu-id="f5911-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="f5911-120">在部署边缘服务器 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="f5911-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="f5911-121">验证边缘部署中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="f5911-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

