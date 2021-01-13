---
title: 在 Skype for Business Server 的拓扑生成器中部署中介服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 摘要：了解如何在 Skype for Business Server 的拓扑生成器中定义和部署中介服务器。
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836912"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="1bb57-103">在 Skype for Business Server 的拓扑生成器中部署中介服务器</span><span class="sxs-lookup"><span data-stu-id="1bb57-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="1bb57-104">**摘要：** 了解如何在 Skype for Business Server 的拓扑生成器中定义和部署中介服务器。</span><span class="sxs-lookup"><span data-stu-id="1bb57-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="1bb57-105">前端池中提供了 企业语音 工作负载、电话拨入式会议和高级 企业语音 应用程序 (响应组应用程序、呼叫停止应用程序、呼叫允许控制 (CAC) 等) 。</span><span class="sxs-lookup"><span data-stu-id="1bb57-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="1bb57-106">中介服务器的功能内置于前端服务器中。</span><span class="sxs-lookup"><span data-stu-id="1bb57-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="1bb57-107">不需要单独的独立中介服务器。</span><span class="sxs-lookup"><span data-stu-id="1bb57-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="1bb57-108">唯一的例外是将 SIP 中继配置为连接到 Internet 电话服务提供商的会话边界控制器的情况。</span><span class="sxs-lookup"><span data-stu-id="1bb57-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="1bb57-109">若要将企业语音基础结构连接到 SIP 中继提供商，必须部署单独的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="1bb57-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="1bb57-110">Skype for Business Server (前端池上并排的中介服务器或独立中介服务器) 与网关之间的连接定义为称为中继的逻辑关联。</span><span class="sxs-lookup"><span data-stu-id="1bb57-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="1bb57-111">本节中的主题介绍如何定义中继，以及在连接到 SIP 中继的情况下，如何部署独立的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="1bb57-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="1bb57-112">在拓扑生成器中定义中介服务器</span><span class="sxs-lookup"><span data-stu-id="1bb57-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="1bb57-113">可以将中介服务器添加为前端池上的并排角色，或定义单独的独立中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="1bb57-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="1bb57-114">将中介服务器添加到前端池</span><span class="sxs-lookup"><span data-stu-id="1bb57-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="1bb57-115">启动拓扑生成器 **：单击"** 开始"，**单击"** 所有程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 2015Topology Builder"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="1bb57-116">在拓扑生成器的控制台树中，展开要定义其前端池的站点的名称。</span><span class="sxs-lookup"><span data-stu-id="1bb57-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="1bb57-117">在控制台树中，右键单击您想要的前端池的类型，然后单击 **"新建前端池"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="1bb57-118">在“定义新的前端池”向导中导航，直到到达“选择并置服务器角色”页。</span><span class="sxs-lookup"><span data-stu-id="1bb57-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="1bb57-119">在 **"选择并集服务器角色"中**，选中" **并插中介服务器"选项**。</span><span class="sxs-lookup"><span data-stu-id="1bb57-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1bb57-120">如果选择的前端池的类型为 Enterprise Edition，则中介服务器组件将安装在该前端池的所有前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="1bb57-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="1bb57-121">中介 **服务器使用的** 下一个跃点池将是并排中介服务器的前端池。</span><span class="sxs-lookup"><span data-stu-id="1bb57-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="1bb57-122">中介 **服务器** 使用的边缘池将是与并排中介服务器的前端池关联的同一边缘池。</span><span class="sxs-lookup"><span data-stu-id="1bb57-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="1bb57-123">单击 **"默认** "以使用此前端池将呼叫路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="1bb57-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="1bb57-124">完成 **将** 一个或多个对等方与前端池关联后，单击"完成"。</span><span class="sxs-lookup"><span data-stu-id="1bb57-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1bb57-125">在继续执行 企业语音 部署过程中的下一步之前，请确保中介服务器池 (即与) 并排的中介服务器组件的前端池正在使用指定的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1bb57-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="1bb57-126">右键单击 **Skype for Business Server 2015** 节点，然后单击"发布 **拓扑"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="1bb57-127">添加独立中介服务器</span><span class="sxs-lookup"><span data-stu-id="1bb57-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="1bb57-128">启动拓扑生成器 **：单击"** 开始"，**单击"** 所有程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 2015Topology Builder"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="1bb57-129">在拓扑生成器的控制台树中，展开要定义中介服务器的站点的名称。</span><span class="sxs-lookup"><span data-stu-id="1bb57-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="1bb57-130">在控制台树中，右键单击 **中介池** 节点，然后单击 **中介服务器池**。</span><span class="sxs-lookup"><span data-stu-id="1bb57-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="1bb57-131">在 **"定义新中介池"中**，键入中介服务器池的完全限定域名 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="1bb57-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="1bb57-132">接下来，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1bb57-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="1bb57-133">如果要在池中部署多个中介服务器以提供高可用性，请选择 **"多计算机池"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="1bb57-134">必须 [部署以支持](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) 具有多个中介服务器的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="1bb57-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="1bb57-135">如果因为不需要高可用性而只想在池中部署一台中介服务器，请选择"**单计算机池"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="1bb57-136">跳过以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1bb57-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="1bb57-137">如果在前一步骤中选择了“多计算机池”，那么在“定义此池中的计算机”项上单击“计算机 FQDN”，键入此池中每个服务器的 FQDN，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="1bb57-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="1bb57-138">对要添加到池中的所有其他中介服务器重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="1bb57-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="1bb57-139">定义该池中的所有计算机后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="1bb57-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="1bb57-140">在 **"选择下一** 跃点"页上，单击"下一跃点池"，单击将使用此中介服务器池的前端池的 FQDN，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="1bb57-141">在“选择边缘服务器”页上执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1bb57-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="1bb57-142">如果要为启用 企业语音 的外部用户提供 PSTN 连接，请在"选择此中介服务器使用的边缘池"下，单击将使用此中介服务器池向这些外部用户提供 PSTN 连接的边缘服务器池的 FQDN，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="1bb57-143">如果您计划不为外部用户启用 企业语音，或者不希望在用户位于内部网络外部时为用户提供 PSTN 连接，请单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="1bb57-144">右键单击 **Skype for Business Server 2015** 节点，然后单击"发布 **拓扑"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="1bb57-145">定义中介服务器侦听端口</span><span class="sxs-lookup"><span data-stu-id="1bb57-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="1bb57-146">按照本主题中的步骤使用拓扑生成器定义中介服务器或池将接受来自对等网关的传入连接的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="1bb57-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="1bb57-147">修改中介服务器侦听端口</span><span class="sxs-lookup"><span data-stu-id="1bb57-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="1bb57-148">启动拓扑生成器 **：单击"** 开始"，**单击"** 所有程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 2015Topology Builder"。**</span><span class="sxs-lookup"><span data-stu-id="1bb57-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="1bb57-149">在拓扑生成器的控制台树中，展开 **中介** 池节点，然后右键单击之前创建的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="1bb57-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="1bb57-150">默认情况下，中介服务器的 SIP 侦听端口对于来自 Skype for Business Server 的 TLS 流量为 5070，来自对等方（如网关、PBX 或 SBC）的 T (LS 流量为 5067) 。</span><span class="sxs-lookup"><span data-stu-id="1bb57-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="1bb57-151">默认情况下，TCP 处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="1bb57-151">TCP port is disabled by default.</span></span> <span data-ttu-id="1bb57-152">如果有不支持 TLS 的网关，则必须启用 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="1bb57-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="1bb57-153">指定中介服务器将接受来自 PSTN 网关的传入连接所需的 TLS 或 TCP 侦听端口范围。</span><span class="sxs-lookup"><span data-stu-id="1bb57-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1bb57-154">如果未选中“启用 TCP 端口”，则不需要输入 TCP 端口范围。</span><span class="sxs-lookup"><span data-stu-id="1bb57-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="1bb57-155">此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="1bb57-155">This setting is optional.</span></span>
  

