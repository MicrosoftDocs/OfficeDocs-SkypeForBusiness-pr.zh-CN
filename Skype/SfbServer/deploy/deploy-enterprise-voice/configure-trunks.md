---
title: 在 Skype for Business Server 2015 中配置中继
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 摘要： 了解如何在 Skype 为业务服务器 2015年配置中介服务器和企业语音的对等方之间中继。
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a><span data-ttu-id="09714-103">在 Skype for Business Server 2015 中配置中继</span><span class="sxs-lookup"><span data-stu-id="09714-103">Configure trunks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="09714-104">**摘要：**了解如何在 Skype 为业务服务器 2015年配置中介服务器和企业语音的对等方之间中继。</span><span class="sxs-lookup"><span data-stu-id="09714-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="09714-105">作为企业语音部署的一部分，您可以配置中继间中介服务器和一个或多个以下等为企业语音客户端和设备在您的组织提供公用交换的电话网络 (PSTN) 连接：</span><span class="sxs-lookup"><span data-stu-id="09714-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="09714-106">到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接</span><span class="sxs-lookup"><span data-stu-id="09714-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="09714-107">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="09714-107">PSTN gateway</span></span>
    
- <span data-ttu-id="09714-108">专用交换机 (PBX)</span><span class="sxs-lookup"><span data-stu-id="09714-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="09714-109">有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="09714-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="09714-110">Skype 的业务服务器功能，支持多个网关之间的中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="09714-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="09714-111">这些关联进行定义的主干，是中介服务器池和公用交换的电话网络 (PSTN) 网关，会话边框控制器 (SBC) 或 IP PBX 之间的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="09714-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="09714-112">使用拓扑生成器将网关与中介服务器 （即，中继） 相关联。</span><span class="sxs-lookup"><span data-stu-id="09714-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="09714-113">要分配或删除业务服务器中 Skype 干线，您必须首先定义拓扑生成器中的主干。</span><span class="sxs-lookup"><span data-stu-id="09714-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="09714-114">干线包括以下关联： 中介服务器的完全合格的域名称 (FQDN)、 中介服务器侦听端口、 FQDN，网关和网关监听端口。</span><span class="sxs-lookup"><span data-stu-id="09714-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="09714-115">若要配置多个中继，可以创建多个相同的网关和中介服务器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="09714-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="09714-116">这提供了额外弹性企业语音基础结构，这是在 interoperational 方案的专用分组交换机 (PBX) 中尤其有用。</span><span class="sxs-lookup"><span data-stu-id="09714-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="09714-117">定义中继，必须将其与路由关联。</span><span class="sxs-lookup"><span data-stu-id="09714-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="09714-118">要关联到工艺路线干线，定义拓扑生成器主干的简单名称。</span><span class="sxs-lookup"><span data-stu-id="09714-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="09714-119">这个简单的名称用作业务服务器控件面板，中继可以与工艺路线相关联在 Skype 的干线名称。</span><span class="sxs-lookup"><span data-stu-id="09714-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="09714-120">简单的干线名称用作业务服务器管理外壳从 Skype 的网关名称。</span><span class="sxs-lookup"><span data-stu-id="09714-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="09714-121">管理员必须选择默认中继与中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="09714-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="09714-122">从拓扑生成器中，关联的中介服务器中，用鼠标右键单击，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="09714-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="09714-123">中介服务器指定的默认网关。</span><span class="sxs-lookup"><span data-stu-id="09714-123">Specify the default gateway for the Mediation Server.</span></span> 
  

