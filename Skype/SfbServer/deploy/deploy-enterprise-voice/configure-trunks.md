---
title: 在 Skype for Business Server 中配置中继
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 摘要： 了解如何在 Skype for Business Server 中配置中介服务器与企业语音的对等方之间的中继。
ms.openlocfilehash: 7d40201cbf2305f464f66ead66ae3a8e7126ca03
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992390"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="ddc49-103">在 Skype for Business Server 中配置中继</span><span class="sxs-lookup"><span data-stu-id="ddc49-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="ddc49-104">**摘要：** 了解如何在 Skype for Business Server 中配置中介服务器与企业语音的对等方之间的中继。</span><span class="sxs-lookup"><span data-stu-id="ddc49-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="ddc49-105">作为企业语音部署的一部分，您可以配置中介服务器和一个或多个您的组织中的企业语音客户端和设备提供公用电话交换网 (pstn) 连接的以下的对等方之间中继：</span><span class="sxs-lookup"><span data-stu-id="ddc49-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="ddc49-106">到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接</span><span class="sxs-lookup"><span data-stu-id="ddc49-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="ddc49-107">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="ddc49-107">PSTN gateway</span></span>
    
- <span data-ttu-id="ddc49-108">专用交换机 (PBX)</span><span class="sxs-lookup"><span data-stu-id="ddc49-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="ddc49-109">有关详细信息，请参阅[规划中的业务服务器 Skype 的 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="ddc49-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="ddc49-110">业务服务器功能的 Skype 支持多个网关和中介服务器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="ddc49-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="ddc49-111">通过定义是中介服务器池和公用电话交换网 (pstn) 网关，会话边界控制器 (SBC) 或 IP PBX 之间的逻辑关联 a trunk 进行这些关联。</span><span class="sxs-lookup"><span data-stu-id="ddc49-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="ddc49-112">使用拓扑生成器将网关与中介服务器 （即，中继） 相关联。</span><span class="sxs-lookup"><span data-stu-id="ddc49-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="ddc49-113">若要分配或删除业务服务器在 Skype 中继，必须首先在拓扑生成器中定义中继。</span><span class="sxs-lookup"><span data-stu-id="ddc49-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="ddc49-114">中继包含的以下关联： 中介服务器的完全限定域名 (FQDN)、 中介服务器侦听端口、 网关 FQDN，和网关侦听端口。</span><span class="sxs-lookup"><span data-stu-id="ddc49-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="ddc49-115">若要配置多个中继，可以创建多个同一个网关和中介服务器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="ddc49-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="ddc49-116">这将提供企业语音基础结构，即在专用交换机 (pbx) interoperational 方案中尤其有用的其他恢复能力。</span><span class="sxs-lookup"><span data-stu-id="ddc49-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="ddc49-117">定义中继，必须将其与路由关联。</span><span class="sxs-lookup"><span data-stu-id="ddc49-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="ddc49-118">若要将路由到中继相关联，请拓扑生成器中定义中继的简单名称。</span><span class="sxs-lookup"><span data-stu-id="ddc49-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="ddc49-119">此简单名称用作中继可以路由相关联的业务 Server Control Panel 中 Skype 的中继名称。</span><span class="sxs-lookup"><span data-stu-id="ddc49-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="ddc49-120">简单 trunk 名称用作业务 Server 命令行管理程序 Skype 的网关名称。</span><span class="sxs-lookup"><span data-stu-id="ddc49-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="ddc49-121">管理员必须选择默认中继与中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="ddc49-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="ddc49-122">从拓扑生成器中，右键单击关联的中介服务器，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ddc49-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="ddc49-123">为中介服务器指定默认网关。</span><span class="sxs-lookup"><span data-stu-id="ddc49-123">Specify the default gateway for the Mediation Server.</span></span> 
  

