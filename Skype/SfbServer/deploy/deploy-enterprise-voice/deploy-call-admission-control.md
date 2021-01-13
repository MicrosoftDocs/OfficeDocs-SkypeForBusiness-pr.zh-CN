---
title: 在 Skype for Business Server 中部署呼叫允许控制
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 呼叫允许控制 (CAC) 是一种解决方案，可确定是否可以基于可用带宽建立实时会话，以帮助防止出现塞塞的网络上用户的差音频/视频质量。
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836882"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="cb201-103">在 Skype for Business Server 中部署呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="cb201-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="cb201-104">呼叫允许控制 (CAC) 是一种解决方案，可确定是否可以基于可用带宽建立实时会话，以帮助防止出现塞塞的网络上用户的差音频/视频质量。</span><span class="sxs-lookup"><span data-stu-id="cb201-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="cb201-105">有关详细信息，请参阅规划 [Skype for Business Server 中的呼叫允许控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="cb201-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="cb201-106">部署呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="cb201-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="cb201-107">收集企业网络拓扑的所有所需信息，如示例所述：收集 Skype for Business Server 中呼叫 [允许控制的要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb201-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="cb201-108">如果尚未定义，则必须定义网络区域与站点，并将子网与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="cb201-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="cb201-109">有关详细信息，请参阅在 Skype for Business 中部署网络区域 [、站点和子网](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="cb201-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="cb201-110">创建带宽策略配置文件，如 [Skype for Business Server 中的"创建带宽策略配置文件"中详述](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cb201-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="cb201-111">创建网络区域链接，如 Skype for Business Server 中的"创建网络 [区域链接"中详述](create-network-region-links.md)。</span><span class="sxs-lookup"><span data-stu-id="cb201-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="cb201-112">创建网络区域间路由，如 Skype for Business Server 中的"创建网络 [区域间路由"中详述](create-network-interregional-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="cb201-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="cb201-113">创建网络站点间策略，如 Skype for Business Server 中的"创建 [网络站点间策略"中详述](create-network-intersite-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cb201-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="cb201-114">启用呼叫允许控制，如 Skype for Business Server 中的"启用呼叫 [允许控制"中详述](enable-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="cb201-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="cb201-115">检查一些最终设置，以确保一切设置正确。</span><span class="sxs-lookup"><span data-stu-id="cb201-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="cb201-116">有关详细信息，请参阅呼叫 [允许控制部署：Skype for Business Server 的最终清单](final-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="cb201-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

