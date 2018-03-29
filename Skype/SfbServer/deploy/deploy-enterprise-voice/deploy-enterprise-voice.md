---
title: 在 Skype for Business Server 2015 中部署企业语音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 摘要： 了解如何部署在中心站点的业务服务器 2015 Skype 为企业语音。
ms.openlocfilehash: d7c6dc347991c198d445932463a44d9fe1a4ff89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="59014-103">在 Skype for Business Server 2015 中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="59014-103">Deploy Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="59014-104">**摘要：**了解如何在中心站点的业务服务器 2015年的 Skype 部署企业语音。</span><span class="sxs-lookup"><span data-stu-id="59014-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server 2015 at a central site.</span></span>
  
<span data-ttu-id="59014-105">使用本主题来部署在中心站点的企业语音。</span><span class="sxs-lookup"><span data-stu-id="59014-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="59014-106">若要部署在分支站点企业语音，请跳至[部署分支站点](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)。</span><span class="sxs-lookup"><span data-stu-id="59014-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>
  
<span data-ttu-id="59014-107">此部分包含部署的过程中的中介服务器搭配使用在每个前端服务器或标准版服务器上，建议，以及对于与独立的中介服务器池的部署。如果您使用拓扑生成器来定义并发布配置在每个前端服务器或标准版服务器上，中介服务器的拓扑结构，因为部署向导已自动安装的文件，则可以跳过以下内容中介服务器安装前端服务器池或标准版服务器的文件时：</span><span class="sxs-lookup"><span data-stu-id="59014-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="59014-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="59014-108">In this section</span></span>

- [<span data-ttu-id="59014-109">在业务服务器 2015年的 Skype 的企业语音的安全和配置先决条件</span><span class="sxs-lookup"><span data-stu-id="59014-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>](enterprise-voice-security.md)
    
- [<span data-ttu-id="59014-110">在拓扑生成器在 Skype 中介服务器部署为业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="59014-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>](deploy-a-mediation-server.md)
    
- [<span data-ttu-id="59014-111">一个网关定义在拓扑生成器在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="59014-111">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>](define-a-gateway.md)
    
- [<span data-ttu-id="59014-112">定义其他中继在拓扑生成器在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="59014-112">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>](define-additional-trunks.md)
    
- [<span data-ttu-id="59014-113">对于业务服务器 2015年在 Skype 的中介服务器的安装文件</span><span class="sxs-lookup"><span data-stu-id="59014-113">Install the files for Mediation Server in Skype for Business Server 2015</span></span>](install-mediation-server.md)
    
- [<span data-ttu-id="59014-114">在 Skype 为业务服务器 2015年配置中继</span><span class="sxs-lookup"><span data-stu-id="59014-114">Configure trunks in Skype for Business Server 2015</span></span>](configure-trunks.md)
    
- [<span data-ttu-id="59014-115">创建或修改用于呼叫者 ID 的演示文稿在 Skype 业务服务器 2015年的翻译规则</span><span class="sxs-lookup"><span data-stu-id="59014-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server 2015</span></span>](caller-id-presentation-rules.md)
    
- [<span data-ttu-id="59014-116">创建或修改调用 ID 的演示文稿在 Skype 业务服务器 2015年的翻译规则</span><span class="sxs-lookup"><span data-stu-id="59014-116">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>](called-id-presentation-rules.md)
    
- [<span data-ttu-id="59014-117">创建或修改中业务 2015年的 Skype 的规范化规则</span><span class="sxs-lookup"><span data-stu-id="59014-117">Create or modify a normalization rule in Skype for Business 2015</span></span>](normalization-rules.md)
    
- [<span data-ttu-id="59014-118">创建或修改业务服务器 2015 Skype 的拨号计划</span><span class="sxs-lookup"><span data-stu-id="59014-118">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)
    
- [<span data-ttu-id="59014-119">配置业务 2015年的 Skype 语音策略、 PSTN 使用记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="59014-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>](voice-and-pstn.md)
    
- [<span data-ttu-id="59014-120">启用用户的 Skype 在企业语音的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="59014-120">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](enable-users-for-enterprise-voice.md)
    
- [<span data-ttu-id="59014-121">为业务服务器 2015年部署在 Skype 的高级的企业语音功能</span><span class="sxs-lookup"><span data-stu-id="59014-121">Deploy advanced Enterprise Voice features in Skype for Business Server 2015</span></span>](deploy-advanced-enterprise-voice-features.md)
    
- [<span data-ttu-id="59014-122">部署在企业 2015年的 Skype 通话管理功能</span><span class="sxs-lookup"><span data-stu-id="59014-122">Deploy call management features in Skype for Business 2015</span></span>](deploy-call-management-features.md)
    
## <a name="see-also"></a><span data-ttu-id="59014-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59014-123">See also</span></span>

#### 

[<span data-ttu-id="59014-124">企业语音在 Skype 业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="59014-124">Plan for Enterprise Voice in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

