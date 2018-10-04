---
title: 为 Business Server Skype 创建边缘拓扑
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 摘要： 了解如何构建、 发布和业务服务器导出边缘服务器拓扑中 Skype。
ms.openlocfilehash: b01f0c107207d79f62a092acc2e287e632969234
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372771"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a><span data-ttu-id="fdc63-103">为 Business Server Skype 创建边缘拓扑</span><span class="sxs-lookup"><span data-stu-id="fdc63-103">Create your Edge topology for Skype for Business Server</span></span>
 
<span data-ttu-id="fdc63-104">**摘要：** 了解如何构建、 发布和业务服务器导出边缘服务器拓扑中 Skype。</span><span class="sxs-lookup"><span data-stu-id="fdc63-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="fdc63-105">拓扑生成器是用于生成边缘服务器拓扑，就像使用任何拓扑组件的 Skype 业务服务器所需的工具。</span><span class="sxs-lookup"><span data-stu-id="fdc63-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server.</span></span> <span data-ttu-id="fdc63-106">执行以下步骤之前，您将需要已设置至少一个前端池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="fdc63-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="fdc63-107">我们将在本文中介绍以下主题：</span><span class="sxs-lookup"><span data-stu-id="fdc63-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="fdc63-108">构建边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="fdc63-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="fdc63-109">发布边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="fdc63-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="fdc63-110">验证边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="fdc63-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="fdc63-111">为了遵循下面的步骤，需要登录到下面提及的域服务器，且用来登录的用户应该是以下域组的成员：</span><span class="sxs-lookup"><span data-stu-id="fdc63-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="fdc63-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="fdc63-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="fdc63-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="fdc63-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="fdc63-114">构建边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="fdc63-114">Build your Edge Server topology</span></span>

<span data-ttu-id="fdc63-115">第一个部署步骤构建您 Skype 的业务 Server 边缘服务器拓扑，其中包括三个选项之一：</span><span class="sxs-lookup"><span data-stu-id="fdc63-115">The first deployment step is building your Skype for Business Server Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="fdc63-116">一台边缘服务器</span><span class="sxs-lookup"><span data-stu-id="fdc63-116">A single Edge Server</span></span>
    
- <span data-ttu-id="fdc63-117">DNS 负载平衡的边缘池 （一个或多个服务器）</span><span class="sxs-lookup"><span data-stu-id="fdc63-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="fdc63-118">硬件负载平衡边缘池 （一个或多个服务器）</span><span class="sxs-lookup"><span data-stu-id="fdc63-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="fdc63-p102">如果不确定自己需要哪种选项，那么在开始遵循这些步骤之前，最好先重温规划文档。否则，让我们开始。</span><span class="sxs-lookup"><span data-stu-id="fdc63-p102">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation. Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="fdc63-121">为单台边缘服务器定义拓扑</span><span class="sxs-lookup"><span data-stu-id="fdc63-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="fdc63-122">登录到您的业务 Server Standard Edition server 的 Skype 或业务 Server 前端池的 Skype。</span><span class="sxs-lookup"><span data-stu-id="fdc63-122">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End pool.</span></span>
    
2. <span data-ttu-id="fdc63-123">一次，打开**Skype 的业务 Server 拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-123">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="fdc63-124">在控制台树中，展开要部署边缘服务器的站点。</span><span class="sxs-lookup"><span data-stu-id="fdc63-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="fdc63-125">右键单击**边缘池**，然后单击**新建边缘池**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="fdc63-126">您将在**定义新边缘池**屏幕上以单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="fdc63-127">在**定义边缘池 FQDN**屏幕中，键入内部完全限定的域名 (FQDN) 的边缘服务器使用，并选择**单计算机池**，单击**下一步**完成。</span><span class="sxs-lookup"><span data-stu-id="fdc63-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="fdc63-128">在“**选择功能**”屏幕上，可选择：</span><span class="sxs-lookup"><span data-stu-id="fdc63-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="fdc63-129">要使用相同的 FQDN 和 IP 地址 SIP 访问服务、 业务 Server Web 会议服务，您 Skype 和 A / V 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="fdc63-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="fdc63-130">如果是这样，需要选中“**使用一个 FQDN 和 IP 地址**”复选框（做到下面的步骤 9 时，请记得这一点）</span><span class="sxs-lookup"><span data-stu-id="fdc63-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="fdc63-131">如果你计划启用联盟，请选中“**为此边缘池启用联盟(端口 5061)**”复选框。</span><span class="sxs-lookup"><span data-stu-id="fdc63-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="fdc63-p104">单击“**下一步**”后，你将进入“**IP 选项**”屏幕。选项如下：</span><span class="sxs-lookup"><span data-stu-id="fdc63-p104">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
   - <span data-ttu-id="fdc63-134">在内部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="fdc63-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="fdc63-135">在内部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="fdc63-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="fdc63-136">在外部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="fdc63-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="fdc63-137">在外部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="fdc63-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="fdc63-138">这些是无需解释，是否您使用的 IPv4 或 IPv6 地址，并且您将应用这些地址上边缘服务器内部或外部 （需要牢记这的步骤 10）。</span><span class="sxs-lookup"><span data-stu-id="fdc63-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="fdc63-139">您还可以使用网络地址转换 (NAT) 地址的外部 IP 地址配置边缘服务器或边缘池的选择。</span><span class="sxs-lookup"><span data-stu-id="fdc63-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="fdc63-140">选中“**此边缘池的外部 IP 地址是由 NAT 转换的**”复选框可以执行此配置。</span><span class="sxs-lookup"><span data-stu-id="fdc63-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="fdc63-141">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="fdc63-142">在“外部 FQDN”屏幕上，你的选择取决于你在上面的步骤 7 中所作的选择。</span><span class="sxs-lookup"><span data-stu-id="fdc63-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="fdc63-143">如果选中**使用单个 FQDN 和 IP 地址**复选框，您需要在**SIP 访问**框中输入您的单个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fdc63-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="fdc63-144">然后，您需要输入不同的端口号为每个边缘服务使所有独立连接。</span><span class="sxs-lookup"><span data-stu-id="fdc63-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="fdc63-145">我们建议 **SIP 访问**边缘服务使用 5061，**Web 会议**边缘服务使用 444，**A/V** 边缘服务使用 443。</span><span class="sxs-lookup"><span data-stu-id="fdc63-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="fdc63-146">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="fdc63-147">如果未选中**使用单个 FQDN 和 IP 地址**复选框，您现在需要输入三个外部 Fqdn 的**SIP 访问**边缘服务， **Web 会议**边缘服务，以及**A / V**边缘服务。</span><span class="sxs-lookup"><span data-stu-id="fdc63-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="fdc63-148">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="fdc63-149">现在，您在**定义内部 IP 地址**屏幕上。</span><span class="sxs-lookup"><span data-stu-id="fdc63-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="fdc63-150">此处，您需要在**内部 IPv4 地址**和**内部 IPv6 地址**文本框中的根据您在步骤 8 中后所做的选择中, 键入边缘服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fdc63-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="fdc63-151">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="fdc63-152">在“**定义外部 IP 地址**”屏幕上，根据你前面的选择，有几个选项：</span><span class="sxs-lookup"><span data-stu-id="fdc63-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="fdc63-153">你可能让所有服务使用一个 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fdc63-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="fdc63-154">如果是这样，在**SIP 访问**文本框中，键入 （无论您使用） 您外部 IPv4 或 IPv6 地址，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="fdc63-155">你可能选择让这些服务使用三个不同的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fdc63-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="fdc63-156">如果是这样，用于**SIP 访问**边缘服务， **Web 会议**边缘服务中，输入您的外部 IPv4 或 IPv6 地址和**A / V**边缘服务，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fdc63-p111">如果先前未选择启用和分配 IPv6 编址，则不会出现此对话框。这是正常现象，请直接进入下一步。</span><span class="sxs-lookup"><span data-stu-id="fdc63-p111">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="fdc63-159">如果您选择在步骤 8 后使用 NAT，您现在将获取与**公共 IP 地址**文本框的屏幕。</span><span class="sxs-lookup"><span data-stu-id="fdc63-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="fdc63-160">您需要输入公共 IPv4 和/或 IPv6 地址已设置为 A / V 边缘服务，要转换的 nat。</span><span class="sxs-lookup"><span data-stu-id="fdc63-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="fdc63-161">然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="fdc63-162">接下来的屏幕是“**定义下一跃点**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="fdc63-163">在**下一跃点池**框中，选择您的内部池，这可能是前端池或独立池的名称。</span><span class="sxs-lookup"><span data-stu-id="fdc63-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="fdc63-164">如果您的环境中有控制器，则应选择控制器。</span><span class="sxs-lookup"><span data-stu-id="fdc63-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="fdc63-165">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fdc63-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="fdc63-166">在**关联前端池**屏幕中，您需要指定一个或多个内部池，包括前端池和 Standard Edition server，与该边缘服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="fdc63-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="fdc63-167">只需选择要使用此边缘服务器的受支持的外部用户进行通信的内部池的名称。</span><span class="sxs-lookup"><span data-stu-id="fdc63-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="fdc63-168">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fdc63-169">内容需要注意以下事项此处是，如果您的内部池或独立服务器已经在使用不同的 Skype 业务 Server 边缘服务器，不能具有多个关联。</span><span class="sxs-lookup"><span data-stu-id="fdc63-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="fdc63-170">如果您选择的内部池或独立服务器上是这种情况下，您将看到有关其他边缘服务器，告知您显示一条警告，您可以决定是否要继续与否。</span><span class="sxs-lookup"><span data-stu-id="fdc63-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="fdc63-171">如果继续这个新的关联，与另一台边缘服务器的连接将停止。</span><span class="sxs-lookup"><span data-stu-id="fdc63-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="fdc63-172">在下一个屏幕上单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="fdc63-173">现在，您将能够发布此更新的技术，并按照[Skype 业务服务器中部署边缘服务器](deploy-edge-servers.md)中的说明从此处部署到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fdc63-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="fdc63-174">定义拓扑的 DNS 负载平衡边缘服务器池</span><span class="sxs-lookup"><span data-stu-id="fdc63-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="fdc63-175">登录到您的业务 Server Standard Edition server 的 Skype 或业务 Server 前端服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="fdc63-175">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="fdc63-176">一次，打开**Skype 的业务 Server 拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-176">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="fdc63-177">在控制台树中，展开要部署边缘服务器的站点。</span><span class="sxs-lookup"><span data-stu-id="fdc63-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="fdc63-178">右键单击**边缘池**，然后单击**新建边缘池**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="fdc63-179">您将在**定义新边缘池**屏幕上以单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="fdc63-180">在**定义边缘池 FQDN**屏幕中，键入内部完全限定的域名 (FQDN) 的边缘池要使用，并选择**多个计算机池**，单击**下一步**完成。</span><span class="sxs-lookup"><span data-stu-id="fdc63-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="fdc63-181">在“**选择功能**”屏幕上，可选择：</span><span class="sxs-lookup"><span data-stu-id="fdc63-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="fdc63-182">要使用相同的 FQDN 和 IP 地址 SIP 访问服务、 业务服务器 Web 会议服务，您 Skype 和 A / V 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="fdc63-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="fdc63-183">如果是这样，需要选中“**使用一个 FQDN 和 IP 地址**”复选框（做到下面的步骤 9 时，请记得这一点）</span><span class="sxs-lookup"><span data-stu-id="fdc63-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="fdc63-184">如果你计划启用联盟，请选中“**为此边缘池启用联盟(端口 5061)**”复选框。</span><span class="sxs-lookup"><span data-stu-id="fdc63-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="fdc63-p117">单击“**下一步**”后，你将进入“**IP 选项**”屏幕。选项如下：</span><span class="sxs-lookup"><span data-stu-id="fdc63-p117">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
    - <span data-ttu-id="fdc63-187">在内部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="fdc63-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="fdc63-188">在内部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="fdc63-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="fdc63-189">在外部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="fdc63-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="fdc63-190">在外部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="fdc63-190">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="fdc63-191">这些是无需解释，是否您使用的 IPv4 或 IPv6 地址，并且您将应用这些地址上边缘服务器内部或外部 （需要记住此步骤 11）。</span><span class="sxs-lookup"><span data-stu-id="fdc63-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="fdc63-192">您还可以使用网络地址转换 (NAT) 地址的外部 IP 地址配置边缘服务器或边缘池的选择。</span><span class="sxs-lookup"><span data-stu-id="fdc63-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="fdc63-193">选中“**此边缘池的外部 IP 地址是由 NAT 转换的**”复选框可以执行此配置。</span><span class="sxs-lookup"><span data-stu-id="fdc63-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="fdc63-194">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="fdc63-195">在“外部 FQDN”屏幕上，你的选择取决于你在上面的步骤 7 中所作的选择。</span><span class="sxs-lookup"><span data-stu-id="fdc63-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="fdc63-196">如果选中**使用单个 FQDN 和 IP 地址**复选框，您需要在**SIP 访问**框中输入您的单个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fdc63-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="fdc63-197">然后，您需要输入不同的端口号为每个边缘服务使所有独立连接。</span><span class="sxs-lookup"><span data-stu-id="fdc63-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="fdc63-198">我们建议 **SIP 访问**边缘服务使用 5061，**Web 会议**边缘服务使用 444，**A/V** 边缘服务使用 443。</span><span class="sxs-lookup"><span data-stu-id="fdc63-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="fdc63-199">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="fdc63-200">如果未选中**使用单个 FQDN 和 IP 地址**复选框，您现在需要输入三个外部 Fqdn 的**SIP 访问**边缘服务， **Web 会议**边缘服务，以及**A / V**边缘服务。</span><span class="sxs-lookup"><span data-stu-id="fdc63-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="fdc63-201">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="fdc63-202">现在您已达到**定义此池中的计算机**屏幕。</span><span class="sxs-lookup"><span data-stu-id="fdc63-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="fdc63-203">单击“**添加**”按钮。</span><span class="sxs-lookup"><span data-stu-id="fdc63-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="fdc63-204">现在，您在**定义内部 IP 地址**屏幕上。</span><span class="sxs-lookup"><span data-stu-id="fdc63-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="fdc63-205">此处，您需要在**内部 IPv4 地址**和**内部 IPv6 地址**文本框中的根据您在步骤 8 中后所做的选择中, 键入边缘服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fdc63-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="fdc63-206">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="fdc63-207">在“**定义外部 IP 地址**”屏幕上，根据你前面的选择，有几个选项：</span><span class="sxs-lookup"><span data-stu-id="fdc63-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="fdc63-208">你可能让所有服务使用一个 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fdc63-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="fdc63-209">如果是这样，在**SIP 访问**文本框中，键入 （无论您使用） 您外部 IPv4 或 IPv6 地址，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="fdc63-210">你可能选择让这些服务使用三个不同的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fdc63-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="fdc63-211">如果是这样，用于**SIP 访问**边缘服务， **Web 会议**边缘服务中，输入您的外部 IPv4 或 IPv6 地址和**A / V**边缘服务，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fdc63-p125">如果先前未选择启用和分配 IPv6 编址，则不会出现此对话框。这是正常现象，请直接进入下一步。</span><span class="sxs-lookup"><span data-stu-id="fdc63-p125">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="fdc63-214">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-214">Click **Finish**.</span></span> <span data-ttu-id="fdc63-215">现在应在**定义此池中的计算机**对话框中列出您刚创建的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fdc63-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="fdc63-216">仍在**定义此池中的计算机**屏幕中，再次单击**添加**按钮，直到您添加了您打算将在此池中的所有边缘服务器重复步骤 11 到 13。</span><span class="sxs-lookup"><span data-stu-id="fdc63-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="fdc63-217">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="fdc63-218">如果您选择在步骤 8 后使用 NAT，您现在将获取与**公共 IP 地址**文本框的屏幕。</span><span class="sxs-lookup"><span data-stu-id="fdc63-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="fdc63-219">您需要输入公共 IPv4 和/或 IPv6 地址已设置为 A / V 边缘服务，要转换的 nat。</span><span class="sxs-lookup"><span data-stu-id="fdc63-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="fdc63-220">然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="fdc63-221">接下来的屏幕是“**定义下一跃点**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="fdc63-222">在**下一跃点池**框中，选择您的内部池，这可能是前端池或独立池的名称。</span><span class="sxs-lookup"><span data-stu-id="fdc63-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="fdc63-223">如果您的环境中有控制器，则应选择控制器。</span><span class="sxs-lookup"><span data-stu-id="fdc63-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="fdc63-224">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fdc63-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="fdc63-225">在**关联前端池**屏幕中，您需要指定一个或多个内部池，包括前端池和 Standard Edition 池，以与此边缘服务器关联。</span><span class="sxs-lookup"><span data-stu-id="fdc63-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="fdc63-226">只需选择要使用此边缘服务器的受支持的外部用户进行通信的内部池的名称。</span><span class="sxs-lookup"><span data-stu-id="fdc63-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="fdc63-227">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fdc63-228">内容需要注意以下事项此处是，如果您的内部池或独立服务器已经在使用不同的 Skype 业务 Server 边缘服务器，不能具有多个关联。</span><span class="sxs-lookup"><span data-stu-id="fdc63-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="fdc63-229">如果您选择的内部池或独立服务器上是这种情况下，您将看到有关其他边缘服务器，告知您显示一条警告，您可以决定是否要继续与否。</span><span class="sxs-lookup"><span data-stu-id="fdc63-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="fdc63-230">如果继续这个新的关联，与另一台边缘服务器的连接将停止。</span><span class="sxs-lookup"><span data-stu-id="fdc63-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="fdc63-231">在下一个屏幕上单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="fdc63-232">现在，您将能够发布此更新的技术，并按照[Skype 业务服务器中部署边缘服务器](deploy-edge-servers.md)中的说明从此处部署到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fdc63-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="fdc63-233">定义的拓扑的硬件负载平衡边缘服务器池</span><span class="sxs-lookup"><span data-stu-id="fdc63-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="fdc63-234">登录到您的业务 Server Standard Edition server 的 Skype 或业务 Server 前端服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="fdc63-234">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="fdc63-235">一次，打开**Skype 的业务 Server 拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-235">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="fdc63-236">在控制台树中，展开要部署边缘服务器的站点。</span><span class="sxs-lookup"><span data-stu-id="fdc63-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="fdc63-237">右键单击**边缘池**，然后单击**新建边缘池**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="fdc63-238">您将在**定义新边缘池**屏幕上以单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="fdc63-239">在**定义边缘池 FQDN**屏幕中，键入内部完全限定的域名 (FQDN) 的边缘池要使用，并选择**多个计算机池**，单击**下一步**完成。</span><span class="sxs-lookup"><span data-stu-id="fdc63-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="fdc63-240">在“**选择功能**”屏幕上，可选择：</span><span class="sxs-lookup"><span data-stu-id="fdc63-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="fdc63-241">要使用相同的 FQDN 和 IP 地址 SIP 访问服务、 业务服务器 Web 会议服务，您 Skype 和 A / V 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="fdc63-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="fdc63-242">如果是这样，需要选中“**使用一个 FQDN 和 IP 地址**”复选框（做到下面的步骤 9 时，请记得这一点）</span><span class="sxs-lookup"><span data-stu-id="fdc63-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="fdc63-243">如果你计划启用联盟，请选中“**为此边缘池启用联盟(端口 5061)**”复选框。</span><span class="sxs-lookup"><span data-stu-id="fdc63-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="fdc63-p133">单击“**下一步**”后，你将进入“**IP 选项**”屏幕。选项如下：</span><span class="sxs-lookup"><span data-stu-id="fdc63-p133">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
   - <span data-ttu-id="fdc63-246">在内部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="fdc63-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="fdc63-247">在内部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="fdc63-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="fdc63-248">在外部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="fdc63-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="fdc63-249">在外部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="fdc63-249">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="fdc63-250">这些是无需解释，是否您使用的 IPv4 或 IPv6 地址，并且您将应用这些地址上边缘服务器内部或外部 （需要记住此步骤 11）。</span><span class="sxs-lookup"><span data-stu-id="fdc63-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="fdc63-251">与其他两种拓扑结构选项，使用硬件负载平衡器时，您**不得**选择**边缘池的外部 IP 地址由 NAT 转换**选项。</span><span class="sxs-lookup"><span data-stu-id="fdc63-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="fdc63-252">这**不受支持**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="fdc63-253">在“外部 FQDN”屏幕上，你的选择取决于你在上面的步骤 7 中所作的选择。</span><span class="sxs-lookup"><span data-stu-id="fdc63-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="fdc63-254">如果选中**使用单个 FQDN 和 IP 地址**复选框，您需要在**SIP 访问**框中输入您的单个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fdc63-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="fdc63-255">然后，您需要输入不同的端口号为每个边缘服务使所有独立连接。</span><span class="sxs-lookup"><span data-stu-id="fdc63-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="fdc63-256">我们建议 **SIP 访问**边缘服务使用 5061，**Web 会议**边缘服务使用 444，**A/V** 边缘服务使用 443。</span><span class="sxs-lookup"><span data-stu-id="fdc63-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="fdc63-257">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="fdc63-258">如果未选中**使用单个 FQDN 和 IP 地址**复选框，您现在需要输入三个外部 Fqdn 的**SIP 访问**边缘服务， **Web 会议**边缘服务，以及**A / V**边缘服务。</span><span class="sxs-lookup"><span data-stu-id="fdc63-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="fdc63-259">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="fdc63-260">现在您已达到**定义此池中的计算机**屏幕。</span><span class="sxs-lookup"><span data-stu-id="fdc63-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="fdc63-261">单击“**添加**”按钮。</span><span class="sxs-lookup"><span data-stu-id="fdc63-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="fdc63-262">现在，您在**定义内部 IP 地址**屏幕上。</span><span class="sxs-lookup"><span data-stu-id="fdc63-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="fdc63-263">此处，您需要在**内部 IPv4 地址**和**内部 IPv6 地址**文本框中的根据您在步骤 8 中后所做的选择中, 键入边缘服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fdc63-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="fdc63-264">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="fdc63-265">在“**定义外部 IP 地址**”屏幕上，根据你前面的选择，有几个选项：</span><span class="sxs-lookup"><span data-stu-id="fdc63-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="fdc63-266">你可能让所有服务使用一个 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fdc63-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="fdc63-267">如果是这样，在**SIP 访问**文本框中，键入 （无论您使用） 您外部 IPv4 或 IPv6 地址，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="fdc63-268">你可能选择让这些服务使用三个不同的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fdc63-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="fdc63-269">如果是这样，用于**SIP 访问**边缘服务， **Web 会议**边缘服务中，输入您的外部 IPv4 或 IPv6 地址和**A / V**边缘服务，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fdc63-p141">如果先前未选择启用和分配 IPv6 编址，则不会出现此对话框。这是正常现象，请直接进入下一步。</span><span class="sxs-lookup"><span data-stu-id="fdc63-p141">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="fdc63-272">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-272">Click **Finish**.</span></span> <span data-ttu-id="fdc63-273">现在应在**定义此池中的计算机**对话框中列出您刚创建的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fdc63-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="fdc63-274">仍在**定义此池中的计算机**屏幕中，再次单击**添加**按钮，直到您添加了您打算将在此池中的所有边缘服务器重复步骤 11 到 13。</span><span class="sxs-lookup"><span data-stu-id="fdc63-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="fdc63-275">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="fdc63-276">接下来的屏幕是“**定义下一跃点**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="fdc63-277">在**下一跃点池**框中，选择您的内部池，这可能是前端池或独立池的名称。</span><span class="sxs-lookup"><span data-stu-id="fdc63-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="fdc63-278">如果您的环境中有控制器，则应选择控制器。</span><span class="sxs-lookup"><span data-stu-id="fdc63-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="fdc63-279">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fdc63-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="fdc63-280">在**关联前端池**屏幕中，您需要指定一个或多个内部池，包括前端池和 Standard Edition 池，以与此边缘服务器关联。</span><span class="sxs-lookup"><span data-stu-id="fdc63-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="fdc63-281">只需选择要使用此边缘服务器的受支持的外部用户进行通信的内部池的名称。</span><span class="sxs-lookup"><span data-stu-id="fdc63-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="fdc63-282">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fdc63-283">内容需要注意以下事项此处是，如果您的内部池或独立服务器已经在使用不同的 Skype 业务 Server 边缘服务器，不能具有多个关联。</span><span class="sxs-lookup"><span data-stu-id="fdc63-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="fdc63-284">如果您选择的内部池或独立服务器上是这种情况下，您将看到有关其他边缘服务器，告知您显示一条警告，您可以决定是否要继续与否。</span><span class="sxs-lookup"><span data-stu-id="fdc63-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="fdc63-285">如果继续这个新的关联，与另一台边缘服务器的连接将停止。</span><span class="sxs-lookup"><span data-stu-id="fdc63-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="fdc63-286">在下一个屏幕上单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="fdc63-287">现在，您将能够发布此更新的技术，并按照[Skype 业务服务器中部署边缘服务器](deploy-edge-servers.md)中的说明从此处部署到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fdc63-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="fdc63-288">发布边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="fdc63-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="fdc63-289">在完成上述步骤后，就可以发布此新拓扑，还允许您将其导出到业务 Server 边缘服务器或边缘池您 Skype。</span><span class="sxs-lookup"><span data-stu-id="fdc63-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server Edge Server or Edge pool.</span></span> <span data-ttu-id="fdc63-290">请按以下步骤执行：</span><span class="sxs-lookup"><span data-stu-id="fdc63-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="fdc63-291">启动“**拓扑生成器**”（如果在前面的过程中还未启动）。</span><span class="sxs-lookup"><span data-stu-id="fdc63-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="fdc63-292">在**拓扑生成器**，在控制台树中，右键单击**Skype 业务服务器**，然后单击**Skype 的业务 Server 拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="fdc63-293">在向导的“**欢迎**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="fdc63-294">在“**创建其他数据库**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="fdc63-295">当状态指示数据库创建成功时，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fdc63-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="fdc63-296">若要查看日志，请单击“**查看日志**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="fdc63-297">若要关闭向导，请单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fdc63-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="fdc63-298">验证边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="fdc63-298">Export your Edge Server topology</span></span>

<span data-ttu-id="fdc63-299">若要成功部署，业务 Server 部署向导的 Skype 需要对中央管理存储数据的访问。</span><span class="sxs-lookup"><span data-stu-id="fdc63-299">To deploy successfully, the Skype for Business Server Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="fdc63-300">对于域或林中的内部服务器，这通常很容易。</span><span class="sxs-lookup"><span data-stu-id="fdc63-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="fdc63-301">边缘服务器的外部域，并因此所需手动到边缘服务器上的位置，通常物理媒体导出拓扑文件。</span><span class="sxs-lookup"><span data-stu-id="fdc63-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="fdc63-302">这样的导出通过 PowerShell 执行：</span><span class="sxs-lookup"><span data-stu-id="fdc63-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="fdc63-303">启动**Skype 的业务 Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="fdc63-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="fdc63-304">在**Skype 的业务 Server Management Shell**中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="fdc63-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="fdc63-305">将导出的文件复制到外部介质 （例如，USB 驱动器或网络共享，可以从边缘服务器的位置达到）。</span><span class="sxs-lookup"><span data-stu-id="fdc63-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

