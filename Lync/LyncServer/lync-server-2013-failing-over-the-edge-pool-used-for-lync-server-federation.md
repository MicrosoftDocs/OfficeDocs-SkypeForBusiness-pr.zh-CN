---
title: Lync Server 2013：对用于 Lync Server 联盟的边缘池进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="72a2e-102">在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="72a2e-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72a2e-103">_**主题上次修改时间:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="72a2e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="72a2e-104">如果您的 Lync Server 联合身份验证配置所在的边缘池已关闭, 则必须将联合身份更改为使用其他边缘池才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="72a2e-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="72a2e-105">故障切换用于 Lync Server 联合身份验证的边缘池</span><span class="sxs-lookup"><span data-stu-id="72a2e-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="72a2e-106">在前端服务器上, 打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="72a2e-106">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="72a2e-107">展开 "**边缘池**", 然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="72a2e-107">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="72a2e-108">选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-108">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="72a2e-109">在 "**编辑属性**" 下的 "**常规**" 下, 清除 "**为此边缘池启用联盟 (端口 5061)**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-109">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="72a2e-110">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="72a2e-110">Click **OK**.</span></span>

3.  <span data-ttu-id="72a2e-111">展开 "**边缘池**", 然后右键单击要用于联盟的边缘服务器或边缘服务器池。</span><span class="sxs-lookup"><span data-stu-id="72a2e-111">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="72a2e-112">选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-112">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="72a2e-113">在 "**常规**" 下的 "**编辑属性**" 下, 选择 "**为此边缘池启用联盟 (端口 5061)**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-113">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="72a2e-114">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="72a2e-114">Click **OK**.</span></span>

5.  <span data-ttu-id="72a2e-115">单击 "**操作**", 选择 "**拓扑**", 选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-115">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="72a2e-116">当系统提示**发布拓扑**时, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-116">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="72a2e-117">发布完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-117">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="72a2e-118">在边缘服务器上, 打开 "Lync Server 部署向导"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="72a2e-119">单击 "**安装或更新 Lync 服务器系统**", 然后单击 "**设置" 或 "删除 lync server 组件**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-119">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="72a2e-120">再次单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-120">Click **Run Again**.</span></span>

7.  <span data-ttu-id="72a2e-121">在 "安装 Lync 服务器组件" 中, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="72a2e-121">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="72a2e-122">"摘要" 屏幕将显示执行时的操作。</span><span class="sxs-lookup"><span data-stu-id="72a2e-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="72a2e-123">部署完成后, 单击 "**查看日志**" 以查看可用的日志文件。</span><span class="sxs-lookup"><span data-stu-id="72a2e-123">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="72a2e-124">单击 "**完成**" 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="72a2e-124">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="72a2e-125">如果包含失败的 Edge 池的网站包含仍在运行的前端服务器, 则必须更新这些前端池上的 Web 会议服务和 A/V 会议服务, 才能使用仍在运行的远程网站中的边缘池。</span><span class="sxs-lookup"><span data-stu-id="72a2e-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="72a2e-126">有关详细信息, 请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="72a2e-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72a2e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72a2e-127">See Also</span></span>


[<span data-ttu-id="72a2e-128">在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="72a2e-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="72a2e-129">在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="72a2e-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="72a2e-130">Lync Server 2013 中的边缘服务器灾难恢复</span><span class="sxs-lookup"><span data-stu-id="72a2e-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

