---
title: 在 Skype for Business Server 2015 中部署呼叫允许控制
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。 有关详细信息，请参阅 Plan for Skype 中的呼叫允许控制的业务服务器 2015年。
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="14d6c-104">在 Skype for Business Server 2015 中部署呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="14d6c-104">Deploy call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="14d6c-105">呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。</span><span class="sxs-lookup"><span data-stu-id="14d6c-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="14d6c-106">有关详细信息，请参阅[规划中的业务服务器 2015 Skype 的呼叫允许控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="14d6c-106">For more information, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="14d6c-107">部署呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="14d6c-107">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="14d6c-108">收集有关您企业的网络拓扑，所需的信息的所有中所述[示例： 收集业务服务器 2015 Skype 中的呼叫允许控制的要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="14d6c-108">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="14d6c-109">如果还未这样做，就必须定义网络区域和站点，然后将子网与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="14d6c-109">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="14d6c-110">有关详细信息，请参阅[Deploy 网络区域、 网站和业务 2015年的 Skype 中的子网](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="14d6c-110">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
3. <span data-ttu-id="14d6c-111">创建带宽策略配置文件，按[创建带宽策略配置文件中的业务服务器 2015 Skype](create-bandwidth-policy-profiles.md)中所述</span><span class="sxs-lookup"><span data-stu-id="14d6c-111">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server 2015](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="14d6c-112">创建网络区域链接，按[创建网络区域链接中的业务服务器 2015 Skype](create-network-region-links.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="14d6c-112">Create network region links, as detailed in [Create network region links in Skype for Business Server 2015](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="14d6c-113">创建网络区域间路由，按[创建网络中的业务服务器 2015 Skype 的 interregional 路由](create-network-interregional-routes.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="14d6c-113">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server 2015](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="14d6c-114">创建网络站点间策略，按[创建网络站点间策略中的业务服务器 2015 Skype](create-network-intersite-policies.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="14d6c-114">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server 2015](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="14d6c-115">启用呼叫允许控制，如[启用呼叫允许控制业务服务器 2015年的 Skype 中](enable-call-admission-control.md)所述。</span><span class="sxs-lookup"><span data-stu-id="14d6c-115">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="14d6c-116">检查几项最终设置，确保一切设置正确。</span><span class="sxs-lookup"><span data-stu-id="14d6c-116">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="14d6c-117">有关详细信息，请参阅[呼叫允许控制部署： 最终清单业务服务器 2015年的 Skype](final-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="14d6c-117">For details, see [Call admission control deployment: final checklist for Skype for Business Server 2015](final-checklist.md).</span></span>
    

