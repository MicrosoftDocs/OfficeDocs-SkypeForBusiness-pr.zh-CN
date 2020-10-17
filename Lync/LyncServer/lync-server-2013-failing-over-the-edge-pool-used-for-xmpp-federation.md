---
title: Lync Server 2013：对用于 XMPP 联盟的边缘池进行故障转移
description: Lync Server 2013：对用于 XMPP 联盟的边缘池进行故障转移。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccdfe119258b4d09ddedefb22d0272d72003bf04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554898"
---
# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="71a6a-103">在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="71a6a-103">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71a6a-104">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="71a6a-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="71a6a-p101">在您的组织中，已将一个边缘池指定为用于 XMPP 联盟的池。如果该池出现故障，您必须先对 XMPP 联盟进行故障转移以使用其他边缘池，直到 XMPP 联盟可重新正常工作。</span><span class="sxs-lookup"><span data-stu-id="71a6a-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="71a6a-107">在您首次安装边缘池并启用 XMPP 联盟时，您可以通过为 XMPP 联盟的所有（而不只是一个）边缘池设置外部 DNS SRV 记录来简化灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="71a6a-107">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="71a6a-108">所有这些 SRV 记录都必须具有不同的优先级设置。</span><span class="sxs-lookup"><span data-stu-id="71a6a-108">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="71a6a-109">所有 XMPP 联盟流量将通过具有优先级最高的 SRV 记录的池。</span><span class="sxs-lookup"><span data-stu-id="71a6a-109">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="71a6a-110">有关启用和设置 XMPP 联盟的详细信息，请参阅 [在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="71a6a-110">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="71a6a-111">在以下过程中，EdgePool1 是最初承载 XMPP 联盟的池，EdgePool2 是现在承载 XMPP 联盟的池。</span><span class="sxs-lookup"><span data-stu-id="71a6a-111">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="71a6a-112">对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="71a6a-112">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="71a6a-113">如果您尚未部署另一个边缘池（当前出现故障的边缘池之外的池），请部署该池。</span><span class="sxs-lookup"><span data-stu-id="71a6a-113">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="71a6a-114">有关详细信息，请参阅 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="71a6a-114">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="71a6a-115">在现在承载 XMPP 联盟的新边缘池 (EdgePool2) 中的每个边缘服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="71a6a-115">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="71a6a-116">运行以下 cmdlet 可将 XMPP 联盟路由重新指向 EdgePool2：</span><span class="sxs-lookup"><span data-stu-id="71a6a-116">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="71a6a-117">在此示例中，Site2 是包括现在承载 XMPP 联盟路由的边缘池的站点，EdgeServer2.contoso.com 是该池中某个边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="71a6a-117">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="71a6a-118">在外部 DNS 服务器上，将 XMPP 联盟的 DNS A 记录更改为指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="71a6a-118">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="71a6a-p104">如果您尚不具有解析为现在承载 XMPP 联盟的边缘池的 XMPP 联盟的 DNS SRV 记录，则必须添加它，如以下示例中所示。此 SRV 记录的端口值必须为 5269。</span><span class="sxs-lookup"><span data-stu-id="71a6a-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="71a6a-121">确认现在承载 XMPP 联盟的边缘池具有已外部打开的端口 5269。</span><span class="sxs-lookup"><span data-stu-id="71a6a-121">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="71a6a-122">在现在承载 XMPP 联盟的边缘池中的所有边缘服务器上启动服务：</span><span class="sxs-lookup"><span data-stu-id="71a6a-122">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

