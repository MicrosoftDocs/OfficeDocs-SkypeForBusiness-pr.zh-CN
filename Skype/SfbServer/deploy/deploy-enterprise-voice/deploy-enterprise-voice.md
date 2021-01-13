---
title: 在 skype for Business Server 企业语音部署
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 摘要：了解如何在中央站点企业语音 Skype for Business Server 部署服务。
ms.openlocfilehash: 246c1e5c03401b885b297ada08677fb40faad60d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812492"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="70e87-103">在 skype for Business Server 企业语音部署</span><span class="sxs-lookup"><span data-stu-id="70e87-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="70e87-104">**摘要：** 了解如何在中央站点企业语音 Skype for Business Server 部署服务。</span><span class="sxs-lookup"><span data-stu-id="70e87-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="70e87-105">使用本主题在企业语音部署部署。</span><span class="sxs-lookup"><span data-stu-id="70e87-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="70e87-106">若要在企业语音部署分支站点，请跳到["部署分支站点"。](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)</span><span class="sxs-lookup"><span data-stu-id="70e87-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="70e87-107">本节包括部署过程，其中中介服务器按照建议并排在每台前端服务器或 Standard Edition 服务器上，以及用于具有独立中介服务器池的部署。如果使用拓扑生成器定义并发布将中介服务器并放在每台前端服务器或 Standard Edition Server 上的拓扑，则您可以跳过以下内容，因为在为前端服务器池或 Standard Edition Server 安装文件时，部署向导已自动为中介服务器安装文件：</span><span class="sxs-lookup"><span data-stu-id="70e87-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="70e87-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="70e87-108">In this section</span></span>

- [<span data-ttu-id="70e87-109">Skype for Business Server 企业语音的安全性和配置先决条件</span><span class="sxs-lookup"><span data-stu-id="70e87-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="70e87-110">在 Skype for Business Server 的拓扑生成器中部署中介服务器</span><span class="sxs-lookup"><span data-stu-id="70e87-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="70e87-111">在 Skype for Business Server 中的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="70e87-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="70e87-112">在 Skype for Business Server 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="70e87-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="70e87-113">在 Skype for Business Server 中安装中介服务器的文件</span><span class="sxs-lookup"><span data-stu-id="70e87-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="70e87-114">在 Skype for Business Server 中配置中继</span><span class="sxs-lookup"><span data-stu-id="70e87-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="70e87-115">在 Skype for Business Server 中为呼叫者 ID 演示文稿创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="70e87-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="70e87-116">在 Skype for Business Server 中为被叫 ID 演示文稿创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="70e87-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="70e87-117">在 Skype for Business 中创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="70e87-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="70e87-118">在 Skype for Business Server 中创建或修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="70e87-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="70e87-119">在 Skype for Business 中配置语音策略、PSTN 用法记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="70e87-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="70e87-120">在 Skype for Business Server 企业语音用户</span><span class="sxs-lookup"><span data-stu-id="70e87-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="70e87-121">在 Skype 企业语音 Server 中部署高级部署功能</span><span class="sxs-lookup"><span data-stu-id="70e87-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="70e87-122">在 Skype for Business 中部署呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="70e87-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="70e87-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70e87-123">See also</span></span>

[<span data-ttu-id="70e87-124">规划企业语音 Skype for Business Server 中的服务</span><span class="sxs-lookup"><span data-stu-id="70e87-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

