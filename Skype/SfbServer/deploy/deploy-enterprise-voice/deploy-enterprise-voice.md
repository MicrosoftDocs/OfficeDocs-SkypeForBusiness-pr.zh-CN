---
title: Deploy 企业语音 in Skype for Business Server
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
description: 摘要：了解如何在中央站点企业语音 Skype for Business Server 部署 Skype for Business Server。
ms.openlocfilehash: c2aead4d42a02acce6b0db9f92866dba3a6e956d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104968"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="2df37-103">Deploy 企业语音 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2df37-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="2df37-104">**摘要：** 了解如何在中央站点企业语音 Skype for Business Server 部署 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="2df37-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="2df37-105">使用本主题在企业语音部署网站。</span><span class="sxs-lookup"><span data-stu-id="2df37-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="2df37-106">若要在企业语音部署分支站点，请跳到部署 [分支站点](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites)。</span><span class="sxs-lookup"><span data-stu-id="2df37-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span></span>

<span data-ttu-id="2df37-107">本节包括部署过程，其中中介服务器根据建议并位于每台前端服务器或 Standard Edition Server 上，还适用于具有独立中介服务器池的部署。如果使用拓扑生成器定义并发布在每台前端服务器或 Standard Edition 服务器上并排中介服务器的拓扑，可以跳过以下内容，因为在为前端服务器池或 Standard Edition Server 安装文件时，部署向导已自动为中介服务器安装文件：</span><span class="sxs-lookup"><span data-stu-id="2df37-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="2df37-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="2df37-108">In this section</span></span>

- [<span data-ttu-id="2df37-109">Skype for Business Server 企业语音的安全性和配置先决条件</span><span class="sxs-lookup"><span data-stu-id="2df37-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="2df37-110">在 Skype for Business Server 的拓扑生成器中部署中介服务器</span><span class="sxs-lookup"><span data-stu-id="2df37-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="2df37-111">在 Skype for Business Server 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="2df37-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="2df37-112">在 Skype for Business Server 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="2df37-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="2df37-113">在 Skype for Business Server 中安装中介服务器文件</span><span class="sxs-lookup"><span data-stu-id="2df37-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="2df37-114">在 Skype for Business Server 中配置中继</span><span class="sxs-lookup"><span data-stu-id="2df37-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="2df37-115">在 Skype for Business Server 中为呼叫者 ID 演示文稿创建或修改转换规则</span><span class="sxs-lookup"><span data-stu-id="2df37-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="2df37-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2df37-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="2df37-117">在 Skype for Business 中创建或修改规范化规则</span><span class="sxs-lookup"><span data-stu-id="2df37-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="2df37-118">在 Skype for Business Server 中创建或修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="2df37-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="2df37-119">在 Skype for Business 中配置语音策略、PSTN 用法记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="2df37-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="2df37-120">在 Skype for Business Server 企业语音用户进行登录</span><span class="sxs-lookup"><span data-stu-id="2df37-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="2df37-121">Deploy advanced 企业语音 features in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2df37-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="2df37-122">在 Skype for Business 中部署呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="2df37-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="2df37-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2df37-123">See also</span></span>

[<span data-ttu-id="2df37-124">Plan for 企业语音 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2df37-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)