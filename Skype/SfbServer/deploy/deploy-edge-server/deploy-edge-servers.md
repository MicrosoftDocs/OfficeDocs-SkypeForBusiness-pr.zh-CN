---
title: 在 Skype for Business 服务器中部署边缘服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 摘要：了解如何将 Edge 服务器部署到 Skype for Business 服务器环境中。
ms.openlocfilehash: 5411c2934191aba1f4efb8eabf5e909c8cad710e
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768305"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="d2dc3-103">在 Skype for Business 服务器中部署边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d2dc3-103">Deploy Edge Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="d2dc3-104">**摘要：** 了解如何将 Edge 服务器部署到 Skype for Business 服务器环境中。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-104">**Summary:** Learn how to deploy Edge Servers into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="d2dc3-105">以下各节包含在 Skype for business Server 文档中查看了[适用于 Edge 服务器部署](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)的 Skype For Business 服务器计划后遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-105">The following sections contain steps that are meant to be followed after the Skype for Business Server [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) documentation has been reviewed.</span></span> <span data-ttu-id="d2dc3-106">部署步骤如下：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-106">The deployment steps are as follows:</span></span>
  
- <span data-ttu-id="d2dc3-107">网络接口</span><span class="sxs-lookup"><span data-stu-id="d2dc3-107">Network interfaces</span></span>
    
- <span data-ttu-id="d2dc3-108">安装</span><span class="sxs-lookup"><span data-stu-id="d2dc3-108">Installation</span></span>
    
- <span data-ttu-id="d2dc3-109">证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-109">Certificates</span></span>
    
- <span data-ttu-id="d2dc3-110">启动边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d2dc3-110">Starting the Edge Servers</span></span>
    
## <a name="network-interfaces"></a><span data-ttu-id="d2dc3-111">网络接口</span><span class="sxs-lookup"><span data-stu-id="d2dc3-111">Network interfaces</span></span>

<span data-ttu-id="d2dc3-112">如规划中所述，你将在托管你的边缘服务器所在的外围网络中配置网络接口，或者在外围网络中没有 DNS。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-112">As noted in Planning, you will either be configuring your network interface with DNS in the perimeter network hosting your Edge Servers, or without DNS in the perimeter network.</span></span>
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="d2dc3-113">使用外围网络中 DNS 服务器的接口配置</span><span class="sxs-lookup"><span data-stu-id="d2dc3-113">Interface configuration with DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="d2dc3-114">为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-114">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2dc3-115">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-115">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="d2dc3-116">在你的外部界面上，你将配置下列操作**之一**：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-116">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="d2dc3-117">a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-117">a.</span></span> <span data-ttu-id="d2dc3-118">在外部外围网络子网上配置三个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-118">Three static IP addresses on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="d2dc3-119">配置适配器 DNS 设置以指向一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-119">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
   <span data-ttu-id="d2dc3-120">b.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-120">b.</span></span> <span data-ttu-id="d2dc3-121">在外部外围网络子网上配置一个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-121">One static IP address on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="d2dc3-122">配置适配器 DNS 设置以指向一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-122">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span> <span data-ttu-id="d2dc3-123">仅当以前已将你的拓扑配置为在端口分配中具有非标准值（在 "[创建 Skype for Business 服务器的边缘拓扑](create-your-edge-topology.md)" 文章中介绍）时，此配置才是可接受的。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-123">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="d2dc3-124">在你的内部接口上，在内部外围网络子网中配置一个静态 IP，并且不设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-124">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="d2dc3-125">配置适配器 DNS 设置，以指向至少一台 DNS 服务器，但最好是一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-125">Configure the adaptor DNS settings to point to at least one DNS server, but preferably a pair of perimeter DNS servers.</span></span>
    
4. <span data-ttu-id="d2dc3-126">在内部接口上为客户端、Skype for business Server 和 Exchange 统一消息（UM）服务器所驻留的所有内部网络创建永久静态路由。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-126">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="d2dc3-127">不使用外围网络中 DNS 服务器的接口配置</span><span class="sxs-lookup"><span data-stu-id="d2dc3-127">Interface configuration without DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="d2dc3-128">为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-128">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d2dc3-129">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-129">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="d2dc3-130">在你的外部界面上，你将配置下列操作**之一**：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-130">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="d2dc3-131">a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-131">a.</span></span> <span data-ttu-id="d2dc3-132">在外部外围网络子网上配置三个静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-132">Three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="d2dc3-133">你还需要在外部接口上配置默认网关，例如，将面向 internet 的路由器或外部防火墙定义为默认网关。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-133">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="d2dc3-134">将适配器 DNS 设置配置为指向一台外部 DNS 服务器，最好是一对外部 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-134">Configure the adapter DNS settings to point to an external DNS server, ideally a pair of external DNS servers.</span></span>
    
   <span data-ttu-id="d2dc3-135">b.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-135">b.</span></span> <span data-ttu-id="d2dc3-136">在外部外围网络子网上配置一个静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-136">One static IP address on the external perimeter network subnet.</span></span> <span data-ttu-id="d2dc3-137">你还需要在外部接口上配置默认网关，例如，将面向 internet 的路由器或外部防火墙定义为默认网关。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-137">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="d2dc3-138">将适配器 DNS 设置配置为指向一台外部 DNS 服务器，最好是一对外部 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-138">Configure the adapter DNS settings to point to an external DNS server, or ideally a pair of external DNS servers.</span></span> <span data-ttu-id="d2dc3-139">仅当以前已将你的拓扑配置为在端口分配中具有非标准值（在 "[创建 Skype for Business 服务器的边缘拓扑](create-your-edge-topology.md)" 文章中介绍）时，此配置才是可接受的。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-139">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="d2dc3-140">在你的内部接口上，在内部外围网络子网中配置一个静态 IP，并且不设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-140">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="d2dc3-141">另外将适配器 DNS 设置留空。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-141">Also leave the adapter DNS settings empty.</span></span>
    
4. <span data-ttu-id="d2dc3-142">在内部接口上为客户端、Skype for business Server 和 Exchange 统一消息（UM）服务器所驻留的所有内部网络创建永久静态路由。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-142">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
5. <span data-ttu-id="d2dc3-143">编辑每台边缘服务器上的主机文件，以包含下一个跃点服务器或虚拟 IP （VIP）的记录。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-143">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP).</span></span> <span data-ttu-id="d2dc3-144">此记录将是在拓扑生成器中配置为 Edge 服务器下一跃点地址的 Director、Standard Edition 服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-144">This record will be the Director, Standard Edition server or Front End pool you configured as the Edge Server next hop address in Topology Builder.</span></span> <span data-ttu-id="d2dc3-145">如果你使用的是 DNS 负载平衡，请为下一个跃点池的每个成员包含一行。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-145">If you're using DNS load balancing, include a line for each member of the next hop pool.</span></span>
    
## <a name="installation"></a><span data-ttu-id="d2dc3-146">安装</span><span class="sxs-lookup"><span data-stu-id="d2dc3-146">Installation</span></span>

<span data-ttu-id="d2dc3-147">若要成功完成这些步骤，你需要按照 "[为 Skype For Business 服务器创建边缘拓扑](create-your-edge-topology.md)" 文章中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-147">To complete these steps successfully, you will need to have followed the steps in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
  
1. <span data-ttu-id="d2dc3-148">使用本地管理员组中的帐户登录到已为 Edge 服务器角色配置的服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-148">Log onto the server you've been configuring for the Edge Server role with an account that's in the local Administrator's group.</span></span>
    
2. <span data-ttu-id="d2dc3-149">你将需要复制到此计算机上的 Edge 服务器拓扑文档末尾的拓扑配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-149">You'll need the topology configuration file you copied out at the end of the Edge Server Topology documentation on this machine.</span></span> <span data-ttu-id="d2dc3-150">访问保存该配置文件的外部介质（如 USB 驱动器或共享）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-150">Access the external media you placed that configuration file on (like a USB drive or share).</span></span>
    
3. <span data-ttu-id="d2dc3-151">启动**部署向导**。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-151">Start the **Deployment Wizard**.</span></span>
    
4. <span data-ttu-id="d2dc3-152">向导打开后，单击 "**安装或更新 Skype for Business 服务器系统**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-152">Once the wizard opens, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="d2dc3-153">向导将运行检查以查看是否已安装任何内容。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-153">The wizard will run checks to see if anything's already installed.</span></span> <span data-ttu-id="d2dc3-154">第一次运行向导时，您将希望从**步骤1开始。安装本地配置存储。**</span><span class="sxs-lookup"><span data-stu-id="d2dc3-154">As this is the first time running the wizard, you'll want to start at **Step 1. Install Local Configuration Store.**</span></span>
    
6. <span data-ttu-id="d2dc3-155">将显示 "**配置中央管理存储的本地副本**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-155">The **Configure Local Replica of Central Management store** dialog will appear.</span></span> <span data-ttu-id="d2dc3-156">您需要单击 "**从文件导入" （建议用于边缘服务器）**。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-156">You need to click **Import from a file (Recommended for Edge Servers)**.</span></span>
    
7. <span data-ttu-id="d2dc3-157">从这里，浏览到你先前导出拓扑的位置，选择 .zip 文件，然后单击“**打开**”，再单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-157">From here, browse to the location of the topology you exported previously, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="d2dc3-158">部署向导将读取配置文件并将 XML 配置文件写入本地计算机。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-158">The Deployment Wizard will read the configuration file and write the XML configuration file to the local computer.</span></span>
    
9. <span data-ttu-id="d2dc3-159">“**正在执行命令**”过程完成后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-159">After the **Executing Commands** process is finished, click **Finish**.</span></span>
    
10. <span data-ttu-id="d2dc3-160">在 "部署向导" 中，单击 "**步骤 2"。设置或删除 Skype for business 服务器组件**。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-160">In the Deployment Wizard, click **Step 2. Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="d2dc3-161">然后，向导将安装在存储在本地计算机上的 XML 配置文件中指定的 Skype for business Server Edge 组件。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-161">The wizard will then install the Skype for Business Server Edge components specified in the XML configuration file that's been stored on the local computer.</span></span>
    
11. <span data-ttu-id="d2dc3-162">安装完成后，您可以移动到以下 "**证书**" 部分中的步骤。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-162">Once the installation's complete, you can move onto the steps in the **Certificates** section below.</span></span>
    
## <a name="certificates"></a><span data-ttu-id="d2dc3-163">证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-163">Certificates</span></span>

<span data-ttu-id="d2dc3-164">边缘服务器的证书要求可在 Edge 证书规划文档中找到。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-164">The certificate requirements for the Edge Server can be found in the Edge Certificate Planning documentation.</span></span> <span data-ttu-id="d2dc3-165">设置证书的步骤如下。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-165">The steps for setting up certificates are below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2dc3-166">运行 "证书向导" 时，你需要以具有你要使用的证书模板类型的正确权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-166">When running the Certificate Wizard, you need to be logged in as an account with the correct permissions for the type of certificate template you're going to use.</span></span> <span data-ttu-id="d2dc3-167">默认情况下，Skype for Business 服务器证书请求将使用 Web 服务器证书模板。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-167">By default, a Skype for Business Server certificate request is going to use the Web Server certificate template.</span></span> <span data-ttu-id="d2dc3-168">如果你使用 RTCUniversalServerAdmins 组成员的帐户登录以通过此模板申请证书，请仔细检查以确保已为该组分配使用该模板的 "注册" 权限。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-168">If you're logged in with an account that's a member of the RTCUniversalServerAdmins group to request a certificate via this template, double-check to make sure the group's been assigned the Enroll permissions to use that template.</span></span> 
  
### <a name="internal-edge-interface-certificates"></a><span data-ttu-id="d2dc3-169">内部边缘接口证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-169">Internal Edge interface certificates</span></span>

 
### <a name="1-download-or-export-the-ca-certification-chain"></a><span data-ttu-id="d2dc3-170">1. 下载或导出 CA 证书链</span><span class="sxs-lookup"><span data-stu-id="d2dc3-170">1. Download or export the CA certification chain</span></span>

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a><span data-ttu-id="d2dc3-171">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-171">&nbsp;&nbsp;&nbsp; a.</span></span> <span data-ttu-id="d2dc3-172">使用 certsrv 网站下载</span><span class="sxs-lookup"><span data-stu-id="d2dc3-172">Download using certsrv web site</span></span>

<span data-ttu-id="d2dc3-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="d2dc3-174">以本地管理员组的成员身份登录内部网络中的 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-174">Log into a Skype for Business Server in your internal network as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="d2dc3-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;型.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="d2dc3-176">打开 "**开始**"，**运行**（或**搜索**并**运行**），然后键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-176">Open up **Start**, and **Run** (or **Search** and **Run** ), and then type the following:</span></span>
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

<span data-ttu-id="d2dc3-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For example:</span></span>
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

<span data-ttu-id="d2dc3-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="d2dc3-179">在发证 CA 的 certsrv 网页上，在 "**选择任务**" 下，单击 "**下载 CA 证书、证书链或 CRL"**。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-179">On the issuing CA's certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
    
<span data-ttu-id="d2dc3-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="d2dc3-181">在“**下载 CA 证书、证书链或 CRL**”下，单击“**下载 CA 证书链**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-181">Under **Download a CA certificate, certificate chain, or CRL**, click **Download CA certificate chain**.</span></span>
    
<span data-ttu-id="d2dc3-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;视听.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="d2dc3-183">在“**文件下载**”框中，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-183">In the **File Download** box, click **Save**.</span></span>
    
<span data-ttu-id="d2dc3-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;六.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="d2dc3-185">将. p7b 文件保存到服务器上的硬盘驱动器，然后将其复制到每个边缘服务器上的某个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-185">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each of your Edge Servers.</span></span>
    
### <a name="nbspnbspnbspb-export-using-mmc"></a><span data-ttu-id="d2dc3-186">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-186">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-187">使用 MMC 导出</span><span class="sxs-lookup"><span data-stu-id="d2dc3-187">Export using MMC</span></span>

<span data-ttu-id="d2dc3-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="d2dc3-189">你可以使用 MMC 从任何加入域的计算机导出 CA 根证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-189">You can export the CA root certificate from any domain joined machine using the MMC.</span></span> <span data-ttu-id="d2dc3-190">依次单击“**开始**”和“**运行**”，或者单击“**搜索**”后键入“**MMC**”打开。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-190">Either go to **Start** and **Run**, or open **Search**, and type **MMC** to open.</span></span>
    
<span data-ttu-id="d2dc3-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;型.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="d2dc3-192">在 MMC 控制台中，单击“**文件**”，然后单击“**添加/删除管理单元**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-192">In the MMC console, click **File**, and then click **Add/Remove Snap-In**.</span></span>
    
<span data-ttu-id="d2dc3-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="d2dc3-194">从“**添加或删除管理单元**”对话框列表中，选择“**证书**”，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-194">From the **Add or Remove Snap-ins** dialog list, choose **Certificates**, and then click **Add**.</span></span> <span data-ttu-id="d2dc3-195">系统提示时，选择“**计算机帐户**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-195">When prompted, select **Computer Account**, and then **Next**.</span></span> <span data-ttu-id="d2dc3-196">在“**选择计算机**”对话框中，选择“**本地计算机**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-196">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="d2dc3-197">单击“**完成**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-197">Click **Finish**, and then **OK**.</span></span>
    
<span data-ttu-id="d2dc3-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="d2dc3-199">展开“**证书(本地计算机)**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-199">Expand **Certificates (Local computer)**.</span></span> <span data-ttu-id="d2dc3-200">展开“**受信任的根证书颁发机构**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-200">Expand **Trusted Root Certification Authorities**.</span></span> <span data-ttu-id="d2dc3-201">选择“**证书**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-201">Select **Certificates**.</span></span>
    
<span data-ttu-id="d2dc3-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;视听.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="d2dc3-203">单击由 CA 颁发的根证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-203">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="d2dc3-204">右键单击该证书，选择菜单上的“**所有任务**”，然后选择“**导出**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-204">Right-click the certificate, choose **All Tasks** on the menu, and then select **Export**.</span></span>
    
<span data-ttu-id="d2dc3-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;六.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="d2dc3-206">“**证书导出向导**”随即打开。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-206">The **Certificate Export Wizard** opens.</span></span> <span data-ttu-id="d2dc3-207">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-207">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii.</span></span> <span data-ttu-id="d2dc3-209">打开“**导出文件格式**”对话框，选择要导出到的格式。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-209">On the **Export File Format** dialog, choose the format you want to export to.</span></span> <span data-ttu-id="d2dc3-210">我们的建议是“**加密消息语法标准 – PKCS #7 证书(P7b)**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-210">Our recommendation is **Cryptographic Message Syntax Standard - PKCS #7 Certificates (P7b)**.</span></span> <span data-ttu-id="d2dc3-211">如果你选择，请记住同时选择 "如果可能，将**所有证书包括在证书路径中**" 复选框，因为这也会导出证书链，包括根 CA 证书和任何中间证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-211">If that's your choice as well, remember to also select the **Include all certificates in the certification path if possible** checkbox, as this will also export the certificate chain, including the root CA certificate and any Intermediate certificates.</span></span> <span data-ttu-id="d2dc3-212">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-212">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii.</span></span> <span data-ttu-id="d2dc3-214">在“**要导出的文件**”对话框的文件名输入框中，键入导出的证书的路径和文件名（默认扩展名为 .p7b）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-214">On the **File to Export** dialog, in the file name entry, type a path and file name (the default extension would be .p7b) for the exported certificate.</span></span> <span data-ttu-id="d2dc3-215">如果更容易，请选择 "**浏览**" 按钮转到要将导出的证书保存到的位置，然后在此处命名导出的证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-215">If it's easier on you, choose the **Browse** button to go to the location you want to save the exported certificate to, and name the exported certificate here.</span></span> <span data-ttu-id="d2dc3-216">单击 "**保存**"，然后在准备就绪后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-216">Click **Save**, and then **Next** when you're ready.</span></span>
    
<span data-ttu-id="d2dc3-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;期.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix.</span></span> <span data-ttu-id="d2dc3-218">查看操作摘要，然后单击“**完成**”完成证书的导出。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-218">Review the summary of your actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="d2dc3-219">单击“**确定**”确认导出成功。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-219">Click **OK** to confirm the successful export.</span></span>
    
<span data-ttu-id="d2dc3-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;个.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x.</span></span> <span data-ttu-id="d2dc3-221">将. p7b 文件复制到每个边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-221">Copy the .p7b file to each of your Edge Servers.</span></span>
    
### <a name="2-import-the-ca-certification-chain"></a><span data-ttu-id="d2dc3-222">2. 导入 CA 证书链</span><span class="sxs-lookup"><span data-stu-id="d2dc3-222">2. Import the CA certification chain</span></span>

<span data-ttu-id="d2dc3-223">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-223">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="d2dc3-224">在每台边缘服务器上，打开 MMC （选择 "**开始**" 和 "**运行**" 或 "**搜索**"，然后键入**mmc**进行打开）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-224">On each Edge Server, open the MMC (choose **Start** and **Run**, or **Search**, and type **MMC** to open).</span></span>
    
<span data-ttu-id="d2dc3-225">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-225">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-226">在“**文件**”菜单上，单击“**添加/删除管理单元**”，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-226">On the **File** menu, click **Add/Remove Snap-in**, and then choose **Add**.</span></span>
    
<span data-ttu-id="d2dc3-227">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-227">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="d2dc3-228">在“**添加或删除管理单元**”框中，单击“**证书**”，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-228">In the **Add or Remove Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
    
<span data-ttu-id="d2dc3-229">&nbsp;&nbsp;&nbsp;3-d.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-229">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="d2dc3-230">在“**证书管理单元**”对话框中，单击“**计算机帐户**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-230">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-231">&nbsp;&nbsp;&nbsp;e.i.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-231">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="d2dc3-232">在“**选择计算机**”对话框中，确保选中“**本地计算机: (运行此控制台的计算机)**”复选框，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-232">In the **Select Computer** dialog box, ensure that the **Local Computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
    
<span data-ttu-id="d2dc3-233">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-233">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="d2dc3-234">单击“**关闭**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-234">Click **Close**, and then **OK**.</span></span>
    
<span data-ttu-id="d2dc3-235">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-235">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="d2dc3-236">在控制台树中，展开“**证书(本地计算机)**”，右键单击“**受信任的根证书颁发机构**”，转到“**所有任务**”，然后单击“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-236">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, go to **All Tasks**, and then click **Import**.</span></span>
    
<span data-ttu-id="d2dc3-237">&nbsp;&nbsp;&nbsp;硬件.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-237">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="d2dc3-238">在出现的向导中，在“**要导入的文件**”文本框中，指定证书的文件名（在上一节中你赋予 .p7b 文件的名称）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-238">In the wizard that appears, in the **File to Import** textbox, specify the file name of the certificate (the name you gave the .p7b file in the previous section).</span></span> <span data-ttu-id="d2dc3-239">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-239">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-240">&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-240">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="d2dc3-241">应选中“**将所有的证书放入下列存储，作为受信任的根证书颁发机构**”单选按钮。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-241">Leave the radio button on **Place all certificates in the following store, as Trusted Root Certification Authorities** should be selected.</span></span> <span data-ttu-id="d2dc3-242">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-242">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-243">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-243">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="d2dc3-244">查看摘要，然后单击“**完成**”以完成导入。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-244">Review the summary, and click **Finish** to complete the import.</span></span>
    
<span data-ttu-id="d2dc3-245">&nbsp;&nbsp;&nbsp;温度.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-245">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="d2dc3-246">将需要为每个要部署的边缘服务器执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-246">This will need to be done for every Edge Server you're deploying.</span></span>
    
### <a name="3-create-the-certificate-request"></a><span data-ttu-id="d2dc3-247">3. 创建证书请求</span><span class="sxs-lookup"><span data-stu-id="d2dc3-247">3. Create the certificate request</span></span>

<span data-ttu-id="d2dc3-248">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-248">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="d2dc3-249">登录到其中一个边缘服务器，启动部署向导，然后在**步骤3：请求、安装或分配证书**，单击 "**运行**" （或**再次运行**，如果已运行此向导）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-249">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates**, click **Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="d2dc3-250">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-250">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-251">在“**证书请求**”页上，确保“**内部边缘证书**”已选中，然后单击“**请求**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-251">On the **Certificate Request** page, ensure **Internal Edge Certificate** is selected, and click **Request**.</span></span>
    
<span data-ttu-id="d2dc3-252">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-252">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="d2dc3-253">在 "**延迟或立即请求**" 页面上，选择 **"将请求立即发送给联机证书颁发机构**" （如果你有权访问边缘环境中的证书），或者**立即发送请求，但稍后再发送**。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-253">On the **Delayed or Immediate Requests** page, choose **Send the request immediately to an online certification authority** if you have access to one from your Edge environment, or **Prepare the request now, but send it later** otherwise.</span></span>
    
<span data-ttu-id="d2dc3-254">&nbsp;&nbsp;&nbsp;3-d.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-254">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="d2dc3-255">在“**证书请求文件**”页上，输入将保存该文件的完整路径和文件名（例如，c:\SkypeInternalEdgeCert.cer）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-255">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="d2dc3-256">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-256">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-257">&nbsp;&nbsp;&nbsp;e.i.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-257">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="d2dc3-258">在“**指定替代证书模板**”页上，要使用除默认 WebServer 模板之外的其他模板，请选中“**使用选定证书颁发机构的备用证书模板**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-258">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span> <span data-ttu-id="d2dc3-259">否则，什么也不做。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-259">Otherwise, do nothing.</span></span>
    
<span data-ttu-id="d2dc3-260">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-260">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="d2dc3-261">在“名称和安全设置”页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-261">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="d2dc3-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="d2dc3-263">在“**友好名称**”中，输入证书的显示名称（例如，内部边缘）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-263">In **Friendly name**, enter a display name for the certificate (such as Internal Edge).</span></span>
    
 <span data-ttu-id="d2dc3-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;型.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="d2dc3-265">在“**位长度**”中，选择位长度（默认为 2048，设得越长越安全，但是会降低性能）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-265">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="d2dc3-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="d2dc3-267">如果需要可导出的证书，必须选中“**将证书私钥标记为可导出**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-267">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
 <span data-ttu-id="d2dc3-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv.</span></span> <span data-ttu-id="d2dc3-269">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-269">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-270">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-270">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="d2dc3-271">在“**组织信息**”页上，输入组织和组织单位 (OU) 的名称。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-271">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="d2dc3-272">可以输入分部或部门（如 IT）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-272">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="d2dc3-273">&nbsp;&nbsp;&nbsp;硬件.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-273">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="d2dc3-274">在“**地理信息**”页上，输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-274">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="d2dc3-275">&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-275">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="d2dc3-276">在“**使用者名称/使用者替代名称**”页上，这应该由向导自动填充。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-276">On the **Subject Name/Subject Alternate Names** page, this should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="d2dc3-277">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-277">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="d2dc3-278">在“**配置其他使用者替代名称**”页上，需要添加所需的任何其他使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-278">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="d2dc3-279">&nbsp;&nbsp;&nbsp;温度.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-279">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="d2dc3-280">在 "**请求摘要**" 页面上，查看将要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-280">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="d2dc3-281">如果需要进行更改，现在就返回并执行更改。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-281">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="d2dc3-282">&nbsp;&nbsp;&nbsp;控制面板.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-282">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="d2dc3-283">然后单击 "**下一步**" 以生成需要提供给 CA 的 CSR 文件（也可以单击 "**查看日志**" 以查看证书请求的日志）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-283">Then click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="d2dc3-284">&nbsp;&nbsp;&nbsp;材料.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-284">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="d2dc3-285">生成请求后，可以单击“**查看**”来查看证书，然后单击“**完成**”关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-285">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="d2dc3-286">CSR 文件的内容需要提供给 CA，这样他们才能生成证书，让你在下一节将其导入此计算机。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-286">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    

### <a name="4-import-the-certificate"></a><span data-ttu-id="d2dc3-287">4. 导入证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-287">4. Import the certificate</span></span>

<span data-ttu-id="d2dc3-288">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-288">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="d2dc3-289">以本地管理员组的成员身份登录到您在最后一个过程中发出证书请求的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-289">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="d2dc3-290">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-290">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-291">在 "部署向导" 的 "**步骤 3" 旁边。请求、安装或分配证书**，请**再次**单击 "运行"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-291">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="d2dc3-292">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-292">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="d2dc3-293">在“**可用的证书任务**”页上，单击“**从 .P7b、.pfx 或 .cer 文件导入证书**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-293">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="d2dc3-294">&nbsp;&nbsp;&nbsp;3-d.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-294">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="d2dc3-295">在“**导入证书**”页上，键入上一节中获得的证书的完整路径和文件名（也可单击“**浏览**”查找并选择该文件）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-295">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span>
    
<span data-ttu-id="d2dc3-296">&nbsp;&nbsp;&nbsp;e.i.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-296">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="d2dc3-297">如果你要为 Edge 池的其他成员导入证书，并且你的证书包含私钥，请确保选中 "**包含证书私钥的证书文件**" 复选框，然后指定密码。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-297">If you're importing certificates for other members of your Edge pool, and your certificate contains a private key, be sure to select the **Certificate file that contains certificate's private key** check box, and specify the password.</span></span> <span data-ttu-id="d2dc3-298">单击“**下一步**”继续。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-298">Click **Next** to continue.</span></span>
    
<span data-ttu-id="d2dc3-299">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-299">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="d2dc3-300">在 "**摘要**" 页面上，在确认信息后单击 "**下一步**"，然后在成功导入证书后**完成**操作。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-300">On the**Summary** page, click **Next** once you've confirmed the information, and **Finish** once the certificate is successfully imported.</span></span>
    
 
### <a name="5-export-the-certificate"></a><span data-ttu-id="d2dc3-301">5. 导出证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-301">5. Export the certificate</span></span>

<span data-ttu-id="d2dc3-302">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-302">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="d2dc3-303">确保你已登录到将证书导入到以前的边缘服务器，作为本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-303">Make sure you've logged onto the Edge Server you imported the certificate to previously, as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="d2dc3-304">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-304">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-305">单击 "**开始**"、"**运行**" （或 "打开**搜索**"），然后键入 " **MMC**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-305">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="d2dc3-306">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-306">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="d2dc3-307">从 MMC 控制台中，单击“**文件**”，再单击“**添加/删除管理单元**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-307">From the MMC console, click **File**, and click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="d2dc3-308">&nbsp;&nbsp;&nbsp;3-d.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-308">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="d2dc3-309">从“**添加或删除管理单元**”框中，单击“**证书**”，再单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-309">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="d2dc3-310">&nbsp;&nbsp;&nbsp;e.i.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-310">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="d2dc3-311">在“**证书**”管理单元对话框中，选择“**计算机帐户**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-311">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="d2dc3-312">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-312">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-313">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-313">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="d2dc3-314">在“**选择计算机**”对话框中，选择“**本地计算机: (运行此控制台的计算机)**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-314">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="d2dc3-315">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-315">Click **Finish**.</span></span> <span data-ttu-id="d2dc3-316">单击“**确定**”，MMC 控制台的配置即告完成。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-316">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="d2dc3-317">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-317">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="d2dc3-318">双击“**证书(本地计算机)**”展开证书存储。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-318">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="d2dc3-319">双击“**个人**”，然后单击“**证书**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-319">Double-click **Personal**, and then click **Certificates**.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="d2dc3-320">你可能在此处，并且在本地计算机的 "证书个人" 存储中看不到任何证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-320">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="d2dc3-321">如果键不在该位置，则无需进行查寻，导入的证书没有与之关联的私钥。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-321">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="d2dc3-322">请再次尝试请求并导入以上步骤，如果您确信一切正确，请与您的 CA 管理员或提供商联系。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-322">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="d2dc3-323">&nbsp;&nbsp;&nbsp;硬件.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-323">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="d2dc3-324">在本地计算机的 "**证书个人" 存储**中，右键单击要导出的证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-324">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="d2dc3-325">从得到的菜单中选择“**所有任务**”，然后单击“**导出**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-325">Select **All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="d2dc3-326">&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-326">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="d2dc3-327">在“**证书导出向导**”中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-327">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="d2dc3-328">选择“**是，导出私钥**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-328">Select **Yes, export the private key**.</span></span> <span data-ttu-id="d2dc3-329">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-329">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-330">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-330">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="d2dc3-331">在“**导出文件格式**”对话框中，选择“**个人信息交换 - PKCS#12 (.PFX)**”，然后选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-331">On the **Export File Formats** dialog, select **Personal Information Exchange - PKCS#12 (.PFX)**, and then select the following:</span></span>
    
<span data-ttu-id="d2dc3-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="d2dc3-333">如果可能，则数据包括证书路径中的所有证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-333">Include all certificates in the certification path, if possible.</span></span>
    
<span data-ttu-id="d2dc3-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;型.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii.</span></span> <span data-ttu-id="d2dc3-335">导出所有扩展属性。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-335">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d2dc3-336">**切勿**选择“**如果导出成功，删除私钥**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-336">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="d2dc3-337">这意味着您必须重新将证书和私钥重新导入到该 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-337">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="d2dc3-338">&nbsp;&nbsp;&nbsp;温度.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-338">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="d2dc3-339">如果要分配密码来保护私钥，可以键入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-339">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="d2dc3-340">重新输入该密码进行确认，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-340">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-341">&nbsp;&nbsp;&nbsp;控制面板.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-341">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="d2dc3-342">为导出的证书键入路径和文件名，并使用文件扩展名 **.pfx**。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-342">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="d2dc3-343">该路径必须可由池中的其他边缘服务器访问，或者你需要通过外部媒体（如 USB 驱动器）移动文件。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-343">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="d2dc3-344">做出选择后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-344">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="d2dc3-345">&nbsp;&nbsp;&nbsp;材料.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-345">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="d2dc3-346">查看“**正在完成证书导出向导**”对话框中的摘要，然后。单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-346">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="d2dc3-347">&nbsp;&nbsp;&nbsp;将要.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-347">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="d2dc3-348">在成功导出对话框中单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-348">Click **OK** in the successful export dialog.</span></span>
    
 
### <a name="6-assign-the-certificate"></a><span data-ttu-id="d2dc3-349">6. 分配证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-349">6. Assign the certificate</span></span>

<span data-ttu-id="d2dc3-350">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-350">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="d2dc3-351">在每个边缘服务器上，在 "部署向导" 的 "**步骤 3" 旁边。请求、安装或分配证书**，请**再次**单击 "运行"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-351">On EACH Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="d2dc3-352">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-352">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-353">在“**可用的证书任务**”页上，单击“**分配现有证书**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-353">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="d2dc3-354">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-354">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="d2dc3-355">在“**证书分配**”页上，选择列表中的“**边缘内部**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-355">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>
    
<span data-ttu-id="d2dc3-356">&nbsp;&nbsp;&nbsp;3-d.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-356">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="d2dc3-357">在 "**证书存储**" 页面上，选择为内部边缘导入的证书（从上一节）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-357">On the **Certificate Store** page, select the certificate you've imported for the internal Edge (from the previous section).</span></span>
    
<span data-ttu-id="d2dc3-358">&nbsp;&nbsp;&nbsp;e.i.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-358">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="d2dc3-359">在“**证书分配摘要**”页上，检查设置，然后单击“**下一步**”分配证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-359">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="d2dc3-360">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-360">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="d2dc3-361">在向导完成页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-361">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="d2dc3-362">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-362">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="d2dc3-363">完成此过程后，最好在每台边缘服务器上打开证书 MMC 管理单元，展开 "**证书（本地计算机）**" **，展开 "证书"，然后**单击 "**证书**"，确认 "详细信息" 窗格中是否列出了 "内部边缘" 证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-363">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each Edge Server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
### <a name="external-edge-interface-certificates"></a><span data-ttu-id="d2dc3-364">外部边缘接口证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-364">External Edge interface certificates</span></span>

 
### <a name="1-create-the-certificate-request"></a><span data-ttu-id="d2dc3-365">1. 创建证书申请</span><span class="sxs-lookup"><span data-stu-id="d2dc3-365">1. Create the certificate request</span></span>

<span data-ttu-id="d2dc3-366">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-366">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="d2dc3-367">登录到其中一个边缘服务器，启动部署向导，然后在**步骤3：请求、安装或分配证书，单击 "运行**" （或**再次运行**，如果已运行此向导）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-367">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates, click Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="d2dc3-368">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-368">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-369">在“**可用的证书任务**”页上，单击“**创建新的证书请求**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-369">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>
    
<span data-ttu-id="d2dc3-370">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-370">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="d2dc3-371">在“**证书请求**”页上，确保“**外部边缘证书**”已选中，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-371">On the **Certificate Request** page, ensure **External Edge Certificate** is selected, and click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-372">&nbsp;&nbsp;&nbsp;3-d.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-372">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="d2dc3-373">在“**延迟的请求或即时请求**”页上，单击“**现在准备请求，但稍后发送**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-373">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>
    
<span data-ttu-id="d2dc3-374">&nbsp;&nbsp;&nbsp;e.i.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-374">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="d2dc3-375">在“**证书请求文件**”页上，输入将保存该文件的完整路径和文件名（例如，c:\SkypeInternalEdgeCert.cer）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-375">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="d2dc3-376">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-376">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-377">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-377">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="d2dc3-378">在“**指定替代证书模板**”页上，要使用除默认 WebServer 模板之外的模板，请选中“**使用选定证书颁发机构的备用证书模板**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-378">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>
    
<span data-ttu-id="d2dc3-379">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-379">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="d2dc3-380">在“名称和安全设置”页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-380">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="d2dc3-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="d2dc3-382">在“**友好名称**”中，键入证书的显示名称（例如，外部边缘）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-382">In **Friendly name**, enter a display name for the certificate (such as External Edge).</span></span>
    
 <span data-ttu-id="d2dc3-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;型.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="d2dc3-384">在“**位长度**”中，选择位长度（默认为 2048，设得越长越安全，但是会降低性能）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-384">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="d2dc3-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="d2dc3-386">如果需要可导出的证书，必须选中“**将证书私钥标记为可导出**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-386">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
  <span data-ttu-id="d2dc3-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv.</span></span> <span data-ttu-id="d2dc3-388">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-388">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-389">&nbsp;&nbsp;&nbsp;硬件.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-389">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="d2dc3-390">在“**组织信息**”页上，输入组织和组织单位 (OU) 的名称。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-390">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="d2dc3-391">可以输入分部或部门（如 IT）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-391">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="d2dc3-392">&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-392">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="d2dc3-393">在“**地理信息**”页上，输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-393">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="d2dc3-394">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-394">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="d2dc3-395">在“**使用者名称/使用者替代名称**”页上，所需的信息由向导自动填充。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-395">On the **Subject Name/Subject Alternate Names** page, the needed information should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="d2dc3-396">&nbsp;&nbsp;&nbsp;温度.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-396">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="d2dc3-397">在 "**主题备用名称（san）** " 页面上的 "SIP 域设置" 中，选中 "域" 复选框以添加 SIP。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="d2dc3-397">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, check the domain checkbox to add a sip.<sipdomain></span></span> <span data-ttu-id="d2dc3-398">输入到 "主题备用名称" 列表。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-398">entry to the subject alternative names list.</span></span>
    
<span data-ttu-id="d2dc3-399">&nbsp;&nbsp;&nbsp;控制面板.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-399">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="d2dc3-400">在“**配置其他使用者替代名称**”页上，需要添加所需的任何其他使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-400">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="d2dc3-401">&nbsp;&nbsp;&nbsp;材料.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-401">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="d2dc3-402">在 "**请求摘要**" 页面上，查看将要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-402">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="d2dc3-403">如果需要进行更改，现在就返回并执行更改。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-403">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="d2dc3-404">&nbsp;&nbsp;&nbsp;将要.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-404">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="d2dc3-405">准备就绪后，单击 "**下一步**" 以生成需要提供给 CA 的 CSR 文件（也可以单击 "**查看日志**" 以查看证书请求的日志）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-405">When you're ready, click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="d2dc3-406">&nbsp;&nbsp;&nbsp;o.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-406">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="d2dc3-407">生成请求后，可以单击“**查看**”来查看证书，然后单击“**完成**”关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-407">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="d2dc3-408">CSR 文件的内容需要提供给 CA，这样他们才能生成证书，让你在下一节将其导入此计算机。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-408">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    
<span data-ttu-id="d2dc3-409">&nbsp;&nbsp;&nbsp;68.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-409">&nbsp;&nbsp;&nbsp;p.</span></span> <span data-ttu-id="d2dc3-410">（可选）在提交 CSR 的内容后，可能需要你提供某些信息，具体如下（CA 之间差异很大，所有这可能不是必需的）：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-410">(OPTIONAL) You may, when submitting the contents of the CSR, be asked for certain information, as follows (CAs vary greatly, so this may not be required):</span></span>
    
  - <span data-ttu-id="d2dc3-411">**Microsoft** 作为服务器平台</span><span class="sxs-lookup"><span data-stu-id="d2dc3-411">**Microsoft** as the server platform</span></span>
    
  - <span data-ttu-id="d2dc3-412">**IIS** 作为版本</span><span class="sxs-lookup"><span data-stu-id="d2dc3-412">**IIS** as the version</span></span>
    
  - <span data-ttu-id="d2dc3-413">**Web Server** 作为使用类型</span><span class="sxs-lookup"><span data-stu-id="d2dc3-413">**Web Server** as the usage type</span></span>
    
  - <span data-ttu-id="d2dc3-414">**PKCS7** 作为响应格式</span><span class="sxs-lookup"><span data-stu-id="d2dc3-414">**PKCS7** as the response format</span></span>
    
 
### <a name="2-import-the-certificate"></a><span data-ttu-id="d2dc3-415">2. 导入证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-415">2. Import the certificate</span></span>

<span data-ttu-id="d2dc3-416">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-416">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="d2dc3-417">以本地管理员组的成员身份登录到您在最后一个过程中发出证书请求的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-417">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="d2dc3-418">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-418">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-419">在 "部署向导" 的 "**步骤 3" 旁边。请求、安装或分配证书**，请**再次**单击 "运行"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-419">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="d2dc3-420">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-420">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="d2dc3-421">在“**可用的证书任务**”页上，单击“**从 .P7b、.pfx 或 .cer 文件导入证书**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-421">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="d2dc3-422">&nbsp;&nbsp;&nbsp;3-d.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-422">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="d2dc3-423">在“**导入证书**”页上，键入上一节中获得的证书的完整路径和文件名（也可单击“**浏览**”查找并选择该文件）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-423">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span> <span data-ttu-id="d2dc3-424">如果你的证书包含私钥，请确保选择 "**证书文件包含证书的私钥**"，然后输入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-424">If your certificate contains a private key, make sure to select **Certificate file contains certificate's private key**, and enter the password for the private key.</span></span> <span data-ttu-id="d2dc3-425">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-425">Click **Next** when ready.</span></span>
    
<span data-ttu-id="d2dc3-426">&nbsp;&nbsp;&nbsp;e.i.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-426">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="d2dc3-427">在“**导入证书摘要**”页上，查看摘要信息，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-427">On the **Import Certificate Summary** page, review the summary information, and click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-428">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-428">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="d2dc3-429">在 "**执行命令**" 页面上，通过单击 "**查看日志**"，可以查看导入完成后的导入结果。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-429">On the **Executing Commands** page, you can review the result of the import when it's complete by clicking **View Log**.</span></span> <span data-ttu-id="d2dc3-430">单击“**完成**”完成证书导入。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-430">Click **Finish** to complete the certificate import.</span></span>
    
<span data-ttu-id="d2dc3-431">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-431">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="d2dc3-432">如果池中有其他边缘服务器，则还需要执行下两个过程。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-432">If you have other Edge Servers in a pool, you'll need to follow the next two procedures as well.</span></span> <span data-ttu-id="d2dc3-433">如果这是独立的边缘服务器，则你已完成外部证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-433">If this is a standalone Edge Server, you're done with external certificates.</span></span>
    
 
### <a name="3-export-the-certificate"></a><span data-ttu-id="d2dc3-434">3. 导出证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-434">3. Export the certificate</span></span>

<span data-ttu-id="d2dc3-435">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-435">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="d2dc3-436">确保已登录到将证书导入为本地管理员的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-436">Make sure you've logged onto the Edge Server you imported the certificate to as a local Administrator.</span></span>
    
<span data-ttu-id="d2dc3-437">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-437">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-438">单击 "**开始**"、"**运行**" （或 "打开**搜索**"），然后键入 " **MMC**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-438">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="d2dc3-439">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-439">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="d2dc3-440">从 MMC 控制台中，单击“**文件**”，然后单击“**添加/删除管理单元**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-440">From the MMC console, click **File**, and then click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="d2dc3-441">&nbsp;&nbsp;&nbsp;3-d.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-441">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="d2dc3-442">从“**添加或删除管理单元**”框中，单击“**证书**”，再单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-442">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="d2dc3-443">&nbsp;&nbsp;&nbsp;e.i.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-443">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="d2dc3-444">在“**证书**”管理单元对话框中，选择“**计算机帐户**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-444">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="d2dc3-445">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-445">Click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-446">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-446">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="d2dc3-447">在“**选择计算机**”对话框中，选择“**本地计算机: (运行此控制台的计算机)**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-447">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="d2dc3-448">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-448">Click **Finish**.</span></span> <span data-ttu-id="d2dc3-449">单击“**确定**”，MMC 控制台的配置即告完成。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-449">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="d2dc3-450">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-450">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="d2dc3-451">双击“**证书(本地计算机)**”展开证书存储。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-451">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="d2dc3-452">双击“**个人**”，然后单击“**证书**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-452">**Double-click Personal**, and then click **Certificates**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d2dc3-453">你可能在此处，并且在本地计算机的 "证书个人" 存储中看不到任何证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-453">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="d2dc3-454">如果键不在该位置，则无需进行查寻，导入的证书没有与之关联的私钥。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-454">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="d2dc3-455">请再次尝试请求并导入以上步骤，如果您确信一切正确，请与您的 CA 管理员或提供商联系。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-455">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="d2dc3-456">&nbsp;&nbsp;&nbsp;硬件.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-456">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="d2dc3-457">在本地计算机的 "**证书个人" 存储**中，右键单击要导出的证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-457">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="d2dc3-458">从得到的菜单中选择“**所有任务**”，然后单击“**导出**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-458">**Select All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="d2dc3-459">&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-459">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="d2dc3-460">在“**证书导出向导**”中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-460">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="d2dc3-461">选择“**是，导出私钥**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-461">Select **Yes, export the private key**.</span></span> <span data-ttu-id="d2dc3-462">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-462">Click **Next**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d2dc3-463">如果为 **"是"，则导出私钥**不可用，因此在获得该证书之前，未将该证书的私钥标记为已导出。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-463">If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it.</span></span> <span data-ttu-id="d2dc3-464">你需要再次向提供商提出证书请求，要求将私钥设置为导出，然后导出才能成功。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-464">You need to request the certificate from the provider again, with the private key set to export, before doing this successfully.</span></span>
  
<span data-ttu-id="d2dc3-465">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-465">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="d2dc3-466">在“导出文件格式”对话框中，选择“个人信息交换 - PKCS#12 (.PFX)”，然后选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-466">On the Export File Formats dialog, select Personal Information Exchange - PKCS#12 (.PFX) and then select the following:</span></span>
    
 <span data-ttu-id="d2dc3-467">&nbsp;&nbsp;&nbsp;怎样.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-467">&nbsp;&nbsp;&nbsp;  i.</span></span> <span data-ttu-id="d2dc3-468">如果可能，则数据包括证书路径中的所有证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-468">Include all certificates in the certification path, if possible.</span></span>
    
 <span data-ttu-id="d2dc3-469">&nbsp;&nbsp;&nbsp;型.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-469">&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="d2dc3-470">导出所有扩展属性。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-470">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d2dc3-471">**切勿**选择“**如果导出成功，删除私钥**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-471">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="d2dc3-472">这意味着您必须重新将证书和私钥重新导入到该 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-472">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="d2dc3-473">&nbsp;&nbsp;&nbsp;温度.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-473">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="d2dc3-474">如果要分配密码来保护私钥，可以键入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-474">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="d2dc3-475">重新输入该密码进行确认，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-475">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="d2dc3-476">&nbsp;&nbsp;&nbsp;控制面板.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-476">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="d2dc3-477">为导出的证书键入路径和文件名，并使用文件扩展名 **.pfx**。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-477">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="d2dc3-478">该路径必须可由池中的其他边缘服务器访问，或者你需要通过外部媒体（如 USB 驱动器）移动文件。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-478">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="d2dc3-479">做出选择后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-479">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="d2dc3-480">&nbsp;&nbsp;&nbsp;材料.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-480">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="d2dc3-481">查看“**正在完成证书导出向导**”对话框中的摘要，然后。单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-481">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="d2dc3-482">&nbsp;&nbsp;&nbsp;将要.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-482">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="d2dc3-483">在成功导出对话框中单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-483">Click **OK** in the successful export dialog.</span></span>
    
<span data-ttu-id="d2dc3-484">&nbsp;&nbsp;&nbsp;o.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-484">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="d2dc3-485">现在，你需要返回到 "导入证书" 部分，并将证书导入到其余所有边缘服务器，然后继续执行分配。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-485">You'll now need to go back to the Import the certificate section prior to this and import the certificate to all your remaining Edge Servers, then proceed with assigning, below.</span></span>
    
 
### <a name="4-assign-the-certificate"></a><span data-ttu-id="d2dc3-486">4. 分配证书</span><span class="sxs-lookup"><span data-stu-id="d2dc3-486">4. Assign the certificate</span></span>

<span data-ttu-id="d2dc3-487">&nbsp;&nbsp;&nbsp;有.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-487">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="d2dc3-488">在**每个**边缘服务器上，在 "部署向导" 的 "**步骤 3" 旁边。请求、安装或分配证书**，请**再次**单击 "运行"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-488">On **EACH** Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="d2dc3-489">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-489">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="d2dc3-490">在“**可用的证书任务**”页上，单击“**分配现有证书**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-490">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="d2dc3-491">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-491">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="d2dc3-492">在 "**证书分配**" 页面上，选择列表中的 "**边缘外部**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-492">On the **Certificate Assignment** page, select **Edge External** in the list.</span></span>
    
<span data-ttu-id="d2dc3-493">&nbsp;&nbsp;&nbsp;3-d.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-493">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="d2dc3-494">在 "**证书存储**" 页面上，选择已为外部边缘导入的证书（从上一节）。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-494">On the **Certificate Store** page, select the certificate you've imported for the external Edge (from the previous section).</span></span>
    
<span data-ttu-id="d2dc3-495">&nbsp;&nbsp;&nbsp;e.i.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-495">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="d2dc3-496">在“**证书分配摘要**”页上，检查设置，然后单击“**下一步**”分配证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-496">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="d2dc3-497">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-497">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="d2dc3-498">在向导完成页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-498">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="d2dc3-499">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="d2dc3-499">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="d2dc3-500">完成此过程后，最好在每台服务器上打开 "证书" MMC 管理单元，展开 "**证书（本地计算机）**"，展开 "**个人**"，单击 "**证书**"，然后确认 "详细信息" 窗格中是否列出了 "内部边缘" 证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-500">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d2dc3-501">你还需要设置反向代理服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-501">You will also have needed to set up the certificates for your reverse proxy server.</span></span> 
  
## <a name="starting-the-edge-servers"></a><span data-ttu-id="d2dc3-502">启动边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d2dc3-502">Starting the Edge Servers</span></span>

<span data-ttu-id="d2dc3-503">设置完成后，你需要在部署中的每台边缘服务器上启动服务：</span><span class="sxs-lookup"><span data-stu-id="d2dc3-503">Once the setup is complete, you'll need to start the services on each Edge server in your deployment:</span></span>
  
1. <span data-ttu-id="d2dc3-504">在每个边缘服务器上，在**部署向导**中的 "**步骤4：启动服务**" 旁边，单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-504">On each Edge Server, in the **Deployment Wizard**, next to **Step 4: Start Services**, click **Run**.</span></span>
    
2. <span data-ttu-id="d2dc3-505">在 "**启动 Skype For Business 服务器服务**" 页面上，查看服务列表，然后单击 "**下一步**" 以启动服务。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-505">On the **Start Skype for Business Server Services** page, review the list of services, and then click **Next** to start the services.</span></span>
    
3. <span data-ttu-id="d2dc3-506">启动服务后，可以单击“**完成**”关闭向导。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-506">After the services are started, you can click **Finish** to close the wizard.</span></span>
    
4. <span data-ttu-id="d2dc3-507">（可选）仍然在“**步骤 4: 启动服务**”下，单击“**服务状态**”。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-507">(Optional) Still under **Step 4: Start Services**, click **Services Status**.</span></span>
    
5.  <span data-ttu-id="d2dc3-508">在每台服务器上的**服务 MMC**中，验证所有 Skype For business 服务器服务是否都在运行。</span><span class="sxs-lookup"><span data-stu-id="d2dc3-508">In the **Services MMC** on each server, verify that all the Skype for Business Server services are running.</span></span>
    

