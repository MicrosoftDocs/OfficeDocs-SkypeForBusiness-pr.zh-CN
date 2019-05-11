---
title: 业务服务器部署在拓扑生成器中 Skype 在中介服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 摘要： 了解如何定义和部署业务服务器在拓扑生成器中 Skype 在中介服务器。
ms.openlocfilehash: a80f5bfbd57c1a533153effe21ca6748eb26aa6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892781"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="08ecf-103">业务服务器部署在拓扑生成器中 Skype 在中介服务器</span><span class="sxs-lookup"><span data-stu-id="08ecf-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="08ecf-104">**摘要：** 了解如何定义和部署业务服务器在拓扑生成器中 Skype 在中介服务器。</span><span class="sxs-lookup"><span data-stu-id="08ecf-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="08ecf-105">企业语音工作负荷、 电话拨入式会议和高级的企业语音应用程序 （响应组应用程序、 呼叫寄存应用程序、 呼叫允许控制 (CAC) 等） 中提供了前端池。</span><span class="sxs-lookup"><span data-stu-id="08ecf-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="08ecf-106">中介服务器的功能是内置前端服务器。</span><span class="sxs-lookup"><span data-stu-id="08ecf-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="08ecf-107">不需要单独的独立中介服务器。</span><span class="sxs-lookup"><span data-stu-id="08ecf-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="08ecf-108">唯一的例外是将 SIP 中继配置为连接到 Internet 电话服务提供商的会话边界控制器的情况。</span><span class="sxs-lookup"><span data-stu-id="08ecf-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="08ecf-109">要连接到您的 SIP 中继提供商的企业语音基础结构，必须部署单独的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="08ecf-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="08ecf-110">Skype 业务服务器 （中介服务器上的前端池或独立的中介服务器并置） 和网关之间的连接被指调用中继的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="08ecf-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="08ecf-111">本节中的主题介绍如何定义中继以及如何部署独立的中介服务器，如果连接到 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="08ecf-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="08ecf-112">在拓扑生成器中定义中介服务器</span><span class="sxs-lookup"><span data-stu-id="08ecf-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="08ecf-113">您可以添加中介服务器作为角色并置在前端池，或定义单独独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="08ecf-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="08ecf-114">将中介服务器添加到前端池</span><span class="sxs-lookup"><span data-stu-id="08ecf-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="08ecf-115">启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**业务 Server 2015Topology 生成器的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="08ecf-116">在拓扑生成器中，在控制台树中，展开要为其定义前端池的站点的名称。</span><span class="sxs-lookup"><span data-stu-id="08ecf-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="08ecf-117">在控制台树中，右键单击您希望，前端池的类型，然后单击**新的前端池...**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="08ecf-118">在“定义新的前端池”\*\*\*\* 向导中导航，直到到达“选择并置服务器角色”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="08ecf-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="08ecf-119">在**选择并置的服务器角色**，选中**并置中介服务器**选项。</span><span class="sxs-lookup"><span data-stu-id="08ecf-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08ecf-120">如果所选的前端池的类型为企业版，然后将所有前端服务器上的前端池的安装中介服务器组件。</span><span class="sxs-lookup"><span data-stu-id="08ecf-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="08ecf-121">使用中介服务器的**下一个跃点池**将是其中并置中介服务器的前端池。</span><span class="sxs-lookup"><span data-stu-id="08ecf-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="08ecf-122">使用中介服务器的**边缘池**将是与位置并置中介服务器的前端池关联的同一个边缘池。</span><span class="sxs-lookup"><span data-stu-id="08ecf-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="08ecf-123">单击**设为默认值**为使用此前端池路由到 PSTN 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="08ecf-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="08ecf-124">完成后，将一个或多个对等方与前端池相关联，请单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08ecf-125">您才能继续下一步中的企业语音部署过程之前，请确保中介服务器池 （即前端池与中介服务器组件并置） 使用您指定的 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="08ecf-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="08ecf-126">右键单击**业务服务器 2015年的 Skype**节点中，，然后单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="08ecf-127">添加独立中介服务器</span><span class="sxs-lookup"><span data-stu-id="08ecf-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="08ecf-128">启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**业务 Server 2015Topology 生成器的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="08ecf-129">在拓扑生成器中，在控制台树中，展开要为其定义中介服务器的站点的名称。</span><span class="sxs-lookup"><span data-stu-id="08ecf-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="08ecf-130">在控制台树中，右键单击**中介池**节点，然后单击**中介服务器池**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="08ecf-131">在**定义新的中介池**，键入中介服务器池完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="08ecf-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="08ecf-132">接下来，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="08ecf-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="08ecf-133">如果您想要部署多台中介服务器池中提供高可用性，然后选择**多计算机池**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="08ecf-134">您必须[部署](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing)以支持有多个中介服务器的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="08ecf-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="08ecf-135">如果您想要部署在池中只有一台中介服务器，因为不要求具备高可用性，然后选择**单计算机池**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="08ecf-136">跳过以下步骤。</span><span class="sxs-lookup"><span data-stu-id="08ecf-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="08ecf-137">如果在前一步骤中选择了“多计算机池”\*\*\*\*，那么在“定义此池中的计算机”\*\*\*\* 项上单击“计算机 FQDN”\*\*\*\*，键入此池中每个服务器的 FQDN，然后单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="08ecf-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="08ecf-138">对于您要添加到池的所有其他中介服务器重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="08ecf-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="08ecf-139">定义该池中的所有计算机后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="08ecf-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="08ecf-140">在**选择下一个跃点**页上，单击**下一跃点池**，单击将使用此中介服务器池，然后单击**下一步**的前端池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="08ecf-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="08ecf-141">在“选择边缘服务器”\*\*\*\* 页上执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="08ecf-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="08ecf-142">如果您想要启用企业语音的外部用户提供 PSTN 连接下**使用此中介服务器选择边缘池**，再单击将使用此中介服务器池提供 PSTN 连接到的边缘服务器池的 FQDN这些外部用户，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="08ecf-143">如果您不打算外部用户启用企业语音，或者如果您不希望在内部网络之外时向用户提供 PSTN 连接，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="08ecf-144">右键单击**业务服务器 2015年的 Skype**节点中，，然后单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="08ecf-145">定义中介服务器侦听端口</span><span class="sxs-lookup"><span data-stu-id="08ecf-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="08ecf-146">按照本主题使用拓扑生成器定义的侦听端口中介服务器中的步骤，或池接受来自对等网关的传入连接。</span><span class="sxs-lookup"><span data-stu-id="08ecf-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="08ecf-147">若要修改的中介服务器侦听端口</span><span class="sxs-lookup"><span data-stu-id="08ecf-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="08ecf-148">启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**业务 Server 2015Topology 生成器的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="08ecf-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="08ecf-149">在拓扑生成器中，在控制台树中，展开**中介池**节点，然后右键单击以前创建的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="08ecf-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="08ecf-150">默认情况下，在中介服务器上的 SIP 侦听端口是用于来自业务服务器 Skype 的 TLS 通信 5070 和 TLS 流量 （如网关，PBXes 或 SBCs） 对等方的 5067。</span><span class="sxs-lookup"><span data-stu-id="08ecf-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="08ecf-151">默认情况下，TCP 端口处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="08ecf-151">TCP port is disabled by default.</span></span> <span data-ttu-id="08ecf-152">如果有不支持 TLS 的网关，则必须启用 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="08ecf-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="08ecf-153">指定所需的 TLS 或 TCP 侦听端口范围中介服务器将接受来自 PSTN 网关的传入连接。</span><span class="sxs-lookup"><span data-stu-id="08ecf-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08ecf-p107">如果未选中“启用 TCP 端口”\*\*\*\*，则不需要输入 TCP 端口范围。此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="08ecf-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

