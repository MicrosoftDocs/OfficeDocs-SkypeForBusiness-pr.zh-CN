---
title: 在 Skype for Business Server 中创建 VIS 池
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 摘要：使用拓扑生成器在 Skype for Business Server 中创建视频互操作服务器池。
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802051"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="1f42b-103">在 Skype for Business Server 中创建 VIS 池</span><span class="sxs-lookup"><span data-stu-id="1f42b-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="1f42b-104">**摘要：** 使用拓扑生成器在 Skype for Business Server 中创建视频互操作服务器池。</span><span class="sxs-lookup"><span data-stu-id="1f42b-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="1f42b-105">使用拓扑生成器创建 VIS 或 VIS 池</span><span class="sxs-lookup"><span data-stu-id="1f42b-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="1f42b-106">在前端服务器上打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="1f42b-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="1f42b-107">从拓扑生成器的左窗格中，右键单击 **"视频互操作服务器池**"并选择 **"新建视频互操作服务器池"。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="1f42b-108">这将打开"新建视频 **互操作服务器池"** 向导。</span><span class="sxs-lookup"><span data-stu-id="1f42b-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="1f42b-109">提供新视频互操作服务器的池 FQDN，然后根据您的要求选择此池具有一台服务器或此池具有多台服务器，然后按 **Next。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="1f42b-110">如果要部署视频互操作服务器池以提供高可用性，请选择 **此池具有多台服务器**。</span><span class="sxs-lookup"><span data-stu-id="1f42b-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="1f42b-111">请牢记此选项：</span><span class="sxs-lookup"><span data-stu-id="1f42b-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="1f42b-112">必须部署 DNS 负载平衡以支持视频互操作服务器池。</span><span class="sxs-lookup"><span data-stu-id="1f42b-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="1f42b-113">下一页上，对于"定义此池中的计算机 **"项，** 在文本字段中输入池中每台服务器的计算机 **FQDN，** 然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="1f42b-114">重复此步骤以将另一个视频互操作服务器添加到池中。</span><span class="sxs-lookup"><span data-stu-id="1f42b-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="1f42b-115">定义池中的所有计算机后，按"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="1f42b-116">如果因为不需要高可用性而只想在池中部署一个视频互操作服务器，则选择此池有 **一** 台服务器并按 **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="1f42b-117">从下拉列表中选择下一个跃点池/FE，然后按"**下一步"。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="1f42b-118">选择要与 VIS 关联的边缘池，然后按 **"完成"。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="1f42b-119">设置 TCP 或 TLS 端口。</span><span class="sxs-lookup"><span data-stu-id="1f42b-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="1f42b-120">从拓扑生成器的左窗格中选择新添加的视频互操作服务器，右键单击它，然后选择"编辑 **属性"。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="1f42b-121">根据你的要求启用或更新 TCP 或 TLS 端口，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="1f42b-122">尽管默认情况下会添加 TLS，但只有 TCP 已使用 Cisco 统一通信管理器 (CallManager 或 CUCM) 。</span><span class="sxs-lookup"><span data-stu-id="1f42b-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="1f42b-123">添加视频网关。</span><span class="sxs-lookup"><span data-stu-id="1f42b-123">Add a video gateway.</span></span> <span data-ttu-id="1f42b-124">为此，请展开"共享组件"，右键单击 **"视频网关**"，然后选择 **"新建视频网关"。**</span><span class="sxs-lookup"><span data-stu-id="1f42b-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="1f42b-125">提供视频网关 FQDN 或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1f42b-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="1f42b-126">视频网关可能在不同的子域中。</span><span class="sxs-lookup"><span data-stu-id="1f42b-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="1f42b-127">系统 VTC 使用的 CUCM 充当视频网关。</span><span class="sxs-lookup"><span data-stu-id="1f42b-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="1f42b-128">适当地选择 IPv4 或 IPv6。</span><span class="sxs-lookup"><span data-stu-id="1f42b-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="1f42b-129">可以使用所有配置的 IP 地址或将服务用途限制为所选 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="1f42b-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="1f42b-130">选择视频网关的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="1f42b-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="1f42b-131">选择 TCP 或 TLS (传输协议) 并将其与为视频 SIP 中继设置的视频互操作服务器关联。</span><span class="sxs-lookup"><span data-stu-id="1f42b-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="1f42b-132">视频网关的传输协议应匹配为 VIS 配置的传输协议。</span><span class="sxs-lookup"><span data-stu-id="1f42b-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="1f42b-133">完成上述步骤后，将添加相应的 SIP 视频中继。</span><span class="sxs-lookup"><span data-stu-id="1f42b-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="1f42b-134">右键单击 SIP 视频中继，然后选择刚刚添加的中继。</span><span class="sxs-lookup"><span data-stu-id="1f42b-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="1f42b-135">视频 SIP 中继名称、关联的视频互操作服务器、SIP 传输协议和端口都可以更改。</span><span class="sxs-lookup"><span data-stu-id="1f42b-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="1f42b-136">视频互操作服务器支持 1：N 中继。</span><span class="sxs-lookup"><span data-stu-id="1f42b-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="1f42b-137">因此，可以添加多个中继，这些中继与单个视频互操作服务器相关联，其中每个中继在不同的视频网关上终止。</span><span class="sxs-lookup"><span data-stu-id="1f42b-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="1f42b-138">限制是，特定视频网关只有一个可以定义到 Skype for Business Server 部署的中继。</span><span class="sxs-lookup"><span data-stu-id="1f42b-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="1f42b-139">发布拓扑文档，如 Skype [for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md)中的"创建和发布新拓扑"中所述。</span><span class="sxs-lookup"><span data-stu-id="1f42b-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1f42b-140">若要提高恢复能力，您可能需要配置第二个视频互操作服务器或 VIS 池或备份前端池。</span><span class="sxs-lookup"><span data-stu-id="1f42b-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="1f42b-141">有关详细信息 [，请参阅](../../plan-your-deployment/video-interop-server.md#resiliency) 复原机制。</span><span class="sxs-lookup"><span data-stu-id="1f42b-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="1f42b-142">现在，使用拓扑生成器执行的所有任务都应完成。</span><span class="sxs-lookup"><span data-stu-id="1f42b-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="1f42b-143">继续将软件安装在新的 VIS 服务器或服务器上。</span><span class="sxs-lookup"><span data-stu-id="1f42b-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="1f42b-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f42b-144">See also</span></span>

[<span data-ttu-id="1f42b-145">在 Skype for Business Server 中部署 VIS 服务器角色</span><span class="sxs-lookup"><span data-stu-id="1f42b-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="1f42b-146">在 Skype for Business Server 中规划视频互操作服务器</span><span class="sxs-lookup"><span data-stu-id="1f42b-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="1f42b-147">在 Skype for Business Server 2015 中创建新拓扑</span><span class="sxs-lookup"><span data-stu-id="1f42b-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
