---
title: 在 Skype for Business Server 2015 中创建 VIS 池
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 摘要： 为业务服务器 2015 使用拓扑生成器创建 Skype 视频互操作服务器池。
ms.openlocfilehash: c66889530bbcc8753e8003667e6ea26589cd5daf
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501700"
---
# <a name="create-a-vis-pool-in-skype-for-business-server-2015"></a><span data-ttu-id="12137-103">在 Skype for Business Server 2015 中创建 VIS 池</span><span class="sxs-lookup"><span data-stu-id="12137-103">Create a VIS pool in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="12137-104">**摘要：** 为业务服务器 2015 使用拓扑生成器创建 Skype 视频互操作服务器池。</span><span class="sxs-lookup"><span data-stu-id="12137-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server 2015 using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="12137-105">使用拓扑生成器创建 VIS 或 VIS 池</span><span class="sxs-lookup"><span data-stu-id="12137-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="12137-106">在前端服务器上打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="12137-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="12137-107">从拓扑生成器的左窗格中，右键单击 * * 视频互操作服务器池 * *，然后选择**新的视频互操作服务器池**。</span><span class="sxs-lookup"><span data-stu-id="12137-107">From the left pane of Topology Builder, right click on ** Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="12137-108">这将打开“**创建新的视频互操作服务器池**”向导。</span><span class="sxs-lookup"><span data-stu-id="12137-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="12137-109">为新的视频互操作服务器提供池 FQDN，然后选择**此池具有一台服务器**或**此池中具有多个服务器**基于您的要求，然后按**下一步**。</span><span class="sxs-lookup"><span data-stu-id="12137-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="12137-110">如果您想要部署视频互操作服务器池以提供高可用性，请选择**此池具有多个服务器**。</span><span class="sxs-lookup"><span data-stu-id="12137-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="12137-111">对于该选项，请记住：</span><span class="sxs-lookup"><span data-stu-id="12137-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="12137-112">您必须部署 DNS 负载平衡来支持视频互操作服务器池。</span><span class="sxs-lookup"><span data-stu-id="12137-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="12137-113">在下一页的“**定义此池中的计算机**”条目上，在文本字段中输入池中每台服务器的**计算机 FQDN**，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="12137-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="12137-114">重复此步骤以向池添加视频互操作的另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="12137-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="12137-115">定义完池中的所有计算机后，请单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="12137-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
    <span data-ttu-id="12137-116">如果您想要部署在池中只有一台视频互操作服务器，因为不要求具备高可用性，然后选择**此池中具有一台服务器**，并按**下一步**。</span><span class="sxs-lookup"><span data-stu-id="12137-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="12137-117">从下拉列表中选择下一个跃点池/FE，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="12137-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="12137-118">选择要与 VIS 关联的边缘池，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="12137-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="12137-119">设置 TCP 或 TLS 端口。</span><span class="sxs-lookup"><span data-stu-id="12137-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="12137-120">从拓扑生成器的左窗格中选择新添加的视频互操作服务器，右键单击它，然后选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="12137-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="12137-121">根据您的要求启用或更新 TCP 或 TLS 端口，然后选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="12137-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="12137-122">尽管默认会添加 TLS，但只为 CUCM 全面测试了 TCP。</span><span class="sxs-lookup"><span data-stu-id="12137-122">Although by default TLS is added, only TCP has been fully tested with CUCM.</span></span>
    
6. <span data-ttu-id="12137-p106">添加视频网关。要执行此操作，展开“共享组件”，右键单击“**视频网关**”，然后选择“**新建视频网关**”。</span><span class="sxs-lookup"><span data-stu-id="12137-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="12137-p107">提供视频网关 FQDN 或 IP 地址。视频网关可以在子域或其他域中。您系统的 VTC 使用的 CUCM 充当视频网关。</span><span class="sxs-lookup"><span data-stu-id="12137-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="12137-p108">适当地选择 IPv4 或 IPv6。您可以使用所有配置的 IP 地址或限制服务使用选定的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="12137-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="12137-130">选择视频网关的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="12137-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="12137-131">选择传输协议 （TCP 或 TLS），并将其与为视频的 SIP 中继设置视频互操作服务器关联。</span><span class="sxs-lookup"><span data-stu-id="12137-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="12137-132">视频网关的传输协议应与为 VIS 配置的传输协议相匹配。</span><span class="sxs-lookup"><span data-stu-id="12137-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="12137-133">完成上述步骤后，将添加对应的 SIP 视频中继。</span><span class="sxs-lookup"><span data-stu-id="12137-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="12137-134">右键单击 SIP 视频中继，然后选择刚才添加的中继。</span><span class="sxs-lookup"><span data-stu-id="12137-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="12137-135">该视频的 SIP 中继名称，关联视频互操作服务器 SIP 传输协议和端口可所有更改。</span><span class="sxs-lookup"><span data-stu-id="12137-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="12137-136">视频互操作服务器支持 1: n 中继。</span><span class="sxs-lookup"><span data-stu-id="12137-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="12137-137">因此多个中继可以将添加，与单个视频互操作服务器，其中每个中继终止在不同的视频网关相关联。</span><span class="sxs-lookup"><span data-stu-id="12137-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="12137-138">限制是特定视频网关，可以对业务服务器部署 Skype 定义的且只有一个中继。</span><span class="sxs-lookup"><span data-stu-id="12137-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="12137-139">发布拓扑文档中所述[创建和发布新拓扑中 Skype 的业务服务器 2015年](../../deploy/install/create-and-publish-new-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="12137-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12137-140">若要提高恢复能力，您可能想要配置第二个视频互操作服务器或 VIS 池或备份的前端池。</span><span class="sxs-lookup"><span data-stu-id="12137-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="12137-141">有关更多信息，请参阅[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)。</span><span class="sxs-lookup"><span data-stu-id="12137-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="12137-p113">现已完成所有使用拓扑生成器执行的任务。请继续在新的 VIS 服务器上安装软件。</span><span class="sxs-lookup"><span data-stu-id="12137-p113">All tasks performed using Topology Builder should now be complete. Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="12137-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12137-144">See also</span></span>

[<span data-ttu-id="12137-145">为业务服务器 2015年部署中 Skype VIS 服务器角色</span><span class="sxs-lookup"><span data-stu-id="12137-145">Deploy the VIS server role in Skype for Business Server 2015</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="12137-146">规划视频互操作性中的服务器 Skype 业务 Server 2015</span><span class="sxs-lookup"><span data-stu-id="12137-146">Plan for Video Interop Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="12137-147">创建和发布新拓扑中 Skype 的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="12137-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)