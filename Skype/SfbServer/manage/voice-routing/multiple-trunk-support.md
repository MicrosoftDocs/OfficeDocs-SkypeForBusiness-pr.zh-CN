---
title: Skype for Business 服务器中的多个中继支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business 服务器功能支持网关和中介服务器之间的多个关联。 这些关联通过定义主干 (这是中介服务器池和公共交换电话网络 (PSTN) 网关、会话边界控制器 (SBC) 或 ip-pbx) 之间的逻辑关联来进行。 使用拓扑生成器将网关与中介服务器相关联 (即中继)。
ms.openlocfilehash: a6a0134ee04d939a10aaf9e36c81124d085af5aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274910"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="9d1e7-105">Skype for Business 服务器中的多个中继支持</span><span class="sxs-lookup"><span data-stu-id="9d1e7-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="9d1e7-106">Skype for Business 服务器功能支持网关和中介服务器之间的多个关联。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="9d1e7-107">这些关联通过定义主干 (这是中介服务器池和公共交换电话网络 (PSTN) 网关、会话边界控制器 (SBC) 或 ip-pbx) 之间的逻辑关联来进行。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="9d1e7-108">使用拓扑生成器将网关与中介服务器相关联 (即中继)。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="9d1e7-109">若要在 Skype for Business 服务器中分配或删除主干, 必须首先在拓扑生成器中定义一个主干。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="9d1e7-110">主干包含以下关联: 中介服务器完全限定的域名 (FQDN)、中介服务器侦听端口、网关 FQDN 和网关侦听端口。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="9d1e7-111">若要配置多个中继, 可以在同一网关和中介服务器之间创建多个关联。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="9d1e7-112">这将为企业语音基础结构提供额外的复原, 这在专用分支 exchange (PBX) interoperational 方案中尤其有用。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="9d1e7-113">定义中继，必须将其与路由关联。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="9d1e7-114">若要将主干关联到路由, 请为拓扑生成器中的主干定义一个简单名称。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="9d1e7-115">此简单名称用作 Skype for Business Server 控制面板中的主干名称, 其中中继可以与路线相关联。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="9d1e7-116">简单主干名称用作 Skype for Business Server Management Shell 中的网关名称。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="9d1e7-117">管理员必须选择与中介服务器关联的默认中继。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="9d1e7-118">从拓扑生成器中, 右键单击关联的中介服务器, 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="9d1e7-119">指定中介服务器的默认网关。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="9d1e7-120">下图显示了为每个中介服务器和网关定义的多个中继。</span><span class="sxs-lookup"><span data-stu-id="9d1e7-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![多个中继分配](../../media/multiple-trunk-assignments.jpg)
