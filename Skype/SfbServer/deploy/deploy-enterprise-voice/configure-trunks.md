---
title: 在 Skype for Business 服务器中配置中继
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '摘要: 了解如何在 Skype for Business 服务器中配置用于企业语音的中介服务器和对等之间的主干。'
ms.openlocfilehash: 714c712816709e8f2211e752f87d20c8d2067c7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233655"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="8dae4-103">在 Skype for Business 服务器中配置中继</span><span class="sxs-lookup"><span data-stu-id="8dae4-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="8dae4-104">**摘要:** 了解如何在 Skype for Business 服务器中配置用于企业语音的中介服务器和对等之间的主干。</span><span class="sxs-lookup"><span data-stu-id="8dae4-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="8dae4-105">作为企业语音部署的一部分, 您可以在中介服务器和一个或多个以下对等方之间配置主干, 以便为企业语音客户端和组织中的设备提供公共交换电话网络 (PSTN) 连接:</span><span class="sxs-lookup"><span data-stu-id="8dae4-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="8dae4-106">到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接</span><span class="sxs-lookup"><span data-stu-id="8dae4-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="8dae4-107">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="8dae4-107">PSTN gateway</span></span>
    
- <span data-ttu-id="8dae4-108">专用交换机 (PBX)</span><span class="sxs-lookup"><span data-stu-id="8dae4-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="8dae4-109">有关更多详细信息, 请参阅[在 Skype For Business 服务器中规划 PSTN 连接](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="8dae4-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="8dae4-110">Skype for Business 服务器功能支持网关和中介服务器之间的多个关联。</span><span class="sxs-lookup"><span data-stu-id="8dae4-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="8dae4-111">这些关联通过定义主干 (这是中介服务器池和公共交换电话网络 (PSTN) 网关、会话边界控制器 (SBC) 或 ip-pbx) 之间的逻辑关联来进行。</span><span class="sxs-lookup"><span data-stu-id="8dae4-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="8dae4-112">使用拓扑生成器将网关与中介服务器相关联 (即中继)。</span><span class="sxs-lookup"><span data-stu-id="8dae4-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="8dae4-113">若要在 Skype for Business 服务器中分配或删除主干, 必须首先在拓扑生成器中定义一个主干。</span><span class="sxs-lookup"><span data-stu-id="8dae4-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="8dae4-114">主干包含以下关联: 中介服务器完全限定的域名 (FQDN)、中介服务器侦听端口、网关 FQDN 和网关侦听端口。</span><span class="sxs-lookup"><span data-stu-id="8dae4-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="8dae4-115">若要配置多个中继, 可以在同一网关和中介服务器之间创建多个关联。</span><span class="sxs-lookup"><span data-stu-id="8dae4-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="8dae4-116">这将为企业语音基础结构提供额外的复原, 这在专用分支 exchange (PBX) interoperational 方案中尤其有用。</span><span class="sxs-lookup"><span data-stu-id="8dae4-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="8dae4-117">定义中继，必须将其与路由关联。</span><span class="sxs-lookup"><span data-stu-id="8dae4-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="8dae4-118">若要将主干关联到路由, 请为拓扑生成器中的主干定义一个简单名称。</span><span class="sxs-lookup"><span data-stu-id="8dae4-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="8dae4-119">此简单名称用作 Skype for Business Server 控制面板中的主干名称, 其中中继可以与路线相关联。</span><span class="sxs-lookup"><span data-stu-id="8dae4-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="8dae4-120">简单主干名称用作 Skype for Business Server Management Shell 中的网关名称。</span><span class="sxs-lookup"><span data-stu-id="8dae4-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="8dae4-121">管理员必须选择与中介服务器关联的默认中继。</span><span class="sxs-lookup"><span data-stu-id="8dae4-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="8dae4-122">从拓扑生成器中, 右键单击关联的中介服务器, 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="8dae4-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="8dae4-123">指定中介服务器的默认网关。</span><span class="sxs-lookup"><span data-stu-id="8dae4-123">Specify the default gateway for the Mediation Server.</span></span> 
  

