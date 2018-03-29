---
title: 为 Skype for Business Server 2015 部署统计信息管理器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要： 阅读本主题，以了解如何部署为 Skype 业务服务器 2015年统计数据管理器。
ms.openlocfilehash: 7730a6b933bbe1d627bffe175a24a60273be3a88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="48768-103">为 Skype for Business Server 2015 部署统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="48768-103">Deploy Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="48768-104">**摘要：**阅读本主题，以了解如何部署为 Skype 业务服务器 2015年统计数据管理器。</span><span class="sxs-lookup"><span data-stu-id="48768-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="48768-105">Skype 业务服务器的统计信息管理器是一个强大的工具，允许您查看 Skype 实时业务服务器运行状况和性能数据。</span><span class="sxs-lookup"><span data-stu-id="48768-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="48768-106">可以跨数百个服务器每隔几秒钟轮询性能数据和统计数据管理器网站上可立即查看结果。</span><span class="sxs-lookup"><span data-stu-id="48768-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="48768-107">您尝试安装统计管理器之前，请确保您熟悉的软件、 网络和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="48768-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="48768-108">有关详细信息，请参阅[规划的业务服务器 2015年的 Skype 统计信息经理](plan.md)。</span><span class="sxs-lookup"><span data-stu-id="48768-108">For more information, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="48768-109">如果您要从以前的版本的统计数据管理器升级，请参阅[升级业务服务器 2015年的 Skype 统计管理](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="48768-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48768-110">统计信息管理器网站已经过测试，可以在 Internet Explorer 11+、Edge 20.10240+ 和 Chrome 46+（当前 Evergreen 版本）上正确运行。</span><span class="sxs-lookup"><span data-stu-id="48768-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="48768-111">您可以找到统计管理器即可下载[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)。</span><span class="sxs-lookup"><span data-stu-id="48768-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="48768-112">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="48768-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="48768-113">部署统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="48768-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="48768-114">对你的部署进行故障排除</span><span class="sxs-lookup"><span data-stu-id="48768-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="48768-115">创建自签名证书</span><span class="sxs-lookup"><span data-stu-id="48768-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="48768-116">部署统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="48768-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="48768-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="48768-117"></span></span>

<span data-ttu-id="48768-118">若要部署统计信息管理器，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="48768-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="48768-119">通过安装 Redis 内存中缓存系统，并确保你已安装合适的证书，准备侦听器主机。</span><span class="sxs-lookup"><span data-stu-id="48768-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="48768-120">在主机上安装侦听器服务。</span><span class="sxs-lookup"><span data-stu-id="48768-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="48768-121">在主机上安装网站。</span><span class="sxs-lookup"><span data-stu-id="48768-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="48768-122">在每个 Skype 为想要监视的业务服务器计算机上安装代理。</span><span class="sxs-lookup"><span data-stu-id="48768-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="48768-123">为你监视的服务器导入拓扑。</span><span class="sxs-lookup"><span data-stu-id="48768-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="48768-124">Redis、侦听器服务和网站必须安装在同一台主机上。</span><span class="sxs-lookup"><span data-stu-id="48768-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="48768-125">请确保主机安装业务服务器没有 Skype。</span><span class="sxs-lookup"><span data-stu-id="48768-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="48768-126">准备侦听器主机。</span><span class="sxs-lookup"><span data-stu-id="48768-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="48768-127">要准备主机，你将需要安装 Redis 内存中缓存系统，并确保该计算机上存在有效证书。</span><span class="sxs-lookup"><span data-stu-id="48768-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="48768-128">Microsoft 建议安装稳定的最新 Redis 3.0 内部版本。</span><span class="sxs-lookup"><span data-stu-id="48768-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="48768-129">统计管理器版本 1.1 的经 Redis 3.0.501，Redis 2.8.2400。</span><span class="sxs-lookup"><span data-stu-id="48768-129">Statistics Manager version 1.1 was tested with Redis 3.0.501 and Redis 2.8.2400.</span></span> 
  
1. <span data-ttu-id="48768-130">从以下站点下载 Redis: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)。</span><span class="sxs-lookup"><span data-stu-id="48768-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="48768-131">可以从下载未签名的安装程序[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="48768-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="48768-132">如有必要，已签名的二进制文件都可以通过常用的包管理器： [Nuget](https://www.nuget.org/packages/Redis-64/)和[Choclatey](https://chocolatey.org/packages/redis-64)。</span><span class="sxs-lookup"><span data-stu-id="48768-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="48768-133">运行提供的 msi 并按照提示操作。</span><span class="sxs-lookup"><span data-stu-id="48768-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="48768-134">请勿选中用于添加防火墙规则的复选框。</span><span class="sxs-lookup"><span data-stu-id="48768-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="48768-135">侦听器服务要求有证书。</span><span class="sxs-lookup"><span data-stu-id="48768-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="48768-136">Microsoft 强烈建议必须由受信任的证书颁发机构签名的证书。</span><span class="sxs-lookup"><span data-stu-id="48768-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="48768-137">如果你要使用自签名证书（例如，用于在实验室中进行测试），请参阅[创建自签名证书](deploy.md#BKMK_SelfCert)。</span><span class="sxs-lookup"><span data-stu-id="48768-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="48768-p106">请注意，代理使用证书指纹验证（而不是链验证）。由于可能使用自签名证书，因此它不会执行完整证书验证。</span><span class="sxs-lookup"><span data-stu-id="48768-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="48768-140">安装侦听器服务</span><span class="sxs-lookup"><span data-stu-id="48768-140">Install the Listener service</span></span>

<span data-ttu-id="48768-141">通过运行 StatsManPerfAgentListener.msi，并指定以下主机上安装侦听器服务：</span><span class="sxs-lookup"><span data-stu-id="48768-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="48768-142">阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="48768-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="48768-143">在下一页上，指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="48768-143">On the next page, specify the following information:</span></span>
    
    - <span data-ttu-id="48768-144">**服务密码：**这是远程代理将用于向侦听服务进行身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="48768-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
    - <span data-ttu-id="48768-145">**服务端口：**这是该侦听器将使用与代理进行通信的 HTTPS 端口号。</span><span class="sxs-lookup"><span data-stu-id="48768-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="48768-146">在安装期间，此端口将允许本地防火墙，通过 URL ACL 将被创建，并将此端口绑定 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="48768-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="48768-147">默认值为 8443。</span><span class="sxs-lookup"><span data-stu-id="48768-147">The default is 8443.</span></span>
    
    - <span data-ttu-id="48768-148">**证书指纹：**这是监听器将使用加密的 HTTPS 协议的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="48768-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="48768-149">网络服务必须具有读取访问权限的专用密钥。</span><span class="sxs-lookup"><span data-stu-id="48768-149">Network Service must have read access to the private key.</span></span>
    
    <span data-ttu-id="48768-150">单击“**选择...**”按钮选择指纹。</span><span class="sxs-lookup"><span data-stu-id="48768-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
    <span data-ttu-id="48768-151">可以通过使用证书管理器或通过使用以下 PowerShell 命令来查找证书指纹：</span><span class="sxs-lookup"><span data-stu-id="48768-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
  ```
  Get-ChildItem -path cert:\LocalMachine\My
  ```

   - <span data-ttu-id="48768-152">**安装目录：**这是将在其安装二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="48768-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="48768-153">可以更改该默认值使用**浏览...**按钮。</span><span class="sxs-lookup"><span data-stu-id="48768-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="48768-154">**应用程序数据目录：**这是存储日志文件夹和其他数据的目录。</span><span class="sxs-lookup"><span data-stu-id="48768-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="48768-155">您可以更改其默认值。</span><span class="sxs-lookup"><span data-stu-id="48768-155">You may change it from the default.</span></span> <span data-ttu-id="48768-156">它不会删除在卸载时。</span><span class="sxs-lookup"><span data-stu-id="48768-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="48768-157">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="48768-157">Click **Install**.</span></span>
    
<span data-ttu-id="48768-158">要验证安装，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="48768-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="48768-159">打开浏览器并定位到https://localhost:\<服务端口\>/healthcheck/</span><span class="sxs-lookup"><span data-stu-id="48768-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="48768-160">默认情况下，服务端口为 8443（除非你指定了其他端口）。</span><span class="sxs-lookup"><span data-stu-id="48768-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="48768-161">为了确保正确安装了侦听器，请查看以下内容：</span><span class="sxs-lookup"><span data-stu-id="48768-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="48768-162">如果运行状况检查页面显示，则表示已成功安装侦听器。</span><span class="sxs-lookup"><span data-stu-id="48768-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="48768-163">如果 KnownServersCount 为 1 或更高，则表示已建立与 Redis 的连接。</span><span class="sxs-lookup"><span data-stu-id="48768-163">If the KnownServersCount is 1 or higher, then the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="48768-164">等待几分钟，且至少安装了一个代理后，检查 ValuesWritten 计数器是否在递增。</span><span class="sxs-lookup"><span data-stu-id="48768-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="48768-165">安装网站</span><span class="sxs-lookup"><span data-stu-id="48768-165">Install the Website</span></span>

<span data-ttu-id="48768-166">通过运行 StatsManWebSite.msi，并指定以下安装在主机上的网站：</span><span class="sxs-lookup"><span data-stu-id="48768-166">Install the Website on the host machine by running the StatsManWebSite.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="48768-167">阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="48768-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="48768-168">在下一页上，指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="48768-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="48768-169">**服务端口：**这是 web 站点将侦听的端口号。</span><span class="sxs-lookup"><span data-stu-id="48768-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="48768-170">您可以使用 IIS 管理器绑定以后更改它。</span><span class="sxs-lookup"><span data-stu-id="48768-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="48768-171">在安装期间，将通过本地防火墙允许此端口。</span><span class="sxs-lookup"><span data-stu-id="48768-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="48768-172">**安装目录：**这是二进制文件的安装的目录。</span><span class="sxs-lookup"><span data-stu-id="48768-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="48768-173">可以更改该默认值使用**浏览...**按钮。</span><span class="sxs-lookup"><span data-stu-id="48768-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="48768-174">**应用程序数据目录：**这是存储日志文件夹和其他数据的目录。</span><span class="sxs-lookup"><span data-stu-id="48768-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="48768-175">您可以更改其默认值。</span><span class="sxs-lookup"><span data-stu-id="48768-175">You may change it from the default.</span></span> <span data-ttu-id="48768-176">它不会删除在卸载时。</span><span class="sxs-lookup"><span data-stu-id="48768-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="48768-177">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="48768-177">Click **Install**.</span></span>
    
<span data-ttu-id="48768-178">若要查看该网站，打开浏览器，然后定位到： http://localhost，webport\>/。</span><span class="sxs-lookup"><span data-stu-id="48768-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="48768-179">若要查看运行状况的信息、 打开浏览器，然后定位到： http://localhost: \<webport\>/运行状况检查 /。</span><span class="sxs-lookup"><span data-stu-id="48768-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="48768-180">默认情况下，Web 端口号为 8080。</span><span class="sxs-lookup"><span data-stu-id="48768-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="48768-181">你可以使用 IIS 管理器更改网站的端口绑定。</span><span class="sxs-lookup"><span data-stu-id="48768-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="48768-182">Web 安装程序会添加名为 StatsManWebSiteUsers 的本地安全组。</span><span class="sxs-lookup"><span data-stu-id="48768-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="48768-183">你可以向此安全组添加帐户以授予对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="48768-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="48768-184">安装代理</span><span class="sxs-lookup"><span data-stu-id="48768-184">Install the Agents</span></span>

<span data-ttu-id="48768-185">在每个 Skype 上安装代理，为您想要监视运行 StatsManPerfAgent.msi，并指定以下的业务服务器：</span><span class="sxs-lookup"><span data-stu-id="48768-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="48768-186">阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="48768-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="48768-187">在下一页上，指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="48768-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="48768-188">**服务密码：**这是远程代理将用于向侦听器服务进行身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="48768-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="48768-189">**服务 URI:**这是监听器所处的位置的 URI。</span><span class="sxs-lookup"><span data-stu-id="48768-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="48768-190">它应该使用https://name:port格式。</span><span class="sxs-lookup"><span data-stu-id="48768-190">It should use the https://name:port format.</span></span>
    
    <span data-ttu-id="48768-191">可以使用 NETBIOS 名称或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="48768-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="48768-192">您可以使用也被指定为**主题**或**主题备用名称**的侦听器服务，证书的名称，但这并不是必需。</span><span class="sxs-lookup"><span data-stu-id="48768-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="48768-193">**服务指纹：**这是使用监听器的 SSL 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="48768-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="48768-194">（由于可能使用自签名证书，因此它不会执行完整证书验证。</span><span class="sxs-lookup"><span data-stu-id="48768-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="48768-195">）</span><span class="sxs-lookup"><span data-stu-id="48768-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="48768-196">**安装目录：**这是将在其安装二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="48768-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="48768-197">可以更改该默认值使用**浏览...**按钮。</span><span class="sxs-lookup"><span data-stu-id="48768-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="48768-198">**应用程序数据目录：**这是存储日志文件夹和加密的 password.txt 文件的目录。</span><span class="sxs-lookup"><span data-stu-id="48768-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="48768-199">您可能会感谢您更改默认值。</span><span class="sxs-lookup"><span data-stu-id="48768-199">You may thanks change it from the default.</span></span> <span data-ttu-id="48768-200">它不会删除在卸载时。</span><span class="sxs-lookup"><span data-stu-id="48768-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="48768-201">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="48768-201">Click **Install**.</span></span>
    
<span data-ttu-id="48768-p121">如果你要在多台计算机上安装代理，你可能想以无人参与模式进行。例如：</span><span class="sxs-lookup"><span data-stu-id="48768-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="48768-204">导入拓扑</span><span class="sxs-lookup"><span data-stu-id="48768-204">Import the topology</span></span>
<span data-ttu-id="48768-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="48768-205"></span></span>

<span data-ttu-id="48768-206">因此统计管理器已安装并运行，您需要导入的业务服务器拓扑 Skype 之后该统计信息经理知道站点、 池和每个服务器的角色。</span><span class="sxs-lookup"><span data-stu-id="48768-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="48768-207">要导入的业务服务器拓扑结构您 Skype，您将使用[Get CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet 来检索有关您的组织中使用的每个池的信息，然后将此信息导入到统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="48768-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="48768-208">要导入的业务服务器拓扑 Skype，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="48768-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="48768-209">在主机上具有业务服务器 PowerShell cmdlet 的 Skype:</span><span class="sxs-lookup"><span data-stu-id="48768-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="48768-210">a.</span><span class="sxs-lookup"><span data-stu-id="48768-210">a.</span></span> <span data-ttu-id="48768-211">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="48768-211">Run the following command:</span></span> 
    
  ```
  Get-CsPool | Export-Clixml -Path mypoolinfo.xml
  ```
    <span data-ttu-id="48768-212">b.</span><span class="sxs-lookup"><span data-stu-id="48768-212">b.</span></span> <span data-ttu-id="48768-213">"Mypoolinfo.xml"文件复制到运行侦听器的服务器。</span><span class="sxs-lookup"><span data-stu-id="48768-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="48768-214">在运行侦听器的主机上：</span><span class="sxs-lookup"><span data-stu-id="48768-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="48768-215">a.</span><span class="sxs-lookup"><span data-stu-id="48768-215">a.</span></span> <span data-ttu-id="48768-216">运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="48768-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="48768-217">b.</span><span class="sxs-lookup"><span data-stu-id="48768-217">b.</span></span> <span data-ttu-id="48768-218">导航到安装侦听器的目录。</span><span class="sxs-lookup"><span data-stu-id="48768-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="48768-219">默认值为：</span><span class="sxs-lookup"><span data-stu-id="48768-219">The default is:</span></span> 
    
  ```
  cd C:\Program Files\Skype for Business Server StatsMan Listener
  ```

3. <span data-ttu-id="48768-220">要确认添加和更新哪些服务器，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="48768-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
  ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
  ```

<span data-ttu-id="48768-221">使用以下命令可以查看所有选项：</span><span class="sxs-lookup"><span data-stu-id="48768-221">The following command enables you to view all options:</span></span>
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="48768-222">要查看你当前导入的服务器信息，请运行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="48768-222">To see your your currently imported server information, run the following script:</span></span> 
  
```
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="48768-223">如果您想要监视服务器不属于您的业务服务器拓扑结构-Exchange Server，Skype 的-可以做运行侦听器的主机上的单个服务器导入。</span><span class="sxs-lookup"><span data-stu-id="48768-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="48768-224">要执行单服务器导入操作，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="48768-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="48768-225">导航到安装侦听器的目录。</span><span class="sxs-lookup"><span data-stu-id="48768-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="48768-226">默认值为：</span><span class="sxs-lookup"><span data-stu-id="48768-226">The default is:</span></span> 
    
  ```
  cd C:\Program Files\Skype for Business Server StatsMan Listener
  ```

2. <span data-ttu-id="48768-227">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="48768-227">Run the following command:</span></span>
    
  ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
  ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="48768-228">对你的部署进行故障排除</span><span class="sxs-lookup"><span data-stu-id="48768-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="48768-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="48768-229"></span></span>

<span data-ttu-id="48768-230">如果代理无法启动，请检查以下各项：</span><span class="sxs-lookup"><span data-stu-id="48768-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="48768-231">在统计信息管理器代理注册？</span><span class="sxs-lookup"><span data-stu-id="48768-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="48768-p129">	确保遵循导入拓扑的说明。请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)。  </span><span class="sxs-lookup"><span data-stu-id="48768-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="48768-234">如果代理位于拓扑中未列出的服务器上（例如，SQL AlwaysOn 群集内的节点），你将需要按照[导入拓扑](deploy.md#BKMK_ImportTopology)中的说明手动添加代理。</span><span class="sxs-lookup"><span data-stu-id="48768-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="48768-235">代理是否可以联系侦听器？</span><span class="sxs-lookup"><span data-stu-id="48768-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="48768-236">确保侦听器服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="48768-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="48768-237">如果侦听器服务未运行，请确保 Redis 正在运行，然后尝试重新启动侦听器。</span><span class="sxs-lookup"><span data-stu-id="48768-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="48768-238">请确保端口已打开侦听器服务，并代理计算机可以进行通信的端口。</span><span class="sxs-lookup"><span data-stu-id="48768-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="48768-239">为确保统计数据管理器正在收集数据，可以按如下所述检查 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="48768-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="48768-240">以下命令检索计数器存储名称：</span><span class="sxs-lookup"><span data-stu-id="48768-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="48768-241">下一个命令检索指定计数器的值：</span><span class="sxs-lookup"><span data-stu-id="48768-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="48768-242">您可能会看到在应用程序事件日志中的所有事件的信息，请参阅[有关业务服务器 2015年的 Skype 解决统计数据管理器](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="48768-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server 2015](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="48768-243">创建自签名证书</span><span class="sxs-lookup"><span data-stu-id="48768-243">Create a self-signed certificate</span></span>
<span data-ttu-id="48768-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="48768-244"></span></span>

<span data-ttu-id="48768-245">Microsoft 强烈建议你使用受信任的证书颁发机构签发的证书。</span><span class="sxs-lookup"><span data-stu-id="48768-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="48768-246">但是，如果你要使用自签名证书以进行测试，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="48768-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="48768-247">以管理员身份登录时，在 PowerShell 控制台中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="48768-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
  ```
  New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
  ```

2. <span data-ttu-id="48768-248">类型`certlm.msc`。</span><span class="sxs-lookup"><span data-stu-id="48768-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="48768-249">这将为本地计算机打开证书管理器。</span><span class="sxs-lookup"><span data-stu-id="48768-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="48768-250">导航到**个人**，然后再打开**证书**。</span><span class="sxs-lookup"><span data-stu-id="48768-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="48768-251">右键单击**StatsManListener-\>所有任务-\>管理私钥...**</span><span class="sxs-lookup"><span data-stu-id="48768-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="48768-252">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="48768-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="48768-253">在“**输入要选择的对象名称**”框中，键入以下内容：网络服务</span><span class="sxs-lookup"><span data-stu-id="48768-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="48768-254">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="48768-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="48768-p132">在“**完全控制**”下方，取消选中“**允许**”复选框。（只需要读取权限。）</span><span class="sxs-lookup"><span data-stu-id="48768-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="48768-257">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="48768-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="48768-258">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="48768-258">For more information</span></span>
<span data-ttu-id="48768-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="48768-259"></span></span>

<span data-ttu-id="48768-260">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="48768-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="48768-261">为业务服务器 2015年计划为 Skype 统计信息经理</span><span class="sxs-lookup"><span data-stu-id="48768-261">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="48768-262">为业务服务器 2015年升级为 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="48768-262">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>](upgrade.md)
    
- [<span data-ttu-id="48768-263">解决业务服务器 2015年的 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="48768-263">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="48768-264">Skype 业务服务器统计信息管理器日志</span><span class="sxs-lookup"><span data-stu-id="48768-264">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

