---
title: Lync Server 2013：对用于 Lync Server 联盟的边缘池进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4e374337f261c6747bc1b147c9f2e02fa51efe3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="59ef8-102">在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="59ef8-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59ef8-103">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="59ef8-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="59ef8-104">如果配置了 Lync Server 联盟的边缘池不可用，则必须将联盟更改为使用其他边缘池，联盟才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="59ef8-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="59ef8-105">对用于 Lync Server 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="59ef8-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="59ef8-p101">在前端服务器上，打开拓扑生成器。展开“边缘池”\*\*\*\*，然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。选择“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59ef8-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="59ef8-p102">在“常规”\*\*\*\* 下的“编辑属性”\*\*\*\* 中，清除“为此边缘池启用联盟(端口 5061)”\*\*\*\*。单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59ef8-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="59ef8-p103">展开“边缘池”\*\*\*\*，然后右键单击现在要用于联盟的边缘服务器或边缘服务器池。选择“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59ef8-p103">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation. Select **Edit properties**.</span></span>

4.  <span data-ttu-id="59ef8-p104">在“常规”\*\*\*\* 下的“编辑属性”\*\*\*\* 中，选择“为此边缘池启用联盟(端口 5061)”\*\*\*\*。单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59ef8-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="59ef8-p105">单击“操作”\*\*\*\*，选择“拓扑”\*\*\*\*，再选择“发布”\*\*\*\*。当“发布拓扑”\*\*\*\* 中出现提示时，单击“下一步”\*\*\*\*。完成发布后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59ef8-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="59ef8-p106">在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”\*\*\*\*，然后单击“安装或删除 Lync Server 组件”\*\*\*\*。单击“再次运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59ef8-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="59ef8-p107">在“设置 Lync Server 组件”中，单击“下一步”\*\*\*\*。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”\*\*\*\* 可查看可用日志文件。单击“完成”\*\*\*\* 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="59ef8-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="59ef8-125">如果包含故障边缘池的站点包含仍在运行的前端服务器，则必须更新这些前端池上的 Web 会议服务和 A/V 会议服务才能在仍在运行的远程站点中使用边缘池。</span><span class="sxs-lookup"><span data-stu-id="59ef8-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="59ef8-126">有关详细信息，请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="59ef8-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59ef8-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59ef8-127">See Also</span></span>


[<span data-ttu-id="59ef8-128">在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="59ef8-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="59ef8-129">在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="59ef8-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="59ef8-130">Lync Server 2013 中的边缘服务器灾难恢复</span><span class="sxs-lookup"><span data-stu-id="59ef8-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

