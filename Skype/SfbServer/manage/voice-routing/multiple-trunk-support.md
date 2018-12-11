---
title: Skype 中的业务服务器的多个中继支持
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 业务服务器功能的 Skype 支持多个网关和中介服务器之间的关联。 通过定义是中介服务器池和公用电话交换网 (pstn) 网关，会话边界控制器 (SBC) 或 IP PBX 之间的逻辑关联 a trunk 进行这些关联。 使用拓扑生成器将网关与中介服务器 （即，中继） 相关联。
ms.openlocfilehash: 086d345eb7492423526466cc77a2ce0d0d9a998e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222784"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="16a3d-105">Skype 中的业务服务器的多个中继支持</span><span class="sxs-lookup"><span data-stu-id="16a3d-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="16a3d-106">业务服务器功能的 Skype 支持多个网关和中介服务器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="16a3d-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="16a3d-107">通过定义是中介服务器池和公用电话交换网 (pstn) 网关，会话边界控制器 (SBC) 或 IP PBX 之间的逻辑关联 a trunk 进行这些关联。</span><span class="sxs-lookup"><span data-stu-id="16a3d-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="16a3d-108">使用拓扑生成器将网关与中介服务器 （即，中继） 相关联。</span><span class="sxs-lookup"><span data-stu-id="16a3d-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="16a3d-109">若要分配或删除业务服务器在 Skype 中继，必须首先在拓扑生成器中定义中继。</span><span class="sxs-lookup"><span data-stu-id="16a3d-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="16a3d-110">中继包含的以下关联： 中介服务器的完全限定域名 (FQDN)、 中介服务器侦听端口、 网关 FQDN，和网关侦听端口。</span><span class="sxs-lookup"><span data-stu-id="16a3d-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="16a3d-111">若要配置多个中继，可以创建多个同一个网关和中介服务器之间的关联。</span><span class="sxs-lookup"><span data-stu-id="16a3d-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="16a3d-112">这将提供企业语音基础结构，即在专用交换机 (pbx) interoperational 方案中尤其有用的其他恢复能力。</span><span class="sxs-lookup"><span data-stu-id="16a3d-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="16a3d-113">定义中继，必须将其与路由关联。</span><span class="sxs-lookup"><span data-stu-id="16a3d-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="16a3d-114">若要将路由到中继相关联，请拓扑生成器中定义中继的简单名称。</span><span class="sxs-lookup"><span data-stu-id="16a3d-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="16a3d-115">此简单名称用作中继可以路由相关联的业务 Server Control Panel 中 Skype 的中继名称。</span><span class="sxs-lookup"><span data-stu-id="16a3d-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="16a3d-116">简单 trunk 名称用作业务 Server 命令行管理程序 Skype 的网关名称。</span><span class="sxs-lookup"><span data-stu-id="16a3d-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="16a3d-117">管理员必须选择默认中继与中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="16a3d-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="16a3d-118">从拓扑生成器中，右键单击关联的中介服务器，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="16a3d-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="16a3d-119">为中介服务器指定默认网关。</span><span class="sxs-lookup"><span data-stu-id="16a3d-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="16a3d-120">下图说明了每个中介服务器和网关定义的多个中继。</span><span class="sxs-lookup"><span data-stu-id="16a3d-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![多个中继分配](../../media/multiple-trunk-assignments.jpg)