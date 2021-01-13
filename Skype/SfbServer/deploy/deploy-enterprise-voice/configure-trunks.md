---
title: 在 Skype for Business Server 中配置中继
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 摘要：了解如何在 Skype for Business Server 中配置中介服务器和对等方企业语音中继。
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824952"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="423cd-103">在 Skype for Business Server 中配置中继</span><span class="sxs-lookup"><span data-stu-id="423cd-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="423cd-104">**摘要：** 了解如何在中介服务器和对等方之间为 Skype for Business Server 企业语音中继。</span><span class="sxs-lookup"><span data-stu-id="423cd-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="423cd-105">作为 企业语音 部署的一部分，可以在中介服务器和以下一个或多个对等方之间配置中继，为您的组织中的 企业语音 客户端和设备提供公用电话交换网 (PSTN) 连接：</span><span class="sxs-lookup"><span data-stu-id="423cd-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="423cd-106">到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接</span><span class="sxs-lookup"><span data-stu-id="423cd-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="423cd-107">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="423cd-107">PSTN gateway</span></span>
    
- <span data-ttu-id="423cd-108">专用交换机 (PBX)</span><span class="sxs-lookup"><span data-stu-id="423cd-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="423cd-109">有关详细信息，请参阅 [Skype for Business Server 中的 PSTN 连接规划](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="423cd-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="423cd-110">Skype for Business Server 功能支持网关和中介服务器之间的多个关联。</span><span class="sxs-lookup"><span data-stu-id="423cd-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="423cd-111">这些关联通过定义中继来建立，中继是中介服务器池与公用电话交换网 (PSTN) 网关、会话边界控制器 (SBC) 或 IP-PBX 之间的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="423cd-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="423cd-112">使用拓扑生成器将网关与中介服务器 (即中继) 。</span><span class="sxs-lookup"><span data-stu-id="423cd-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="423cd-113">若要在 Skype for Business Server 中分配或删除中继，必须先在拓扑生成器中定义中继。</span><span class="sxs-lookup"><span data-stu-id="423cd-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="423cd-114">中继包含以下关联：中介服务器完全限定域名 (FQDN) 、中介服务器侦听端口、网关 FQDN 和网关侦听端口。</span><span class="sxs-lookup"><span data-stu-id="423cd-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="423cd-115">若要配置多个中继，可以在同一网关和中介服务器之间创建多个关联。</span><span class="sxs-lookup"><span data-stu-id="423cd-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="423cd-116">这为网络基础结构企业语音复原能力，在专用交换机和 PBX (互操作) 尤其有用。</span><span class="sxs-lookup"><span data-stu-id="423cd-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="423cd-117">定义中继，必须将其与路由关联。</span><span class="sxs-lookup"><span data-stu-id="423cd-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="423cd-118">若要将中继与路由关联，请为拓扑生成器中的中继定义一个简单的名称。</span><span class="sxs-lookup"><span data-stu-id="423cd-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="423cd-119">此简单名称用作 Skype for Business Server 控制面板中的中继名称，其中中继可以与路由关联。</span><span class="sxs-lookup"><span data-stu-id="423cd-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="423cd-120">简单中继名称用作 Skype for Business Server 命令行管理程序 中的网关名称。</span><span class="sxs-lookup"><span data-stu-id="423cd-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="423cd-121">管理员必须选择与中介服务器关联的默认中继。</span><span class="sxs-lookup"><span data-stu-id="423cd-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="423cd-122">在拓扑生成器中，右键单击关联的中介服务器，然后单击"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="423cd-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="423cd-123">指定中介服务器的默认网关。</span><span class="sxs-lookup"><span data-stu-id="423cd-123">Specify the default gateway for the Mediation Server.</span></span> 
  

