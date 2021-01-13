---
title: Skype for Business Server 中的多个中继支持
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 功能支持网关和中介服务器之间的多个关联。 这些关联通过定义中继来建立，中继是中介服务器池与公用电话交换网 (PSTN) 网关、会话边界控制器 (SBC) 或 IP-PBX 之间的逻辑关联。 使用拓扑生成器将网关与中介服务器 (即中继) 。
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826222"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="5af25-105">Skype for Business Server 中的多个中继支持</span><span class="sxs-lookup"><span data-stu-id="5af25-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="5af25-106">Skype for Business Server 功能支持网关和中介服务器之间的多个关联。</span><span class="sxs-lookup"><span data-stu-id="5af25-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="5af25-107">这些关联通过定义中继来建立，中继是中介服务器池与公用电话交换网 (PSTN) 网关、会话边界控制器 (SBC) 或 IP-PBX 之间的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="5af25-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="5af25-108">使用拓扑生成器将网关与中介服务器 (即中继) 。</span><span class="sxs-lookup"><span data-stu-id="5af25-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="5af25-109">若要在 Skype for Business Server 中分配或删除中继，必须先在拓扑生成器中定义中继。</span><span class="sxs-lookup"><span data-stu-id="5af25-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="5af25-110">中继包含以下关联：中介服务器完全限定域名 (FQDN) 、中介服务器侦听端口、网关 FQDN 和网关侦听端口。</span><span class="sxs-lookup"><span data-stu-id="5af25-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="5af25-111">若要配置多个中继，可以在同一网关和中介服务器之间创建多个关联。</span><span class="sxs-lookup"><span data-stu-id="5af25-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="5af25-112">这为网络基础结构企业语音复原能力，在专用交换机和 PBX (互操作) 尤其有用。</span><span class="sxs-lookup"><span data-stu-id="5af25-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="5af25-113">定义中继，必须将其与路由关联。</span><span class="sxs-lookup"><span data-stu-id="5af25-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="5af25-114">若要将中继与路由关联，请为拓扑生成器中的中继定义一个简单的名称。</span><span class="sxs-lookup"><span data-stu-id="5af25-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="5af25-115">此简单名称用作 Skype for Business Server 控制面板中的中继名称，其中中继可以与路由关联。</span><span class="sxs-lookup"><span data-stu-id="5af25-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="5af25-116">简单中继名称用作 Skype for Business Server 命令行管理程序 中的网关名称。</span><span class="sxs-lookup"><span data-stu-id="5af25-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="5af25-117">管理员必须选择与中介服务器关联的默认中继。</span><span class="sxs-lookup"><span data-stu-id="5af25-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="5af25-118">在拓扑生成器中，右键单击关联的中介服务器，然后单击"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="5af25-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="5af25-119">指定中介服务器的默认网关。</span><span class="sxs-lookup"><span data-stu-id="5af25-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="5af25-120">下图演示了为每个中介服务器和网关定义的多个中继。</span><span class="sxs-lookup"><span data-stu-id="5af25-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![多个中继分配](../../media/multiple-trunk-assignments.jpg)
