---
title: Lync Server 2013：混合和拆分域-自动发现
description: Lync Server 2013：混合和拆分域自动发现。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972233fd10d2b68a002d2d3a203f61bb0bd29574
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554878"
---
# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="592b1-103">Lync Server 2013 中的混合和拆分域自动发现</span><span class="sxs-lookup"><span data-stu-id="592b1-103">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="592b1-104">_**上次修改的主题：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="592b1-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="592b1-105">共享 SIP 地址空间（也称为 *拆分域* 部署或 *混合* 部署）是在本地部署和联机环境中部署用户的配置。</span><span class="sxs-lookup"><span data-stu-id="592b1-105">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="592b1-106">所需的结果是，无论用户的主服务器位于何处 (本地或联机) ，都会登录到部署并重定向到其主服务器位置。</span><span class="sxs-lookup"><span data-stu-id="592b1-106">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="592b1-107">为实现此目的，Lync Server 2013 的自动发现功能用于将联机用户重定向到联机拓扑。</span><span class="sxs-lookup"><span data-stu-id="592b1-107">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="592b1-108">为此，可以通过使用 Lync Server 命令行管理程序、 **CsHostingProvider** Cmdlet 和 **CsHostingProvider** Cmdlet 来配置自动发现统一资源定位器 (URL) 。</span><span class="sxs-lookup"><span data-stu-id="592b1-108">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="592b1-109">拆分域部署的移动性</span><span class="sxs-lookup"><span data-stu-id="592b1-109">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="592b1-110">您需要收集和记录下列部署的属性：</span><span class="sxs-lookup"><span data-stu-id="592b1-110">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="592b1-111">在 Lync Server 命令行管理程序中，键入</span><span class="sxs-lookup"><span data-stu-id="592b1-111">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="592b1-112">在结果中，查找具有属性 **ProxyFQDN** 的在线提供商。</span><span class="sxs-lookup"><span data-stu-id="592b1-112">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="592b1-113">例如，sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="592b1-113">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="592b1-114">记录 ProxyFQDN 的值。</span><span class="sxs-lookup"><span data-stu-id="592b1-114">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="592b1-115">在内部部署 Lync Server 控制面板中启用联合，以允许与联机提供程序进行联盟。</span><span class="sxs-lookup"><span data-stu-id="592b1-115">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="592b1-116">为在线提供商启用联盟。</span><span class="sxs-lookup"><span data-stu-id="592b1-116">Enable federation for the online provider.</span></span> <span data-ttu-id="592b1-117">默认情况下，所有联机用户都启用了域联盟，并且可以与所有域进行通信。</span><span class="sxs-lookup"><span data-stu-id="592b1-117">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="592b1-118">如果要定义阻止和允许的域，请确定您将明确允许或显式阻止的域。</span><span class="sxs-lookup"><span data-stu-id="592b1-118">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="592b1-119">对于联机联盟，如果使用 IPv6) 记录，则必须规划防火墙例外、证书和 DNS 主机 (A 或 AAAA。</span><span class="sxs-lookup"><span data-stu-id="592b1-119">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="592b1-120">此外，您还必须配置联盟策略。</span><span class="sxs-lookup"><span data-stu-id="592b1-120">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="592b1-121">有关详细信息，请参阅 [规划 Lync Server 2013 和 Office 通信服务器联合](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="592b1-121">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

