---
title: 在部署边缘服务器 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 摘要： 了解如何为您 Skype 业务服务器环境中部署边缘服务器。
ms.openlocfilehash: 85fb06ace0cabab5693973f0c6dd5564abdabcaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893194"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="fe2aa-103">在部署边缘服务器 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="fe2aa-103">Deploy Edge Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="fe2aa-104">**摘要：** 了解如何为您 Skype 业务服务器环境中部署边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-104">**Summary:** Learn how to deploy Edge Servers into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="fe2aa-105">以下各节包含为了后已审阅 for Business Server[规划边缘服务器部署中的业务服务器 Skype](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)文档 Skype 遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-105">The following sections contain steps that are meant to be followed after the Skype for Business Server [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) documentation has been reviewed.</span></span> <span data-ttu-id="fe2aa-106">部署步骤如下：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-106">The deployment steps are as follows:</span></span>
  
- <span data-ttu-id="fe2aa-107">网络接口</span><span class="sxs-lookup"><span data-stu-id="fe2aa-107">Network interfaces</span></span>
    
- <span data-ttu-id="fe2aa-108">安装</span><span class="sxs-lookup"><span data-stu-id="fe2aa-108">Installation</span></span>
    
- <span data-ttu-id="fe2aa-109">证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-109">Certificates</span></span>
    
- <span data-ttu-id="fe2aa-110">启动边缘服务器</span><span class="sxs-lookup"><span data-stu-id="fe2aa-110">Starting the Edge Servers</span></span>
    
## <a name="network-interfaces"></a><span data-ttu-id="fe2aa-111">网络接口</span><span class="sxs-lookup"><span data-stu-id="fe2aa-111">Network interfaces</span></span>

<span data-ttu-id="fe2aa-112">在规划如前所述，您将可以配置您的网络接口与 DNS 在外围网络承载边缘服务器，或没有 DNS 外围网络中。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-112">As noted in Planning, you will either be configuring your network interface with DNS in the perimeter network hosting your Edge Servers, or without DNS in the perimeter network.</span></span>
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="fe2aa-113">使用外围网络中 DNS 服务器的接口配置</span><span class="sxs-lookup"><span data-stu-id="fe2aa-113">Interface configuration with DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="fe2aa-114">为每台边缘服务器，一个用于面向内部的接口，，一个用于面向外部的接口安装两个网络适配器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-114">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fe2aa-115">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-115">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="fe2aa-116">在您的外部接口，您将配置**一个**下列选项：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-116">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="fe2aa-117">a.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-117">a.</span></span> <span data-ttu-id="fe2aa-118">在外部外围网络子网上配置三个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-118">Three static IP addresses on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="fe2aa-119">配置适配器 DNS 设置以指向一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-119">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
   <span data-ttu-id="fe2aa-120">b.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-120">b.</span></span> <span data-ttu-id="fe2aa-121">在外部外围网络子网上配置一个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-121">One static IP address on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="fe2aa-122">配置适配器 DNS 设置以指向一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-122">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span> <span data-ttu-id="fe2aa-123">此配置仅可接受的如果已配置拓扑在端口分配中, 具有非标准值的[边缘拓扑的 Skype 业务服务器创建](create-your-edge-topology.md)一文中介绍。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-123">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="fe2aa-124">在内部接口上配置内部外围网络子网上, 一个静态 IP 和未设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-124">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="fe2aa-125">配置适配器 DNS 设置，以指向至少一台 DNS 服务器，但最好是一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-125">Configure the adaptor DNS settings to point to at least one DNS server, but preferably a pair of perimeter DNS servers.</span></span>
    
4. <span data-ttu-id="fe2aa-126">在客户端，Skype Business Server 和 Exchange 统一消息 (UM) 服务器所在所有内部网络的内部接口上创建永久静态路由。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-126">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="fe2aa-127">不使用外围网络中 DNS 服务器的接口配置</span><span class="sxs-lookup"><span data-stu-id="fe2aa-127">Interface configuration without DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="fe2aa-128">为每台边缘服务器，一个用于面向内部的接口，，一个用于面向外部的接口安装两个网络适配器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-128">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fe2aa-129">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-129">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="fe2aa-130">在您的外部接口，您将配置**一个**下列选项：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-130">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="fe2aa-131">a.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-131">a.</span></span> <span data-ttu-id="fe2aa-132">在外部外围网络子网上配置三个静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-132">Three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="fe2aa-133">您还需要将默认网关配置的外部接口，例如，定义为默认网关的面向 internet 的路由器或外部防火墙。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-133">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="fe2aa-134">将适配器 DNS 设置配置为指向一台外部 DNS 服务器，最好是一对外部 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-134">Configure the adapter DNS settings to point to an external DNS server, ideally a pair of external DNS servers.</span></span>
    
   <span data-ttu-id="fe2aa-135">b.</span><span class="sxs-lookup"><span data-stu-id="fe2aa-135">b.</span></span> <span data-ttu-id="fe2aa-136">在外部外围网络子网上配置一个静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-136">One static IP address on the external perimeter network subnet.</span></span> <span data-ttu-id="fe2aa-137">您还需要将默认网关配置的外部接口，例如，定义为默认网关的面向 internet 的路由器或外部防火墙。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-137">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="fe2aa-138">将适配器 DNS 设置配置为指向一台外部 DNS 服务器，最好是一对外部 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-138">Configure the adapter DNS settings to point to an external DNS server, or ideally a pair of external DNS servers.</span></span> <span data-ttu-id="fe2aa-139">此配置仅可接受的如果已配置拓扑在端口分配中, 具有非标准值的[边缘拓扑的 Skype 业务服务器创建](create-your-edge-topology.md)一文中介绍。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-139">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="fe2aa-140">在内部接口上配置内部外围网络子网上, 一个静态 IP 和未设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-140">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="fe2aa-141">另外将适配器 DNS 设置留空。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-141">Also leave the adapter DNS settings empty.</span></span>
    
4. <span data-ttu-id="fe2aa-142">在客户端，Skype Business Server 和 Exchange 统一消息 (UM) 服务器所在所有内部网络的内部接口上创建永久静态路由。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-142">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
5. <span data-ttu-id="fe2aa-143">编辑上包含的下一个跃点服务器的记录每台边缘服务器或虚拟 IP (VIP) 的主机文件。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-143">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP).</span></span> <span data-ttu-id="fe2aa-144">此记录将控制器、 Standard Edition server 或前端池配置为在拓扑生成器中的边缘服务器下一个跃点地址。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-144">This record will be the Director, Standard Edition server or Front End pool you configured as the Edge Server next hop address in Topology Builder.</span></span> <span data-ttu-id="fe2aa-145">如果您正在使用 DNS 负载平衡，包括行的下一个跃点池的每个成员。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-145">If you're using DNS load balancing, include a line for each member of the next hop pool.</span></span>
    
## <a name="installation"></a><span data-ttu-id="fe2aa-146">安装</span><span class="sxs-lookup"><span data-stu-id="fe2aa-146">Installation</span></span>

<span data-ttu-id="fe2aa-147">要成功完成这些步骤，您将需要遵循了[创建边缘拓扑的 Skype 业务 server](create-your-edge-topology.md)文章中的步骤。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-147">To complete these steps successfully, you will need to have followed the steps in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
  
1. <span data-ttu-id="fe2aa-148">登录到您已具有帐户的本地管理员组中的边缘服务器角色的已配置的服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-148">Log onto the server you've been configuring for the Edge Server role with an account that's in the local Administrator's group.</span></span>
    
2. <span data-ttu-id="fe2aa-149">您将需要在此计算机上的边缘服务器拓扑文档的末尾复制出来的拓扑配置文件。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-149">You'll need the topology configuration file you copied out at the end of the Edge Server Topology documentation on this machine.</span></span> <span data-ttu-id="fe2aa-150">访问保存该配置文件的外部介质（如 USB 驱动器或共享）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-150">Access the external media you placed that configuration file on (like a USB drive or share).</span></span>
    
3. <span data-ttu-id="fe2aa-151">启动**部署向导**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-151">Start the **Deployment Wizard**.</span></span>
    
4. <span data-ttu-id="fe2aa-152">一旦打开向导后，单击**安装或更新 Skype 业务 Server 系统**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-152">Once the wizard opens, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="fe2aa-153">向导将运行检查以查看是否已安装任何内容。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-153">The wizard will run checks to see if anything's already installed.</span></span> <span data-ttu-id="fe2aa-154">因为这是首次运行向导时，您需要从**步骤 1 开始。安装本地配置存储。**</span><span class="sxs-lookup"><span data-stu-id="fe2aa-154">As this is the first time running the wizard, you'll want to start at **Step 1. Install Local Configuration Store.**</span></span>
    
6. <span data-ttu-id="fe2aa-155">将出现**配置本地副本的中央管理存储**对话框。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-155">The **Configure Local Replica of Central Management store** dialog will appear.</span></span> <span data-ttu-id="fe2aa-156">您需要单击**导入从文件 （边缘服务器的推荐）**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-156">You need to click **Import from a file (Recommended for Edge Servers)**.</span></span>
    
7. <span data-ttu-id="fe2aa-157">从这里，浏览到你先前导出拓扑的位置，选择 .zip 文件，然后单击“**打开**”，再单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-157">From here, browse to the location of the topology you exported previously, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="fe2aa-158">部署向导会读取的配置文件，并将 XML 配置文件写入本地计算机。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-158">The Deployment Wizard will read the configuration file and write the XML configuration file to the local computer.</span></span>
    
9. <span data-ttu-id="fe2aa-159">“**正在执行命令**”过程完成后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-159">After the **Executing Commands** process is finished, click **Finish**.</span></span>
    
10. <span data-ttu-id="fe2aa-160">在部署向导中，单击**步骤 2。安装或删除业务服务器组件 Skype**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-160">In the Deployment Wizard, click **Step 2. Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="fe2aa-161">然后，该向导将安装已存储在本地计算机的 XML 配置文件中指定的业务服务器边缘组件的 Skype。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-161">The wizard will then install the Skype for Business Server Edge components specified in the XML configuration file that's been stored on the local computer.</span></span>
    
11. <span data-ttu-id="fe2aa-162">一旦安装的完整信息，您可以将其移动到下面的**证书**部分中的步骤。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-162">Once the installation's complete, you can move onto the steps in the **Certificates** section below.</span></span>
    
## <a name="certificates"></a><span data-ttu-id="fe2aa-163">证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-163">Certificates</span></span>

<span data-ttu-id="fe2aa-164">边缘证书规划文档中找不到边缘服务器的证书要求。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-164">The certificate requirements for the Edge Server can be found in the Edge Certificate Planning documentation.</span></span> <span data-ttu-id="fe2aa-165">设置证书的步骤如下。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-165">The steps for setting up certificates are below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe2aa-166">当运行证书向导，您需要以正确的权限类型的证书模板具有您要使用的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-166">When running the Certificate Wizard, you need to be logged in as an account with the correct permissions for the type of certificate template you're going to use.</span></span> <span data-ttu-id="fe2aa-167">默认情况下，业务服务器证书请求 Skype 将要使用的 Web 服务器证书模板。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-167">By default, a Skype for Business Server certificate request is going to use the Web Server certificate template.</span></span> <span data-ttu-id="fe2aa-168">如果您正在登录请求通过此模板的证书，请仔细检查以确保组的 RTCUniversalServerAdmins 组成员的帐户已分配要使用该模板的注册权限。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-168">If you're logged in with an account that's a member of the RTCUniversalServerAdmins group to request a certificate via this template, double-check to make sure the group's been assigned the Enroll permissions to use that template.</span></span> 
  
### <a name="internal-edge-interface-certificates"></a><span data-ttu-id="fe2aa-169">内部边缘接口证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-169">Internal Edge interface certificates</span></span>

 
### <a name="1-download-or-export-the-ca-certification-chain"></a><span data-ttu-id="fe2aa-170">1.下载或导出 CA 证书链</span><span class="sxs-lookup"><span data-stu-id="fe2aa-170">1. Download or export the CA certification chain</span></span>

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a><span data-ttu-id="fe2aa-171">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-171">&nbsp;&nbsp;&nbsp; a.</span></span> <span data-ttu-id="fe2aa-172">使用 certsrv 网站下载</span><span class="sxs-lookup"><span data-stu-id="fe2aa-172">Download using certsrv web site</span></span>

<span data-ttu-id="fe2aa-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="fe2aa-174">登录到 Skype 业务服务器在内部网络中以本地 Administrators 组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-174">Log into a Skype for Business Server in your internal network as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="fe2aa-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="fe2aa-176">打开**开始**，请**运行**（或**搜索**和**运行**），然后键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-176">Open up **Start**, and **Run** (or **Search** and **Run** ), and then type the following:</span></span>
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

<span data-ttu-id="fe2aa-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For example:</span></span>
    
  ```
  https://ca01/contoso.com/certsrv
  ```

<span data-ttu-id="fe2aa-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="fe2aa-179">在发证 CA 的 certsrv 网页上，在**选择任务**，单击**下载 CA 证书、 证书链或 CRL**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-179">On the issuing CA's certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
    
<span data-ttu-id="fe2aa-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="fe2aa-181">在“**下载 CA 证书、证书链或 CRL**”下，单击“**下载 CA 证书链**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-181">Under **Download a CA certificate, certificate chain, or CRL**, click **Download CA certificate chain**.</span></span>
    
<span data-ttu-id="fe2aa-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="fe2aa-183">在“**文件下载**”框中，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-183">In the **File Download** box, click **Save**.</span></span>
    
<span data-ttu-id="fe2aa-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="fe2aa-185">在服务器上，将.p7b 文件保存到硬盘上，然后将其复制到每台边缘服务器上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-185">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each of your Edge Servers.</span></span>
    
### <a name="nbspnbspnbspb-export-using-mmc"></a><span data-ttu-id="fe2aa-186">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-186">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-187">使用 MMC 导出</span><span class="sxs-lookup"><span data-stu-id="fe2aa-187">Export using MMC</span></span>

<span data-ttu-id="fe2aa-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="fe2aa-189">你可以使用 MMC 从任何加入域的计算机导出 CA 根证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-189">You can export the CA root certificate from any domain joined machine using the MMC.</span></span> <span data-ttu-id="fe2aa-190">依次单击“**开始**”和“**运行**”，或者单击“**搜索**”后键入“**MMC**”打开。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-190">Either go to **Start** and **Run**, or open **Search**, and type **MMC** to open.</span></span>
    
<span data-ttu-id="fe2aa-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="fe2aa-192">在 MMC 控制台中，单击“**文件**”，然后单击“**添加/删除管理单元**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-192">In the MMC console, click **File**, and then click **Add/Remove Snap-In**.</span></span>
    
<span data-ttu-id="fe2aa-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="fe2aa-194">从“**添加或删除管理单元**”对话框列表中，选择“**证书**”，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-194">From the **Add or Remove Snap-ins** dialog list, choose **Certificates**, and then click **Add**.</span></span> <span data-ttu-id="fe2aa-195">系统提示时，选择“**计算机帐户**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-195">When prompted, select **Computer Account**, and then **Next**.</span></span> <span data-ttu-id="fe2aa-196">在“**选择计算机**”对话框中，选择“**本地计算机**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-196">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="fe2aa-197">单击“**完成**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-197">Click **Finish**, and then **OK**.</span></span>
    
<span data-ttu-id="fe2aa-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="fe2aa-199">展开“**证书(本地计算机)**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-199">Expand **Certificates (Local computer)**.</span></span> <span data-ttu-id="fe2aa-200">展开“**受信任的根证书颁发机构**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-200">Expand **Trusted Root Certification Authorities**.</span></span> <span data-ttu-id="fe2aa-201">选择“**证书**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-201">Select **Certificates**.</span></span>
    
<span data-ttu-id="fe2aa-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="fe2aa-203">单击由 CA 颁发的根证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-203">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="fe2aa-204">右键单击该证书，选择菜单上的“**所有任务**”，然后选择“**导出**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-204">Right-click the certificate, choose **All Tasks** on the menu, and then select **Export**.</span></span>
    
<span data-ttu-id="fe2aa-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="fe2aa-206">“**证书导出向导**”随即打开。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-206">The **Certificate Export Wizard** opens.</span></span> <span data-ttu-id="fe2aa-207">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-207">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii.</span></span> <span data-ttu-id="fe2aa-209">打开“**导出文件格式**”对话框，选择要导出到的格式。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-209">On the **Export File Format** dialog, choose the format you want to export to.</span></span> <span data-ttu-id="fe2aa-210">我们的建议是“**加密消息语法标准 – PKCS #7 证书(P7b)**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-210">Our recommendation is **Cryptographic Message Syntax Standard - PKCS #7 Certificates (P7b)**.</span></span> <span data-ttu-id="fe2aa-211">如果您的所选择的请记住还选中**如果可能，包括证书路径中的所有证书**复选框，如这还将导出的证书链，包括根 CA 证书和任何中间证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-211">If that's your choice as well, remember to also select the **Include all certificates in the certification path if possible** checkbox, as this will also export the certificate chain, including the root CA certificate and any Intermediate certificates.</span></span> <span data-ttu-id="fe2aa-212">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-212">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii.</span></span> <span data-ttu-id="fe2aa-214">在“**要导出的文件**”对话框的文件名输入框中，键入导出的证书的路径和文件名（默认扩展名为 .p7b）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-214">On the **File to Export** dialog, in the file name entry, type a path and file name (the default extension would be .p7b) for the exported certificate.</span></span> <span data-ttu-id="fe2aa-215">如果是在您更轻松地，选择**浏览**按钮以转到要保存到，导出的证书的位置，然后命名导出的证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-215">If it's easier on you, choose the **Browse** button to go to the location you want to save the exported certificate to, and name the exported certificate here.</span></span> <span data-ttu-id="fe2aa-216">准备好之后，单击**保存**，然后**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-216">Click **Save**, and then **Next** when you're ready.</span></span>
    
<span data-ttu-id="fe2aa-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix.</span></span> <span data-ttu-id="fe2aa-218">查看操作摘要，然后单击“**完成**”完成证书的导出。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-218">Review the summary of your actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="fe2aa-219">单击“**确定**”确认导出成功。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-219">Click **OK** to confirm the successful export.</span></span>
    
<span data-ttu-id="fe2aa-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x.</span></span> <span data-ttu-id="fe2aa-221">将.p7b 文件复制到每台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-221">Copy the .p7b file to each of your Edge Servers.</span></span>
    
### <a name="2-import-the-ca-certification-chain"></a><span data-ttu-id="fe2aa-222">2.导入 CA 证书链</span><span class="sxs-lookup"><span data-stu-id="fe2aa-222">2. Import the CA certification chain</span></span>

<span data-ttu-id="fe2aa-223">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-223">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="fe2aa-224">在每台边缘服务器上打开 MMC （选择**开始**和**运行**，或**搜索**，并键入**MMC**以打开）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-224">On each Edge Server, open the MMC (choose **Start** and **Run**, or **Search**, and type **MMC** to open).</span></span>
    
<span data-ttu-id="fe2aa-225">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-225">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-226">在“**文件**”菜单上，单击“**添加/删除管理单元**”，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-226">On the **File** menu, click **Add/Remove Snap-in**, and then choose **Add**.</span></span>
    
<span data-ttu-id="fe2aa-227">&nbsp;&nbsp;&nbsp;c。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-227">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="fe2aa-228">在“**添加或删除管理单元**”框中，单击“**证书**”，然后单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-228">In the **Add or Remove Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
    
<span data-ttu-id="fe2aa-229">&nbsp;&nbsp;&nbsp;d。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-229">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="fe2aa-230">在“**证书管理单元**”对话框中，单击“**计算机帐户**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-230">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-231">&nbsp;&nbsp;&nbsp;e。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-231">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="fe2aa-232">在“**选择计算机**”对话框中，确保选中“**本地计算机: (运行此控制台的计算机)**”复选框，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-232">In the **Select Computer** dialog box, ensure that the **Local Computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
    
<span data-ttu-id="fe2aa-233">&nbsp;&nbsp;&nbsp;f。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-233">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="fe2aa-234">单击“**关闭**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-234">Click **Close**, and then **OK**.</span></span>
    
<span data-ttu-id="fe2aa-235">&nbsp;&nbsp;&nbsp;g。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-235">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="fe2aa-236">在控制台树中，展开“**证书(本地计算机)**”，右键单击“**受信任的根证书颁发机构**”，转到“**所有任务**”，然后单击“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-236">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, go to **All Tasks**, and then click **Import**.</span></span>
    
<span data-ttu-id="fe2aa-237">&nbsp;&nbsp;&nbsp;h。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-237">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="fe2aa-238">在出现的向导中，在“**要导入的文件**”文本框中，指定证书的文件名（在上一节中你赋予 .p7b 文件的名称）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-238">In the wizard that appears, in the **File to Import** textbox, specify the file name of the certificate (the name you gave the .p7b file in the previous section).</span></span> <span data-ttu-id="fe2aa-239">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-239">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-240">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-240">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="fe2aa-241">应选中“**将所有的证书放入下列存储，作为受信任的根证书颁发机构**”单选按钮。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-241">Leave the radio button on **Place all certificates in the following store, as Trusted Root Certification Authorities** should be selected.</span></span> <span data-ttu-id="fe2aa-242">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-242">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-243">&nbsp;&nbsp;&nbsp;j。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-243">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="fe2aa-244">查看摘要，然后单击“**完成**”以完成导入。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-244">Review the summary, and click **Finish** to complete the import.</span></span>
    
<span data-ttu-id="fe2aa-245">&nbsp;&nbsp;&nbsp;k。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-245">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="fe2aa-246">这需要完成的您正在部署的每台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-246">This will need to be done for every Edge Server you're deploying.</span></span>
    
### <a name="3-create-the-certificate-request"></a><span data-ttu-id="fe2aa-247">3.创建证书请求</span><span class="sxs-lookup"><span data-stu-id="fe2aa-247">3. Create the certificate request</span></span>

<span data-ttu-id="fe2aa-248">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-248">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="fe2aa-249">登录到其中一台边缘服务器上，启动部署向导中，并在**步骤 3： 请求、 安装或分配证书**，单击**运行**（或**再次运行**，如果您已运行此向导）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-249">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates**, click **Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="fe2aa-250">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-250">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-251">在“**证书请求**”页上，确保“**内部边缘证书**”已选中，然后单击“**请求**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-251">On the **Certificate Request** page, ensure **Internal Edge Certificate** is selected, and click **Request**.</span></span>
    
<span data-ttu-id="fe2aa-252">&nbsp;&nbsp;&nbsp;c。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-252">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="fe2aa-253">在**延迟请求或即时请求**页上，选择**发送给联机证书颁发机构立即请求**如果您从边缘环境或**现在，准备请求，但稍后发送**否则为之一可以访问。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-253">On the **Delayed or Immediate Requests** page, choose **Send the request immediately to an online certification authority** if you have access to one from your Edge environment, or **Prepare the request now, but send it later** otherwise.</span></span>
    
<span data-ttu-id="fe2aa-254">&nbsp;&nbsp;&nbsp;d。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-254">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="fe2aa-255">在“**证书请求文件**”页上，输入将保存该文件的完整路径和文件名（例如，c:\SkypeInternalEdgeCert.cer）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-255">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="fe2aa-256">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-256">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-257">&nbsp;&nbsp;&nbsp;e。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-257">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="fe2aa-258">在“**指定替代证书模板**”页上，要使用除默认 WebServer 模板之外的其他模板，请选中“**使用选定证书颁发机构的备用证书模板**”复选框。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-258">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span> <span data-ttu-id="fe2aa-259">否则，什么也不做。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-259">Otherwise, do nothing.</span></span>
    
<span data-ttu-id="fe2aa-260">&nbsp;&nbsp;&nbsp;f。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-260">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="fe2aa-261">在“名称和安全设置”页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-261">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="fe2aa-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="fe2aa-263">在“**友好名称**”中，输入证书的显示名称（例如，内部边缘）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-263">In **Friendly name**, enter a display name for the certificate (such as Internal Edge).</span></span>
    
 <span data-ttu-id="fe2aa-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="fe2aa-265">在“**位长度**”中，选择位长度（默认为 2048，设得越长越安全，但是会降低性能）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-265">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="fe2aa-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="fe2aa-267">如果需要可导出的证书，必须选中“**将证书私钥标记为可导出**”复选框。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-267">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
 <span data-ttu-id="fe2aa-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv.</span></span> <span data-ttu-id="fe2aa-269">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-269">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-270">&nbsp;&nbsp;&nbsp;g。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-270">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="fe2aa-271">在“**组织信息**”页上，输入组织和组织单位 (OU) 的名称。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-271">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="fe2aa-272">可以输入分部或部门（如 IT）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-272">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="fe2aa-273">&nbsp;&nbsp;&nbsp;h。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-273">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="fe2aa-274">在“**地理信息**”页上，输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-274">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="fe2aa-275">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-275">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="fe2aa-276">在“**使用者名称/使用者替代名称**”页上，这应该由向导自动填充。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-276">On the **Subject Name/Subject Alternate Names** page, this should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="fe2aa-277">&nbsp;&nbsp;&nbsp;j。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-277">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="fe2aa-278">在“**配置其他使用者替代名称**”页上，需要添加所需的任何其他使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-278">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="fe2aa-279">&nbsp;&nbsp;&nbsp;k。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-279">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="fe2aa-280">在**请求摘要**页中，查找要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-280">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="fe2aa-281">如果需要进行更改，现在就返回并执行更改。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-281">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="fe2aa-282">&nbsp;&nbsp;&nbsp;l。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-282">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="fe2aa-283">然后单击**下一步**生成您需要向 CA （您可以单击**查看日志**，以查看证书请求的日志） 提供 CSR 文件。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-283">Then click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="fe2aa-284">&nbsp;&nbsp;&nbsp;m。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-284">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="fe2aa-285">生成请求后，可以单击“**查看**”来查看证书，然后单击“**完成**”关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-285">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="fe2aa-286">CSR 文件的内容需要提供给 CA，这样他们才能生成证书，让你在下一节将其导入此计算机。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-286">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    

### <a name="4-import-the-certificate"></a><span data-ttu-id="fe2aa-287">4.导入证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-287">4. Import the certificate</span></span>

<span data-ttu-id="fe2aa-288">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-288">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="fe2aa-289">登录，以本地 Administrators 组的成员身份，到边缘服务器中所做您的证书请求从最后一个过程。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-289">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="fe2aa-290">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-290">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-291">在部署向导旁边**步骤 3。请求、 安装或分配证书**，**再次运行**单击。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-291">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="fe2aa-292">&nbsp;&nbsp;&nbsp;c。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-292">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="fe2aa-293">在“**可用的证书任务**”页上，单击“**从 .P7b、.pfx 或 .cer 文件导入证书**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-293">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="fe2aa-294">&nbsp;&nbsp;&nbsp;d。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-294">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="fe2aa-295">在“**导入证书**”页上，键入上一节中获得的证书的完整路径和文件名（也可单击“**浏览**”查找并选择该文件）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-295">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span>
    
<span data-ttu-id="fe2aa-296">&nbsp;&nbsp;&nbsp;e。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-296">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="fe2aa-297">如果您的证书包含私钥的其他成员的边缘池，正在导入的证书，请务必选择 **，其中包含证书的私钥的证书文件**复选框，并指定密码。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-297">If you're importing certificates for other members of your Edge pool, and your certificate contains a private key, be sure to select the **Certificate file that contains certificate's private key** check box, and specify the password.</span></span> <span data-ttu-id="fe2aa-298">单击“**下一步**”继续。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-298">Click **Next** to continue.</span></span>
    
<span data-ttu-id="fe2aa-299">&nbsp;&nbsp;&nbsp;f。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-299">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="fe2aa-300">在**摘要**页上，单击**下一步**，一旦成功导入证书后，您已确认信息和**完成**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-300">On the**Summary** page, click **Next** once you've confirmed the information, and **Finish** once the certificate is successfully imported.</span></span>
    
 
### <a name="5-export-the-certificate"></a><span data-ttu-id="fe2aa-301">5.导出证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-301">5. Export the certificate</span></span>

<span data-ttu-id="fe2aa-302">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-302">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="fe2aa-303">请确保您已登录到边缘服务器导入证书之前，以本地 Administrators 组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-303">Make sure you've logged onto the Edge Server you imported the certificate to previously, as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="fe2aa-304">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-304">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-305">单击**启动\*\*\*\*运行**（或打开**搜索**），然后键入**MMC**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-305">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="fe2aa-306">&nbsp;&nbsp;&nbsp;c。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-306">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="fe2aa-307">从 MMC 控制台中，单击“**文件**”，再单击“**添加/删除管理单元**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-307">From the MMC console, click **File**, and click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="fe2aa-308">&nbsp;&nbsp;&nbsp;d。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-308">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="fe2aa-309">从“**添加或删除管理单元**”框中，单击“**证书**”，再单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-309">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="fe2aa-310">&nbsp;&nbsp;&nbsp;e。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-310">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="fe2aa-311">在“**证书**”管理单元对话框中，选择“**计算机帐户**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-311">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="fe2aa-312">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-312">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-313">&nbsp;&nbsp;&nbsp;f。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-313">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="fe2aa-314">在“**选择计算机**”对话框中，选择“**本地计算机: (运行此控制台的计算机)**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-314">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="fe2aa-315">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-315">Click **Finish**.</span></span> <span data-ttu-id="fe2aa-316">单击“**确定**”，MMC 控制台的配置即告完成。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-316">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="fe2aa-317">&nbsp;&nbsp;&nbsp;g。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-317">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="fe2aa-318">双击“**证书(本地计算机)**”展开证书存储。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-318">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="fe2aa-319">双击“**个人**”，然后单击“**证书**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-319">Double-click **Personal**, and then click **Certificates**.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="fe2aa-320">您可能在这里，并且您看不到中证书个人存储的本地计算机任何证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-320">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="fe2aa-321">您不需要智能寻线周围，如果该密钥的不存在，导入证书没有与其关联的私钥。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-321">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="fe2aa-322">重试请求并导入一个更多时间，上述步骤和如果您确保您获取的右侧，与您的 CA 管理员或提供程序。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-322">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="fe2aa-323">&nbsp;&nbsp;&nbsp;h。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-323">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="fe2aa-324">在**个人证书存储**的本地计算机，请右键单击要从中导出的证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-324">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="fe2aa-325">从得到的菜单中选择“**所有任务**”，然后单击“**导出**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-325">Select **All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="fe2aa-326">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-326">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="fe2aa-327">在“**证书导出向导**”中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-327">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="fe2aa-328">选择“**是，导出私钥**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-328">Select **Yes, export the private key**.</span></span> <span data-ttu-id="fe2aa-329">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-329">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-330">&nbsp;&nbsp;&nbsp;j。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-330">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="fe2aa-331">在“**导出文件格式**”对话框中，选择“**个人信息交换 - PKCS#12 (.PFX)**”，然后选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-331">On the **Export File Formats** dialog, select **Personal Information Exchange - PKCS#12 (.PFX)**, and then select the following:</span></span>
    
<span data-ttu-id="fe2aa-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="fe2aa-333">如果可能，则数据包括证书路径中的所有证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-333">Include all certificates in the certification path, if possible.</span></span>
    
<span data-ttu-id="fe2aa-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii.</span></span> <span data-ttu-id="fe2aa-335">导出所有扩展属性。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-335">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="fe2aa-336">**切勿**选择“**如果导出成功，删除私钥**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-336">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="fe2aa-337">它将意味着您必须重新导入的证书和私钥返回到此边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-337">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="fe2aa-338">&nbsp;&nbsp;&nbsp;k。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-338">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="fe2aa-339">如果要分配密码来保护私钥，可以键入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-339">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="fe2aa-340">重新输入该密码进行确认，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-340">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-341">&nbsp;&nbsp;&nbsp;l。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-341">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="fe2aa-342">为导出的证书键入路径和文件名，并使用文件扩展名 **.pfx**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-342">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="fe2aa-343">路径也需要可由其他边缘服务器池中，或您需要将文件移动通过外部介质 （如 USB 驱动器）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-343">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="fe2aa-344">所做的选择时，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-344">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="fe2aa-345">&nbsp;&nbsp;&nbsp;m。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-345">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="fe2aa-346">查看“**正在完成证书导出向导**”对话框中的摘要，然后。单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-346">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="fe2aa-347">&nbsp;&nbsp;&nbsp;n。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-347">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="fe2aa-348">在成功导出对话框中单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-348">Click **OK** in the successful export dialog.</span></span>
    
 
### <a name="6-assign-the-certificate"></a><span data-ttu-id="fe2aa-349">6.分配证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-349">6. Assign the certificate</span></span>

<span data-ttu-id="fe2aa-350">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-350">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="fe2aa-351">对于每个边缘服务器，在部署向导中，旁边**步骤 3。请求、 安装或分配证书**，单击**再次运行**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-351">On EACH Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="fe2aa-352">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-352">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-353">在“**可用的证书任务**”页上，单击“**分配现有证书**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-353">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="fe2aa-354">&nbsp;&nbsp;&nbsp;c。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-354">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="fe2aa-355">在“**证书分配**”页上，选择列表中的“**边缘内部**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-355">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>
    
<span data-ttu-id="fe2aa-356">&nbsp;&nbsp;&nbsp;d。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-356">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="fe2aa-357">在**证书存储**页上，选择已为 （的上一节） 的内部边缘导入的证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-357">On the **Certificate Store** page, select the certificate you've imported for the internal Edge (from the previous section).</span></span>
    
<span data-ttu-id="fe2aa-358">&nbsp;&nbsp;&nbsp;e。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-358">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="fe2aa-359">在“**证书分配摘要**”页上，检查设置，然后单击“**下一步**”分配证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-359">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="fe2aa-360">&nbsp;&nbsp;&nbsp;f。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-360">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="fe2aa-361">在向导完成页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-361">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="fe2aa-362">&nbsp;&nbsp;&nbsp;g。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-362">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="fe2aa-363">完成此过程后，它是非常好的方法，以打开证书 MMC 管理单元中每台边缘服务器上，展开**证书 （本地计算机）**、 展开**个人**，单击**证书**，确认在内部边缘证书的详细信息窗格中列出。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-363">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each Edge Server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
### <a name="external-edge-interface-certificates"></a><span data-ttu-id="fe2aa-364">外部边缘接口证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-364">External Edge interface certificates</span></span>

 
### <a name="1-create-the-certificate-request"></a><span data-ttu-id="fe2aa-365">1.创建证书请求</span><span class="sxs-lookup"><span data-stu-id="fe2aa-365">1. Create the certificate request</span></span>

<span data-ttu-id="fe2aa-366">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-366">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="fe2aa-367">登录到其中一台边缘服务器上，启动部署向导中，并在**步骤 3： 请求、 安装或分配证书，单击运行**（或**再次运行**，如果您已运行此向导）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-367">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates, click Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="fe2aa-368">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-368">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-369">在“**可用的证书任务**”页上，单击“**创建新的证书请求**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-369">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>
    
<span data-ttu-id="fe2aa-370">&nbsp;&nbsp;&nbsp;c。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-370">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="fe2aa-371">在“**证书请求**”页上，确保“**外部边缘证书**”已选中，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-371">On the **Certificate Request** page, ensure **External Edge Certificate** is selected, and click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-372">&nbsp;&nbsp;&nbsp;d。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-372">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="fe2aa-373">在“**延迟的请求或即时请求**”页上，单击“**现在准备请求，但稍后发送**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-373">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>
    
<span data-ttu-id="fe2aa-374">&nbsp;&nbsp;&nbsp;e。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-374">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="fe2aa-375">在“**证书请求文件**”页上，输入将保存该文件的完整路径和文件名（例如，c:\SkypeInternalEdgeCert.cer）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-375">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="fe2aa-376">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-376">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-377">&nbsp;&nbsp;&nbsp;f。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-377">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="fe2aa-378">在“**指定替代证书模板**”页上，要使用除默认 WebServer 模板之外的模板，请选中“**使用选定证书颁发机构的备用证书模板**”复选框。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-378">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>
    
<span data-ttu-id="fe2aa-379">&nbsp;&nbsp;&nbsp;g。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-379">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="fe2aa-380">在“名称和安全设置”页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-380">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="fe2aa-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="fe2aa-382">在“**友好名称**”中，键入证书的显示名称（例如，外部边缘）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-382">In **Friendly name**, enter a display name for the certificate (such as External Edge).</span></span>
    
 <span data-ttu-id="fe2aa-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="fe2aa-384">在“**位长度**”中，选择位长度（默认为 2048，设得越长越安全，但是会降低性能）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-384">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="fe2aa-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="fe2aa-386">如果需要可导出的证书，必须选中“**将证书私钥标记为可导出**”复选框。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-386">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
  <span data-ttu-id="fe2aa-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv.</span></span> <span data-ttu-id="fe2aa-388">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-388">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-389">&nbsp;&nbsp;&nbsp;h。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-389">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="fe2aa-390">在“**组织信息**”页上，输入组织和组织单位 (OU) 的名称。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-390">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="fe2aa-391">可以输入分部或部门（如 IT）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-391">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="fe2aa-392">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-392">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="fe2aa-393">在“**地理信息**”页上，输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-393">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="fe2aa-394">&nbsp;&nbsp;&nbsp;j。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-394">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="fe2aa-395">在“**使用者名称/使用者替代名称**”页上，所需的信息由向导自动填充。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-395">On the **Subject Name/Subject Alternate Names** page, the needed information should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="fe2aa-396">&nbsp;&nbsp;&nbsp;k。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-396">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="fe2aa-397">在**使用者替代名称 (San) 上的 SIP 域设置**页上，检查域复选框添加对 sip。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="fe2aa-397">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, check the domain checkbox to add a sip.<sipdomain></span></span> <span data-ttu-id="fe2aa-398">向使用者替代名称列表的条目。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-398">entry to the subject alternative names list.</span></span>
    
<span data-ttu-id="fe2aa-399">&nbsp;&nbsp;&nbsp;l。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-399">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="fe2aa-400">在“**配置其他使用者替代名称**”页上，需要添加所需的任何其他使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-400">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="fe2aa-401">&nbsp;&nbsp;&nbsp;m。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-401">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="fe2aa-402">在**请求摘要**页中，查找要用于生成请求的证书信息。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-402">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="fe2aa-403">如果需要进行更改，现在就返回并执行更改。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-403">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="fe2aa-404">&nbsp;&nbsp;&nbsp;n。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-404">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="fe2aa-405">准备好之后，单击**下一步**生成您需要向 CA （您可以单击**查看日志**，以查看证书请求的日志） 提供 CSR 文件。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-405">When you're ready, click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="fe2aa-406">&nbsp;&nbsp;&nbsp;o。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-406">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="fe2aa-407">生成请求后，可以单击“**查看**”来查看证书，然后单击“**完成**”关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-407">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="fe2aa-408">CSR 文件的内容需要提供给 CA，这样他们才能生成证书，让你在下一节将其导入此计算机。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-408">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    
<span data-ttu-id="fe2aa-409">&nbsp;&nbsp;&nbsp;p。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-409">&nbsp;&nbsp;&nbsp;p.</span></span> <span data-ttu-id="fe2aa-410">（可选）在提交 CSR 的内容后，可能需要你提供某些信息，具体如下（CA 之间差异很大，所有这可能不是必需的）：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-410">(OPTIONAL) You may, when submitting the contents of the CSR, be asked for certain information, as follows (CAs vary greatly, so this may not be required):</span></span>
    
  - <span data-ttu-id="fe2aa-411">**Microsoft** 作为服务器平台</span><span class="sxs-lookup"><span data-stu-id="fe2aa-411">**Microsoft** as the server platform</span></span>
    
  - <span data-ttu-id="fe2aa-412">**IIS** 作为版本</span><span class="sxs-lookup"><span data-stu-id="fe2aa-412">**IIS** as the version</span></span>
    
  - <span data-ttu-id="fe2aa-413">**Web Server** 作为使用类型</span><span class="sxs-lookup"><span data-stu-id="fe2aa-413">**Web Server** as the usage type</span></span>
    
  - <span data-ttu-id="fe2aa-414">**PKCS7** 作为响应格式</span><span class="sxs-lookup"><span data-stu-id="fe2aa-414">**PKCS7** as the response format</span></span>
    
 
### <a name="2-import-the-certificate"></a><span data-ttu-id="fe2aa-415">2.导入证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-415">2. Import the certificate</span></span>

<span data-ttu-id="fe2aa-416">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-416">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="fe2aa-417">登录，以本地 Administrators 组的成员身份，到边缘服务器中所做您的证书请求从最后一个过程。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-417">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="fe2aa-418">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-418">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-419">在部署向导旁边**步骤 3。请求、 安装或分配证书**，**再次运行**单击。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-419">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="fe2aa-420">&nbsp;&nbsp;&nbsp;c。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-420">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="fe2aa-421">在“**可用的证书任务**”页上，单击“**从 .P7b、.pfx 或 .cer 文件导入证书**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-421">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="fe2aa-422">&nbsp;&nbsp;&nbsp;d。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-422">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="fe2aa-423">在“**导入证书**”页上，键入上一节中获得的证书的完整路径和文件名（也可单击“**浏览**”查找并选择该文件）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-423">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span> <span data-ttu-id="fe2aa-424">如果您的证书包含私钥，请确保选择**证书文件包含证书的私钥**，并输入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-424">If your certificate contains a private key, make sure to select **Certificate file contains certificate's private key**, and enter the password for the private key.</span></span> <span data-ttu-id="fe2aa-425">完成后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-425">Click **Next** when ready.</span></span>
    
<span data-ttu-id="fe2aa-426">&nbsp;&nbsp;&nbsp;e。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-426">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="fe2aa-427">在“**导入证书摘要**”页上，查看摘要信息，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-427">On the **Import Certificate Summary** page, review the summary information, and click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-428">&nbsp;&nbsp;&nbsp;f。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-428">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="fe2aa-429">在**正在执行命令**页上，您可以查看结果的导入完成后，单击**查看日志**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-429">On the **Executing Commands** page, you can review the result of the import when it's complete by clicking **View Log**.</span></span> <span data-ttu-id="fe2aa-430">单击“**完成**”完成证书导入。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-430">Click **Finish** to complete the certificate import.</span></span>
    
<span data-ttu-id="fe2aa-431">&nbsp;&nbsp;&nbsp;g。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-431">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="fe2aa-432">如果您有其他边缘服务器池中，需要按照下面的两个步骤。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-432">If you have other Edge Servers in a pool, you'll need to follow the next two procedures as well.</span></span> <span data-ttu-id="fe2aa-433">如果这是独立的边缘服务器，完成外部证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-433">If this is a standalone Edge Server, you're done with external certificates.</span></span>
    
 
### <a name="3-export-the-certificate"></a><span data-ttu-id="fe2aa-434">3.导出证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-434">3. Export the certificate</span></span>

<span data-ttu-id="fe2aa-435">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-435">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="fe2aa-436">请确保您已登录到边缘服务器导入证书作为本地管理员。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-436">Make sure you've logged onto the Edge Server you imported the certificate to as a local Administrator.</span></span>
    
<span data-ttu-id="fe2aa-437">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-437">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-438">单击**启动\*\*\*\*运行**（或打开**搜索**），然后键入**MMC**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-438">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="fe2aa-439">&nbsp;&nbsp;&nbsp;c。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-439">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="fe2aa-440">从 MMC 控制台中，单击“**文件**”，然后单击“**添加/删除管理单元**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-440">From the MMC console, click **File**, and then click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="fe2aa-441">&nbsp;&nbsp;&nbsp;d。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-441">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="fe2aa-442">从“**添加或删除管理单元**”框中，单击“**证书**”，再单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-442">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="fe2aa-443">&nbsp;&nbsp;&nbsp;e。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-443">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="fe2aa-444">在“**证书**”管理单元对话框中，选择“**计算机帐户**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-444">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="fe2aa-445">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-445">Click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-446">&nbsp;&nbsp;&nbsp;f。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-446">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="fe2aa-447">在“**选择计算机**”对话框中，选择“**本地计算机: (运行此控制台的计算机)**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-447">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="fe2aa-448">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-448">Click **Finish**.</span></span> <span data-ttu-id="fe2aa-449">单击“**确定**”，MMC 控制台的配置即告完成。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-449">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="fe2aa-450">&nbsp;&nbsp;&nbsp;g。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-450">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="fe2aa-451">双击“**证书(本地计算机)**”展开证书存储。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-451">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="fe2aa-452">双击“**个人**”，然后单击“**证书**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-452">**Double-click Personal**, and then click **Certificates**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="fe2aa-453">您可能在这里，并且您看不到中证书个人存储的本地计算机任何证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-453">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="fe2aa-454">您不需要智能寻线周围，如果该密钥的不存在，导入证书没有与其关联的私钥。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-454">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="fe2aa-455">重试请求并导入一个更多时间，上述步骤和如果您确保您获取的右侧，与您的 CA 管理员或提供程序。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-455">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="fe2aa-456">&nbsp;&nbsp;&nbsp;h。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-456">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="fe2aa-457">在**个人证书存储**的本地计算机，请右键单击要从中导出的证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-457">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="fe2aa-458">从得到的菜单中选择“**所有任务**”，然后单击“**导出**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-458">**Select All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="fe2aa-459">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-459">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="fe2aa-460">在“**证书导出向导**”中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-460">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="fe2aa-461">选择“**是，导出私钥**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-461">Select **Yes, export the private key**.</span></span> <span data-ttu-id="fe2aa-462">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-462">Click **Next**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="fe2aa-463">如果**是，导出私钥**不可用，则此证书的私钥未标记为导出之前你猜对。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-463">If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it.</span></span> <span data-ttu-id="fe2aa-464">你需要再次向提供商提出证书请求，要求将私钥设置为导出，然后导出才能成功。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-464">You need to request the certificate from the provider again, with the private key set to export, before doing this successfully.</span></span>
  
<span data-ttu-id="fe2aa-465">&nbsp;&nbsp;&nbsp;j。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-465">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="fe2aa-466">在“导出文件格式”对话框中，选择“个人信息交换 - PKCS#12 (.PFX)”，然后选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-466">On the Export File Formats dialog, select Personal Information Exchange - PKCS#12 (.PFX) and then select the following:</span></span>
    
 <span data-ttu-id="fe2aa-467">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-467">&nbsp;&nbsp;&nbsp;  i.</span></span> <span data-ttu-id="fe2aa-468">如果可能，则数据包括证书路径中的所有证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-468">Include all certificates in the certification path, if possible.</span></span>
    
 <span data-ttu-id="fe2aa-469">&nbsp;&nbsp;&nbsp;ii。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-469">&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="fe2aa-470">导出所有扩展属性。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-470">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="fe2aa-471">**切勿**选择“**如果导出成功，删除私钥**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-471">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="fe2aa-472">它将意味着您必须重新导入的证书和私钥返回到此边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-472">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="fe2aa-473">&nbsp;&nbsp;&nbsp;k。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-473">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="fe2aa-474">如果要分配密码来保护私钥，可以键入私钥的密码。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-474">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="fe2aa-475">重新输入该密码进行确认，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-475">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="fe2aa-476">&nbsp;&nbsp;&nbsp;l。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-476">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="fe2aa-477">为导出的证书键入路径和文件名，并使用文件扩展名 **.pfx**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-477">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="fe2aa-478">路径也需要可由其他边缘服务器池中，或您需要将文件移动通过外部介质 （如 USB 驱动器）。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-478">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="fe2aa-479">所做的选择时，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-479">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="fe2aa-480">&nbsp;&nbsp;&nbsp;m。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-480">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="fe2aa-481">查看“**正在完成证书导出向导**”对话框中的摘要，然后。单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-481">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="fe2aa-482">&nbsp;&nbsp;&nbsp;n。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-482">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="fe2aa-483">在成功导出对话框中单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-483">Click **OK** in the successful export dialog.</span></span>
    
<span data-ttu-id="fe2aa-484">&nbsp;&nbsp;&nbsp;o。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-484">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="fe2aa-485">您现在需要返回导入到此之前的证书部分并将证书导入到所有剩余边缘服务器，然后继续进行分配，下面。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-485">You'll now need to go back to the Import the certificate section prior to this and import the certificate to all your remaining Edge Servers, then proceed with assigning, below.</span></span>
    
 
### <a name="4-assign-the-certificate"></a><span data-ttu-id="fe2aa-486">4.分配证书</span><span class="sxs-lookup"><span data-stu-id="fe2aa-486">4. Assign the certificate</span></span>

<span data-ttu-id="fe2aa-487">&nbsp;&nbsp;&nbsp;一个。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-487">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="fe2aa-488">对于**每**边缘服务器，在部署向导中，旁边**步骤 3。请求、 安装或分配证书**，单击**再次运行**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-488">On **EACH** Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="fe2aa-489">&nbsp;&nbsp;&nbsp;b。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-489">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="fe2aa-490">在“**可用的证书任务**”页上，单击“**分配现有证书**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-490">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="fe2aa-491">&nbsp;&nbsp;&nbsp;c。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-491">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="fe2aa-492">在**证书分配**页中，选择列表中的**外部边缘**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-492">On the **Certificate Assignment** page, select **Edge External** in the list.</span></span>
    
<span data-ttu-id="fe2aa-493">&nbsp;&nbsp;&nbsp;d。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-493">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="fe2aa-494">在**证书存储**页上，选择您已导入 （的上一节） 的外部边缘的证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-494">On the **Certificate Store** page, select the certificate you've imported for the external Edge (from the previous section).</span></span>
    
<span data-ttu-id="fe2aa-495">&nbsp;&nbsp;&nbsp;e。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-495">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="fe2aa-496">在“**证书分配摘要**”页上，检查设置，然后单击“**下一步**”分配证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-496">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="fe2aa-497">&nbsp;&nbsp;&nbsp;f。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-497">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="fe2aa-498">在向导完成页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-498">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="fe2aa-499">&nbsp;&nbsp;&nbsp;g。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-499">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="fe2aa-500">完成此过程后，它是非常好的方法，以打开证书 MMC 管理单元中每台服务器上，展开**证书 （本地计算机）**、 展开**个人**，单击**证书**，确认在内部边缘证书的详细信息窗格中列出。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-500">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="fe2aa-501">你还需要设置反向代理服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-501">You will also have needed to set up the certificates for your reverse proxy server.</span></span> 
  
## <a name="starting-the-edge-servers"></a><span data-ttu-id="fe2aa-502">启动边缘服务器</span><span class="sxs-lookup"><span data-stu-id="fe2aa-502">Starting the Edge Servers</span></span>

<span data-ttu-id="fe2aa-503">安装完成后，您将需要在部署中每台边缘服务器上启动服务：</span><span class="sxs-lookup"><span data-stu-id="fe2aa-503">Once the setup is complete, you'll need to start the services on each Edge server in your deployment:</span></span>
  
1. <span data-ttu-id="fe2aa-504">每台边缘服务器，在**部署向导**中，单击**步骤 4： 启动服务**，单击**运行**。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-504">On each Edge Server, in the **Deployment Wizard**, next to **Step 4: Start Services**, click **Run**.</span></span>
    
2. <span data-ttu-id="fe2aa-505">在**业务服务器服务启动 Skype**页上，检查服务列表，然后单击**下一步**以启动服务。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-505">On the **Start Skype for Business Server Services** page, review the list of services, and then click **Next** to start the services.</span></span>
    
3. <span data-ttu-id="fe2aa-506">启动服务后，可以单击“**完成**”关闭向导。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-506">After the services are started, you can click **Finish** to close the wizard.</span></span>
    
4. <span data-ttu-id="fe2aa-507">（可选）仍然在“**步骤 4: 启动服务**”下，单击“**服务状态**”。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-507">(Optional) Still under **Step 4: Start Services**, click **Services Status**.</span></span>
    
5.  <span data-ttu-id="fe2aa-508">在**服务 MMC**每台服务器上，确认 Business Server 服务的所有 Skype 都在都运行。</span><span class="sxs-lookup"><span data-stu-id="fe2aa-508">In the **Services MMC** on each server, verify that all the Skype for Business Server services are running.</span></span>
    

