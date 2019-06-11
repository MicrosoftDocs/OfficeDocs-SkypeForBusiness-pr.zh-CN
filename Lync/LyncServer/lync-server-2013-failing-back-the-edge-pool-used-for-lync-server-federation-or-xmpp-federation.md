---
title: 对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="ea823-102">在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="ea823-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea823-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ea823-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ea823-104">将用于托管联合身份验证的边缘池恢复为联机状态后, 请使用此过程将 Lync Server 联合身份验证路由和/或 XMPP 联盟路由重新故障, 以再次使用此还原的边缘池。</span><span class="sxs-lookup"><span data-stu-id="ea823-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="ea823-105">向还原的边缘池回切联合</span><span class="sxs-lookup"><span data-stu-id="ea823-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="ea823-106">在现在再次可用的 Edge 池中, 启动 Edge 服务。</span><span class="sxs-lookup"><span data-stu-id="ea823-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="ea823-107">如果你希望恢复 Lync Server 联合身份验证路由以使用还原的边缘服务器, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="ea823-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="ea823-108">在前端服务器上, 打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="ea823-108">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="ea823-109">展开 "**边缘池**", 然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="ea823-109">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="ea823-110">选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-110">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="ea823-111">在 "**编辑属性**" 下的 "**常规**" 下, 清除 "**为此边缘池启用联盟 (端口 5061)**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-111">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="ea823-112">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ea823-112">Click **OK**.</span></span>
    
      - <span data-ttu-id="ea823-113">展开 "**边缘池**", 然后右键单击要用于联盟的原始边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="ea823-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="ea823-114">选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="ea823-115">在 "**常规**" 下的 "**编辑属性**" 下, 选择 "**为此边缘池启用联盟 (端口 5061)**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-115">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="ea823-116">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ea823-116">Click **OK**.</span></span>
    
      - <span data-ttu-id="ea823-117">单击 "**操作**", 选择 "**拓扑**", 选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-117">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="ea823-118">当系统提示**发布拓扑**时, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-118">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="ea823-119">发布完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-119">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="ea823-120">在边缘服务器上, 打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="ea823-120">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="ea823-121">单击 "**安装或更新 Lync 服务器系统**", 然后单击 "**设置" 或 "删除 lync server 组件**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-121">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="ea823-122">再次单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-122">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="ea823-123">在 "安装 Lync 服务器组件" 中, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ea823-123">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="ea823-124">"摘要" 屏幕将显示执行时的操作。</span><span class="sxs-lookup"><span data-stu-id="ea823-124">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="ea823-125">部署完成后, 单击 "**查看日志**" 以查看可用的日志文件。</span><span class="sxs-lookup"><span data-stu-id="ea823-125">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="ea823-126">单击 "**完成**" 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="ea823-126">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="ea823-127">如果想要恢复 XMPP 联盟路由以使用还原的边缘服务器, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="ea823-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="ea823-128">运行以下 cmdlet 以将 XMPP 联盟路由 repoint 到边缘池, 该池现在将托管 XMPP 联合身份验证 (在此示例中, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="ea823-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="ea823-129">在此示例中, Site1 是包含边缘池的网站, 它现在将托管 XMPP 联合路由, EdgeServer1.contoso.com 是该池中的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ea823-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="ea823-130">如果你还没有可解析为 XMPP 联合的 DNS SRV 记录, 并且该记录将托管到将托管 XMPP 联合的边缘池, 则必须添加它, 如下例所示。</span><span class="sxs-lookup"><span data-stu-id="ea823-130">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="ea823-131">此 SRV 记录必须具有端口值5269。</span><span class="sxs-lookup"><span data-stu-id="ea823-131">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="ea823-132">在外部 DNS 服务器上, 将 XMPP 联合的 DNS A 记录更改为指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="ea823-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="ea823-133">验证现在将托管 XMPP 联合身份验证的边缘池是否具有端口5269在外部打开。</span><span class="sxs-lookup"><span data-stu-id="ea823-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="ea823-134">如果前端池仍在包含发生故障且已还原的边缘池的网站中运行, 则应在这些前端池上更新 Web 会议服务和 A/V 会议服务, 再次使用其本地网站上的边缘池。</span><span class="sxs-lookup"><span data-stu-id="ea823-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="ea823-135">有关详细信息, 请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="ea823-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="ea823-136">如果与失败的 Edge 池位于同一站点的前端池也失败, 您现在可以使用 Invoke-CsPoolFailback 来故障回复前端池。</span><span class="sxs-lookup"><span data-stu-id="ea823-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea823-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea823-137">See Also</span></span>


[<span data-ttu-id="ea823-138">在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="ea823-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="ea823-139">在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="ea823-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="ea823-140">Lync Server 2013 中的边缘服务器灾难恢复</span><span class="sxs-lookup"><span data-stu-id="ea823-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

