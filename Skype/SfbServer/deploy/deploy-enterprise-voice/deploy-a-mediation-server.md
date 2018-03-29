---
title: 在 Skype for Business Server 2015 拓扑生成器中部署中介服务器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 摘要： 了解如何定义和部署业务服务器 2015年在拓扑生成器在 Skype 中介服务器。
ms.openlocfilehash: bfb915528ba73851d3bd60cc8ff3b33b968376e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="51a07-103">在 Skype for Business Server 2015 拓扑生成器中部署中介服务器</span><span class="sxs-lookup"><span data-stu-id="51a07-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="51a07-104">**摘要：**了解如何定义和部署业务服务器 2015年在拓扑生成器在 Skype 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="51a07-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="51a07-105">企业语音工作负载、 拨入会议和高级的企业语音应用程序 （响应组应用程序、 应用程序调用公园、 调用许可控制 (CAC) 等） 中提供了前端池。</span><span class="sxs-lookup"><span data-stu-id="51a07-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="51a07-106">中介服务器的功能是内置于前端服务器。</span><span class="sxs-lookup"><span data-stu-id="51a07-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="51a07-107">不需要单独的独立中介服务器。</span><span class="sxs-lookup"><span data-stu-id="51a07-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="51a07-108">唯一的例外是将 SIP 中继配置为连接到 Internet 电话服务提供商的会话边界控制器的情况。</span><span class="sxs-lookup"><span data-stu-id="51a07-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="51a07-109">若要连接到您的 SIP 中继提供商企业语音基础结构，必须部署一个单独的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="51a07-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="51a07-110">Skype 业务 （搭配前端池或独立的中介服务器上使用中介服务器） 的服务器和网关之间的连接被指称为主干的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="51a07-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="51a07-111">本节中的主题介绍如何定义中继以及如何部署独立的中介服务器，如果您连接到 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="51a07-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="51a07-112">在拓扑生成器中定义中介服务器</span><span class="sxs-lookup"><span data-stu-id="51a07-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="51a07-113">可以将中介服务器作为前端池，并入角色添加或定义一个单独的独立中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="51a07-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="51a07-114">中介服务器添加到前端池</span><span class="sxs-lookup"><span data-stu-id="51a07-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="51a07-115">起始拓扑生成器中： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，然后都单击**Skype 业务服务器 2015Topology 生成器**。</span><span class="sxs-lookup"><span data-stu-id="51a07-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="51a07-116">在拓扑生成器中，在控制台树中，展开要为其定义一个前端池的站点名称。</span><span class="sxs-lookup"><span data-stu-id="51a07-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="51a07-117">在控制台树中，右键单击您希望，前端池的类型，然后单击**新的前端池...**。</span><span class="sxs-lookup"><span data-stu-id="51a07-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="51a07-118">在“定义新的前端池”****向导中导航，直到到达“选择并置服务器角色”****页。</span><span class="sxs-lookup"><span data-stu-id="51a07-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="51a07-119">**选择按顺序排列的服务器角色**，请检查**布置中介服务器**的选项。</span><span class="sxs-lookup"><span data-stu-id="51a07-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51a07-120">如果您所选的前端池的类型是企业版，然后将所有前端服务器的该前端池上安装中介服务器组件。</span><span class="sxs-lookup"><span data-stu-id="51a07-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="51a07-121">使用中介服务器的**下一跃点池**将中介服务器的搭配，前端池。</span><span class="sxs-lookup"><span data-stu-id="51a07-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="51a07-122">使用中介服务器的**边缘池**将会与中介服务器的搭配，前端池相关联的相同边缘池。</span><span class="sxs-lookup"><span data-stu-id="51a07-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="51a07-123">单击**设为默认**来使用该前端池可将路由到 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="51a07-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="51a07-124">在完成相关联的一个或多个对等端到前端池时，请单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="51a07-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51a07-125">进入企业语音部署过程的下一步之前，请确保中介服务器池 （亦即前端池与中介服务器组件搭配使用） 使用指定 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="51a07-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="51a07-126">该**业务服务器 2015年的 Skype**节点，用鼠标右键单击，然后单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="51a07-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="51a07-127">添加独立中介服务器</span><span class="sxs-lookup"><span data-stu-id="51a07-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="51a07-128">起始拓扑生成器中： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，然后都单击**Skype 业务服务器 2015Topology 生成器**。</span><span class="sxs-lookup"><span data-stu-id="51a07-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="51a07-129">在拓扑生成器中，在控制台树中，展开要为其定义中介服务器的站点的名称。</span><span class="sxs-lookup"><span data-stu-id="51a07-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="51a07-130">在控制台树中，**中介池**节点中，用鼠标右键单击，然后单击**中介服务器池**。</span><span class="sxs-lookup"><span data-stu-id="51a07-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="51a07-131">在**定义新的中介池**，键入中介服务器池完全合格的域名称 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="51a07-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="51a07-132">接下来，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="51a07-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="51a07-133">如果您要部署多个中介池中的服务器来提供高可用性，请选择**多个计算机池**。</span><span class="sxs-lookup"><span data-stu-id="51a07-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51a07-134">您必须部署 (.../../ plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) 来支持有多个中介服务器的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="51a07-134">You must deploy  (../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="51a07-135">如果您要部署池中的一个中介服务器，因为您不需要高可用性，则选择**单台计算机池**。</span><span class="sxs-lookup"><span data-stu-id="51a07-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="51a07-136">跳过以下步骤。</span><span class="sxs-lookup"><span data-stu-id="51a07-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="51a07-137">如果在前一步骤中选择了“多计算机池”****，那么在“定义此池中的计算机”****项上单击“计算机 FQDN”****，键入此池中每个服务器的 FQDN，然后单击“添加”****。</span><span class="sxs-lookup"><span data-stu-id="51a07-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="51a07-138">对于所有其他您想要添加到池中的中介服务器重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="51a07-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="51a07-139">定义该池中的所有计算机后，单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="51a07-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="51a07-140">在**下一个跃点中选择**页上，单击**下一步跳池**，单击，将使用该中介服务器池，然后单击**下一步**的前端池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="51a07-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="51a07-141">在“选择边缘服务器”****页上执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="51a07-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="51a07-142">如果您想要提供给外部用户启用企业语音，PSTN 连接下**选择边缘池被中介服务器**，请单击将使用该中介服务器池提供的 PSTN 连接到边缘服务器池的 FQDN这些外部的用户，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="51a07-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="51a07-143">如果不打算启用外部用户的企业语音，或者如果您不想在内部网络之外时，向用户提供的 PSTN 连接性，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="51a07-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="51a07-144">该**业务服务器 2015年的 Skype**节点，用鼠标右键单击，然后单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="51a07-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="51a07-145">定义的中介服务器侦听端口</span><span class="sxs-lookup"><span data-stu-id="51a07-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="51a07-146">请按照本主题中，可以使用拓扑生成器定义侦听端口中介服务器或池将接受传入的连接，从网关等。</span><span class="sxs-lookup"><span data-stu-id="51a07-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="51a07-147">若要修改中介服务器侦听端口</span><span class="sxs-lookup"><span data-stu-id="51a07-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="51a07-148">起始拓扑生成器中： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，然后都单击**Skype 业务服务器 2015Topology 生成器**。</span><span class="sxs-lookup"><span data-stu-id="51a07-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="51a07-149">在拓扑生成器中，在控制台树中，展开**中介池**节点，右键单击先前创建的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="51a07-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="51a07-150">默认情况下，中介服务器的 SIP 侦听端口是从 Skype 业务服务器的 TLS 通信的 5070 和 TLS 通信从对等方 （如网关、 PBXes 或 SBCs） 5067。</span><span class="sxs-lookup"><span data-stu-id="51a07-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="51a07-151">默认情况下，TCP 端口处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="51a07-151">TCP port is disabled by default.</span></span> <span data-ttu-id="51a07-152">如果有不支持 TLS 的网关，则必须启用 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="51a07-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="51a07-153">指定所需的 TLS 或 TCP 侦听端口范围中介服务器接受传入的连接从 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="51a07-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="51a07-p107">如果未选中“启用 TCP 端口”****，则不需要输入 TCP 端口范围。此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="51a07-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

