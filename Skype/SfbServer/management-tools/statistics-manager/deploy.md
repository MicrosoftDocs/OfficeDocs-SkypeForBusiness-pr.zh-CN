---
title: 部署 Skype for Business Server 的统计信息管理器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要：阅读本主题，了解如何为 Skype for Business Server 部署统计信息管理器。
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814812"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="11e78-103">部署 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="11e78-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="11e78-104">**摘要：** 阅读本主题，了解如何为 Skype for Business Server 部署统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="11e78-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="11e78-105">Skype for Business Server 统计信息管理器是一个强大的工具，允许你实时查看 Skype for Business Server 运行状况和性能数据。</span><span class="sxs-lookup"><span data-stu-id="11e78-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="11e78-106">您可以每隔几秒钟轮询数百台服务器的性能数据，并立即在统计信息管理器网站上查看结果。</span><span class="sxs-lookup"><span data-stu-id="11e78-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="11e78-107">在尝试安装统计信息管理器之前，请确保你熟悉软件、网络和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="11e78-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="11e78-108">有关详细信息，请参阅[Plan for Statistics Manager for Skype for Business Server。](plan.md)</span><span class="sxs-lookup"><span data-stu-id="11e78-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="11e78-109">如果要从早期版本的统计信息管理器升级，请参阅 Upgrade Statistics [Manager for Skype for Business Server。](upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="11e78-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="11e78-110">统计信息管理器网站已经过测试，在 Internet Explorer 11+、Edge 20.10240+ 和 Chrome 46+ (当前常青版本) 。</span><span class="sxs-lookup"><span data-stu-id="11e78-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="11e78-111">您可以在以下网站找到统计信息管理器：可下载 [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) 。</span><span class="sxs-lookup"><span data-stu-id="11e78-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="11e78-112">本主题包含以下各部分：</span><span class="sxs-lookup"><span data-stu-id="11e78-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="11e78-113">部署统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="11e78-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="11e78-114">部署疑难解答</span><span class="sxs-lookup"><span data-stu-id="11e78-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="11e78-115">创建自签名证书</span><span class="sxs-lookup"><span data-stu-id="11e78-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="11e78-116">部署统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="11e78-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="11e78-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="11e78-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="11e78-118">若要部署统计信息管理器，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="11e78-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="11e78-119">通过安装 Redis 内存中缓存系统以及确保已安装相应的证书来准备侦听器主机。</span><span class="sxs-lookup"><span data-stu-id="11e78-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="11e78-120">在主机上安装侦听器服务。</span><span class="sxs-lookup"><span data-stu-id="11e78-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="11e78-121">在主机上安装网站。</span><span class="sxs-lookup"><span data-stu-id="11e78-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="11e78-122">在你希望监视的每个 Skype for Business Server 计算机上安装代理。</span><span class="sxs-lookup"><span data-stu-id="11e78-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="11e78-123">导入要监控的服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="11e78-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="11e78-124">Redis、侦听器服务和网站必须全部安装在同一台主机上。</span><span class="sxs-lookup"><span data-stu-id="11e78-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="11e78-125">请确保主机未安装 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="11e78-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="11e78-126">准备侦听器主机</span><span class="sxs-lookup"><span data-stu-id="11e78-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="11e78-127">若要准备主机，您需要安装 Redis 内存中缓存系统，并确保计算机上有有效的证书。</span><span class="sxs-lookup"><span data-stu-id="11e78-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="11e78-128">Microsoft 建议你安装 Redis 3.0 的最新稳定内部版本。</span><span class="sxs-lookup"><span data-stu-id="11e78-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="11e78-129">统计信息管理器版本 2.0 已使用 Redis 3.2.100 进行了测试。</span><span class="sxs-lookup"><span data-stu-id="11e78-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="11e78-130">从以下网站下载 Redis： [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)</span><span class="sxs-lookup"><span data-stu-id="11e78-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="11e78-131">可以从中下载未签名的安装程序 [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="11e78-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="11e78-132">如果需要，通过热门程序包管理器提供已签名的二进制文件[：Nuget](https://www.nuget.org/packages/Redis-64/)和[Choclatey。](https://chocolatey.org/packages/redis-64)</span><span class="sxs-lookup"><span data-stu-id="11e78-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="11e78-133">运行提供的 msi 并按照提示执行。</span><span class="sxs-lookup"><span data-stu-id="11e78-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="11e78-134">不要选中添加防火墙规则的框。</span><span class="sxs-lookup"><span data-stu-id="11e78-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="11e78-135">侦听器服务需要证书。</span><span class="sxs-lookup"><span data-stu-id="11e78-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="11e78-136">Microsoft 强烈建议你拥有由受信任的证书颁发机构签名的证书。</span><span class="sxs-lookup"><span data-stu-id="11e78-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="11e78-137">如果要使用自签名证书，例如在实验室中进行测试，请参阅"[创建自签名证书"。](deploy.md#BKMK_SelfCert)</span><span class="sxs-lookup"><span data-stu-id="11e78-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="11e78-138">请注意，代理使用证书指纹验证 (而不是链验证) 。</span><span class="sxs-lookup"><span data-stu-id="11e78-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="11e78-139">它将不会执行完整证书验证，因为可以使用自签名证书。</span><span class="sxs-lookup"><span data-stu-id="11e78-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="11e78-140">安装侦听器服务</span><span class="sxs-lookup"><span data-stu-id="11e78-140">Install the Listener service</span></span>

<span data-ttu-id="11e78-141">通过运行安装程序并指定以下内容，在StatsManPerfAgentListener.msi安装侦听器服务：</span><span class="sxs-lookup"><span data-stu-id="11e78-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="11e78-142">查看许可协议，如果同意，请选择 **"我接受** 许可协议中的条款"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="11e78-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="11e78-143">下一页上，指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="11e78-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="11e78-144">**服务密码：** 这是远程代理用于向侦听器服务进行身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="11e78-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="11e78-145">**服务端口：** 这是侦听器用于与代理通信的 HTTPS 端口号。</span><span class="sxs-lookup"><span data-stu-id="11e78-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="11e78-146">在安装过程中，将允许通过本地防火墙访问此端口，将创建 URL ACL，并且 SSL 证书将绑定到此端口。</span><span class="sxs-lookup"><span data-stu-id="11e78-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="11e78-147">默认值为 8443。</span><span class="sxs-lookup"><span data-stu-id="11e78-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="11e78-148">**证书指纹：** 这是侦听器用于加密 HTTPS 协议的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="11e78-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="11e78-149">网络服务必须具有私钥的读取权限。</span><span class="sxs-lookup"><span data-stu-id="11e78-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="11e78-150">单击 **"选择..."** 按钮以选择指纹。</span><span class="sxs-lookup"><span data-stu-id="11e78-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="11e78-151">可以使用证书管理器或以下 PowerShell 命令查找证书指纹：</span><span class="sxs-lookup"><span data-stu-id="11e78-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - <span data-ttu-id="11e78-152">**安装目录：** 这是将安装二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="11e78-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="11e78-153">可以使用"浏览..."按钮从默认值 **更改** 它。</span><span class="sxs-lookup"><span data-stu-id="11e78-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="11e78-154">**AppData 目录：** 这是将存储 Logs 文件夹和其他数据的目录。</span><span class="sxs-lookup"><span data-stu-id="11e78-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="11e78-155">你可以从默认值更改它。</span><span class="sxs-lookup"><span data-stu-id="11e78-155">You may change it from the default.</span></span> <span data-ttu-id="11e78-156">卸载时不会将其删除。</span><span class="sxs-lookup"><span data-stu-id="11e78-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="11e78-157">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="11e78-157">Click **Install**.</span></span>
    
<span data-ttu-id="11e78-158">若要验证安装，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="11e78-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="11e78-159">打开浏览器并导航到 https://localhost: \<service-port\> /healthcheck/</span><span class="sxs-lookup"><span data-stu-id="11e78-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="11e78-160">默认情况下，服务端口为 8443 (，除非您指定了其他端口) 。</span><span class="sxs-lookup"><span data-stu-id="11e78-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="11e78-161">若要确保侦听器安装正确，请查找以下内容：</span><span class="sxs-lookup"><span data-stu-id="11e78-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="11e78-162">如果显示运行状况检查页，则侦听器安装成功。</span><span class="sxs-lookup"><span data-stu-id="11e78-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="11e78-163">如果 KnownServerCount 为 1 或更高，则建立与 Redis 的连接。</span><span class="sxs-lookup"><span data-stu-id="11e78-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="11e78-164">等待几分钟，并安装至少一个代理后，请检查 ValuesWritten 计数器是否正在递增。</span><span class="sxs-lookup"><span data-stu-id="11e78-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="11e78-165">安装网站</span><span class="sxs-lookup"><span data-stu-id="11e78-165">Install the Website</span></span>

<span data-ttu-id="11e78-166">通过运行 Skype for Business Server StatsManWebSite.msi (、Real-Time 统计信息管理器 [ (64 ](https://www.microsoft.com/en-in/download/details.aspx?id=57518) 位) ) 并指定以下内容，在主机上安装网站：</span><span class="sxs-lookup"><span data-stu-id="11e78-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="11e78-167">查看许可协议，如果同意，请选择 **"我接受** 许可协议中的条款"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="11e78-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="11e78-168">下一页上，指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="11e78-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="11e78-169">**服务端口：** 这是网站将侦听的端口号。</span><span class="sxs-lookup"><span data-stu-id="11e78-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="11e78-170">稍后可以使用 IIS 管理器绑定更改它。</span><span class="sxs-lookup"><span data-stu-id="11e78-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="11e78-171">在安装过程中，允许通过本地防火墙访问此端口。</span><span class="sxs-lookup"><span data-stu-id="11e78-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="11e78-172">**安装目录：** 这是将安装二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="11e78-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="11e78-173">可以使用"浏览..."按钮从默认值 **更改** 它。</span><span class="sxs-lookup"><span data-stu-id="11e78-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="11e78-174">**AppData 目录：** 这是将存储 Logs 文件夹和其他数据的目录。</span><span class="sxs-lookup"><span data-stu-id="11e78-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="11e78-175">你可以从默认值更改它。</span><span class="sxs-lookup"><span data-stu-id="11e78-175">You may change it from the default.</span></span> <span data-ttu-id="11e78-176">卸载时不会将其删除。</span><span class="sxs-lookup"><span data-stu-id="11e78-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="11e78-177">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="11e78-177">Click **Install**.</span></span>
    
<span data-ttu-id="11e78-178">若要查看网站，请打开浏览器，然后导航到 http://localhost ：.webport \> /。</span><span class="sxs-lookup"><span data-stu-id="11e78-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="11e78-179">若要仅查看运行状况信息，请打开浏览器，然后导航到 http://localhost: \<webport\> ：/healthcheck/。</span><span class="sxs-lookup"><span data-stu-id="11e78-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="11e78-180">默认情况下，Web 端口号为 8080。</span><span class="sxs-lookup"><span data-stu-id="11e78-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="11e78-181">可以使用 IIS 管理器更改网站的端口绑定。</span><span class="sxs-lookup"><span data-stu-id="11e78-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="11e78-182">Web 安装程序添加本地安全组，称为 StatsManWebSiteUsers。</span><span class="sxs-lookup"><span data-stu-id="11e78-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="11e78-183">你可以向此安全组添加帐户以授予对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="11e78-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="11e78-184">安装代理</span><span class="sxs-lookup"><span data-stu-id="11e78-184">Install the Agents</span></span>

<span data-ttu-id="11e78-185">通过运行代理并指定以下内容，在你希望监视的每个 Skype for Business Server StatsManPerfAgent.msi代理：</span><span class="sxs-lookup"><span data-stu-id="11e78-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="11e78-186">查看许可协议，如果同意，请选择 **"我接受** 许可协议中的条款"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="11e78-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="11e78-187">下一页上，指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="11e78-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="11e78-188">**服务密码：** 这是远程代理用于向侦听器服务进行身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="11e78-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="11e78-189">**服务 URI：** 这是侦听器所在的 URI。</span><span class="sxs-lookup"><span data-stu-id="11e78-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="11e78-190">它应使用该 https://name:port 格式。</span><span class="sxs-lookup"><span data-stu-id="11e78-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="11e78-191">可以使用 NETBIOS 名称或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="11e78-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="11e78-192">您可以使用指定为侦听器服务上证书的"主题"或"主题备用名称"的名称，但这不是一项要求。</span><span class="sxs-lookup"><span data-stu-id="11e78-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="11e78-193">**服务指纹：** 这是侦听器使用的 SSL 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="11e78-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="11e78-194">代理将使用此指纹向侦听器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="11e78-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="11e78-195"> (不会执行完整证书验证，因为可以使用自签名证书。) </span><span class="sxs-lookup"><span data-stu-id="11e78-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="11e78-196">**安装目录：** 这是将安装二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="11e78-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="11e78-197">可以使用"浏览..."按钮从默认值 **更改** 它。</span><span class="sxs-lookup"><span data-stu-id="11e78-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="11e78-198">**AppData 目录：** 这是将存储 Logs 文件夹和加密password.txt目录。</span><span class="sxs-lookup"><span data-stu-id="11e78-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="11e78-199">你可以从默认值更改它。</span><span class="sxs-lookup"><span data-stu-id="11e78-199">You may thanks change it from the default.</span></span> <span data-ttu-id="11e78-200">卸载时不会将其删除。</span><span class="sxs-lookup"><span data-stu-id="11e78-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="11e78-201">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="11e78-201">Click **Install**.</span></span>
    
<span data-ttu-id="11e78-202">如果要在多台计算机中安装代理，你可能希望以无人参与模式进行安装。</span><span class="sxs-lookup"><span data-stu-id="11e78-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="11e78-203">例如：</span><span class="sxs-lookup"><span data-stu-id="11e78-203">For example:</span></span> 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="11e78-204">导入拓扑</span><span class="sxs-lookup"><span data-stu-id="11e78-204">Import the topology</span></span>
<span data-ttu-id="11e78-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="11e78-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="11e78-206">安装并运行统计信息管理器后，需要导入 Skype for Business Server 拓扑，以便统计信息管理器知道每个服务器的站点、池和角色。</span><span class="sxs-lookup"><span data-stu-id="11e78-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="11e78-207">若要导入 Skype for Business Server 拓扑，将使用 [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet 检索有关组织使用的每个池的信息，然后将此信息导入统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="11e78-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="11e78-208">若要导入 Skype for Business Server 拓扑，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="11e78-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="11e78-209">在具有 Skype for Business Server PowerShell cmdlet 的主机上：</span><span class="sxs-lookup"><span data-stu-id="11e78-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="11e78-210">a.</span><span class="sxs-lookup"><span data-stu-id="11e78-210">a.</span></span> <span data-ttu-id="11e78-211">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="11e78-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="11e78-212">b.</span><span class="sxs-lookup"><span data-stu-id="11e78-212">b.</span></span> <span data-ttu-id="11e78-213">将"mypoolinfo.xml"文件复制到运行侦听器的服务器。</span><span class="sxs-lookup"><span data-stu-id="11e78-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="11e78-214">在运行侦听器的主机上：</span><span class="sxs-lookup"><span data-stu-id="11e78-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="11e78-215">a.</span><span class="sxs-lookup"><span data-stu-id="11e78-215">a.</span></span> <span data-ttu-id="11e78-216">运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="11e78-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="11e78-217">b.</span><span class="sxs-lookup"><span data-stu-id="11e78-217">b.</span></span> <span data-ttu-id="11e78-218">导航到安装侦听器的目录。</span><span class="sxs-lookup"><span data-stu-id="11e78-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="11e78-219">默认值为：</span><span class="sxs-lookup"><span data-stu-id="11e78-219">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="11e78-220">若要确认要添加和更新的服务器，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="11e78-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="11e78-221">通过以下命令可以查看所有选项：</span><span class="sxs-lookup"><span data-stu-id="11e78-221">The following command enables you to view all options:</span></span>
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="11e78-222">若要查看当前导入的服务器信息，请运行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="11e78-222">To see your currently imported server information, run the following script:</span></span> 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="11e78-223">如果要监视不在 Skype for Business Server 拓扑中的服务器（例如 Exchange Server，可以在运行侦听器的主机上执行单服务器导入。</span><span class="sxs-lookup"><span data-stu-id="11e78-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="11e78-224">若要执行单服务器导入，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="11e78-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="11e78-225">导航到安装侦听器的目录。</span><span class="sxs-lookup"><span data-stu-id="11e78-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="11e78-226">默认值为：</span><span class="sxs-lookup"><span data-stu-id="11e78-226">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="11e78-227">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="11e78-227">Run the following command:</span></span>
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="11e78-228">部署疑难解答</span><span class="sxs-lookup"><span data-stu-id="11e78-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="11e78-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="11e78-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="11e78-230">如果代理无法启动，请检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="11e78-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="11e78-231">代理是否注册到统计信息管理器中？</span><span class="sxs-lookup"><span data-stu-id="11e78-231">Is the agent registered in Statistics Manager?</span></span>
    
    1. <span data-ttu-id="11e78-232">确保按照导入拓扑的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="11e78-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="11e78-233">请参阅["导入拓扑"。](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="11e78-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
        
    2. <span data-ttu-id="11e78-234">如果代理位于拓扑 (中未列出的服务器上，例如 SQL AlwaysOn 群集) 中的节点，则需要按照导入拓扑中的说明手动添加[代理。](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="11e78-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="11e78-235">代理能否与侦听器联系？</span><span class="sxs-lookup"><span data-stu-id="11e78-235">Can the Agent contact the Listener?</span></span>
    
    1. <span data-ttu-id="11e78-236">确保侦听器服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="11e78-236">Make sure the Listener service is running.</span></span> 
        
        <span data-ttu-id="11e78-237">如果未运行，请确保 Redis 正在运行，然后尝试重新启动侦听器。</span><span class="sxs-lookup"><span data-stu-id="11e78-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
        
    2. <span data-ttu-id="11e78-238">确保端口对侦听器服务开放，并且代理计算机可以与端口通信。</span><span class="sxs-lookup"><span data-stu-id="11e78-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="11e78-239">若要确保统计信息管理器正在收集数据，可以按如下方式检查 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="11e78-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="11e78-240">以下命令检索计数器存储名称：</span><span class="sxs-lookup"><span data-stu-id="11e78-240">The following command retrieves the counter storage names:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="11e78-241">下一个命令检索指定计数器的值：</span><span class="sxs-lookup"><span data-stu-id="11e78-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="11e78-242">有关你可能在应用程序事件日志中看到的所有事件的信息，请参阅 Skype for Business Server 的统计信息 [管理器疑难解答](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="11e78-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="11e78-243">"创建自签名证书"</span><span class="sxs-lookup"><span data-stu-id="11e78-243">Create a self-signed certificate</span></span>
<span data-ttu-id="11e78-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="11e78-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="11e78-245">Microsoft 强烈建议你使用由受信任的证书颁发机构签名的证书。</span><span class="sxs-lookup"><span data-stu-id="11e78-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="11e78-246">但是，如果要将自签名证书用于测试目的，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="11e78-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="11e78-247">以管理员身份登录时，从 PowerShell 控制台中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="11e78-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="11e78-248">类型  `certlm.msc` 。</span><span class="sxs-lookup"><span data-stu-id="11e78-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="11e78-249">这将打开本地计算机证书管理器。</span><span class="sxs-lookup"><span data-stu-id="11e78-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="11e78-250">导航到 **"个人**"，然后打开 **"证书"。**</span><span class="sxs-lookup"><span data-stu-id="11e78-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="11e78-251">右键单击 **StatsManListener- \> 所有任务 - \> 管理私钥...**</span><span class="sxs-lookup"><span data-stu-id="11e78-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="11e78-252">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="11e78-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="11e78-253">在 **"输入要选择的对象名称"框中** ，键入以下内容：网络服务</span><span class="sxs-lookup"><span data-stu-id="11e78-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="11e78-254">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="11e78-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="11e78-255">在 **"完全控制**"下，取消选中 **"允许** "复选框。</span><span class="sxs-lookup"><span data-stu-id="11e78-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="11e78-256"> (只读访问权限是必需的。) </span><span class="sxs-lookup"><span data-stu-id="11e78-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="11e78-257">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="11e78-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="11e78-258">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="11e78-258">For more information</span></span>
<span data-ttu-id="11e78-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="11e78-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="11e78-260">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="11e78-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="11e78-261">Skype for Business Server 的统计信息管理器规划</span><span class="sxs-lookup"><span data-stu-id="11e78-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="11e78-262">更新 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="11e78-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="11e78-263">[Skype for Business Server](troubleshoot.md) 统计信息管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="11e78-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
