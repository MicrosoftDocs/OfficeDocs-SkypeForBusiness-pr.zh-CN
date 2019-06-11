---
title: 'Lync Server 2013: 混合和拆分域-自动发现'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 389288a695f7e8ed96ab72d16f612ffd92a7b013
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="1c3df-102">Lync Server 2013 中的混合和拆分域自动发现</span><span class="sxs-lookup"><span data-stu-id="1c3df-102">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c3df-103">_**主题上次修改时间:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="1c3df-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="1c3df-104">共享 SIP 地址空间 (也称为*拆分域*部署或*混合*部署) 是在内部部署和联机环境中部署用户的配置。</span><span class="sxs-lookup"><span data-stu-id="1c3df-104">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="1c3df-105">所需的结果是让用户无论其主服务器位于何处 (内部部署还是联机), 登录到部署并被重定向到其主服务器位置。</span><span class="sxs-lookup"><span data-stu-id="1c3df-105">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="1c3df-106">为了实现此目的, Lync Server 2013 的自动发现功能用于将联机用户重定向到联机拓扑。</span><span class="sxs-lookup"><span data-stu-id="1c3df-106">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="1c3df-107">你可以通过使用 Lync Server Management Shell、 **CsHostingProvider** Cmdlet 和**CsHostingProvider** cmdlet 配置自动发现统一资源定位器 (URL) 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1c3df-107">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="1c3df-108">拆分域部署的移动性</span><span class="sxs-lookup"><span data-stu-id="1c3df-108">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="1c3df-109">你将需要收集和记录以下已部署的属性:</span><span class="sxs-lookup"><span data-stu-id="1c3df-109">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="1c3df-110">从 Lync Server 命令行管理程序中, 键入</span><span class="sxs-lookup"><span data-stu-id="1c3df-110">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="1c3df-111">在结果中, 查找具有属性**ProxyFQDN**的联机提供程序。</span><span class="sxs-lookup"><span data-stu-id="1c3df-111">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="1c3df-112">例如, sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="1c3df-112">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="1c3df-113">记录 ProxyFQDN 的值。</span><span class="sxs-lookup"><span data-stu-id="1c3df-113">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="1c3df-114">在本地 Lync Server "控制面板" 中启用联盟, 从而允许与联机提供程序进行联盟。</span><span class="sxs-lookup"><span data-stu-id="1c3df-114">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="1c3df-115">为联机提供程序启用联盟。</span><span class="sxs-lookup"><span data-stu-id="1c3df-115">Enable federation for the online provider.</span></span> <span data-ttu-id="1c3df-116">默认情况下, 将为域联盟启用所有联机用户, 并且可以与所有域通信。</span><span class="sxs-lookup"><span data-stu-id="1c3df-116">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="1c3df-117">如果你要定义阻止的域和允许的域, 请确定你将明确允许或显式阻止的域。</span><span class="sxs-lookup"><span data-stu-id="1c3df-117">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="1c3df-118">对于联机联盟, 你必须为防火墙例外、证书和 DNS 主机 (如果使用 IPv6) 记录制定计划。</span><span class="sxs-lookup"><span data-stu-id="1c3df-118">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="1c3df-119">此外, 必须配置联合身份验证策略。</span><span class="sxs-lookup"><span data-stu-id="1c3df-119">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="1c3df-120">有关详细信息, 请参阅[规划 Lync Server 2013 和 Office 通信服务器联合身份验证](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="1c3df-120">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

