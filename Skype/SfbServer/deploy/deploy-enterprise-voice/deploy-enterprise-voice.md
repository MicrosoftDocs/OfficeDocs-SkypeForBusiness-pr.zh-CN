---
title: 在 Skype for Business 服务器中部署企业语音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：了解如何在中央站点部署适用于 Skype for Business 服务器的企业语音。
ms.openlocfilehash: 1b1b1d0f79d1730bd491314f4f4e97b43b0acb62
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767545"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="d5aa8-103">在 Skype for Business 服务器中部署企业语音</span><span class="sxs-lookup"><span data-stu-id="d5aa8-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="d5aa8-104">**摘要：** 了解如何在中心站点部署适用于 Skype for Business 服务器的企业语音。</span><span class="sxs-lookup"><span data-stu-id="d5aa8-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="d5aa8-105">使用本主题在中央站点部署企业语音。</span><span class="sxs-lookup"><span data-stu-id="d5aa8-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="d5aa8-106">若要在分支站点部署企业语音，请跳过[部署分支站点](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5aa8-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="d5aa8-107">本部分包括部署的过程，其中中介服务器在每个前端服务器或标准版服务器上 collocated，也可以使用独立的中介服务器池进行部署。如果你使用拓扑生成器定义和发布在每台前端服务器或标准版服务器上 collocates 中介服务器的拓扑，则可以跳过以下内容，因为部署向导已自动安装了文件在安装前端服务器池或标准版服务器的文件时，中介服务器：</span><span class="sxs-lookup"><span data-stu-id="d5aa8-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="d5aa8-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="d5aa8-108">In this section</span></span>

- [<span data-ttu-id="d5aa8-109">Skype for business 服务器中的企业语音的安全和配置先决条件</span><span class="sxs-lookup"><span data-stu-id="d5aa8-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="d5aa8-110">在 Skype for Business Server 的拓扑生成器中部署中介服务器</span><span class="sxs-lookup"><span data-stu-id="d5aa8-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="d5aa8-111">在 Skype for Business Server 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="d5aa8-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="d5aa8-112">在 Skype for Business Server 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="d5aa8-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="d5aa8-113">在 Skype for Business Server 中安装中介服务器的文件</span><span class="sxs-lookup"><span data-stu-id="d5aa8-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="d5aa8-114">在 Skype for Business 服务器中配置中继</span><span class="sxs-lookup"><span data-stu-id="d5aa8-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="d5aa8-115">在 Skype for Business Server 中创建或修改呼叫者 ID 演示文稿的翻译规则</span><span class="sxs-lookup"><span data-stu-id="d5aa8-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="d5aa8-116">在 Skype for Business Server 中创建或修改呼叫 ID 演示文稿的翻译规则</span><span class="sxs-lookup"><span data-stu-id="d5aa8-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="d5aa8-117">在 Skype for Business 中创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="d5aa8-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="d5aa8-118">在 Skype for Business 服务器中创建或修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="d5aa8-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="d5aa8-119">在 Skype for Business 中配置语音策略、PSTN 使用记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="d5aa8-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="d5aa8-120">在 Skype for business 服务器中启用企业语音用户</span><span class="sxs-lookup"><span data-stu-id="d5aa8-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="d5aa8-121">在 Skype for Business 服务器中部署高级企业语音功能</span><span class="sxs-lookup"><span data-stu-id="d5aa8-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="d5aa8-122">在 Skype for Business 中部署呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="d5aa8-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="d5aa8-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5aa8-123">See also</span></span>

[<span data-ttu-id="d5aa8-124">Skype for business Server 中的 "规划企业语音"</span><span class="sxs-lookup"><span data-stu-id="d5aa8-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

