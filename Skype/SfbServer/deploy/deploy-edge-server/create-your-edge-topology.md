---
title: 为 Skype for Business Server 2015 创建边缘拓扑
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 摘要： 了解如何创建、 发布和导出业务服务器 2015 Skype 在边缘服务器拓扑。
ms.openlocfilehash: 336bef93fbb0d58c07ebd845fff2751e85464900
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-your-edge-topology-for-skype-for-business-server-2015"></a><span data-ttu-id="d6e81-103">为 Skype for Business Server 2015 创建边缘拓扑</span><span class="sxs-lookup"><span data-stu-id="d6e81-103">Create your Edge topology for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d6e81-104">**摘要：**了解如何创建、 发布和导出业务服务器 2015 Skype 在边缘服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="d6e81-104">**Summary:** Learn how to build, publish, and export your Edge Server topology in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d6e81-105">拓扑生成器是需要使用来生成边缘服务器拓扑结构，就像它用于所有拓扑组件为 Skype 业务服务器 2015年的工具。</span><span class="sxs-lookup"><span data-stu-id="d6e81-105">Topology Builder is the tool you need to use to build your Edge Server topology, just as it's used for any topology component for Skype for Business Server 2015.</span></span> <span data-ttu-id="d6e81-106">执行以下步骤之前，您需要设置至少一个前端池或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="d6e81-106">Before following the steps below, you will need to have set up at least one Front End pool or a Standard Edition server.</span></span>
  
<span data-ttu-id="d6e81-107">我们将在本文中介绍以下主题：</span><span class="sxs-lookup"><span data-stu-id="d6e81-107">We cover the following topics in this article:</span></span>
  
- <span data-ttu-id="d6e81-108">建立边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="d6e81-108">Build your Edge Server topology</span></span>
    
- <span data-ttu-id="d6e81-109">发布边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="d6e81-109">Publish your Edge Server topology</span></span>
    
- <span data-ttu-id="d6e81-110">验证边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="d6e81-110">Export your Edge Server topology</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="d6e81-111">为了遵循下面的步骤，需要登录到下面提及的域服务器，且用来登录的用户应该是以下域组的成员：</span><span class="sxs-lookup"><span data-stu-id="d6e81-111">To follow the steps below, you're going to need to log into the domain servers mentioned below as a user who's a member of the following domain groups:</span></span> 
  
- <span data-ttu-id="d6e81-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d6e81-112">RTCUniversalServerAdmins</span></span>
    
- <span data-ttu-id="d6e81-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="d6e81-113">Domain Admins</span></span>
    
## <a name="build-your-edge-server-topology"></a><span data-ttu-id="d6e81-114">建立边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="d6e81-114">Build your Edge Server topology</span></span>

<span data-ttu-id="d6e81-115">第一个部署步骤构建您 Skype 业务服务器 2015年边缘服务器拓扑，组成三个选项之一：</span><span class="sxs-lookup"><span data-stu-id="d6e81-115">The first deployment step is building your Skype for Business Server 2015 Edge Server topology, which consists of one of three options:</span></span>
  
- <span data-ttu-id="d6e81-116">单个的边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d6e81-116">A single Edge Server</span></span>
    
- <span data-ttu-id="d6e81-117">DNS 负载平衡边缘池 （一个或多个服务器）</span><span class="sxs-lookup"><span data-stu-id="d6e81-117">A DNS load balanced Edge pool (one or more servers)</span></span>
    
- <span data-ttu-id="d6e81-118">硬件负载平衡边缘池 （一个或多个服务器）</span><span class="sxs-lookup"><span data-stu-id="d6e81-118">A hardware load balanced Edge pool (one or more servers)</span></span>
    
<span data-ttu-id="d6e81-p102">如果不确定自己需要哪种选项，那么在开始遵循这些步骤之前，最好先重温规划文档。否则，让我们开始。</span><span class="sxs-lookup"><span data-stu-id="d6e81-p102">If you aren't sure what you need, then before you start following these steps, it's a good time to go over the Planning documentation. Otherwise, let's begin.</span></span>
  
### <a name="defining-the-topology-for-a-single-edge-server"></a><span data-ttu-id="d6e81-121">定义单个边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="d6e81-121">Defining the topology for a single Edge Server</span></span>

1. <span data-ttu-id="d6e81-122">登录到您的 Skype 业务服务器 2015年标准版服务器或 Skype 业务服务器 2015年前端池。</span><span class="sxs-lookup"><span data-stu-id="d6e81-122">Log onto your Skype for Business Server 2015 Standard Edition server, or a Skype for Business Server 2015 Front End pool.</span></span>
    
2. <span data-ttu-id="d6e81-123">一次，打开**Skype 业务服务器 2015年拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-123">Once there, open **Skype for Business Server 2015 Topology Builder**.</span></span>
    
3. <span data-ttu-id="d6e81-124">在控制台树中，展开您要部署边缘服务器到该站点。</span><span class="sxs-lookup"><span data-stu-id="d6e81-124">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="d6e81-125">**边缘池**，右键单击，然后单击**新边池**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-125">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="d6e81-126">您将**定义新边池**在屏幕上以单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-126">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="d6e81-127">**定义边池的 FQDN**在屏幕上，键入内部的完全限定的域名称 (FQDN)，将边缘服务器使用，并选择**单个计算机池**，单击**下一步**完成。</span><span class="sxs-lookup"><span data-stu-id="d6e81-127">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge Server is going to use, and select **Single computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="d6e81-128">在“**选择功能**”屏幕上，可选择：</span><span class="sxs-lookup"><span data-stu-id="d6e81-128">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="d6e81-129">您可能想要相同的 FQDN 和 IP 地址用于 SIP 访问服务、 业务服务器 2015 Web 会议服务，为您 Skype 和 A / V 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="d6e81-129">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server 2015 Web Conferencing service, and your A/V Edge service.</span></span> <span data-ttu-id="d6e81-130">如果是这样，需要选中“**使用一个 FQDN 和 IP 地址**”复选框（做到下面的步骤 9 时，请记得这一点）</span><span class="sxs-lookup"><span data-stu-id="d6e81-130">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="d6e81-131">如果你计划启用联盟，请选中“**为此边缘池启用联盟(端口 5061)**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d6e81-131">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="d6e81-p104">单击“**下一步**”后，你将进入“**IP 选项**”屏幕。选项如下：</span><span class="sxs-lookup"><span data-stu-id="d6e81-p104">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
   - <span data-ttu-id="d6e81-134">在内部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="d6e81-134">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="d6e81-135">在内部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="d6e81-135">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="d6e81-136">在外部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="d6e81-136">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="d6e81-137">在外部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="d6e81-137">Enable IPv6 on the external interface</span></span>
    
   <span data-ttu-id="d6e81-138">这些是很容易理解，是否正在使用 IPv4 或 IPv6 地址，并且您要将这些地址应用边缘服务器上内部还是在外部 （您需要牢记这步骤 10）。</span><span class="sxs-lookup"><span data-stu-id="d6e81-138">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 10).</span></span> <span data-ttu-id="d6e81-139">此外可以选择配置边缘服务器或边缘池使用的外部 IP 地址的网络地址转换 (NAT) 地址。</span><span class="sxs-lookup"><span data-stu-id="d6e81-139">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="d6e81-140">选中“**此边缘池的外部 IP 地址是由 NAT 转换的**”复选框可以执行此配置。</span><span class="sxs-lookup"><span data-stu-id="d6e81-140">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="d6e81-141">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-141">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="d6e81-142">在“外部 FQDN”屏幕上，你的选择取决于你在上面的步骤 7 中所作的选择。</span><span class="sxs-lookup"><span data-stu-id="d6e81-142">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="d6e81-143">如果选中**使用的单个 FQDN 和 IP 地址**复选框，您需要在**SIP 访问**框中，输入您单个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d6e81-143">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="d6e81-144">然后您将需要输入不同的端口号为每个边缘服务允许其所有连接独立。</span><span class="sxs-lookup"><span data-stu-id="d6e81-144">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="d6e81-145">我们建议 **SIP 访问**边缘服务使用 5061，**Web 会议**边缘服务使用 444，**A/V** 边缘服务使用 443。</span><span class="sxs-lookup"><span data-stu-id="d6e81-145">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="d6e81-146">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-146">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="d6e81-147">如果没有检查**使用单个 FQDN 和 IP 地址**复选框，您现在需要输入三个外部 Fqdn **SIP 访问**边缘服务，**网络会议**边缘服务，和**A / V**边缘服务。</span><span class="sxs-lookup"><span data-stu-id="d6e81-147">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="d6e81-148">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-148">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="d6e81-149">你现在在屏幕上**定义的内部 IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-149">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="d6e81-150">这里您需要在**内部的 IPv4 地址**和**内部 IPv6 地址**文本框中，具体取决于您在第 8 步中所做的选择键入边缘服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d6e81-150">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="d6e81-151">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-151">Click **Next** when ready.</span></span>
    
11. <span data-ttu-id="d6e81-152">在“**定义外部 IP 地址**”屏幕上，根据你前面的选择，有几个选项：</span><span class="sxs-lookup"><span data-stu-id="d6e81-152">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="d6e81-153">你可能让所有服务使用一个 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d6e81-153">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="d6e81-154">如果是这样， **SIP 访问**文本框中，键入您外部 IPv4 或 IPv6 地址 （无论您正在使用），然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-154">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="d6e81-155">你可能选择让这些服务使用三个不同的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d6e81-155">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="d6e81-156">如果真是这样， **SIP 访问**边缘服务，**网络会议**边缘服务中，输入外部 IPv4 或 IPv6 地址和**A / V**边服务，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-156">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d6e81-p111">如果先前未选择启用和分配 IPv6 编址，则不会出现此对话框。这是正常现象，请直接进入下一步。</span><span class="sxs-lookup"><span data-stu-id="d6e81-p111">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
12. <span data-ttu-id="d6e81-159">如果您选择了在步骤 8 中回使用 NAT，您现在将获得的**公用 IP 地址**文本框的画面。</span><span class="sxs-lookup"><span data-stu-id="d6e81-159">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="d6e81-160">您将需要输入公用 IPv4 和/或 IPv6 地址已经设置的 A / V 边缘服务要翻译通过 nat。</span><span class="sxs-lookup"><span data-stu-id="d6e81-160">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="d6e81-161">然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-161">Then click **Next**.</span></span>
    
13. <span data-ttu-id="d6e81-162">接下来的屏幕是“**定义下一跃点**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-162">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="d6e81-163">在**下一个跃点库**框中，选择您内部池，可能是一个前端池或独立池的名称。</span><span class="sxs-lookup"><span data-stu-id="d6e81-163">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="d6e81-164">如果导演在您的环境中，应选择控制器。</span><span class="sxs-lookup"><span data-stu-id="d6e81-164">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="d6e81-165">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d6e81-165">Then click **Next**.</span></span>
    
14. <span data-ttu-id="d6e81-166">在**关联的前端池**屏幕中，您需要指定一个或多个内部池，包括前端池和标准版服务器将与该边缘服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="d6e81-166">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition servers, to associate with this Edge Server.</span></span> <span data-ttu-id="d6e81-167">只需选择您希望使用此边缘服务器与支持的外部用户进行通信的内部池的名称。</span><span class="sxs-lookup"><span data-stu-id="d6e81-167">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="d6e81-168">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d6e81-168">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d6e81-169">请记住下面的内容是，如果您的内部池或独立服务器已经使用了不同的 Skype 业务服务器 2015年边缘服务器，它们不能具有多个关联。</span><span class="sxs-lookup"><span data-stu-id="d6e81-169">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server 2015 Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="d6e81-170">如果您选择内部池或独立服务器，在这种情况下，您将看到显示一条警告通知您有关其他边缘服务器，并且您可以决定您是否要继续或不。</span><span class="sxs-lookup"><span data-stu-id="d6e81-170">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="d6e81-171">如果继续这个新的关联，与另一台边缘服务器的连接将停止。</span><span class="sxs-lookup"><span data-stu-id="d6e81-171">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
15. <span data-ttu-id="d6e81-172">在下一个屏幕上单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-172">Click **Finish** on the next screen.</span></span>
    
16. <span data-ttu-id="d6e81-173">现在，您可以在发布此更新的技术，并按照[业务服务器 2015年的 Skype 在部署边缘服务器](deploy-edge-servers.md)中的说明进行操作，从这里到边缘服务器部署。</span><span class="sxs-lookup"><span data-stu-id="d6e81-173">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server 2015](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="d6e81-174">为 DNS 中定义拓扑结构的负载平衡的边缘服务器池</span><span class="sxs-lookup"><span data-stu-id="d6e81-174">Defining the topology for a DNS load balanced Edge Server pool</span></span>

1. <span data-ttu-id="d6e81-175">登录到您的 Skype 业务服务器 2015年标准版服务器或 Skype 业务服务器 2015年前结束服务器。</span><span class="sxs-lookup"><span data-stu-id="d6e81-175">Log onto your Skype for Business Server 2015 Standard Edition server, or a Skype for Business Server 2015 Front End Server.</span></span>
    
2. <span data-ttu-id="d6e81-176">一次，打开**Skype 业务服务器 2015年拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-176">Once there, open **Skype for Business Server 2015 Topology Builder**.</span></span>
    
3. <span data-ttu-id="d6e81-177">在控制台树中，展开您要部署边缘服务器到该站点。</span><span class="sxs-lookup"><span data-stu-id="d6e81-177">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="d6e81-178">**边缘池**，右键单击，然后单击**新边池**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-178">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="d6e81-179">您将**定义新边池**在屏幕上以单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-179">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="d6e81-180">**定义边池的 FQDN**在屏幕上，键入内部边缘池即将使用，完全合格的域名称 (FQDN) 并选择**多个计算机池**，单击**下一步**完成。</span><span class="sxs-lookup"><span data-stu-id="d6e81-180">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="d6e81-181">在“**选择功能**”屏幕上，可选择：</span><span class="sxs-lookup"><span data-stu-id="d6e81-181">On the **Select features** screen, you have a choice:</span></span>
    
    - <span data-ttu-id="d6e81-182">您可能想要相同的 FQDN 和 IP 地址用于 SIP 访问服务、 业务服务器 2015 Web 会议服务，为您 Skype 和 A / V 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="d6e81-182">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server 2015 Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="d6e81-183">如果是这样，需要选中“**使用一个 FQDN 和 IP 地址**”复选框（做到下面的步骤 9 时，请记得这一点）</span><span class="sxs-lookup"><span data-stu-id="d6e81-183">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
    - <span data-ttu-id="d6e81-184">如果你计划启用联盟，请选中“**为此边缘池启用联盟(端口 5061)**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d6e81-184">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="d6e81-p117">单击“**下一步**”后，你将进入“**IP 选项**”屏幕。选项如下：</span><span class="sxs-lookup"><span data-stu-id="d6e81-p117">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
    - <span data-ttu-id="d6e81-187">在内部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="d6e81-187">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="d6e81-188">在内部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="d6e81-188">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="d6e81-189">在外部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="d6e81-189">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="d6e81-190">在外部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="d6e81-190">Enable IPv6 on the external interface</span></span>
    
    <span data-ttu-id="d6e81-191">这些是很容易理解，是否正在使用 IPv4 或 IPv6 地址，并且您要将这些地址应用边缘服务器上内部还是在外部 （您需要牢记这步骤 11）。</span><span class="sxs-lookup"><span data-stu-id="d6e81-191">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span> <span data-ttu-id="d6e81-192">此外可以选择配置边缘服务器或边缘池使用的外部 IP 地址的网络地址转换 (NAT) 地址。</span><span class="sxs-lookup"><span data-stu-id="d6e81-192">You also have the option of configuring your Edge Server or your Edge pool to use a network address translation (NAT) address for the external IP address.</span></span> <span data-ttu-id="d6e81-193">选中“**此边缘池的外部 IP 地址是由 NAT 转换的**”复选框可以执行此配置。</span><span class="sxs-lookup"><span data-stu-id="d6e81-193">You can do this by choosing **The external IP address of this Edge pool is translated by NAT** check box .</span></span> <span data-ttu-id="d6e81-194">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-194">Click **Next** when ready.</span></span>
    
9. <span data-ttu-id="d6e81-195">在“外部 FQDN”屏幕上，你的选择取决于你在上面的步骤 7 中所作的选择。</span><span class="sxs-lookup"><span data-stu-id="d6e81-195">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="d6e81-196">如果选中**使用的单个 FQDN 和 IP 地址**复选框，您需要在**SIP 访问**框中，输入您单个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d6e81-196">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="d6e81-197">然后您将需要输入不同的端口号为每个边缘服务允许其所有连接独立。</span><span class="sxs-lookup"><span data-stu-id="d6e81-197">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="d6e81-198">我们建议 **SIP 访问**边缘服务使用 5061，**Web 会议**边缘服务使用 444，**A/V** 边缘服务使用 443。</span><span class="sxs-lookup"><span data-stu-id="d6e81-198">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="d6e81-199">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-199">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="d6e81-200">如果没有检查**使用单个 FQDN 和 IP 地址**复选框，您现在需要输入三个外部 Fqdn **SIP 访问**边缘服务，**网络会议**边缘服务，和**A / V**边缘服务。</span><span class="sxs-lookup"><span data-stu-id="d6e81-200">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="d6e81-201">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-201">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="d6e81-202">现在您已经达到了**定义该池中的计算机**屏幕。</span><span class="sxs-lookup"><span data-stu-id="d6e81-202">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="d6e81-203">单击“**添加**”按钮。</span><span class="sxs-lookup"><span data-stu-id="d6e81-203">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="d6e81-204">你现在在屏幕上**定义的内部 IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-204">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="d6e81-205">这里您需要在**内部的 IPv4 地址**和**内部 IPv6 地址**文本框中，具体取决于您在第 8 步中所做的选择键入边缘服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d6e81-205">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="d6e81-206">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-206">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="d6e81-207">在“**定义外部 IP 地址**”屏幕上，根据你前面的选择，有几个选项：</span><span class="sxs-lookup"><span data-stu-id="d6e81-207">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="d6e81-208">你可能让所有服务使用一个 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d6e81-208">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="d6e81-209">如果是这样， **SIP 访问**文本框中，键入您外部 IPv4 或 IPv6 地址 （无论您正在使用），然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-209">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="d6e81-210">你可能选择让这些服务使用三个不同的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d6e81-210">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="d6e81-211">如果真是这样， **SIP 访问**边缘服务，**网络会议**边缘服务中，输入外部 IPv4 或 IPv6 地址和**A / V**边服务，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-211">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d6e81-p125">如果先前未选择启用和分配 IPv6 编址，则不会出现此对话框。这是正常现象，请直接进入下一步。</span><span class="sxs-lookup"><span data-stu-id="d6e81-p125">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="d6e81-214">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-214">Click **Finish**.</span></span> <span data-ttu-id="d6e81-215">现在应在**定义该池中的计算机**对话框中列出刚创建的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="d6e81-215">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="d6e81-216">虽然仍然在**定义该池中的计算机**屏幕上，请再次单击**添加**按钮，直到添加了您打算将此池中的所有边缘服务器重复步骤 11 至 13。</span><span class="sxs-lookup"><span data-stu-id="d6e81-216">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="d6e81-217">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-217">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="d6e81-218">如果您选择了在步骤 8 中回使用 NAT，您现在将获得的**公用 IP 地址**文本框的画面。</span><span class="sxs-lookup"><span data-stu-id="d6e81-218">If you chose to use NAT back in Step 8, you'll now get a screen with a **Public IP address** textbox.</span></span> <span data-ttu-id="d6e81-219">您将需要输入公用 IPv4 和/或 IPv6 地址已经设置的 A / V 边缘服务要翻译通过 nat。</span><span class="sxs-lookup"><span data-stu-id="d6e81-219">You'll need to enter the public IPv4 and/or IPv6 address you've set for the A/V Edge service, to be translated by NAT.</span></span> <span data-ttu-id="d6e81-220">然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-220">Then click **Next**.</span></span>
    
16. <span data-ttu-id="d6e81-221">接下来的屏幕是“**定义下一跃点**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-221">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="d6e81-222">在**下一个跃点库**框中，选择您内部池，可能是一个前端池或独立池的名称。</span><span class="sxs-lookup"><span data-stu-id="d6e81-222">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="d6e81-223">如果导演在您的环境中，应选择控制器。</span><span class="sxs-lookup"><span data-stu-id="d6e81-223">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="d6e81-224">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d6e81-224">Then click **Next**.</span></span>
    
17. <span data-ttu-id="d6e81-225">在**关联的前端池**屏幕中，您需要指定一个或多个内部池，包括前端池和标准版池，将与此边缘服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="d6e81-225">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="d6e81-226">只需选择您希望使用此边缘服务器与支持的外部用户进行通信的内部池的名称。</span><span class="sxs-lookup"><span data-stu-id="d6e81-226">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="d6e81-227">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d6e81-227">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d6e81-228">请记住下面的内容是，如果您的内部池或独立服务器已经使用了不同的 Skype 业务服务器 2015年边缘服务器，它们不能具有多个关联。</span><span class="sxs-lookup"><span data-stu-id="d6e81-228">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server 2015 Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="d6e81-229">如果您选择内部池或独立服务器，在这种情况下，您将看到显示一条警告通知您有关其他边缘服务器，并且您可以决定您是否要继续或不。</span><span class="sxs-lookup"><span data-stu-id="d6e81-229">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="d6e81-230">如果继续这个新的关联，与另一台边缘服务器的连接将停止。</span><span class="sxs-lookup"><span data-stu-id="d6e81-230">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
18. <span data-ttu-id="d6e81-231">在下一个屏幕上单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-231">Click **Finish** on the next screen.</span></span>
    
19. <span data-ttu-id="d6e81-232">现在，您可以在发布此更新的技术，并按照[业务服务器 2015年的 Skype 在部署边缘服务器](deploy-edge-servers.md)中的说明进行操作，从这里到边缘服务器部署。</span><span class="sxs-lookup"><span data-stu-id="d6e81-232">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server 2015](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="d6e81-233">定义的拓扑硬件负载平衡边缘服务器池</span><span class="sxs-lookup"><span data-stu-id="d6e81-233">Defining the topology for a hardware load balanced Edge Server pool</span></span>

1. <span data-ttu-id="d6e81-234">登录到您的 Skype 业务服务器 2015年标准版服务器或 Skype 业务服务器 2015年前结束服务器。</span><span class="sxs-lookup"><span data-stu-id="d6e81-234">Log onto your Skype for Business Server 2015 Standard Edition server, or a Skype for Business Server 2015 Front End Server.</span></span>
    
2. <span data-ttu-id="d6e81-235">一次，打开**Skype 业务服务器 2015年拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-235">Once there, open **Skype for Business Server 2015 Topology Builder**.</span></span>
    
3. <span data-ttu-id="d6e81-236">在控制台树中，展开您要部署边缘服务器到该站点。</span><span class="sxs-lookup"><span data-stu-id="d6e81-236">In the console tree, expand the site you're going to deploy the Edge Server to.</span></span>
    
4. <span data-ttu-id="d6e81-237">**边缘池**，右键单击，然后单击**新边池**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-237">Right-click **Edge pools**, and then click **New Edge pool**.</span></span>
    
5. <span data-ttu-id="d6e81-238">您将**定义新边池**在屏幕上以单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-238">You'll click **Next** on the **Define New Edge pool** screen.</span></span>
    
6. <span data-ttu-id="d6e81-239">**定义边池的 FQDN**在屏幕上，键入内部边缘池即将使用，完全合格的域名称 (FQDN) 并选择**多个计算机池**，单击**下一步**完成。</span><span class="sxs-lookup"><span data-stu-id="d6e81-239">On the **Define the Edge pool FQDN** screen, type the internal fully qualified domain name (FQDN) that the Edge pool is going to use, and select **Multiple computer pool**, clicking **Next** when done.</span></span>
    
7. <span data-ttu-id="d6e81-240">在“**选择功能**”屏幕上，可选择：</span><span class="sxs-lookup"><span data-stu-id="d6e81-240">On the **Select features** screen, you have a choice:</span></span>
    
   - <span data-ttu-id="d6e81-241">您可能想要相同的 FQDN 和 IP 地址用于 SIP 访问服务、 业务服务器 2015 Web 会议服务，为您 Skype 和 A / V 边缘服务。</span><span class="sxs-lookup"><span data-stu-id="d6e81-241">You may intend to use the same FQDN and IP address for your SIP Access service, your Skype for Business Server 2015 Web Conferencing Service, and your A/V Edge service.</span></span> <span data-ttu-id="d6e81-242">如果是这样，需要选中“**使用一个 FQDN 和 IP 地址**”复选框（做到下面的步骤 9 时，请记得这一点）</span><span class="sxs-lookup"><span data-stu-id="d6e81-242">If so, you need to choose the **Use a single FQDN and IP address checkbox** (and keep this in mind for Step 9 below)</span></span>
    
   - <span data-ttu-id="d6e81-243">如果你计划启用联盟，请选中“**为此边缘池启用联盟(端口 5061)**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d6e81-243">If you're planning to enable federation, choose the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
8. <span data-ttu-id="d6e81-p133">单击“**下一步**”后，你将进入“**IP 选项**”屏幕。选项如下：</span><span class="sxs-lookup"><span data-stu-id="d6e81-p133">Once you've clicked **Next**, you'll find yourself on the **IP Options** screen. Your options are as follows:</span></span>
    
   - <span data-ttu-id="d6e81-246">在内部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="d6e81-246">Enable IPv4 on the internal interface</span></span>
    
   - <span data-ttu-id="d6e81-247">在内部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="d6e81-247">Enable IPv6 on the internal interface</span></span>
    
   - <span data-ttu-id="d6e81-248">在外部接口上启用 IPv4</span><span class="sxs-lookup"><span data-stu-id="d6e81-248">Enable IPv4 on the external interface</span></span>
    
   - <span data-ttu-id="d6e81-249">在外部接口上启用 IPv6</span><span class="sxs-lookup"><span data-stu-id="d6e81-249">Enable IPv6 on the external interface</span></span>
    
    <span data-ttu-id="d6e81-250">这些是很容易理解，是否正在使用 IPv4 或 IPv6 地址，并且您要将这些地址应用边缘服务器上内部还是在外部 （您需要牢记这步骤 11）。</span><span class="sxs-lookup"><span data-stu-id="d6e81-250">These are pretty self-explanatory, whether you're using IPv4 or IPv6 addresses, and you're applying those addresses on your Edge Server internally or externally (you'll need to keep this in mind for Step 11).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d6e81-251">两个拓扑与其他选项不同，使用硬件负载平衡器时，您**不必须**选择**通过 NAT 转换边缘池的外部 IP 地址**的选项。</span><span class="sxs-lookup"><span data-stu-id="d6e81-251">Unlike the other two topology options, when using a hardware load balancer, you **MUST NOT** select the option **The external IP address of the Edge Pool is translated by NAT**.</span></span> <span data-ttu-id="d6e81-252">这**不受支持**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-252">This is **not supported**.</span></span>
  
9. <span data-ttu-id="d6e81-253">在“外部 FQDN”屏幕上，你的选择取决于你在上面的步骤 7 中所作的选择。</span><span class="sxs-lookup"><span data-stu-id="d6e81-253">On the External FQDNs screen, your choices depend on the selection you made in Step 7 above.</span></span>
    
   - <span data-ttu-id="d6e81-254">如果选中**使用的单个 FQDN 和 IP 地址**复选框，您需要在**SIP 访问**框中，输入您单个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d6e81-254">If you checked the **Use a single FQDN and IP Address** check box, you need to enter your single external FQDN in the **SIP Access** box.</span></span> <span data-ttu-id="d6e81-255">然后您将需要输入不同的端口号为每个边缘服务允许其所有连接独立。</span><span class="sxs-lookup"><span data-stu-id="d6e81-255">Then you'll need to enter different port numbers for each edge service to allow them all to connect independently.</span></span> <span data-ttu-id="d6e81-256">我们建议 **SIP 访问**边缘服务使用 5061，**Web 会议**边缘服务使用 444，**A/V** 边缘服务使用 443。</span><span class="sxs-lookup"><span data-stu-id="d6e81-256">We recommend 5061 for the **SIP Access** Edge service, 444 for the **Web Conferencing** Edge service, and 443 for the **A/V** Edge service.</span></span> <span data-ttu-id="d6e81-257">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-257">Click **Next** when done.</span></span>
    
   - <span data-ttu-id="d6e81-258">如果没有检查**使用单个 FQDN 和 IP 地址**复选框，您现在需要输入三个外部 Fqdn **SIP 访问**边缘服务，**网络会议**边缘服务，和**A / V**边缘服务。</span><span class="sxs-lookup"><span data-stu-id="d6e81-258">If you didn't check the **Use a single FQDN and IP Address** check box, you'll now need to enter the three external FQDNs for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service.</span></span> <span data-ttu-id="d6e81-259">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-259">Click **Next** when done.</span></span>
    
10. <span data-ttu-id="d6e81-260">现在您已经达到了**定义该池中的计算机**屏幕。</span><span class="sxs-lookup"><span data-stu-id="d6e81-260">Now you've reached the **Define the computers in this pool** screen.</span></span> <span data-ttu-id="d6e81-261">单击“**添加**”按钮。</span><span class="sxs-lookup"><span data-stu-id="d6e81-261">Click the **Add** button.</span></span>
    
11. <span data-ttu-id="d6e81-262">你现在在屏幕上**定义的内部 IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-262">You're now on the **Define the Internal IP address** screen.</span></span> <span data-ttu-id="d6e81-263">这里您需要在**内部的 IPv4 地址**和**内部 IPv6 地址**文本框中，具体取决于您在第 8 步中所做的选择键入边缘服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d6e81-263">Here you'll type the IP address of your Edge Server in the **Internal IPv4 address** and **Internal IPv6 address** text boxes, depending on the choices you made back in Step 8.</span></span> <span data-ttu-id="d6e81-264">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-264">Click **Next** when ready.</span></span>
    
12. <span data-ttu-id="d6e81-265">在“**定义外部 IP 地址**”屏幕上，根据你前面的选择，有几个选项：</span><span class="sxs-lookup"><span data-stu-id="d6e81-265">On the **Define the External IP address** screen, you have a few options depending on your previous choices:</span></span>
    
    - <span data-ttu-id="d6e81-266">你可能让所有服务使用一个 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d6e81-266">You may be using a single FQDN for all services.</span></span> <span data-ttu-id="d6e81-267">如果是这样， **SIP 访问**文本框中，键入您外部 IPv4 或 IPv6 地址 （无论您正在使用），然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-267">If so, type your external IPv4 or IPv6 address (whichever you're using) into the **SIP Access** text box, and then click **Next**.</span></span>
    
    - <span data-ttu-id="d6e81-268">你可能选择让这些服务使用三个不同的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d6e81-268">You may have chosen to use three separate FQDNs and IP addresses for the services.</span></span> <span data-ttu-id="d6e81-269">如果真是这样， **SIP 访问**边缘服务，**网络会议**边缘服务中，输入外部 IPv4 或 IPv6 地址和**A / V**边服务，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-269">If that's the case, enter your external IPv4 or IPv6 addresses for the **SIP Access** Edge service, the **Web Conferencing** Edge service, and the **A/V** Edge service, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d6e81-p141">如果先前未选择启用和分配 IPv6 编址，则不会出现此对话框。这是正常现象，请直接进入下一步。</span><span class="sxs-lookup"><span data-stu-id="d6e81-p141">If you didn't previously choose to enable and assign IPv6 addressing, you won't see this dialog box. That's normal, just go to the next step.</span></span> 
  
13. <span data-ttu-id="d6e81-272">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-272">Click **Finish**.</span></span> <span data-ttu-id="d6e81-273">现在应在**定义该池中的计算机**对话框中列出刚创建的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="d6e81-273">The Edge Server you just created should now be listed in the **Define the computers in this pool** dialog box.</span></span>
    
14. <span data-ttu-id="d6e81-274">虽然仍然在**定义该池中的计算机**屏幕上，请再次单击**添加**按钮，直到添加了您打算将此池中的所有边缘服务器重复步骤 11 至 13。</span><span class="sxs-lookup"><span data-stu-id="d6e81-274">While still on the **Define the computers in this pool** screen, click the **Add** button again and repeat steps 11 through 13 until you've added all the Edge Servers you intend to have in this pool.</span></span> <span data-ttu-id="d6e81-275">完成后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-275">When this is complete, click **Next**.</span></span>
    
15. <span data-ttu-id="d6e81-276">接下来的屏幕是“**定义下一跃点**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-276">Next screen up is **Define the next hop**.</span></span> <span data-ttu-id="d6e81-277">在**下一个跃点库**框中，选择您内部池，可能是一个前端池或独立池的名称。</span><span class="sxs-lookup"><span data-stu-id="d6e81-277">In the **Next hop pool** box, select the name of your internal pool, which might be a Front End pool or a Standalone pool.</span></span> <span data-ttu-id="d6e81-278">如果导演在您的环境中，应选择控制器。</span><span class="sxs-lookup"><span data-stu-id="d6e81-278">If you have a Director in your environment, you should choose the Director.</span></span> <span data-ttu-id="d6e81-279">然后单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d6e81-279">Then click **Next**.</span></span>
    
16. <span data-ttu-id="d6e81-280">在**关联的前端池**屏幕中，您需要指定一个或多个内部池，包括前端池和标准版池，将与此边缘服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="d6e81-280">On the **Associate Front End pools** screen, you'll need to specify one or more internal pools, including Front End pools and Standard Edition pools, to associate with this Edge Server.</span></span> <span data-ttu-id="d6e81-281">只需选择您希望使用此边缘服务器与支持的外部用户进行通信的内部池的名称。</span><span class="sxs-lookup"><span data-stu-id="d6e81-281">Just choose the names of the internal pools you want using this Edge Server to communicate with supported external users.</span></span> <span data-ttu-id="d6e81-282">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d6e81-282">Click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d6e81-283">请记住下面的内容是，如果您的内部池或独立服务器已经使用了不同的 Skype 业务服务器 2015年边缘服务器，它们不能具有多个关联。</span><span class="sxs-lookup"><span data-stu-id="d6e81-283">Something to keep in mind here is, if your internal pools or standalone servers are already using a different Skype for Business Server 2015 Edge Server, they can't have multiple associations.</span></span> <span data-ttu-id="d6e81-284">如果您选择内部池或独立服务器，在这种情况下，您将看到显示一条警告通知您有关其他边缘服务器，并且您可以决定您是否要继续或不。</span><span class="sxs-lookup"><span data-stu-id="d6e81-284">If you choose an internal pool or standalone server that's in that situation, you'll see a warning appear telling you about the other Edge Server, and you can decide whether you want to continue or not.</span></span> <span data-ttu-id="d6e81-285">如果继续这个新的关联，与另一台边缘服务器的连接将停止。</span><span class="sxs-lookup"><span data-stu-id="d6e81-285">If you go ahead with this new association, the connection to the other Edge Server will stop.</span></span> 
  
17. <span data-ttu-id="d6e81-286">在下一个屏幕上单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-286">Click **Finish** on the next screen.</span></span>
    
18. <span data-ttu-id="d6e81-287">现在，您可以在发布此更新的技术，并按照[业务服务器 2015年的 Skype 在部署边缘服务器](deploy-edge-servers.md)中的说明进行操作，从这里到边缘服务器部署。</span><span class="sxs-lookup"><span data-stu-id="d6e81-287">Now you'll be able to publish this updated technology, and follow the instructions in [Deploy Edge Servers in Skype for Business Server 2015](deploy-edge-servers.md) to deploy to your Edge Server from here.</span></span>
    
## <a name="publish-your-edge-server-topology"></a><span data-ttu-id="d6e81-288">发布边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="d6e81-288">Publish your Edge Server topology</span></span>

<span data-ttu-id="d6e81-289">一旦完成上述步骤后，就可以发布此新的拓扑，还允许您将它导出到您 Skype 业务服务器 2015年边或边池。</span><span class="sxs-lookup"><span data-stu-id="d6e81-289">Once you've finished the steps above, it's time to publish this new topology, which will also allow you to export it to your Skype for Business Server 2015 Edge Server or Edge pool.</span></span> <span data-ttu-id="d6e81-290">请按以下步骤执行：</span><span class="sxs-lookup"><span data-stu-id="d6e81-290">Follow these steps:</span></span>
  
1. <span data-ttu-id="d6e81-291">启动“**拓扑生成器**”（如果在前面的过程中还未启动）。</span><span class="sxs-lookup"><span data-stu-id="d6e81-291">Start **Topology Builder** (if it's not started already from the previous procedure).</span></span>
    
2. <span data-ttu-id="d6e81-292">在**拓扑生成器**，在控制台树中，右键单击**业务服务器 2015年的 Skype** ，然后单击**Skype 业务服务器拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-292">In **Topology Builder**, in the console tree, right-click **Skype for Business Server 2015** and then click **Skype for Business Server Topology Builder**.</span></span>
    
3. <span data-ttu-id="d6e81-293">在向导的“**欢迎**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-293">On the **Welcome** page of the wizard, click **Next**.</span></span>
    
4. <span data-ttu-id="d6e81-294">在“**创建其他数据库**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-294">On the **Create other databases** page, click **Next**.</span></span>
    
5. <span data-ttu-id="d6e81-295">当状态指示数据库创建成功时，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d6e81-295">When the status indicates that the database creation succeeded, do the following:</span></span>
    
    - <span data-ttu-id="d6e81-296">若要查看日志，请单击“**查看日志**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-296">To view the log, click **View log**.</span></span>
    
    - <span data-ttu-id="d6e81-297">若要关闭向导，请单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d6e81-297">To close the wizard, click **Finish**.</span></span>
    
## <a name="export-your-edge-server-topology"></a><span data-ttu-id="d6e81-298">验证边缘服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="d6e81-298">Export your Edge Server topology</span></span>

<span data-ttu-id="d6e81-299">若要成功部署，Skype 业务服务器 2015年部署向导需要集中管理存储数据的访问。</span><span class="sxs-lookup"><span data-stu-id="d6e81-299">To deploy successfully, the Skype for Business Server 2015 Deployment Wizard needs access to the Central Management store data.</span></span> <span data-ttu-id="d6e81-300">对于域或林中的内部服务器，这通常很容易。</span><span class="sxs-lookup"><span data-stu-id="d6e81-300">For internal servers in your domain or forest, this typically is straightforward.</span></span> <span data-ttu-id="d6e81-301">边缘服务器是域中，外部，因此很需要手动将该拓扑文件导出到边缘服务器的位置，通常在物理介质上。</span><span class="sxs-lookup"><span data-stu-id="d6e81-301">Edge Servers are outside of the domain, and so it's necessary to manually export the topology file to the Edge Server location, usually on a physical media.</span></span> <span data-ttu-id="d6e81-302">这样的导出通过 PowerShell 执行：</span><span class="sxs-lookup"><span data-stu-id="d6e81-302">This export is done via PowerShell:</span></span>
  
1. <span data-ttu-id="d6e81-303">启动**业务服务器管理外壳的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="d6e81-303">Start the **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d6e81-304">在**Skype 的业务服务器管理外壳程序**中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d6e81-304">In the **Skype for Business Server Management Shell**, run the following:</span></span>
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. <span data-ttu-id="d6e81-305">将导出的文件复制到外部媒体 （例如，USB 驱动器或网络共享，可以达到从边缘服务器的位置）。</span><span class="sxs-lookup"><span data-stu-id="d6e81-305">Copy the exported file to external media (for example, a USB drive or network share that you can reach from the Edge Server's location).</span></span>
    

