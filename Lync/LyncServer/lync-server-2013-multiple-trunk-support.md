---
title: 'Lync Server 2013: 多个中继支持'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156db04ceb26809c7043f30e9e01ea0071e0a31d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="75e4c-102">Lync Server 2013 中的多个中继支持</span><span class="sxs-lookup"><span data-stu-id="75e4c-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75e4c-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="75e4c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="75e4c-104">Lync Server 2013 功能支持网关和中介服务器之间的多个关联。</span><span class="sxs-lookup"><span data-stu-id="75e4c-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="75e4c-105">这些关联通过定义主干 (这是中介服务器池和公共交换电话网络 (PSTN) 网关、会话边界控制器 (SBC) 或 ip-pbx) 之间的逻辑关联来进行。</span><span class="sxs-lookup"><span data-stu-id="75e4c-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="75e4c-106">使用拓扑生成器将网关与中介服务器相关联 (即中继)。</span><span class="sxs-lookup"><span data-stu-id="75e4c-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="75e4c-107">若要在 Lync Server 2013 中分配或删除主干, 必须首先在拓扑生成器中定义一个主干。</span><span class="sxs-lookup"><span data-stu-id="75e4c-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="75e4c-108">主干包含以下关联: 中介服务器完全限定的域名 (FQDN)、中介服务器侦听端口、网关 FQDN 和网关侦听端口。</span><span class="sxs-lookup"><span data-stu-id="75e4c-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="75e4c-109">若要配置多个中继, 可以在同一网关和中介服务器之间创建多个关联。</span><span class="sxs-lookup"><span data-stu-id="75e4c-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="75e4c-110">这将为企业语音基础结构提供额外的复原, 这在专用分支 exchange (PBX) interoperational 方案中尤其有用。</span><span class="sxs-lookup"><span data-stu-id="75e4c-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="75e4c-111">定义中继，必须将其与路由关联。</span><span class="sxs-lookup"><span data-stu-id="75e4c-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="75e4c-112">若要将主干关联到路由, 请为拓扑生成器中的主干定义一个简单名称。</span><span class="sxs-lookup"><span data-stu-id="75e4c-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="75e4c-113">此简单名称用作 Lync Server 控制面板中的主干名称, 其中中继可以与路由相关联。</span><span class="sxs-lookup"><span data-stu-id="75e4c-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="75e4c-114">简单主干名称用作 Lync Server 命令行管理程序中的网关名称。</span><span class="sxs-lookup"><span data-stu-id="75e4c-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="75e4c-115">管理员必须选择与中介服务器关联的默认中继。</span><span class="sxs-lookup"><span data-stu-id="75e4c-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="75e4c-116">从拓扑生成器中, 右键单击关联的中介服务器, 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="75e4c-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="75e4c-117">指定中介服务器的默认网关。</span><span class="sxs-lookup"><span data-stu-id="75e4c-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="75e4c-118">下图显示了为每个中介服务器和网关定义的多个中继。</span><span class="sxs-lookup"><span data-stu-id="75e4c-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="75e4c-119">**M-N 中继路由**</span><span class="sxs-lookup"><span data-stu-id="75e4c-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="75e4c-120">![多个中继分配。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多个中继分配。")</span><span class="sxs-lookup"><span data-stu-id="75e4c-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

