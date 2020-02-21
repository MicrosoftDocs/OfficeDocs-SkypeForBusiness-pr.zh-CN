---
title: 对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3531e50efec5d981249e892c692a20095bef9eff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="ab8c0-102">在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="ab8c0-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab8c0-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ab8c0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ab8c0-104">在出故障的用于承载联盟的边缘池重新联机后，使用此过程对 Lync Server 联盟路由和/或 XMPP 联盟路由进行故障回复以再次使用这一恢复的边缘池。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="ab8c0-105">将联盟故障回复到恢复的边缘池</span><span class="sxs-lookup"><span data-stu-id="ab8c0-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="ab8c0-106">在此时再次可用的边缘池上，启动边缘服务。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="ab8c0-107">如果想要对 Lync Server 联盟路由进行故障回复以使用恢复的边缘服务器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ab8c0-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="ab8c0-p101">在前端服务器上，打开拓扑生成器。展开“边缘池”\*\*\*\*，然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。选择“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="ab8c0-p102">在“编辑属性”\*\*\*\* 中的“常规”\*\*\*\* 下，清除“为此边缘池启用联盟（端口 5061）”\*\*\*\*。单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="ab8c0-p103">展开“边缘池”\*\*\*\*，然后右键单击您想再次用于联盟的原始边缘服务器或边缘服务器池。选择“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-p103">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="ab8c0-p104">在“编辑属性”\*\*\*\* 中的“常规”\*\*\*\* 下，选择“为此边缘池启用联盟（端口 5061）”\*\*\*\*。单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="ab8c0-p105">单击“操作”\*\*\*\*，选择“拓扑”\*\*\*\*，再选择“发布”\*\*\*\*。当“发布拓扑”\*\*\*\* 中出现提示时，单击“下一步”\*\*\*\*。完成发布后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="ab8c0-p106">在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”\*\*\*\*，然后单击“安装或删除 Lync Server 组件”\*\*\*\*。单击“再次运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="ab8c0-p107">在“设置 Lync Server 组件”中，单击“下一步”\*\*\*\*。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”\*\*\*\* 可查看可用日志文件。单击“完成”\*\*\*\* 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="ab8c0-127">如果想要对 XMPP 联盟路由进行故障回复以使用恢复的边缘服务器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ab8c0-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="ab8c0-128">运行以下 cmdlet 以将 XMPP 联盟路由重新指向此时将承载 XMPP 联盟的服务器（在此示例中为 EdgeServer1）：</span><span class="sxs-lookup"><span data-stu-id="ab8c0-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="ab8c0-129">在此示例中，Site1 是包含此时将承载 XMPP 联盟路由的边缘池的站点，EdgeServer1.contoso.com 是该池中边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="ab8c0-p108">如果您尚未拥有解析到此时将承载 XMPP 联盟的边缘池的 XMPP 联盟的 DNS SRV 记录，则必须添加该记录，如下例所示。该 SRV 记录的端口值必须为 5269。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="ab8c0-132">在外部 DNS 服务器上，将 XMPP 联盟的 DNS A 记录更改为指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="ab8c0-133">确认此时将承载 XMPP 联盟的边缘池已将端口 5269 向外部开放。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="ab8c0-134">如果前端池在含有出过故障并且已恢复的边缘池的站点中持续运行，则应该更新这些前端池上的 Web 会议服务和 A/V 会议服务，以在其本地站点上再次使用边缘池。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="ab8c0-135">有关详细信息，请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="ab8c0-136">如果在出现了故障边缘池的同一站点上的前端池也出现故障，则现在可以使用 Invoke–CsPoolFailback 对前端池进行故障回复。</span><span class="sxs-lookup"><span data-stu-id="ab8c0-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab8c0-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab8c0-137">See Also</span></span>


[<span data-ttu-id="ab8c0-138">在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="ab8c0-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="ab8c0-139">在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="ab8c0-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="ab8c0-140">Lync Server 2013 中的边缘服务器灾难恢复</span><span class="sxs-lookup"><span data-stu-id="ab8c0-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

