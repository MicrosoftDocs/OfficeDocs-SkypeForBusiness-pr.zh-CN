---
title: 在 Skype for Business Server 中部署边缘服务器
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
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 摘要：了解如何将边缘服务器部署到 Skype for Business Server 环境中。
ms.openlocfilehash: 8e23e157d4eb86f5b3d2bd5fa3ab3a54fd8aadc8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804372"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="cf147-103">在 Skype for Business Server 中部署边缘服务器</span><span class="sxs-lookup"><span data-stu-id="cf147-103">Deploy Edge Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="cf147-104">**摘要：** 了解如何将边缘服务器部署到 Skype for Business Server 环境中。</span><span class="sxs-lookup"><span data-stu-id="cf147-104">**Summary:** Learn how to deploy Edge Servers into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="cf147-105">以下各节包含一些步骤，这些步骤是在查看 Skype for Business Server 文档中的 Skype for [Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) 边缘服务器部署计划后要遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="cf147-105">The following sections contain steps that are meant to be followed after the Skype for Business Server [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) documentation has been reviewed.</span></span> <span data-ttu-id="cf147-106">部署步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf147-106">The deployment steps are as follows:</span></span>
  
- <span data-ttu-id="cf147-107">网络接口</span><span class="sxs-lookup"><span data-stu-id="cf147-107">Network interfaces</span></span>
    
- <span data-ttu-id="cf147-108">安装</span><span class="sxs-lookup"><span data-stu-id="cf147-108">Installation</span></span>
    
- <span data-ttu-id="cf147-109">证书</span><span class="sxs-lookup"><span data-stu-id="cf147-109">Certificates</span></span>
    
- <span data-ttu-id="cf147-110">启动边缘服务器</span><span class="sxs-lookup"><span data-stu-id="cf147-110">Starting the Edge Servers</span></span>
    
## <a name="network-interfaces"></a><span data-ttu-id="cf147-111">网络接口</span><span class="sxs-lookup"><span data-stu-id="cf147-111">Network interfaces</span></span>

<span data-ttu-id="cf147-112">如规划中已指出，您将在托管边缘服务器的外围网络中使用 DNS 配置网络接口，或在外围网络中配置 DNS。</span><span class="sxs-lookup"><span data-stu-id="cf147-112">As noted in Planning, you will either be configuring your network interface with DNS in the perimeter network hosting your Edge Servers, or without DNS in the perimeter network.</span></span>
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="cf147-113">外围网络中 DNS 服务器的接口配置</span><span class="sxs-lookup"><span data-stu-id="cf147-113">Interface configuration with DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="cf147-114">为每台边缘服务器安装两个网络适配器，一个适用于面向内部的接口，另一个适用于面向外部的接口。</span><span class="sxs-lookup"><span data-stu-id="cf147-114">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cf147-115">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="cf147-115">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="cf147-116">在外部接口上，将配置 **以下项** 之一：</span><span class="sxs-lookup"><span data-stu-id="cf147-116">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="cf147-117">a.</span><span class="sxs-lookup"><span data-stu-id="cf147-117">a.</span></span> <span data-ttu-id="cf147-118">外部外围网络子网上的三个静态 IP 地址，将默认网关指向外部防火墙的内部接口。</span><span class="sxs-lookup"><span data-stu-id="cf147-118">Three static IP addresses on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="cf147-119">将适配器 DNS 设置配置为指向一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-119">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
   <span data-ttu-id="cf147-120">b.</span><span class="sxs-lookup"><span data-stu-id="cf147-120">b.</span></span> <span data-ttu-id="cf147-121">外部外围网络子网上的一个静态 IP 地址，将默认网关指向外部防火墙的内部接口。</span><span class="sxs-lookup"><span data-stu-id="cf147-121">One static IP address on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="cf147-122">将适配器 DNS 设置配置为指向一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-122">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span> <span data-ttu-id="cf147-123">只有在之前将拓扑配置为在端口分配中具有非标准值时，此配置才可接受，如"为 Skype for Business [Server](create-your-edge-topology.md) 创建边缘拓扑"一文所介绍。</span><span class="sxs-lookup"><span data-stu-id="cf147-123">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="cf147-124">在内部接口上，在内部外围网络子网上配置一个静态 IP，不设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="cf147-124">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="cf147-125">将适配器 DNS 设置配置为指向至少一台 DNS 服务器，但最好是一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-125">Configure the adaptor DNS settings to point to at least one DNS server, but preferably a pair of perimeter DNS servers.</span></span>
    
4. <span data-ttu-id="cf147-126">在内部接口上创建到客户端、Skype for Business Server 和 Exchange 统一消息服务器所在的所有内部网络的 (UM) 路由。</span><span class="sxs-lookup"><span data-stu-id="cf147-126">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="cf147-127">外围网络中没有 DNS 服务器的接口配置</span><span class="sxs-lookup"><span data-stu-id="cf147-127">Interface configuration without DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="cf147-128">为每台边缘服务器安装两个网络适配器，一个适用于面向内部的接口，另一个适用于面向外部的接口。</span><span class="sxs-lookup"><span data-stu-id="cf147-128">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cf147-129">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="cf147-129">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="cf147-130">在外部接口上，将配置 **以下项** 之一：</span><span class="sxs-lookup"><span data-stu-id="cf147-130">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="cf147-131">a.</span><span class="sxs-lookup"><span data-stu-id="cf147-131">a.</span></span> <span data-ttu-id="cf147-132">外部外围网络子网上的三个静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="cf147-132">Three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="cf147-133">您还需要在外部接口上配置默认网关，例如，将面向 Internet 的路由器或外部防火墙定义为默认网关。</span><span class="sxs-lookup"><span data-stu-id="cf147-133">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="cf147-134">将适配器 DNS 设置配置为指向外部 DNS 服务器，最好是一对外部 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-134">Configure the adapter DNS settings to point to an external DNS server, ideally a pair of external DNS servers.</span></span>
    
   <span data-ttu-id="cf147-135">b.</span><span class="sxs-lookup"><span data-stu-id="cf147-135">b.</span></span> <span data-ttu-id="cf147-136">外部外围网络子网上的一个静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="cf147-136">One static IP address on the external perimeter network subnet.</span></span> <span data-ttu-id="cf147-137">您还需要在外部接口上配置默认网关，例如，将面向 Internet 的路由器或外部防火墙定义为默认网关。</span><span class="sxs-lookup"><span data-stu-id="cf147-137">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="cf147-138">将适配器 DNS 设置配置为指向外部 DNS 服务器，或最好是一对外部 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-138">Configure the adapter DNS settings to point to an external DNS server, or ideally a pair of external DNS servers.</span></span> <span data-ttu-id="cf147-139">只有在之前将拓扑配置为在端口分配中具有非标准值时，此配置才可接受，如"为 Skype for Business [Server](create-your-edge-topology.md) 创建边缘拓扑"一文所介绍。</span><span class="sxs-lookup"><span data-stu-id="cf147-139">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="cf147-140">在内部接口上，在内部外围网络子网上配置一个静态 IP，不设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="cf147-140">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="cf147-141">此外，将适配器 DNS 设置留空。</span><span class="sxs-lookup"><span data-stu-id="cf147-141">Also leave the adapter DNS settings empty.</span></span>
    
4. <span data-ttu-id="cf147-142">在内部接口上创建到客户端、Skype for Business Server 和 Exchange 统一消息服务器所在的所有内部网络的 (UM) 路由。</span><span class="sxs-lookup"><span data-stu-id="cf147-142">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
5. <span data-ttu-id="cf147-143">编辑每台边缘服务器上主机文件，以包含下一个跃点服务器或虚拟 IP (VIP) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-143">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP).</span></span> <span data-ttu-id="cf147-144">此记录将是在拓扑生成器中配置为边缘服务器下一跃点地址的控制器、Standard Edition Server 或前端池。</span><span class="sxs-lookup"><span data-stu-id="cf147-144">This record will be the Director, Standard Edition server or Front End pool you configured as the Edge Server next hop address in Topology Builder.</span></span> <span data-ttu-id="cf147-145">如果使用的是 DNS 负载平衡，请为下一个跃点池的每个成员包括一行。</span><span class="sxs-lookup"><span data-stu-id="cf147-145">If you're using DNS load balancing, include a line for each member of the next hop pool.</span></span>
    
## <a name="installation"></a><span data-ttu-id="cf147-146">安装</span><span class="sxs-lookup"><span data-stu-id="cf147-146">Installation</span></span>

<span data-ttu-id="cf147-147">若要成功完成这些步骤，你需要遵循"为 [Skype for Business Server](create-your-edge-topology.md) 创建边缘拓扑"一文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="cf147-147">To complete these steps successfully, you will need to have followed the steps in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
  
1. <span data-ttu-id="cf147-148">使用本地管理员组的帐户登录到为边缘服务器角色配置的服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-148">Log onto the server you've been configuring for the Edge Server role with an account that's in the local Administrator's group.</span></span>
    
2. <span data-ttu-id="cf147-149">您需要在此计算机上边缘服务器拓扑文档末尾复制的拓扑配置文件。</span><span class="sxs-lookup"><span data-stu-id="cf147-149">You'll need the topology configuration file you copied out at the end of the Edge Server Topology documentation on this machine.</span></span> <span data-ttu-id="cf147-150">访问你放置该配置文件的外部媒体， (U 盘或共享) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-150">Access the external media you placed that configuration file on (like a USB drive or share).</span></span>
    
3. <span data-ttu-id="cf147-151">启动 **部署向导**。</span><span class="sxs-lookup"><span data-stu-id="cf147-151">Start the **Deployment Wizard**.</span></span>
    
4. <span data-ttu-id="cf147-152">打开向导后，单击 **"安装或更新 Skype for Business Server 系统"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-152">Once the wizard opens, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="cf147-153">向导将运行检查以查看是否已安装任何内容。</span><span class="sxs-lookup"><span data-stu-id="cf147-153">The wizard will run checks to see if anything's already installed.</span></span> <span data-ttu-id="cf147-154">由于这是第一次运行向导，因此您需要从步骤 **1 开始。安装本地配置存储。**</span><span class="sxs-lookup"><span data-stu-id="cf147-154">As this is the first time running the wizard, you'll want to start at **Step 1. Install Local Configuration Store.**</span></span>
    
6. <span data-ttu-id="cf147-155">将显示 **"配置中央管理存储的本地副本"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="cf147-155">The **Configure Local Replica of Central Management store** dialog will appear.</span></span> <span data-ttu-id="cf147-156">你需要单击"从 **建议用于边缘服务器 (文件导入) 。**</span><span class="sxs-lookup"><span data-stu-id="cf147-156">You need to click **Import from a file (Recommended for Edge Servers)**.</span></span>
    
7. <span data-ttu-id="cf147-157">从此处浏览到之前导出的拓扑的位置，选择 .zip 文件，单击"打开"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-157">From here, browse to the location of the topology you exported previously, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="cf147-158">部署向导将读取配置文件，将 XML 配置文件写入本地计算机。</span><span class="sxs-lookup"><span data-stu-id="cf147-158">The Deployment Wizard will read the configuration file and write the XML configuration file to the local computer.</span></span>
    
9. <span data-ttu-id="cf147-159">“正在执行命令”过程完成后，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="cf147-159">After the **Executing Commands** process is finished, click **Finish**.</span></span>
    
10. <span data-ttu-id="cf147-160">在部署向导中，单击 **"步骤 2"。安装或删除 Skype for Business Server 组件**。</span><span class="sxs-lookup"><span data-stu-id="cf147-160">In the Deployment Wizard, click **Step 2. Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="cf147-161">然后，该向导将安装本地计算机上存储的 XML 配置文件中指定的 Skype for Business Server 边缘组件。</span><span class="sxs-lookup"><span data-stu-id="cf147-161">The wizard will then install the Skype for Business Server Edge components specified in the XML configuration file that's been stored on the local computer.</span></span>
    
11. <span data-ttu-id="cf147-162">安装完成后，可以继续下面的"证书 **"部分中的步骤** 。</span><span class="sxs-lookup"><span data-stu-id="cf147-162">Once the installation's complete, you can move onto the steps in the **Certificates** section below.</span></span>
    
## <a name="certificates"></a><span data-ttu-id="cf147-163">证书</span><span class="sxs-lookup"><span data-stu-id="cf147-163">Certificates</span></span>

<span data-ttu-id="cf147-164">边缘服务器的证书要求可在边缘证书规划文档中找到。</span><span class="sxs-lookup"><span data-stu-id="cf147-164">The certificate requirements for the Edge Server can be found in the Edge Certificate Planning documentation.</span></span> <span data-ttu-id="cf147-165">以下是设置证书的步骤。</span><span class="sxs-lookup"><span data-stu-id="cf147-165">The steps for setting up certificates are below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cf147-166">运行证书向导时，您需要以帐户身份登录，该帐户对将使用的证书模板类型具有正确的权限。</span><span class="sxs-lookup"><span data-stu-id="cf147-166">When running the Certificate Wizard, you need to be logged in as an account with the correct permissions for the type of certificate template you're going to use.</span></span> <span data-ttu-id="cf147-167">默认情况下，Skype for Business Server 证书请求将使用 Web 服务器证书模板。</span><span class="sxs-lookup"><span data-stu-id="cf147-167">By default, a Skype for Business Server certificate request is going to use the Web Server certificate template.</span></span> <span data-ttu-id="cf147-168">如果使用 RTCUniversalServerAdmins 组的成员帐户登录，以通过此模板请求证书，请仔细检查以确保该组已分配有使用该模板的注册权限。</span><span class="sxs-lookup"><span data-stu-id="cf147-168">If you're logged in with an account that's a member of the RTCUniversalServerAdmins group to request a certificate via this template, double-check to make sure the group's been assigned the Enroll permissions to use that template.</span></span> 
  
### <a name="internal-edge-interface-certificates"></a><span data-ttu-id="cf147-169">内部边缘接口证书</span><span class="sxs-lookup"><span data-stu-id="cf147-169">Internal Edge interface certificates</span></span>

 
### <a name="1-download-or-export-the-ca-certification-chain"></a><span data-ttu-id="cf147-170">1. 下载或导出 CA 认证链</span><span class="sxs-lookup"><span data-stu-id="cf147-170">1. Download or export the CA certification chain</span></span>

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a><span data-ttu-id="cf147-171">&nbsp;&nbsp;&nbsp; a.</span><span class="sxs-lookup"><span data-stu-id="cf147-171">&nbsp;&nbsp;&nbsp; a.</span></span> <span data-ttu-id="cf147-172">使用 certsrv 网站下载</span><span class="sxs-lookup"><span data-stu-id="cf147-172">Download using certsrv web site</span></span>

<span data-ttu-id="cf147-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span><span class="sxs-lookup"><span data-stu-id="cf147-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="cf147-174">以本地用户帐户的一员登录到内部网络的 Skype for Business 管理员组。</span><span class="sxs-lookup"><span data-stu-id="cf147-174">Log into a Skype for Business Server in your internal network as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="cf147-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span><span class="sxs-lookup"><span data-stu-id="cf147-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="cf147-176">打开"**开始\*\*\*\*"、 (\*\*\*\*或"** 搜索和) ，然后键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="cf147-176">Open up **Start**, and **Run** (or **Search** and **Run** ), and then type the following:</span></span>
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

<span data-ttu-id="cf147-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如：</span><span class="sxs-lookup"><span data-stu-id="cf147-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For example:</span></span>
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

<span data-ttu-id="cf147-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span><span class="sxs-lookup"><span data-stu-id="cf147-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="cf147-179">在颁发 CA 的 certsrv 网页上，在"选择任务"下，单击"下载 **CA 证书、证书链或 CRL"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-179">On the issuing CA's certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
    
<span data-ttu-id="cf147-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="cf147-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="cf147-181">在 **"下载 CA 证书、证书链或 CRL"** 下，单击 **"下载 CA 证书链"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-181">Under **Download a CA certificate, certificate chain, or CRL**, click **Download CA certificate chain**.</span></span>
    
<span data-ttu-id="cf147-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span><span class="sxs-lookup"><span data-stu-id="cf147-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="cf147-183">在"**文件下载"** 框中，单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-183">In the **File Download** box, click **Save**.</span></span>
    
<span data-ttu-id="cf147-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span><span class="sxs-lookup"><span data-stu-id="cf147-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="cf147-185">将 .p7b 文件保存到服务器的硬盘驱动器，然后将该文件复制到每台边缘服务器的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cf147-185">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each of your Edge Servers.</span></span>
    
### <a name="nbspnbspnbspb-export-using-mmc"></a><span data-ttu-id="cf147-186">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-186">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-187">使用 MMC 导出</span><span class="sxs-lookup"><span data-stu-id="cf147-187">Export using MMC</span></span>

<span data-ttu-id="cf147-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span><span class="sxs-lookup"><span data-stu-id="cf147-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="cf147-189">可以使用 MMC 从任何加入域的计算机上导出 CA 根证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-189">You can export the CA root certificate from any domain joined machine using the MMC.</span></span> <span data-ttu-id="cf147-190">转到"开始 **"** 和" **运行**"，或打开 **"搜索**"，然后键入 **MMC** 以打开。</span><span class="sxs-lookup"><span data-stu-id="cf147-190">Either go to **Start** and **Run**, or open **Search**, and type **MMC** to open.</span></span>
    
<span data-ttu-id="cf147-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span><span class="sxs-lookup"><span data-stu-id="cf147-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="cf147-192">在 MMC 控制台中，单击 **"** 文件"，然后单击"**添加/删除管理单元"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-192">In the MMC console, click **File**, and then click **Add/Remove Snap-In**.</span></span>
    
<span data-ttu-id="cf147-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span><span class="sxs-lookup"><span data-stu-id="cf147-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="cf147-194">从 **"添加或删除管理单元"对话框** 列表中，选择"**证书**"，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-194">From the **Add or Remove Snap-ins** dialog list, choose **Certificates**, and then click **Add**.</span></span> <span data-ttu-id="cf147-195">当系统提示时，选择 **"计算机帐户**"，然后选择"下 **一步"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-195">When prompted, select **Computer Account**, and then **Next**.</span></span> <span data-ttu-id="cf147-196">在“选择计算机”对话框中，选择“本地计算机”。</span><span class="sxs-lookup"><span data-stu-id="cf147-196">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="cf147-197">单击 **"完成**"，然后单击 **"确定"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-197">Click **Finish**, and then **OK**.</span></span>
    
<span data-ttu-id="cf147-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="cf147-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="cf147-199">展开 **本地 (证书) 。**</span><span class="sxs-lookup"><span data-stu-id="cf147-199">Expand **Certificates (Local computer)**.</span></span> <span data-ttu-id="cf147-200">展开 **“受信任的根证书颁发机构”**。</span><span class="sxs-lookup"><span data-stu-id="cf147-200">Expand **Trusted Root Certification Authorities**.</span></span> <span data-ttu-id="cf147-201">选择 **"证书"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-201">Select **Certificates**.</span></span>
    
<span data-ttu-id="cf147-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span><span class="sxs-lookup"><span data-stu-id="cf147-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="cf147-203">单击由 CA 颁发的根证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-203">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="cf147-204">右键单击证书 **，在菜单** 上选择"所有任务"，然后选择"导出 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-204">Right-click the certificate, choose **All Tasks** on the menu, and then select **Export**.</span></span>
    
<span data-ttu-id="cf147-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span><span class="sxs-lookup"><span data-stu-id="cf147-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="cf147-206">证书 **导出向导将** 打开。</span><span class="sxs-lookup"><span data-stu-id="cf147-206">The **Certificate Export Wizard** opens.</span></span> <span data-ttu-id="cf147-207">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-207">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;。</span><span class="sxs-lookup"><span data-stu-id="cf147-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii.</span></span> <span data-ttu-id="cf147-209">在 **"导出文件格式"** 对话框中，选择要导出到的格式。</span><span class="sxs-lookup"><span data-stu-id="cf147-209">On the **Export File Format** dialog, choose the format you want to export to.</span></span> <span data-ttu-id="cf147-210">我们的建议是 **加密邮件语法标准 - PKCS #7证书 (P7b) 。**</span><span class="sxs-lookup"><span data-stu-id="cf147-210">Our recommendation is **Cryptographic Message Syntax Standard - PKCS #7 Certificates (P7b)**.</span></span> <span data-ttu-id="cf147-211">如果这也是你的选择，请记住，如果可能，还要选中"在证书路径中包括所有证书"复选框，因为这也将导出证书链，包括根 CA 证书和任何中间证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-211">If that's your choice as well, remember to also select the **Include all certificates in the certification path if possible** checkbox, as this will also export the certificate chain, including the root CA certificate and any Intermediate certificates.</span></span> <span data-ttu-id="cf147-212">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-212">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;。</span><span class="sxs-lookup"><span data-stu-id="cf147-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii.</span></span> <span data-ttu-id="cf147-214">在" **要** 导出的文件"对话框的文件名条目中，键入路径和文件名 (导出证书的默认扩展名为 .p7b) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-214">On the **File to Export** dialog, in the file name entry, type a path and file name (the default extension would be .p7b) for the exported certificate.</span></span> <span data-ttu-id="cf147-215">如果更轻松，请选择"浏览"按钮以转到想要将导出的证书保存到的位置，并在此处命名导出的证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-215">If it's easier on you, choose the **Browse** button to go to the location you want to save the exported certificate to, and name the exported certificate here.</span></span> <span data-ttu-id="cf147-216">单击 **"** 保存 **"，然后在** 准备就绪时单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="cf147-216">Click **Save**, and then **Next** when you're ready.</span></span>
    
<span data-ttu-id="cf147-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix.</span><span class="sxs-lookup"><span data-stu-id="cf147-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix.</span></span> <span data-ttu-id="cf147-218">查看操作摘要，然后单击" **完成** "完成证书导出。</span><span class="sxs-lookup"><span data-stu-id="cf147-218">Review the summary of your actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="cf147-219">单击“确定”确认导出成功。</span><span class="sxs-lookup"><span data-stu-id="cf147-219">Click **OK** to confirm the successful export.</span></span>
    
<span data-ttu-id="cf147-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x.</span><span class="sxs-lookup"><span data-stu-id="cf147-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x.</span></span> <span data-ttu-id="cf147-221">将 .p7b 文件复制到每台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-221">Copy the .p7b file to each of your Edge Servers.</span></span>
    
### <a name="2-import-the-ca-certification-chain"></a><span data-ttu-id="cf147-222">2. 导入 CA 认证链</span><span class="sxs-lookup"><span data-stu-id="cf147-222">2. Import the CA certification chain</span></span>

<span data-ttu-id="cf147-223">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="cf147-223">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="cf147-224">在每个边缘服务器上，打开 MMC **(选择"\*\*\*\*开始"和**"运行"或 **"** 搜索"，然后键入 **MMC** 以打开) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-224">On each Edge Server, open the MMC (choose **Start** and **Run**, or **Search**, and type **MMC** to open).</span></span>
    
<span data-ttu-id="cf147-225">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-225">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-226">在"**文件**"菜单上，单击 **"添加/删除管理单元"，** 然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-226">On the **File** menu, click **Add/Remove Snap-in**, and then choose **Add**.</span></span>
    
<span data-ttu-id="cf147-227">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="cf147-227">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="cf147-228">在 **"添加或删除管理单元**"框中 **，单击"** 证书"，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-228">In the **Add or Remove Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
    
<span data-ttu-id="cf147-229">&nbsp;&nbsp;&nbsp;d.</span><span class="sxs-lookup"><span data-stu-id="cf147-229">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="cf147-230">在 **“证书管理单元”** 对话框中，单击 **“计算机帐户”**，然后单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="cf147-230">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
    
<span data-ttu-id="cf147-231">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="cf147-231">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="cf147-232">在 **"选择** 计算机"对话框中，确保选中"本地计算机 **： (** 运行此控制台的计算机) 复选框，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-232">In the **Select Computer** dialog box, ensure that the **Local Computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
    
<span data-ttu-id="cf147-233">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="cf147-233">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="cf147-234">单击 **"关闭**"，然后单击 **"确定"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-234">Click **Close**, and then **OK**.</span></span>
    
<span data-ttu-id="cf147-235">&nbsp;&nbsp;&nbsp;g.</span><span class="sxs-lookup"><span data-stu-id="cf147-235">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="cf147-236">在控制台树中，展开"本地 (证书) ，右键单击"受信任的根证书颁发机构"，转到"所有任务"，然后单击"**导入"。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cf147-236">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, go to **All Tasks**, and then click **Import**.</span></span>
    
<span data-ttu-id="cf147-237">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="cf147-237">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="cf147-238">在出现的向导中，在"要导入的文件"文本框中，指定证书的文件名 (指定在上一部分中为 .p7b 文件指定) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-238">In the wizard that appears, in the **File to Import** textbox, specify the file name of the certificate (the name you gave the .p7b file in the previous section).</span></span> <span data-ttu-id="cf147-239">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-239">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-240">&nbsp;&nbsp;&nbsp;i.</span><span class="sxs-lookup"><span data-stu-id="cf147-240">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="cf147-241">将单选按钮保留为将 **所有证书放在** 以下存储中，因为应选择受信任的根证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="cf147-241">Leave the radio button on **Place all certificates in the following store, as Trusted Root Certification Authorities** should be selected.</span></span> <span data-ttu-id="cf147-242">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-242">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-243">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="cf147-243">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="cf147-244">查看摘要，然后单击" **完成** "完成导入。</span><span class="sxs-lookup"><span data-stu-id="cf147-244">Review the summary, and click **Finish** to complete the import.</span></span>
    
<span data-ttu-id="cf147-245">&nbsp;&nbsp;&nbsp;k.</span><span class="sxs-lookup"><span data-stu-id="cf147-245">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="cf147-246">这将需要为要部署的每台边缘服务器完成。</span><span class="sxs-lookup"><span data-stu-id="cf147-246">This will need to be done for every Edge Server you're deploying.</span></span>
    
### <a name="3-create-the-certificate-request"></a><span data-ttu-id="cf147-247">3. 创建证书请求</span><span class="sxs-lookup"><span data-stu-id="cf147-247">3. Create the certificate request</span></span>

<span data-ttu-id="cf147-248">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="cf147-248">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="cf147-249">登录到其中一台边缘服务器，启动部署向导，在步骤 **3：** 请求、安装或分配证书上，单击"运行 **("** 或"再次运行"（如果已运行此向导) ）。</span><span class="sxs-lookup"><span data-stu-id="cf147-249">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates**, click **Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="cf147-250">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-250">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-251">在"**证书请求"** 页上，确保 **选择了内部边缘证书**，然后单击"请求 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-251">On the **Certificate Request** page, ensure **Internal Edge Certificate** is selected, and click **Request**.</span></span>
    
<span data-ttu-id="cf147-252">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="cf147-252">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="cf147-253">在"**延迟** 请求"或"即时请求"页上，选择"如果可以从边缘环境访问联机证书颁发机构，则立即将请求发送到联机证书颁发机构"，或立即准备请求，但稍后以其他 **方式发送。**</span><span class="sxs-lookup"><span data-stu-id="cf147-253">On the **Delayed or Immediate Requests** page, choose **Send the request immediately to an online certification authority** if you have access to one from your Edge environment, or **Prepare the request now, but send it later** otherwise.</span></span>
    
<span data-ttu-id="cf147-254">&nbsp;&nbsp;&nbsp;d.</span><span class="sxs-lookup"><span data-stu-id="cf147-254">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="cf147-255">在" **证书** 请求文件"页上，输入文件保存位置的完整部分和文件名 (如 c：\SkypeInternalEdgeCert.cer) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-255">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="cf147-256">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-256">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-257">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="cf147-257">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="cf147-258">在 **"指定备用证书** 模板"页上，若要使用默认 WebServer 模板外的其他模板，请选中"使用所选证书颁发机构的替代证书模板"复选框。</span><span class="sxs-lookup"><span data-stu-id="cf147-258">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span> <span data-ttu-id="cf147-259">否则，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="cf147-259">Otherwise, do nothing.</span></span>
    
<span data-ttu-id="cf147-260">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="cf147-260">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="cf147-261">在“名称和安全设置”页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cf147-261">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="cf147-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span><span class="sxs-lookup"><span data-stu-id="cf147-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="cf147-263">在 **友好名称** 中，为证书显示名称一个 (，如内部边缘) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-263">In **Friendly name**, enter a display name for the certificate (such as Internal Edge).</span></span>
    
 <span data-ttu-id="cf147-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span><span class="sxs-lookup"><span data-stu-id="cf147-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="cf147-265">在 **位** 长度中，选择位长度 (默认值为 2048，可以更高、更安全，但会使性能降低) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-265">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="cf147-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span><span class="sxs-lookup"><span data-stu-id="cf147-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="cf147-267">如果需要可导出的证书，则必须选中"将 **证书私钥标记为可导出"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="cf147-267">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
 <span data-ttu-id="cf147-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv.</span><span class="sxs-lookup"><span data-stu-id="cf147-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv.</span></span> <span data-ttu-id="cf147-269">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-269">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-270">&nbsp;&nbsp;&nbsp;g.</span><span class="sxs-lookup"><span data-stu-id="cf147-270">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="cf147-271">在" **组织信息** "页上，输入 OU 组织中组织 (单位) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-271">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="cf147-272">你可以向 IT 部门或 (部门，例如) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-272">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="cf147-273">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="cf147-273">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="cf147-274">在 **"地理信息"** 页上，输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="cf147-274">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="cf147-275">&nbsp;&nbsp;&nbsp;i.</span><span class="sxs-lookup"><span data-stu-id="cf147-275">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="cf147-276">在 **"主题名称/主题备用** 名称"页上，向导应自动填充此名称。</span><span class="sxs-lookup"><span data-stu-id="cf147-276">On the **Subject Name/Subject Alternate Names** page, this should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="cf147-277">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="cf147-277">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="cf147-278">在" **配置其他主题替代** 名称"页上，需要添加所需的任何其他主题替代名称。</span><span class="sxs-lookup"><span data-stu-id="cf147-278">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="cf147-279">&nbsp;&nbsp;&nbsp;k.</span><span class="sxs-lookup"><span data-stu-id="cf147-279">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="cf147-280">在 **"请求摘要** "页上，查看将用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="cf147-280">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="cf147-281">如果需要进行更改，请返回并现在执行。</span><span class="sxs-lookup"><span data-stu-id="cf147-281">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="cf147-282">&nbsp;&nbsp;&nbsp;l.</span><span class="sxs-lookup"><span data-stu-id="cf147-282">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="cf147-283">然后单击 **"** 下一步"生成需要向 CA 提供的 CSR 文件 (还可以单击"查看日志"查看日志中的证书请求) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-283">Then click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="cf147-284">&nbsp;&nbsp;&nbsp;m.</span><span class="sxs-lookup"><span data-stu-id="cf147-284">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="cf147-285">生成请求后，可以单击 **"** 查看"查看证书，然后 **完成以关闭** 窗口。</span><span class="sxs-lookup"><span data-stu-id="cf147-285">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="cf147-286">CSR 文件的内容需要给定给 CA，以便他们可以生成证书，以便您可以在下一节中导入到此计算机。</span><span class="sxs-lookup"><span data-stu-id="cf147-286">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    

### <a name="4-import-the-certificate"></a><span data-ttu-id="cf147-287">4. 导入证书</span><span class="sxs-lookup"><span data-stu-id="cf147-287">4. Import the certificate</span></span>

<span data-ttu-id="cf147-288">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="cf147-288">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="cf147-289">以本地证书颁发机构管理员组登录到上一过程中您提出证书请求的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-289">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="cf147-290">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-290">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-291">在部署向导中，在步骤 **3 旁边。请求、安装或分配证书，** 单击"**再次运行"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-291">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="cf147-292">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="cf147-292">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="cf147-293">在" **可用证书任务** "页上，单击 **"从 "导入证书"。P7b、.pfx 或 .cer 文件**。</span><span class="sxs-lookup"><span data-stu-id="cf147-293">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="cf147-294">&nbsp;&nbsp;&nbsp;d.</span><span class="sxs-lookup"><span data-stu-id="cf147-294">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="cf147-295">在"导入证书"页上，键入在上一部分中获得的证书的完整路径和文件名 (或者您可以单击"浏览"以查找并选择该文件) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-295">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span>
    
<span data-ttu-id="cf147-296">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="cf147-296">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="cf147-297">如果要为边缘池的其他成员导入证书，并且证书包含私钥，请务必选中包含证书私钥的证书文件复选框，并指定密码。</span><span class="sxs-lookup"><span data-stu-id="cf147-297">If you're importing certificates for other members of your Edge pool, and your certificate contains a private key, be sure to select the **Certificate file that contains certificate's private key** check box, and specify the password.</span></span> <span data-ttu-id="cf147-298">单击“下一步”即可继续。</span><span class="sxs-lookup"><span data-stu-id="cf147-298">Click **Next** to continue.</span></span>
    
<span data-ttu-id="cf147-299">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="cf147-299">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="cf147-300">在 **"摘要"** 页上，确认信息后单击"下一步"，在成功导入证书后完成。</span><span class="sxs-lookup"><span data-stu-id="cf147-300">On the **Summary** page, click **Next** once you've confirmed the information, and **Finish** once the certificate is successfully imported.</span></span>
    
 
### <a name="5-export-the-certificate"></a><span data-ttu-id="cf147-301">5. 导出证书</span><span class="sxs-lookup"><span data-stu-id="cf147-301">5. Export the certificate</span></span>

<span data-ttu-id="cf147-302">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="cf147-302">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="cf147-303">确保你已以本地证书组的成员身份登录到之前将证书导入管理员组。</span><span class="sxs-lookup"><span data-stu-id="cf147-303">Make sure you've logged onto the Edge Server you imported the certificate to previously, as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="cf147-304">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-304">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-305">单击 **"开始\*\*\*\*" (** 或打开 **"** 搜索) ，然后键入 **MMC。**</span><span class="sxs-lookup"><span data-stu-id="cf147-305">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="cf147-306">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="cf147-306">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="cf147-307">在 MMC 控制台中，单击 **"文件**"，然后单击 **"添加/删除管理单元"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-307">From the MMC console, click **File**, and click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="cf147-308">&nbsp;&nbsp;&nbsp;d.</span><span class="sxs-lookup"><span data-stu-id="cf147-308">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="cf147-309">在 **"添加或删除管理单元"** 框中 **，单击"** 证书"，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-309">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="cf147-310">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="cf147-310">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="cf147-311">在 **"证书**"管理单元对话框中，选择 **"计算机帐户"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-311">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="cf147-312">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-312">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-313">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="cf147-313">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="cf147-314">在 **"选择计算机** "对话框中，选择"本地计算机 **： (** 运行此控制台的计算机) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-314">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="cf147-315">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="cf147-315">Click **Finish**.</span></span> <span data-ttu-id="cf147-316">单击 **"** 确定"，MMC 控制台的配置已完成。</span><span class="sxs-lookup"><span data-stu-id="cf147-316">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="cf147-317">&nbsp;&nbsp;&nbsp;g.</span><span class="sxs-lookup"><span data-stu-id="cf147-317">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="cf147-318">双击“证书(本地计算机)”扩展证书存储。</span><span class="sxs-lookup"><span data-stu-id="cf147-318">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="cf147-319">双击"**个人**"，然后单击"证书 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-319">Double-click **Personal**, and then click **Certificates**.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="cf147-320">您可能在此处，并且在本地计算机的证书个人存储中看不到任何证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-320">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="cf147-321">无需四处搜寻，如果密钥不存在，则导入的证书没有与之关联的私钥。</span><span class="sxs-lookup"><span data-stu-id="cf147-321">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="cf147-322">再尝试一次上述请求和导入步骤，如果确定正确，请与 CA 管理员或提供商联系。</span><span class="sxs-lookup"><span data-stu-id="cf147-322">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="cf147-323">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="cf147-323">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="cf147-324">在本地 **计算机的证书** 个人存储中，右键单击要导出的证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-324">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="cf147-325">从 **生成的菜单中** 选择"所有任务"，然后单击"导出 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-325">Select **All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="cf147-326">&nbsp;&nbsp;&nbsp;i.</span><span class="sxs-lookup"><span data-stu-id="cf147-326">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="cf147-327">在“证书导出向导”中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="cf147-327">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="cf147-328">选择“是，导出私钥”。</span><span class="sxs-lookup"><span data-stu-id="cf147-328">Select **Yes, export the private key**.</span></span> <span data-ttu-id="cf147-329">单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="cf147-329">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-330">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="cf147-330">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="cf147-331">在 **"导出文件格式"** 对话框中，选择" **个人信息交换 - PKCS#12" (。PFX) ，** 然后选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="cf147-331">On the **Export File Formats** dialog, select **Personal Information Exchange - PKCS#12 (.PFX)**, and then select the following:</span></span>
    
<span data-ttu-id="cf147-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span><span class="sxs-lookup"><span data-stu-id="cf147-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="cf147-333">如果可能，在证书路径中包括所有证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-333">Include all certificates in the certification path, if possible.</span></span>
    
<span data-ttu-id="cf147-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii.</span><span class="sxs-lookup"><span data-stu-id="cf147-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii.</span></span> <span data-ttu-id="cf147-335">导出所有扩展属性。</span><span class="sxs-lookup"><span data-stu-id="cf147-335">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="cf147-336">**如果\*\*\*\*导出成功，从不选择"删除私钥"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-336">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="cf147-337">这意味着您必须将证书和私钥重新导入回此边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-337">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="cf147-338">&nbsp;&nbsp;&nbsp;k.</span><span class="sxs-lookup"><span data-stu-id="cf147-338">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="cf147-339">如果要分配密码来保护私钥，可以键入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="cf147-339">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="cf147-340">重新输入密码以确认，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-340">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="cf147-341">&nbsp;&nbsp;&nbsp;l.</span><span class="sxs-lookup"><span data-stu-id="cf147-341">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="cf147-342">使用文件扩展名 **.pfx** 键入导出证书的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="cf147-342">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="cf147-343">该路径需要由池中的其他边缘服务器访问，或者你需要通过外部媒体传输（如 USB 驱动器 (移动) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-343">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="cf147-344">做出 **选择** 后单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="cf147-344">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="cf147-345">&nbsp;&nbsp;&nbsp;m.</span><span class="sxs-lookup"><span data-stu-id="cf147-345">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="cf147-346">查看"正在完成证书导出向导"对话框上的摘要，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-346">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="cf147-347">&nbsp;&nbsp;&nbsp;n.</span><span class="sxs-lookup"><span data-stu-id="cf147-347">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="cf147-348">在成功导出对话框中单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="cf147-348">Click **OK** in the successful export dialog.</span></span>
    
 
### <a name="6-assign-the-certificate"></a><span data-ttu-id="cf147-349">6. 分配证书</span><span class="sxs-lookup"><span data-stu-id="cf147-349">6. Assign the certificate</span></span>

<span data-ttu-id="cf147-350">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="cf147-350">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="cf147-351">在每个边缘服务器上，在部署向导中，在步骤 **3 旁边。请求、安装或分配证书**，单击"**再次运行"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-351">On EACH Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="cf147-352">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-352">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-353">在"**可用证书任务**"页上，单击"**分配现有证书"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-353">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="cf147-354">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="cf147-354">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="cf147-355">在“证书分配”页上，选择列表中的“边缘内部”。</span><span class="sxs-lookup"><span data-stu-id="cf147-355">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>
    
<span data-ttu-id="cf147-356">&nbsp;&nbsp;&nbsp;d.</span><span class="sxs-lookup"><span data-stu-id="cf147-356">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="cf147-357">在 **"证书存储** "页上，从上一部分中选择为内部边缘 (导入的证书) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-357">On the **Certificate Store** page, select the certificate you've imported for the internal Edge (from the previous section).</span></span>
    
<span data-ttu-id="cf147-358">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="cf147-358">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="cf147-359">在 **"证书分配摘要"** 页上，查看设置，然后单击"下一步 **"分配** 证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-359">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="cf147-360">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="cf147-360">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="cf147-361">在向导完成页上，单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="cf147-361">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="cf147-362">&nbsp;&nbsp;&nbsp;g.</span><span class="sxs-lookup"><span data-stu-id="cf147-362">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="cf147-363">完成此过程后，在每台边缘服务器上打开证书 MMC 管理单元、展开证书 (本地计算机 **) 、** 展开"个人"、单击"证书"并确认内部边缘证书在详细信息窗格中列出是一个不错的主意。</span><span class="sxs-lookup"><span data-stu-id="cf147-363">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each Edge Server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
### <a name="external-edge-interface-certificates"></a><span data-ttu-id="cf147-364">外部边缘接口证书</span><span class="sxs-lookup"><span data-stu-id="cf147-364">External Edge interface certificates</span></span>

 
### <a name="1-create-the-certificate-request"></a><span data-ttu-id="cf147-365">1. 创建证书请求</span><span class="sxs-lookup"><span data-stu-id="cf147-365">1. Create the certificate request</span></span>

<span data-ttu-id="cf147-366">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="cf147-366">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="cf147-367">登录到其中一台边缘服务器，启动部署向导，在"步骤 **3：** 请求、安装或分配证书"上，单击"运行 ("或"再次运行"（如果已运行此向导) ）。</span><span class="sxs-lookup"><span data-stu-id="cf147-367">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates, click Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="cf147-368">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-368">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-369">在“可用的证书任务”页上，单击“创建新的证书请求”。</span><span class="sxs-lookup"><span data-stu-id="cf147-369">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>
    
<span data-ttu-id="cf147-370">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="cf147-370">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="cf147-371">在"**证书请求"** 页上，确保 **已选择外部边缘证书**，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-371">On the **Certificate Request** page, ensure **External Edge Certificate** is selected, and click **Next**.</span></span>
    
<span data-ttu-id="cf147-372">&nbsp;&nbsp;&nbsp;d.</span><span class="sxs-lookup"><span data-stu-id="cf147-372">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="cf147-373">在“延迟的请求或即时请求”页上，单击“现在准备请求，但稍后发送”。</span><span class="sxs-lookup"><span data-stu-id="cf147-373">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>
    
<span data-ttu-id="cf147-374">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="cf147-374">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="cf147-375">在" **证书** 请求文件"页上，输入文件保存位置的完整部分和文件名 (如 c：\SkypeInternalEdgeCert.cer) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-375">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="cf147-376">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-376">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-377">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="cf147-377">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="cf147-378">在 **"指定备用证书** 模板"页上，若要使用默认 WebServer 模板外的其他模板，请选中"使用所选证书颁发机构的替代证书模板"复选框。</span><span class="sxs-lookup"><span data-stu-id="cf147-378">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>
    
<span data-ttu-id="cf147-379">&nbsp;&nbsp;&nbsp;g.</span><span class="sxs-lookup"><span data-stu-id="cf147-379">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="cf147-380">在“名称和安全设置”页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cf147-380">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="cf147-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span><span class="sxs-lookup"><span data-stu-id="cf147-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="cf147-382">在 **友好名称** 中，显示名称外部边缘 (，例如外部边缘) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-382">In **Friendly name**, enter a display name for the certificate (such as External Edge).</span></span>
    
 <span data-ttu-id="cf147-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span><span class="sxs-lookup"><span data-stu-id="cf147-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="cf147-384">在 **位** 长度中，选择位长度 (默认值为 2048，可以更高、更安全，但会使性能降低) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-384">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="cf147-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span><span class="sxs-lookup"><span data-stu-id="cf147-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="cf147-386">如果需要可导出的证书，则必须选中"将 **证书私钥标记为可导出"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="cf147-386">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
  <span data-ttu-id="cf147-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv.</span><span class="sxs-lookup"><span data-stu-id="cf147-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv.</span></span> <span data-ttu-id="cf147-388">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-388">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-389">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="cf147-389">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="cf147-390">在" **组织信息** "页上，输入 OU 组织中组织 (单位) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-390">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="cf147-391">你可以向 IT 部门或 (部门，例如) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-391">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="cf147-392">&nbsp;&nbsp;&nbsp;i.</span><span class="sxs-lookup"><span data-stu-id="cf147-392">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="cf147-393">在 **"地理信息"** 页上，输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="cf147-393">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="cf147-394">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="cf147-394">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="cf147-395">在 **"主题名称/主题备用** 名称"页上，向导应自动填充所需信息。</span><span class="sxs-lookup"><span data-stu-id="cf147-395">On the **Subject Name/Subject Alternate Names** page, the needed information should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="cf147-396">&nbsp;&nbsp;&nbsp;k.</span><span class="sxs-lookup"><span data-stu-id="cf147-396">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="cf147-397">在 **"主题备用名称"和** " (的 SIP 域) ，选中域复选框以添加 sip。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="cf147-397">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, check the domain checkbox to add a sip.<sipdomain></span></span> <span data-ttu-id="cf147-398">条目。</span><span class="sxs-lookup"><span data-stu-id="cf147-398">entry to the subject alternative names list.</span></span>
    
<span data-ttu-id="cf147-399">&nbsp;&nbsp;&nbsp;l.</span><span class="sxs-lookup"><span data-stu-id="cf147-399">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="cf147-400">在" **配置其他主题替代** 名称"页上，需要添加所需的任何其他主题替代名称。</span><span class="sxs-lookup"><span data-stu-id="cf147-400">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="cf147-401">&nbsp;&nbsp;&nbsp;m.</span><span class="sxs-lookup"><span data-stu-id="cf147-401">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="cf147-402">在 **"请求摘要** "页上，查看将用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="cf147-402">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="cf147-403">如果需要进行更改，请返回并现在执行。</span><span class="sxs-lookup"><span data-stu-id="cf147-403">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="cf147-404">&nbsp;&nbsp;&nbsp;n.</span><span class="sxs-lookup"><span data-stu-id="cf147-404">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="cf147-405">准备就绪后，单击"下一步"生成需要向 CA 提供的 CSR 文件 (还可以单击"查看日志"来查看日志中的证书请求) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-405">When you're ready, click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="cf147-406">&nbsp;&nbsp;&nbsp;o.</span><span class="sxs-lookup"><span data-stu-id="cf147-406">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="cf147-407">生成请求后，可以单击 **"** 查看"查看证书，然后 **完成以关闭** 窗口。</span><span class="sxs-lookup"><span data-stu-id="cf147-407">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="cf147-408">CSR 文件的内容需要给定给 CA，以便他们可以生成证书，以便您可以在下一节中导入到此计算机。</span><span class="sxs-lookup"><span data-stu-id="cf147-408">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    
<span data-ttu-id="cf147-409">&nbsp;&nbsp;&nbsp;p.</span><span class="sxs-lookup"><span data-stu-id="cf147-409">&nbsp;&nbsp;&nbsp;p.</span></span> <span data-ttu-id="cf147-410"> (可选) 在提交 CSR 内容时，可能会要求你提供某些信息，如下所示 (AA 差异很大，因此在提交 CSR 时可能) ：</span><span class="sxs-lookup"><span data-stu-id="cf147-410">(OPTIONAL) You may, when submitting the contents of the CSR, be asked for certain information, as follows (CAs vary greatly, so this may not be required):</span></span>
    
  - <span data-ttu-id="cf147-411">**Microsoft** 作为服务器平台</span><span class="sxs-lookup"><span data-stu-id="cf147-411">**Microsoft** as the server platform</span></span>
    
  - <span data-ttu-id="cf147-412">**IIS** 作为版本</span><span class="sxs-lookup"><span data-stu-id="cf147-412">**IIS** as the version</span></span>
    
  - <span data-ttu-id="cf147-413">**用作** 使用类型的 Web 服务器</span><span class="sxs-lookup"><span data-stu-id="cf147-413">**Web Server** as the usage type</span></span>
    
  - <span data-ttu-id="cf147-414">**作为响应格式的 PKCS7**</span><span class="sxs-lookup"><span data-stu-id="cf147-414">**PKCS7** as the response format</span></span>
    
 
### <a name="2-import-the-certificate"></a><span data-ttu-id="cf147-415">2. 导入证书</span><span class="sxs-lookup"><span data-stu-id="cf147-415">2. Import the certificate</span></span>

<span data-ttu-id="cf147-416">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="cf147-416">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="cf147-417">以本地证书颁发机构管理员组登录到上一过程中您提出证书请求的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-417">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="cf147-418">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-418">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-419">在部署向导中，在步骤 **3 旁边。请求、安装或分配证书，** 单击"**再次运行"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-419">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="cf147-420">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="cf147-420">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="cf147-421">在" **可用证书任务** "页上，单击 **"从 "导入证书"。P7b、.pfx 或 .cer 文件**。</span><span class="sxs-lookup"><span data-stu-id="cf147-421">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="cf147-422">&nbsp;&nbsp;&nbsp;d.</span><span class="sxs-lookup"><span data-stu-id="cf147-422">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="cf147-423">在"导入证书"页上，键入在上一部分中获得的证书的完整路径和文件名 (或者您可以单击"浏览"以查找并选择该文件) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-423">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span> <span data-ttu-id="cf147-424">如果证书包含私钥，请确保选择证书文件 **包含** 证书的私钥，并输入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="cf147-424">If your certificate contains a private key, make sure to select **Certificate file contains certificate's private key**, and enter the password for the private key.</span></span> <span data-ttu-id="cf147-425">准备就绪 **后** 单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="cf147-425">Click **Next** when ready.</span></span>
    
<span data-ttu-id="cf147-426">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="cf147-426">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="cf147-427">在"**导入证书摘要"** 页上，查看摘要信息，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-427">On the **Import Certificate Summary** page, review the summary information, and click **Next**.</span></span>
    
<span data-ttu-id="cf147-428">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="cf147-428">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="cf147-429">在 **"正在执行命令** "页上，可以通过单击"查看日志"查看导入完成后 **的结果**。</span><span class="sxs-lookup"><span data-stu-id="cf147-429">On the **Executing Commands** page, you can review the result of the import when it's complete by clicking **View Log**.</span></span> <span data-ttu-id="cf147-430">单击 **"** 完成"完成证书导入。</span><span class="sxs-lookup"><span data-stu-id="cf147-430">Click **Finish** to complete the certificate import.</span></span>
    
<span data-ttu-id="cf147-431">&nbsp;&nbsp;&nbsp;g.</span><span class="sxs-lookup"><span data-stu-id="cf147-431">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="cf147-432">如果池中有其他边缘服务器，则还需要执行以下两个过程。</span><span class="sxs-lookup"><span data-stu-id="cf147-432">If you have other Edge Servers in a pool, you'll need to follow the next two procedures as well.</span></span> <span data-ttu-id="cf147-433">如果这是独立的边缘服务器，则使用外部证书完成。</span><span class="sxs-lookup"><span data-stu-id="cf147-433">If this is a standalone Edge Server, you're done with external certificates.</span></span>
    
 
### <a name="3-export-the-certificate"></a><span data-ttu-id="cf147-434">3. 导出证书</span><span class="sxs-lookup"><span data-stu-id="cf147-434">3. Export the certificate</span></span>

<span data-ttu-id="cf147-435">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="cf147-435">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="cf147-436">确保已以本地管理员身份登录到将证书导入到的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-436">Make sure you've logged onto the Edge Server you imported the certificate to as a local Administrator.</span></span>
    
<span data-ttu-id="cf147-437">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-437">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-438">单击 **"开始\*\*\*\*" (** 或打开 **"** 搜索) ，然后键入 **MMC。**</span><span class="sxs-lookup"><span data-stu-id="cf147-438">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="cf147-439">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="cf147-439">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="cf147-440">在 MMC 控制台中，单击 **"** 文件"，然后单击 **"添加/删除管理单元"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-440">From the MMC console, click **File**, and then click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="cf147-441">&nbsp;&nbsp;&nbsp;d.</span><span class="sxs-lookup"><span data-stu-id="cf147-441">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="cf147-442">在 **"添加或删除管理单元"** 框中 **，单击"** 证书"，然后单击"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-442">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="cf147-443">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="cf147-443">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="cf147-444">在 **"证书**"管理单元对话框中，选择 **"计算机帐户"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-444">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="cf147-445">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cf147-445">Click **Next**.</span></span>
    
<span data-ttu-id="cf147-446">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="cf147-446">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="cf147-447">在 **"选择计算机** "对话框中，选择"本地计算机 **： (** 运行此控制台的计算机) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-447">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="cf147-448">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="cf147-448">Click **Finish**.</span></span> <span data-ttu-id="cf147-449">单击 **"** 确定"，MMC 控制台的配置已完成。</span><span class="sxs-lookup"><span data-stu-id="cf147-449">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="cf147-450">&nbsp;&nbsp;&nbsp;g.</span><span class="sxs-lookup"><span data-stu-id="cf147-450">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="cf147-451">双击“证书(本地计算机)”扩展证书存储。</span><span class="sxs-lookup"><span data-stu-id="cf147-451">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="cf147-452">**双击"个人"，** 然后单击"证书 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-452">**Double-click Personal**, and then click **Certificates**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="cf147-453">您可能在此处，并且在本地计算机的证书个人存储中看不到任何证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-453">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="cf147-454">无需四处搜寻，如果密钥不存在，则导入的证书没有与之关联的私钥。</span><span class="sxs-lookup"><span data-stu-id="cf147-454">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="cf147-455">再尝试一次上述请求和导入步骤，如果确定正确，请与 CA 管理员或提供商联系。</span><span class="sxs-lookup"><span data-stu-id="cf147-455">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="cf147-456">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="cf147-456">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="cf147-457">在本地 **计算机的证书** 个人存储中，右键单击要导出的证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-457">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="cf147-458">**从生成的菜单中** 选择"所有任务"，然后单击"导出 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-458">**Select All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="cf147-459">&nbsp;&nbsp;&nbsp;i.</span><span class="sxs-lookup"><span data-stu-id="cf147-459">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="cf147-460">在“证书导出向导”中，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="cf147-460">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="cf147-461">选择“是，导出私钥”。</span><span class="sxs-lookup"><span data-stu-id="cf147-461">Select **Yes, export the private key**.</span></span> <span data-ttu-id="cf147-462">单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="cf147-462">Click **Next**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="cf147-463">如果是 **，导出私钥** 不可用，那么在获得该证书之前，该证书的私钥未标记为导出。</span><span class="sxs-lookup"><span data-stu-id="cf147-463">If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it.</span></span> <span data-ttu-id="cf147-464">您需要再次从提供程序请求证书，将私钥设置为导出，然后才能成功执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cf147-464">You need to request the certificate from the provider again, with the private key set to export, before doing this successfully.</span></span>
  
<span data-ttu-id="cf147-465">&nbsp;&nbsp;&nbsp;j.</span><span class="sxs-lookup"><span data-stu-id="cf147-465">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="cf147-466">在"导出文件格式"对话框中，选择"个人信息交换 - PKCS#12" (。PFX) ，然后选择以下内容：</span><span class="sxs-lookup"><span data-stu-id="cf147-466">On the Export File Formats dialog, select Personal Information Exchange - PKCS#12 (.PFX) and then select the following:</span></span>
    
 <span data-ttu-id="cf147-467">&nbsp;&nbsp;&nbsp;  i.</span><span class="sxs-lookup"><span data-stu-id="cf147-467">&nbsp;&nbsp;&nbsp;  i.</span></span> <span data-ttu-id="cf147-468">如果可能，在证书路径中包括所有证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-468">Include all certificates in the certification path, if possible.</span></span>
    
 <span data-ttu-id="cf147-469">&nbsp;&nbsp;&nbsp;  ii.</span><span class="sxs-lookup"><span data-stu-id="cf147-469">&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="cf147-470">导出所有扩展属性。</span><span class="sxs-lookup"><span data-stu-id="cf147-470">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="cf147-471">**如果\*\*\*\*导出成功，从不选择"删除私钥"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-471">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="cf147-472">这意味着您必须将证书和私钥重新导入回此边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="cf147-472">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="cf147-473">&nbsp;&nbsp;&nbsp;k.</span><span class="sxs-lookup"><span data-stu-id="cf147-473">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="cf147-474">如果要分配密码来保护私钥，可以键入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="cf147-474">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="cf147-475">重新输入密码以确认，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-475">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="cf147-476">&nbsp;&nbsp;&nbsp;l.</span><span class="sxs-lookup"><span data-stu-id="cf147-476">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="cf147-477">使用文件扩展名 **.pfx** 键入导出证书的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="cf147-477">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="cf147-478">该路径需要由池中的其他边缘服务器访问，或者你需要通过外部媒体传输（如 USB 驱动器 (移动) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-478">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="cf147-479">做出 **选择** 后单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="cf147-479">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="cf147-480">&nbsp;&nbsp;&nbsp;m.</span><span class="sxs-lookup"><span data-stu-id="cf147-480">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="cf147-481">查看"正在完成证书导出向导"对话框上的摘要，然后单击"完成 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-481">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="cf147-482">&nbsp;&nbsp;&nbsp;n.</span><span class="sxs-lookup"><span data-stu-id="cf147-482">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="cf147-483">在成功导出对话框中单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="cf147-483">Click **OK** in the successful export dialog.</span></span>
    
<span data-ttu-id="cf147-484">&nbsp;&nbsp;&nbsp;o.</span><span class="sxs-lookup"><span data-stu-id="cf147-484">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="cf147-485">您现在需要返回到之前"导入证书"部分，并将证书导入到所有剩余边缘服务器，然后继续进行分配，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cf147-485">You'll now need to go back to the Import the certificate section prior to this and import the certificate to all your remaining Edge Servers, then proceed with assigning, below.</span></span>
    
 
### <a name="4-assign-the-certificate"></a><span data-ttu-id="cf147-486">4. 分配证书</span><span class="sxs-lookup"><span data-stu-id="cf147-486">4. Assign the certificate</span></span>

<span data-ttu-id="cf147-487">&nbsp;&nbsp;&nbsp;a.</span><span class="sxs-lookup"><span data-stu-id="cf147-487">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="cf147-488">在每个 **边缘** 服务器上，在部署向导中，在步骤 **3 旁边。请求、安装或分配证书**，单击"**再次运行"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-488">On **EACH** Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="cf147-489">&nbsp;&nbsp;&nbsp;b.</span><span class="sxs-lookup"><span data-stu-id="cf147-489">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="cf147-490">在"**可用证书任务**"页上，单击"**分配现有证书"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-490">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="cf147-491">&nbsp;&nbsp;&nbsp;c.</span><span class="sxs-lookup"><span data-stu-id="cf147-491">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="cf147-492">在" **证书分配"** 页上， **选择列表中的"边缘** 外部"。</span><span class="sxs-lookup"><span data-stu-id="cf147-492">On the **Certificate Assignment** page, select **Edge External** in the list.</span></span>
    
<span data-ttu-id="cf147-493">&nbsp;&nbsp;&nbsp;d.</span><span class="sxs-lookup"><span data-stu-id="cf147-493">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="cf147-494">在 **"证书存储** "页上，从上一部分中选择为外部边缘 (导入的证书) 。</span><span class="sxs-lookup"><span data-stu-id="cf147-494">On the **Certificate Store** page, select the certificate you've imported for the external Edge (from the previous section).</span></span>
    
<span data-ttu-id="cf147-495">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="cf147-495">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="cf147-496">在 **"证书分配摘要"** 页上，查看设置，然后单击"下一步 **"分配** 证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-496">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="cf147-497">&nbsp;&nbsp;&nbsp;f.</span><span class="sxs-lookup"><span data-stu-id="cf147-497">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="cf147-498">在向导完成页上，单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="cf147-498">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="cf147-499">&nbsp;&nbsp;&nbsp;g.</span><span class="sxs-lookup"><span data-stu-id="cf147-499">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="cf147-500">完成此过程后，在每个服务器上打开"证书 MMC"管理单元，展开"证书 **" (本地计算机) ，** 展开"个人"，单击"证书"并确认内部边缘证书在详细信息窗格中列出是一个不错的主意。</span><span class="sxs-lookup"><span data-stu-id="cf147-500">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="cf147-501">您还需要为反向代理服务器设置证书。</span><span class="sxs-lookup"><span data-stu-id="cf147-501">You will also have needed to set up the certificates for your reverse proxy server.</span></span> 
  
## <a name="starting-the-edge-servers"></a><span data-ttu-id="cf147-502">启动边缘服务器</span><span class="sxs-lookup"><span data-stu-id="cf147-502">Starting the Edge Servers</span></span>

<span data-ttu-id="cf147-503">设置完成后，需要在部署中的每台边缘服务器上启动服务：</span><span class="sxs-lookup"><span data-stu-id="cf147-503">Once the setup is complete, you'll need to start the services on each Edge server in your deployment:</span></span>
  
1. <span data-ttu-id="cf147-504">在每台边缘服务器的部署 **向导中**，单击"步骤 **4： 启动服务"旁边的**"运行 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-504">On each Edge Server, in the **Deployment Wizard**, next to **Step 4: Start Services**, click **Run**.</span></span>
    
2. <span data-ttu-id="cf147-505">在 **"启动 Skype for Business Server 服务**"页上，查看服务列表，然后单击"下一步"以启动服务。 </span><span class="sxs-lookup"><span data-stu-id="cf147-505">On the **Start Skype for Business Server Services** page, review the list of services, and then click **Next** to start the services.</span></span>
    
3. <span data-ttu-id="cf147-506">启动服务后，可以单击" **完成** "关闭向导。</span><span class="sxs-lookup"><span data-stu-id="cf147-506">After the services are started, you can click **Finish** to close the wizard.</span></span>
    
4. <span data-ttu-id="cf147-507"> (可选) 步骤 **4：启动服务** 下，单击"**服务状态"。**</span><span class="sxs-lookup"><span data-stu-id="cf147-507">(Optional) Still under **Step 4: Start Services**, click **Services Status**.</span></span>
    
5.  <span data-ttu-id="cf147-508">在每台服务器的"服务 **MMC"** 中，验证所有 Skype for Business Server 服务是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="cf147-508">In the **Services MMC** on each server, verify that all the Skype for Business Server services are running.</span></span>
    

