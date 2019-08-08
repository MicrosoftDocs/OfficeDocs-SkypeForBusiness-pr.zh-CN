---
title: 在 Skype for Business 服务器中部署呼叫许可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。
ms.openlocfilehash: 0b2df103c432cd6b304f93b3a36af6e87c4bc2e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233188"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="29f66-103">在 Skype for Business 服务器中部署呼叫许可控制</span><span class="sxs-lookup"><span data-stu-id="29f66-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="29f66-104">呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。</span><span class="sxs-lookup"><span data-stu-id="29f66-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="29f66-105">有关详细信息, 请参阅[在 Skype For Business 服务器中计划呼叫许可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="29f66-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="29f66-106">部署呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="29f66-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="29f66-107">为您的企业网络拓扑收集所有所需的信息, 如示例所述[: 在 Skype For Business 服务器中收集呼叫许可控制的要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="29f66-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="29f66-108">如果还未这样做，就必须定义网络区域和站点，然后将子网与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="29f66-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="29f66-109">有关详细信息, 请参阅[在 Skype For business 中部署网络区域、网站和子网](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="29f66-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="29f66-110">创建带宽策略配置文件, 详细信息请见在[Skype For Business Server 中创建带宽策略配置文件中](create-bandwidth-policy-profiles.md)的详细信息</span><span class="sxs-lookup"><span data-stu-id="29f66-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="29f66-111">创建网络区域链接, 详细信息请见在[Skype For Business 服务器中创建网络区域链接](create-network-region-links.md)中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="29f66-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="29f66-112">创建网络区域内路由, 详细信息请见在[Skype For Business 服务器中创建网络 interregional 路由](create-network-interregional-routes.md)中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="29f66-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="29f66-113">创建网络站点间策略, 详细信息请见在[Skype For Business 服务器中创建网络站点间策略](create-network-intersite-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="29f66-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="29f66-114">启用呼叫许可控制, 如在[Skype For Business 服务器的 "启用呼叫许可控制](enable-call-admission-control.md)" 中详细介绍。</span><span class="sxs-lookup"><span data-stu-id="29f66-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="29f66-115">检查几项最终设置，确保一切设置正确。</span><span class="sxs-lookup"><span data-stu-id="29f66-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="29f66-116">有关详细信息, 请参阅[呼叫许可控制部署: Skype for Business 服务器的最终清单](final-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="29f66-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

