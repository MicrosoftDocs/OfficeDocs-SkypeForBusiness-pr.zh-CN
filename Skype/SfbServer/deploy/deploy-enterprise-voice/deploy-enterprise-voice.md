---
title: 为业务服务器部署中 Skype 的企业语音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 摘要： 了解如何在中央站点的业务服务器 Skype 部署企业语音。
ms.openlocfilehash: 85abf6cc99224fc2a36eb37cd5e9441073ce6165
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23241432"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="7d22e-103">为业务服务器部署中 Skype 的企业语音</span><span class="sxs-lookup"><span data-stu-id="7d22e-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="7d22e-104">**摘要：** 了解如何在中央站点的业务服务器 Skype 部署企业语音。</span><span class="sxs-lookup"><span data-stu-id="7d22e-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="7d22e-105">使用本主题将在中央站点的企业语音部署。</span><span class="sxs-lookup"><span data-stu-id="7d22e-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="7d22e-106">若要部署企业语音，在分支站点，请跳到[部署分支站点](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7d22e-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="7d22e-107">本节包括部署过程中的中介服务器并置在每台前端服务器或 Standard Edition 服务器上的建议，以及对于有独立的中介服务器池的部署。如果您使用拓扑生成器定义和发布拓扑的并置中介服务器上每个前端服务器或 Standard Edition 服务器，因为部署向导已自动安装的文件，则可以跳过以下内容安装前端服务器池或 Standard Edition server 的文件时的中介服务器：</span><span class="sxs-lookup"><span data-stu-id="7d22e-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="7d22e-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="7d22e-108">In this section</span></span>

- [<span data-ttu-id="7d22e-109">Skype 业务服务器中的企业语音的安全性和配置先决条件</span><span class="sxs-lookup"><span data-stu-id="7d22e-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="7d22e-110">业务服务器部署在拓扑生成器中 Skype 在中介服务器</span><span class="sxs-lookup"><span data-stu-id="7d22e-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="7d22e-111">为业务服务器中 Skype 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="7d22e-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="7d22e-112">为业务服务器中 Skype 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="7d22e-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="7d22e-113">安装 Business Server Skype 中的中介服务器的文件</span><span class="sxs-lookup"><span data-stu-id="7d22e-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="7d22e-114">在 Skype for Business Server 中配置中继</span><span class="sxs-lookup"><span data-stu-id="7d22e-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="7d22e-115">创建或修改转换规则的呼叫者 ID 演示文稿中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="7d22e-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="7d22e-116">创建或修改转换规则的呼叫 ID 演示文稿中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="7d22e-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="7d22e-117">创建或修改规范化规则中的业务的 Skype</span><span class="sxs-lookup"><span data-stu-id="7d22e-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="7d22e-118">创建或修改拨号计划中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="7d22e-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="7d22e-119">Skype for Business 中配置语音策略、 PSTN 用法记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="7d22e-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="7d22e-120">Skype 中的企业语音的用户启用企业服务器</span><span class="sxs-lookup"><span data-stu-id="7d22e-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="7d22e-121">为业务服务器部署中 Skype 的高级的企业语音功能</span><span class="sxs-lookup"><span data-stu-id="7d22e-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="7d22e-122">部署 Skype for Business 中的呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="7d22e-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="7d22e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d22e-123">See also</span></span>

[<span data-ttu-id="7d22e-124">规划业务服务器的 Skype 中的企业语音</span><span class="sxs-lookup"><span data-stu-id="7d22e-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

