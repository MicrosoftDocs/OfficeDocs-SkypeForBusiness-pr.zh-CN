---
title: 为 Skype for Business Server 创建边缘拓扑
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
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 摘要：了解如何在 Skype for Business Server 中生成、发布和导出边缘服务器拓扑。
ms.openlocfilehash: 8dff318b5d198eb1e8d59ef465bf648125f31327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804392"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a><span data-ttu-id="89e23-103">为 Skype for Business Server 创建边缘拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-103">Create your Edge topology for Skype for Business Server</span></span>
 
<span data-ttu-id="89e23-104">**摘要：** 了解如何在 Skype for Business Server 中生成、发布和导出边缘服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="89e23-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="89e23-105">拓扑生成器是生成边缘服务器拓扑所需的工具，就像它用于 Skype for Business Server 的任何拓扑组件一样。</span><span class="sxs-lookup"><span data-stu-id="89e23-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server.</span></span> <span data-ttu-id="89e23-106">在按照以下步骤操作之前，至少需要设置一个前端池或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="89e23-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="89e23-107">我们将在本文中介绍以下主题：</span><span class="sxs-lookup"><span data-stu-id="89e23-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="89e23-108">构建边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="89e23-109">发布边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="89e23-110">导出边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="89e23-111">若要按照以下步骤操作，你需要以以下域组的成员用户登录下面提到的域服务器：</span><span class="sxs-lookup"><span data-stu-id="89e23-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="89e23-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="89e23-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="89e23-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="89e23-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="89e23-114">构建边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-114">Build your Edge Server topology</span></span>

<span data-ttu-id="89e23-115">第一个部署步骤是构建 Skype for Business Server 边缘服务器拓扑，其中包括以下三个选项之一：</span><span class="sxs-lookup"><span data-stu-id="89e23-115">The first deployment step is building your Skype for Business Server Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="89e23-116">单个边缘服务器</span><span class="sxs-lookup"><span data-stu-id="89e23-116">A single Edge Server</span></span>
    
- <span data-ttu-id="89e23-117">DNS 负载平衡边缘池 (一台或多台服务器) </span><span class="sxs-lookup"><span data-stu-id="89e23-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="89e23-118">硬件负载平衡边缘池 (一台或多台服务器) </span><span class="sxs-lookup"><span data-stu-id="89e23-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="89e23-119">如果您不确定所需的内容，那么在开始执行这些步骤之前，应该先了解一下规划文档。</span><span class="sxs-lookup"><span data-stu-id="89e23-119">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation.</span></span> <span data-ttu-id="89e23-120">否则，让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="89e23-120">Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="89e23-121">定义单个边缘服务器的拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="89e23-122">登录到 Skype for Business Server Standard Edition Server 或 Skype for Business Server 前端池。</span><span class="sxs-lookup"><span data-stu-id="89e23-122">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End pool.</span></span>
    
2. <span data-ttu-id="89e23-123">一旦存在，打开 **Skype for Business Server 拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="89e23-123">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="89e23-124">在控制台树中，展开要部署边缘服务器的站点。</span><span class="sxs-lookup"><span data-stu-id="89e23-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="89e23-125">右键单击 **边缘池**，然后单击 **"新建边缘池"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="89e23-126">你将 **在"定义** 新边缘池 **"屏幕上单击"下一步** "。</span><span class="sxs-lookup"><span data-stu-id="89e23-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="89e23-127">在"定义边缘池 **FQDN"** 屏幕上，键入边缘服务器将使用的内部完全限定域名 (FQDN) ，然后选择"单计算机池"，完成后单击"下一步"。 </span><span class="sxs-lookup"><span data-stu-id="89e23-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="89e23-128">在 **"选择功能** "屏幕上，可以选择：</span><span class="sxs-lookup"><span data-stu-id="89e23-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="89e23-129">你可能打算对 SIP 访问服务、Skype for Business Server Web 会议服务和 A/V 边缘服务使用相同的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89e23-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="89e23-130">如果是这样，你需要选择"使用单个 **FQDN** 和 IP 地址"复选框 (在下面的步骤 9 中记住) </span><span class="sxs-lookup"><span data-stu-id="89e23-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="89e23-131">如果计划启用联盟，请选中"为此边缘池启用联盟 (**端口 5061**) 复选框。</span><span class="sxs-lookup"><span data-stu-id="89e23-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="89e23-132">单击"下一步"后，你将在 IP 选项 **屏幕上找到** 自己。</span><span class="sxs-lookup"><span data-stu-id="89e23-132">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="89e23-133">选项如下所示：</span><span class="sxs-lookup"><span data-stu-id="89e23-133">Your options are as follows:</span></span>
    
   - <span data-ttu-id="89e23-134">在内部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="89e23-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="89e23-135">在内部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="89e23-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="89e23-136">在外部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="89e23-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="89e23-137">在外部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="89e23-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="89e23-138">无论你使用的是 IPv4 还是 IPv6 地址，这些地址都很容易理解，并且你要在边缘服务器上内部或外部应用这些地址 (在步骤 10) 中需要记住这一点。</span><span class="sxs-lookup"><span data-stu-id="89e23-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="89e23-139">还可以选择将边缘服务器或边缘池配置为使用外部 IP 地址的 NAT (NAT) 地址的网络地址转换。</span><span class="sxs-lookup"><span data-stu-id="89e23-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="89e23-140">为此，请选中 **"NAT"** 复选框转换此边缘池的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89e23-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="89e23-141">准备就绪 **后** 单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="89e23-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="89e23-142">在"外部 FQNS"屏幕上，您的选择取决于您在以上步骤 7 中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="89e23-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="89e23-143">如果选中了" **使用单个 FQDN** 和 IP 地址"复选框，则需要在 SIP 访问框中输入单个 **外部** FQDN。</span><span class="sxs-lookup"><span data-stu-id="89e23-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="89e23-144">然后，你需要为每个边缘服务输入不同的端口号，以允许它们相互独立连接。</span><span class="sxs-lookup"><span data-stu-id="89e23-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="89e23-145">建议 SIP 访问边缘服务为5061，建议 **为 Web** 会议边缘服务为 444，A/V边缘服务为 443。</span><span class="sxs-lookup"><span data-stu-id="89e23-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="89e23-146">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="89e23-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="89e23-147">如果未选中"使用单个 **FQDN** 和 IP 地址"复选框，则现在将需要为 **SIP** 访问边缘服务 **、Web** 会议边缘服务和 **A/V** 边缘服务输入三个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="89e23-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="89e23-148">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="89e23-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="89e23-149">现在，您位于"定义 **内部 IP 地址"** 屏幕上。</span><span class="sxs-lookup"><span data-stu-id="89e23-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="89e23-150">在这里，你将在"内部 **IPv4** 地址"和"内部 **IPv6** 地址"文本框中键入边缘服务器的 IP 地址，具体取决于你在步骤 8 中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="89e23-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="89e23-151">准备就绪 **后** 单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="89e23-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="89e23-152">在 **"定义外部 IP 地址** "屏幕上，有一些选项取决于您之前的选择：</span><span class="sxs-lookup"><span data-stu-id="89e23-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="89e23-153">您可以针对所有服务使用单个 FQDN。</span><span class="sxs-lookup"><span data-stu-id="89e23-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="89e23-154">如果是，请在 SIP 访问文本框中键入外部 IPv4 或 IPv6 (，) SIP **访问** 文本框中键入您的外部 IPv4 或 IPv6 **地址**。</span><span class="sxs-lookup"><span data-stu-id="89e23-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="89e23-155">您可能已选择为服务使用三个单独的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89e23-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="89e23-156">如果是这种情况，请输入 **SIP** 访问边缘服务 **、Web** 会议边缘服务和 **A/V** 边缘服务的外部 IPv4 或 IPv6 地址，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89e23-157">如果之前未选择启用和分配 IPv6 寻址，则看不到此对话框。</span><span class="sxs-lookup"><span data-stu-id="89e23-157">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="89e23-158">这很正常，只需转到下一步。</span><span class="sxs-lookup"><span data-stu-id="89e23-158">That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="89e23-159">如果在步骤 8 中选择重新使用 NAT，现在将看到一个包含公用 **IP** 地址文本框的屏幕。</span><span class="sxs-lookup"><span data-stu-id="89e23-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="89e23-160">你需要输入为 A/V 边缘服务设置的公共 IPv4 和/或 IPv6 地址，以通过 NAT 转换。</span><span class="sxs-lookup"><span data-stu-id="89e23-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="89e23-161">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="89e23-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="89e23-162">下一个屏幕向上 **是"定义下一个跃点"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="89e23-163">在 **"下一个** 跃点池"框中，选择内部池的名称，该名称可能是前端池或独立池。</span><span class="sxs-lookup"><span data-stu-id="89e23-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="89e23-164">如果环境中有控制器，应选择控制器。</span><span class="sxs-lookup"><span data-stu-id="89e23-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="89e23-165">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="89e23-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="89e23-166">在 **"关联前端** 池"屏幕上，需要指定一个或多个内部池（包括前端池和 Standard Edition Server）以与此边缘服务器关联。</span><span class="sxs-lookup"><span data-stu-id="89e23-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="89e23-167">只需选择希望使用此边缘服务器与支持的外部用户进行通信的内部池的名称。</span><span class="sxs-lookup"><span data-stu-id="89e23-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="89e23-168">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="89e23-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89e23-169">这里需要记住的一点就是，如果内部池或独立服务器已在使用不同的 Skype for Business Server 边缘服务器，则它们不能有多个关联。</span><span class="sxs-lookup"><span data-stu-id="89e23-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="89e23-170">如果选择处于该情况的内部池或独立服务器，将显示一条警告，告知您有关其他边缘服务器的信息，您可以决定是否要继续。</span><span class="sxs-lookup"><span data-stu-id="89e23-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="89e23-171">如果继续此新关联，则与其他边缘服务器的连接将停止。</span><span class="sxs-lookup"><span data-stu-id="89e23-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="89e23-172">单击 **下一** 个屏幕的"完成"。</span><span class="sxs-lookup"><span data-stu-id="89e23-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="89e23-173">现在，你将能够发布此更新的技术，并按照 Skype for Business [Server](deploy-edge-servers.md) 中"部署边缘服务器"中的说明从此处部署到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="89e23-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="89e23-174">定义 DNS 负载平衡边缘服务器池的拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="89e23-175">登录到 Skype for Business Server Standard Edition Server 或 Skype for Business Server 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="89e23-175">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="89e23-176">一旦存在，打开 **Skype for Business Server 拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="89e23-176">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="89e23-177">在控制台树中，展开要部署边缘服务器的站点。</span><span class="sxs-lookup"><span data-stu-id="89e23-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="89e23-178">右键单击 **边缘池**，然后单击 **"新建边缘池"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="89e23-179">你将 **在"定义** 新边缘池 **"屏幕上单击"下一步** "。</span><span class="sxs-lookup"><span data-stu-id="89e23-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="89e23-180">在"定义边缘池 **FQDN"** 屏幕上，键入边缘池将使用的内部完全限定域名 (FQDN) ，然后选择"多计算机池"，完成后单击"下一步"。 </span><span class="sxs-lookup"><span data-stu-id="89e23-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="89e23-181">在 **"选择功能** "屏幕上，可以选择：</span><span class="sxs-lookup"><span data-stu-id="89e23-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="89e23-182">你可能打算对 SIP 访问服务、Skype for Business Server Web 会议服务和 A/V 边缘服务使用相同的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89e23-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="89e23-183">如果是这样，你需要选择"使用单个 **FQDN** 和 IP 地址"复选框 (在下面的步骤 9 中记住) </span><span class="sxs-lookup"><span data-stu-id="89e23-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="89e23-184">如果计划启用联盟，请选中"为此边缘池启用联盟 (**端口 5061**) 复选框。</span><span class="sxs-lookup"><span data-stu-id="89e23-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="89e23-185">单击"下一步"后，你将在 IP 选项 **屏幕上找到** 自己。</span><span class="sxs-lookup"><span data-stu-id="89e23-185">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="89e23-186">选项如下所示：</span><span class="sxs-lookup"><span data-stu-id="89e23-186">Your options are as follows:</span></span>
    
    - <span data-ttu-id="89e23-187">在内部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="89e23-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="89e23-188">在内部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="89e23-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="89e23-189">在外部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="89e23-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="89e23-190">在外部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="89e23-190">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="89e23-191">无论你使用的是 IPv4 还是 IPv6 地址，这些地址都很容易理解，并且你要在边缘服务器上内部或外部应用这些地址 (在步骤 11) 中需要记住这一点。</span><span class="sxs-lookup"><span data-stu-id="89e23-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="89e23-192">还可以选择将边缘服务器或边缘池配置为使用外部 IP 地址的 NAT (NAT) 地址的网络地址转换。</span><span class="sxs-lookup"><span data-stu-id="89e23-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="89e23-193">为此，请选中 **"NAT"** 复选框转换此边缘池的外部 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89e23-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="89e23-194">准备就绪 **后** 单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="89e23-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="89e23-195">在"外部 FQNS"屏幕上，您的选择取决于您在以上步骤 7 中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="89e23-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="89e23-196">如果选中了" **使用单个 FQDN** 和 IP 地址"复选框，则需要在 SIP 访问框中输入单个 **外部** FQDN。</span><span class="sxs-lookup"><span data-stu-id="89e23-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="89e23-197">然后，你需要为每个边缘服务输入不同的端口号，以允许它们相互独立连接。</span><span class="sxs-lookup"><span data-stu-id="89e23-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="89e23-198">建议 SIP 访问边缘服务为5061，建议 **为 Web** 会议边缘服务为 444，A/V边缘服务为 443。</span><span class="sxs-lookup"><span data-stu-id="89e23-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="89e23-199">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="89e23-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="89e23-200">如果未选中"使用单个 **FQDN** 和 IP 地址"复选框，则现在将需要为 **SIP** 访问边缘服务 **、Web** 会议边缘服务和 **A/V** 边缘服务输入三个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="89e23-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="89e23-201">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="89e23-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="89e23-202">现在你已到达"在此池 **屏幕中定义计算机"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="89e23-203">单击“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="89e23-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="89e23-204">现在，您位于"定义 **内部 IP 地址"** 屏幕上。</span><span class="sxs-lookup"><span data-stu-id="89e23-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="89e23-205">在这里，你将在"内部 **IPv4** 地址"和"内部 **IPv6** 地址"文本框中键入边缘服务器的 IP 地址，具体取决于你在步骤 8 中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="89e23-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="89e23-206">准备就绪 **后** 单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="89e23-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="89e23-207">在 **"定义外部 IP 地址** "屏幕上，有一些选项取决于您之前的选择：</span><span class="sxs-lookup"><span data-stu-id="89e23-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="89e23-208">您可以针对所有服务使用单个 FQDN。</span><span class="sxs-lookup"><span data-stu-id="89e23-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="89e23-209">如果是，请在 SIP 访问文本框中键入外部 IPv4 或 IPv6 (，) SIP **访问** 文本框中键入您的外部 IPv4 或 IPv6 **地址**。</span><span class="sxs-lookup"><span data-stu-id="89e23-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="89e23-210">您可能已选择为服务使用三个单独的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89e23-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="89e23-211">如果是这种情况，请输入 **SIP** 访问边缘服务 **、Web** 会议边缘服务和 **A/V** 边缘服务的外部 IPv4 或 IPv6 地址，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89e23-212">如果之前未选择启用和分配 IPv6 寻址，则看不到此对话框。</span><span class="sxs-lookup"><span data-stu-id="89e23-212">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="89e23-213">这很正常，只需转到下一步。</span><span class="sxs-lookup"><span data-stu-id="89e23-213">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="89e23-214">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="89e23-214">Click **Finish**.</span></span> <span data-ttu-id="89e23-215">您刚刚创建的边缘服务器现在应列在"定义此池 **的计算机"** 对话框中。</span><span class="sxs-lookup"><span data-stu-id="89e23-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="89e23-216">仍在"定义此池中的计算机"屏幕上，再次单击"添加"按钮，并重复步骤 11 至 13，直到添加要在此池中拥有的所有边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="89e23-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="89e23-217">完成此操作后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="89e23-218">如果在步骤 8 中选择重新使用 NAT，现在将看到一个包含公用 **IP** 地址文本框的屏幕。</span><span class="sxs-lookup"><span data-stu-id="89e23-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="89e23-219">你需要输入为 A/V 边缘服务设置的公共 IPv4 和/或 IPv6 地址，以通过 NAT 转换。</span><span class="sxs-lookup"><span data-stu-id="89e23-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="89e23-220">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="89e23-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="89e23-221">下一个屏幕向上 **是"定义下一个跃点"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="89e23-222">在 **"下一个** 跃点池"框中，选择内部池的名称，该名称可能是前端池或独立池。</span><span class="sxs-lookup"><span data-stu-id="89e23-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="89e23-223">如果环境中有控制器，应选择控制器。</span><span class="sxs-lookup"><span data-stu-id="89e23-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="89e23-224">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="89e23-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="89e23-225">在 **"关联前端** 池"屏幕上，需要指定一个或多个内部池（包括前端池和 Standard Edition 池）以与此边缘服务器关联。</span><span class="sxs-lookup"><span data-stu-id="89e23-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="89e23-226">只需选择希望使用此边缘服务器与支持的外部用户进行通信的内部池的名称。</span><span class="sxs-lookup"><span data-stu-id="89e23-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="89e23-227">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="89e23-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89e23-228">这里需要记住的一点就是，如果内部池或独立服务器已在使用不同的 Skype for Business Server 边缘服务器，则它们不能有多个关联。</span><span class="sxs-lookup"><span data-stu-id="89e23-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="89e23-229">如果选择处于该情况的内部池或独立服务器，将显示一条警告，告知您有关其他边缘服务器的信息，您可以决定是否要继续。</span><span class="sxs-lookup"><span data-stu-id="89e23-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="89e23-230">如果继续此新关联，则与其他边缘服务器的连接将停止。</span><span class="sxs-lookup"><span data-stu-id="89e23-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="89e23-231">单击 **下一** 个屏幕的"完成"。</span><span class="sxs-lookup"><span data-stu-id="89e23-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="89e23-232">现在，你将能够发布此更新的技术，并按照 Skype for Business [Server](deploy-edge-servers.md) 中"部署边缘服务器"中的说明从此处部署到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="89e23-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="89e23-233">定义硬件负载平衡边缘服务器池的拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="89e23-234">登录到 Skype for Business Server Standard Edition Server 或 Skype for Business Server 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="89e23-234">Log onto your Skype for Business Server Standard Edition server, or a Skype for Business Server Front End Server.</span></span>
    
2. <span data-ttu-id="89e23-235">一旦存在，打开 **Skype for Business Server 拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="89e23-235">Once there, open **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="89e23-236">在控制台树中，展开要部署边缘服务器的站点。</span><span class="sxs-lookup"><span data-stu-id="89e23-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="89e23-237">右键单击 **边缘池**，然后单击 **"新建边缘池"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="89e23-238">你将 **在"定义** 新边缘池 **"屏幕上单击"下一步** "。</span><span class="sxs-lookup"><span data-stu-id="89e23-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="89e23-239">在"定义边缘池 **FQDN"** 屏幕上，键入边缘池将使用的内部完全限定域名 (FQDN) ，然后选择"多计算机池"，完成后单击"下一步"。 </span><span class="sxs-lookup"><span data-stu-id="89e23-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="89e23-240">在 **"选择功能** "屏幕上，可以选择：</span><span class="sxs-lookup"><span data-stu-id="89e23-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="89e23-241">你可能打算对 SIP 访问服务、Skype for Business Server Web 会议服务和 A/V 边缘服务使用相同的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89e23-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="89e23-242">如果是这样，你需要选择"使用单个 **FQDN** 和 IP 地址"复选框 (在下面的步骤 9 中记住) </span><span class="sxs-lookup"><span data-stu-id="89e23-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="89e23-243">如果计划启用联盟，请选中"为此边缘池启用联盟 (**端口 5061**) 复选框。</span><span class="sxs-lookup"><span data-stu-id="89e23-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="89e23-244">单击"下一步"后，你将在 IP 选项 **屏幕上找到** 自己。</span><span class="sxs-lookup"><span data-stu-id="89e23-244">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen.</span></span> <span data-ttu-id="89e23-245">选项如下所示：</span><span class="sxs-lookup"><span data-stu-id="89e23-245">Your options are as follows:</span></span>
    
   - <span data-ttu-id="89e23-246">在内部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="89e23-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="89e23-247">在内部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="89e23-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="89e23-248">在外部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="89e23-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="89e23-249">在外部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="89e23-249">Enable IPv6 on the external interface</span></span>
    
     <span data-ttu-id="89e23-250">无论你使用的是 IPv4 还是 IPv6 地址，这些地址都很容易理解，并且你要在边缘服务器上内部或外部应用这些地址 (在步骤 11) 中需要记住这一点。</span><span class="sxs-lookup"><span data-stu-id="89e23-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="89e23-251">与其他两个拓扑选项不同，在使用硬件负载平衡器时，不得选择选项边缘池的外部 **IP** 地址由 NAT 转换。</span><span class="sxs-lookup"><span data-stu-id="89e23-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="89e23-252">这 **不受支持**。</span><span class="sxs-lookup"><span data-stu-id="89e23-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="89e23-253">在"外部 FQNS"屏幕上，您的选择取决于您在以上步骤 7 中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="89e23-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="89e23-254">如果选中了" **使用单个 FQDN** 和 IP 地址"复选框，则需要在 SIP 访问框中输入单个 **外部** FQDN。</span><span class="sxs-lookup"><span data-stu-id="89e23-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="89e23-255">然后，你需要为每个边缘服务输入不同的端口号，以允许它们相互独立连接。</span><span class="sxs-lookup"><span data-stu-id="89e23-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="89e23-256">建议 SIP 访问边缘服务为5061，建议 **为 Web** 会议边缘服务为 444，A/V边缘服务为 443。</span><span class="sxs-lookup"><span data-stu-id="89e23-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="89e23-257">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="89e23-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="89e23-258">如果未选中"使用单个 **FQDN** 和 IP 地址"复选框，则现在将需要为 **SIP** 访问边缘服务 **、Web** 会议边缘服务和 **A/V** 边缘服务输入三个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="89e23-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="89e23-259">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="89e23-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="89e23-260">现在你已到达"在此池 **屏幕中定义计算机"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="89e23-261">单击“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="89e23-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="89e23-262">现在，您位于"定义 **内部 IP 地址"** 屏幕上。</span><span class="sxs-lookup"><span data-stu-id="89e23-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="89e23-263">在这里，你将在"内部 **IPv4** 地址"和"内部 **IPv6** 地址"文本框中键入边缘服务器的 IP 地址，具体取决于你在步骤 8 中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="89e23-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="89e23-264">准备就绪 **后** 单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="89e23-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="89e23-265">在 **"定义外部 IP 地址** "屏幕上，有一些选项取决于您之前的选择：</span><span class="sxs-lookup"><span data-stu-id="89e23-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="89e23-266">您可以针对所有服务使用单个 FQDN。</span><span class="sxs-lookup"><span data-stu-id="89e23-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="89e23-267">如果是，请在 SIP 访问文本框中键入外部 IPv4 或 IPv6 (，) SIP **访问** 文本框中键入您的外部 IPv4 或 IPv6 **地址**。</span><span class="sxs-lookup"><span data-stu-id="89e23-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="89e23-268">您可能已选择为服务使用三个单独的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="89e23-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="89e23-269">如果是这种情况，请输入 **SIP** 访问边缘服务 **、Web** 会议边缘服务和 **A/V** 边缘服务的外部 IPv4 或 IPv6 地址，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89e23-270">如果之前未选择启用和分配 IPv6 寻址，则看不到此对话框。</span><span class="sxs-lookup"><span data-stu-id="89e23-270">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box.</span></span> <span data-ttu-id="89e23-271">这很正常，只需转到下一步。</span><span class="sxs-lookup"><span data-stu-id="89e23-271">That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="89e23-272">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="89e23-272">Click **Finish**.</span></span> <span data-ttu-id="89e23-273">您刚刚创建的边缘服务器现在应列在"定义此池 **的计算机"** 对话框中。</span><span class="sxs-lookup"><span data-stu-id="89e23-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="89e23-274">仍在"定义此池中的计算机"屏幕上，再次单击"添加"按钮，并重复步骤 11 至 13，直到添加要在此池中拥有的所有边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="89e23-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="89e23-275">完成此操作后，单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="89e23-276">下一个屏幕向上 **是"定义下一个跃点"。**</span><span class="sxs-lookup"><span data-stu-id="89e23-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="89e23-277">在 **"下一个** 跃点池"框中，选择内部池的名称，该名称可能是前端池或独立池。</span><span class="sxs-lookup"><span data-stu-id="89e23-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="89e23-278">如果环境中有控制器，应选择控制器。</span><span class="sxs-lookup"><span data-stu-id="89e23-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="89e23-279">然后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="89e23-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="89e23-280">在 **"关联前端** 池"屏幕上，需要指定一个或多个内部池（包括前端池和 Standard Edition 池）以与此边缘服务器关联。</span><span class="sxs-lookup"><span data-stu-id="89e23-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="89e23-281">只需选择希望使用此边缘服务器与支持的外部用户进行通信的内部池的名称。</span><span class="sxs-lookup"><span data-stu-id="89e23-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="89e23-282">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="89e23-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89e23-283">这里需要记住的一点就是，如果内部池或独立服务器已在使用不同的 Skype for Business Server 边缘服务器，则它们不能有多个关联。</span><span class="sxs-lookup"><span data-stu-id="89e23-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="89e23-284">如果选择处于该情况的内部池或独立服务器，将显示一条警告，告知您有关其他边缘服务器的信息，您可以决定是否要继续。</span><span class="sxs-lookup"><span data-stu-id="89e23-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="89e23-285">如果继续此新关联，则与其他边缘服务器的连接将停止。</span><span class="sxs-lookup"><span data-stu-id="89e23-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="89e23-286">单击 **下一** 个屏幕的"完成"。</span><span class="sxs-lookup"><span data-stu-id="89e23-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="89e23-287">现在，你将能够发布此更新的技术，并按照 Skype for Business [Server](deploy-edge-servers.md) 中"部署边缘服务器"中的说明从此处部署到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="89e23-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="89e23-288">发布边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="89e23-289">完成上述步骤后，可以发布此新拓扑，这也允许你将其导出到 Skype for Business Server 边缘服务器或边缘池。</span><span class="sxs-lookup"><span data-stu-id="89e23-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server Edge Server or Edge pool.</span></span> <span data-ttu-id="89e23-290">请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="89e23-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="89e23-291">如果 **拓扑生成器** (上一过程尚未启动，请启动拓扑生成器) 。</span><span class="sxs-lookup"><span data-stu-id="89e23-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="89e23-292">在 **拓扑生成器的** 控制台树中，右键单击 **Skype for Business Server，** 然后单击 Skype for Business Server **拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="89e23-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="89e23-293">在向导的“欢迎”页上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="89e23-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="89e23-294">在“创建其他数据库”页上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="89e23-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="89e23-295">当状态指示数据库创建成功时，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="89e23-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="89e23-296">要查看日志，请单击“查看日志”。</span><span class="sxs-lookup"><span data-stu-id="89e23-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="89e23-297">要关闭向导，请单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="89e23-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="89e23-298">导出边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="89e23-298">Export your Edge Server topology</span></span>

<span data-ttu-id="89e23-299">若要成功部署，Skype for Business Server 部署向导需要访问中央管理存储数据。</span><span class="sxs-lookup"><span data-stu-id="89e23-299">To deploy successfully, the Skype for Business Server Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="89e23-300">对于域或林中的内部服务器，这通常很简单。</span><span class="sxs-lookup"><span data-stu-id="89e23-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="89e23-301">边缘服务器位于域之外，因此有必要手动将拓扑文件导出到边缘服务器位置，通常位于物理媒体上。</span><span class="sxs-lookup"><span data-stu-id="89e23-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="89e23-302">此导出通过 PowerShell 完成：</span><span class="sxs-lookup"><span data-stu-id="89e23-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="89e23-303">启动 **Skype for Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="89e23-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="89e23-304">在 **Skype for Business Server 命令行管理程序** 中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="89e23-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="89e23-305">将导出的文件复制到外部媒体 (例如，可以从边缘服务器的位置访问的 USB 驱动器或网络) 。</span><span class="sxs-lookup"><span data-stu-id="89e23-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

