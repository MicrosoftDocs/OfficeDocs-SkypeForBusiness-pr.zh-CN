---
title: Lync Server 2013：对用于 XMPP 联盟的边缘池进行故障转移
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
ms.openlocfilehash: 9d1c76dc37ce1abb2d34c474d4144b0894d93a0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="cb1c1-102">在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="cb1c1-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb1c1-103">_**主题上次修改时间：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="cb1c1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="cb1c1-104">在你的组织中，有一个边界池指定为用于 XMPP 联合身份验证的池。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-104">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="cb1c1-105">如果此池停止运行，则必须故障转移 XMPP 联合身份验证才能使用其他边缘池，然后 XMPP 联盟才能再次工作。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-105">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="cb1c1-106">当你首次安装 Edge 池并启用 XMPP 联合身份验证时，你可以通过为 XMPP 联盟的所有边缘池设置外部 DNS SRV 记录（而不是仅一个）来简化灾难恢复过程。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="cb1c1-107">其中每个 SRV 记录都必须具有不同的优先级集。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="cb1c1-108">所有 XMPP 联盟流量都将经历具有最高优先级的 SRV 记录的池。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="cb1c1-109">有关启用和设置 XMPP 联合身份验证的详细信息，请参阅[在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="cb1c1-110">在以下过程中，EdgePool1 是最初托管 XMPP 联盟的池，EdgePool2 是池，它现在将托管 XMPP 联合。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="cb1c1-111">故障切换用于 XMPP 联盟的边缘池</span><span class="sxs-lookup"><span data-stu-id="cb1c1-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="cb1c1-112">如果尚未部署另一个边缘池（除了当前已关闭的），请部署该池。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="cb1c1-113">有关详细信息，请参阅[在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="cb1c1-114">在现在将托管 XMPP 联合身份验证（EdgePool2）的新边缘池中的每个边缘服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="cb1c1-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="cb1c1-115">运行以下 cmdlet 以将 XMPP 联盟路由 repoint 到 EdgePool2：</span><span class="sxs-lookup"><span data-stu-id="cb1c1-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="cb1c1-116">在此示例中，Site2 是包含边缘池的网站，它现在将托管 XMPP 联合路由，EdgeServer2.contoso.com 是该池中的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="cb1c1-117">在外部 DNS 服务器上，将 XMPP 联合的 DNS A 记录更改为指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="cb1c1-118">如果你还没有可解析为 XMPP 联合的 DNS SRV 记录，并且该记录将托管到将托管 XMPP 联合的边缘池，则必须添加它，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-118">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="cb1c1-119">此 SRV 记录必须具有端口值5269。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-119">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="cb1c1-120">验证现在将托管 XMPP 联合身份验证的边缘池是否具有端口5269在外部打开。</span><span class="sxs-lookup"><span data-stu-id="cb1c1-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="cb1c1-121">在边缘池中的所有边缘服务器上启动服务，现在将托管 XMPP 联合身份验证：</span><span class="sxs-lookup"><span data-stu-id="cb1c1-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

