---
title: 为业务 Server 部署的 Skype 的统计信息管理器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 摘要： 阅读本主题可了解如何为业务服务器部署 for Skype 的统计信息管理器。
ms.openlocfilehash: 2813b12dfda612374f1e10d4082d54ce46d88216
ms.sourcegitcommit: 160ced7013c1c46595c4362c2f32c5769b082294
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699421"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="d9f80-103">为业务 Server 部署的 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="d9f80-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="d9f80-104">**摘要：** 阅读本主题可了解如何为业务服务器部署 for Skype 的统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="d9f80-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="d9f80-105">适用于业务服务器 Skype 的统计信息管理器是一个强大的工具，允许您查看 Skype 的实时业务服务器运行状况和性能数据。</span><span class="sxs-lookup"><span data-stu-id="d9f80-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="d9f80-106">可以跨服务器数百每隔几秒钟轮询性能数据，并立即统计信息管理器网站上查看结果。</span><span class="sxs-lookup"><span data-stu-id="d9f80-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="d9f80-107">您尝试安装统计信息管理器之前，请确保您熟悉的软件、 网络和硬件要求。</span><span class="sxs-lookup"><span data-stu-id="d9f80-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="d9f80-108">有关详细信息，请参阅[计划为统计信息管理器中的 Skype 业务服务器](plan.md)。</span><span class="sxs-lookup"><span data-stu-id="d9f80-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9f80-109">如果您要从早期版本的统计信息管理器中进行升级，请参阅[适用于业务服务器 Skype 升级统计信息管理器](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="d9f80-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d9f80-110">统计信息管理器网站已经过测试，可以在 Internet Explorer 11+、Edge 20.10240+ 和 Chrome 46+（当前 Evergreen 版本）上正确运行。</span><span class="sxs-lookup"><span data-stu-id="d9f80-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="d9f80-111">您可以找到统计信息管理器在可下载[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)。</span><span class="sxs-lookup"><span data-stu-id="d9f80-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="d9f80-112">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="d9f80-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="d9f80-113">部署统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="d9f80-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="d9f80-114">对你的部署进行故障排除</span><span class="sxs-lookup"><span data-stu-id="d9f80-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="d9f80-115">创建自签名证书</span><span class="sxs-lookup"><span data-stu-id="d9f80-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="d9f80-116">部署统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="d9f80-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="d9f80-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="d9f80-117"></span></span>

<span data-ttu-id="d9f80-118">若要部署的统计信息管理器，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="d9f80-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="d9f80-119">通过安装 Redis 内存中缓存系统，并确保你已安装合适的证书，准备侦听器主机。</span><span class="sxs-lookup"><span data-stu-id="d9f80-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="d9f80-120">在主机上安装侦听器服务。</span><span class="sxs-lookup"><span data-stu-id="d9f80-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="d9f80-121">在主机上安装网站。</span><span class="sxs-lookup"><span data-stu-id="d9f80-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="d9f80-122">在每个 Skype 要监控的企业服务器计算机上安装代理。</span><span class="sxs-lookup"><span data-stu-id="d9f80-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="d9f80-123">为你监视的服务器导入拓扑。</span><span class="sxs-lookup"><span data-stu-id="d9f80-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d9f80-124">Redis、侦听器服务和网站必须安装在同一台主机上。</span><span class="sxs-lookup"><span data-stu-id="d9f80-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="d9f80-125">确保主机计算机的业务服务器安装没有 Skype。</span><span class="sxs-lookup"><span data-stu-id="d9f80-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="d9f80-126">准备侦听器主机。</span><span class="sxs-lookup"><span data-stu-id="d9f80-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="d9f80-127">要准备主机，你将需要安装 Redis 内存中缓存系统，并确保该计算机上存在有效证书。</span><span class="sxs-lookup"><span data-stu-id="d9f80-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="d9f80-128">Microsoft 建议安装稳定的最新 Redis 3.0 内部版本。</span><span class="sxs-lookup"><span data-stu-id="d9f80-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="d9f80-129">统计信息管理器版本 2.0 与 Redis 3.2.100 测试。</span><span class="sxs-lookup"><span data-stu-id="d9f80-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="d9f80-130">从以下网站下载 Redis: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)。</span><span class="sxs-lookup"><span data-stu-id="d9f80-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="d9f80-131">可以从下载未签名安装程序[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="d9f80-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="d9f80-132">如果需要，可通过以下常用程序包管理器获取签名的二进制文件：[Nuget](https://www.nuget.org/packages/Redis-64/) 和 [Choclatey](https://chocolatey.org/packages/redis-64)。</span><span class="sxs-lookup"><span data-stu-id="d9f80-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="d9f80-133">运行提供的 msi 并按照提示操作。</span><span class="sxs-lookup"><span data-stu-id="d9f80-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="d9f80-134">请勿选中用于添加防火墙规则的复选框。</span><span class="sxs-lookup"><span data-stu-id="d9f80-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="d9f80-135">侦听器服务要求有证书。</span><span class="sxs-lookup"><span data-stu-id="d9f80-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="d9f80-136">Microsoft 强烈建议您有由受信任的证书颁发机构签名的证书。</span><span class="sxs-lookup"><span data-stu-id="d9f80-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="d9f80-137">如果你要使用自签名证书（例如，用于在实验室中进行测试），请参阅[创建自签名证书](deploy.md#BKMK_SelfCert)。</span><span class="sxs-lookup"><span data-stu-id="d9f80-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="d9f80-p106">请注意，代理使用证书指纹验证（而不是链验证）。由于可能使用自签名证书，因此它不会执行完整证书验证。</span><span class="sxs-lookup"><span data-stu-id="d9f80-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="d9f80-140">安装侦听器服务</span><span class="sxs-lookup"><span data-stu-id="d9f80-140">Install the Listener service</span></span>

<span data-ttu-id="d9f80-141">通过运行 StatsManPerfAgentListener.msi 并指定以下安装在主机上的侦听器服务：</span><span class="sxs-lookup"><span data-stu-id="d9f80-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="d9f80-142">阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d9f80-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="d9f80-143">在下一页上，指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="d9f80-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="d9f80-144">**服务密码：** 这是远程代理将用于向侦听服务进行身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="d9f80-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="d9f80-145">**服务端口：** 这是在侦听器将使用与代理进行通信的 HTTPS 端口号。</span><span class="sxs-lookup"><span data-stu-id="d9f80-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="d9f80-146">安装过程中，此端口将允许通过本地防火墙，将创建 URL ACL，并且将 SSL 证书绑定到此端口。</span><span class="sxs-lookup"><span data-stu-id="d9f80-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="d9f80-147">默认值为 8443。</span><span class="sxs-lookup"><span data-stu-id="d9f80-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="d9f80-148">**证书指纹：** 这是在侦听器将使用加密 HTTPS 协议的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="d9f80-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="d9f80-149">网络服务必须具有读取访问权限的私钥。</span><span class="sxs-lookup"><span data-stu-id="d9f80-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="d9f80-150">单击“**选择...**”按钮选择指纹。</span><span class="sxs-lookup"><span data-stu-id="d9f80-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="d9f80-151">可以通过使用证书管理器或通过使用以下 PowerShell 命令来查找证书指纹：</span><span class="sxs-lookup"><span data-stu-id="d9f80-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="d9f80-152">**安装目录：** 这是将在其安装二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="d9f80-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="d9f80-153">您可以从默认更改它通过使用**浏览...** 按钮。</span><span class="sxs-lookup"><span data-stu-id="d9f80-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="d9f80-154">**应用程序数据 Dir:** 这是存储的 Logs 文件夹和其他数据的目录。</span><span class="sxs-lookup"><span data-stu-id="d9f80-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="d9f80-155">您可以从默认更改它。</span><span class="sxs-lookup"><span data-stu-id="d9f80-155">You may change it from the default.</span></span> <span data-ttu-id="d9f80-156">它不会删除在卸载。</span><span class="sxs-lookup"><span data-stu-id="d9f80-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="d9f80-157">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="d9f80-157">Click **Install**.</span></span>
    
<span data-ttu-id="d9f80-158">要验证安装，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d9f80-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="d9f80-159">打开浏览器并导航到https://localhost:\<service-port\>/healthcheck/</span><span class="sxs-lookup"><span data-stu-id="d9f80-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="d9f80-160">默认情况下，服务端口为 8443（除非你指定了其他端口）。</span><span class="sxs-lookup"><span data-stu-id="d9f80-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="d9f80-161">为了确保正确安装了侦听器，请查看以下内容：</span><span class="sxs-lookup"><span data-stu-id="d9f80-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="d9f80-162">如果运行状况检查页面显示，则表示已成功安装侦听器。</span><span class="sxs-lookup"><span data-stu-id="d9f80-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="d9f80-163">如果 KnownServersCount 为 1 或更高，则表示已建立与 Redis 的连接。</span><span class="sxs-lookup"><span data-stu-id="d9f80-163">If the KnownServersCount is 1 or higher, then the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="d9f80-164">等待几分钟，且至少安装了一个代理后，检查 ValuesWritten 计数器是否在递增。</span><span class="sxs-lookup"><span data-stu-id="d9f80-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="d9f80-165">安装网站</span><span class="sxs-lookup"><span data-stu-id="d9f80-165">Install the Website</span></span>

<span data-ttu-id="d9f80-166">通过运行 （附带[的业务服务器实时统计信息管理器 （64 位） 的 Skype](https://www.microsoft.com/en-in/download/details.aspx?id=57518)） StatsManWebSite.msi 安装在主机上的网站并指定以下：</span><span class="sxs-lookup"><span data-stu-id="d9f80-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="d9f80-167">阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d9f80-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="d9f80-168">在下一页上，指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="d9f80-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="d9f80-169">**服务端口：** 这是网站将侦听的端口号。</span><span class="sxs-lookup"><span data-stu-id="d9f80-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="d9f80-170">您可以通过使用 IIS 管理器绑定更高版本更改它。</span><span class="sxs-lookup"><span data-stu-id="d9f80-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="d9f80-171">安装过程中，将通过本地防火墙允许此端口。</span><span class="sxs-lookup"><span data-stu-id="d9f80-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="d9f80-172">**安装目录：** 这是安装二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="d9f80-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="d9f80-173">您可以从默认更改它通过使用**浏览...** 按钮。</span><span class="sxs-lookup"><span data-stu-id="d9f80-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="d9f80-174">**应用程序数据 Dir:** 这是存储的 Logs 文件夹和其他数据的目录。</span><span class="sxs-lookup"><span data-stu-id="d9f80-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="d9f80-175">您可以从默认更改它。</span><span class="sxs-lookup"><span data-stu-id="d9f80-175">You may change it from the default.</span></span> <span data-ttu-id="d9f80-176">它不会删除在卸载。</span><span class="sxs-lookup"><span data-stu-id="d9f80-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="d9f80-177">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="d9f80-177">Click **Install**.</span></span>
    
<span data-ttu-id="d9f80-178">若要查看网站，请打开浏览器中，并导航到： http://localhost，webport\>/。</span><span class="sxs-lookup"><span data-stu-id="d9f80-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="d9f80-179">若要查看运行状况的信息、 打开浏览器中，并导航到： http://localhost:\<webport\>/healthcheck/。</span><span class="sxs-lookup"><span data-stu-id="d9f80-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="d9f80-180">默认情况下，Web 端口号为 8080。</span><span class="sxs-lookup"><span data-stu-id="d9f80-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="d9f80-181">你可以使用 IIS 管理器更改网站的端口绑定。</span><span class="sxs-lookup"><span data-stu-id="d9f80-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="d9f80-182">Web 安装程序会添加名为 StatsManWebSiteUsers 的本地安全组。</span><span class="sxs-lookup"><span data-stu-id="d9f80-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="d9f80-183">你可以向此安全组添加帐户以授予对网站的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d9f80-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="d9f80-184">安装代理</span><span class="sxs-lookup"><span data-stu-id="d9f80-184">Install the Agents</span></span>

<span data-ttu-id="d9f80-185">您希望通过运行 StatsManPerfAgent.msi 并指定以下监控的企业服务器，请在每个 Skype 上上安装代理：</span><span class="sxs-lookup"><span data-stu-id="d9f80-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="d9f80-186">阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d9f80-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="d9f80-187">在下一页上，指定以下信息：</span><span class="sxs-lookup"><span data-stu-id="d9f80-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="d9f80-188">**服务密码：** 这是远程代理将用于向侦听器服务进行身份验证的密码。</span><span class="sxs-lookup"><span data-stu-id="d9f80-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="d9f80-189">**服务 URI:** 这是在侦听器所在的 URI。</span><span class="sxs-lookup"><span data-stu-id="d9f80-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="d9f80-190">它应使用https://name:port格式。</span><span class="sxs-lookup"><span data-stu-id="d9f80-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="d9f80-191">可以使用 NETBIOS 名称或 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d9f80-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="d9f80-192">您可以使用也被指定为**主题**或的侦听器服务上的证书的**使用者替代名称**的名称，但这不是要求。</span><span class="sxs-lookup"><span data-stu-id="d9f80-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="d9f80-193">**服务指纹：** 这是使用侦听器 SSL 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="d9f80-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="d9f80-194">（由于可能使用自签名证书，因此它不会执行完整证书验证。</span><span class="sxs-lookup"><span data-stu-id="d9f80-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="d9f80-195">）</span><span class="sxs-lookup"><span data-stu-id="d9f80-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="d9f80-196">**安装目录：** 这是将在其安装二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="d9f80-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="d9f80-197">您可以从默认更改它通过使用**浏览...** 按钮。</span><span class="sxs-lookup"><span data-stu-id="d9f80-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="d9f80-198">**应用程序数据 Dir:** 这是存储日志文件夹和加密的 password.txt 文件的目录。</span><span class="sxs-lookup"><span data-stu-id="d9f80-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="d9f80-199">您可能感谢您更改其默认值。</span><span class="sxs-lookup"><span data-stu-id="d9f80-199">You may thanks change it from the default.</span></span> <span data-ttu-id="d9f80-200">它不会删除在卸载。</span><span class="sxs-lookup"><span data-stu-id="d9f80-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="d9f80-201">单击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="d9f80-201">Click **Install**.</span></span>
    
<span data-ttu-id="d9f80-p121">如果你要在多台计算机上安装代理，你可能想以无人参与模式进行。例如：</span><span class="sxs-lookup"><span data-stu-id="d9f80-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="d9f80-204">导入拓扑</span><span class="sxs-lookup"><span data-stu-id="d9f80-204">Import the topology</span></span>
<span data-ttu-id="d9f80-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="d9f80-205"></span></span>

<span data-ttu-id="d9f80-206">统计信息管理器安装并运行，您需要导入的企业服务器拓扑 Skype 之后，以便该统计信息管理器知道站点、 池和每个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d9f80-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="d9f80-207">要导入您的企业服务器拓扑的 Skype，将使用[Get-cspool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet 可以检索有关组织中使用的每个池的信息，然后将此信息导入统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="d9f80-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="d9f80-208">要导入的企业服务器拓扑 Skype，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="d9f80-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="d9f80-209">主机上具有业务 Server PowerShell cmdlet Skype:</span><span class="sxs-lookup"><span data-stu-id="d9f80-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="d9f80-210">a.</span><span class="sxs-lookup"><span data-stu-id="d9f80-210">a.</span></span> <span data-ttu-id="d9f80-211">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d9f80-211">Run the following command:</span></span> 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="d9f80-212">b.</span><span class="sxs-lookup"><span data-stu-id="d9f80-212">b.</span></span> <span data-ttu-id="d9f80-213">将"mypoolinfo.xml"文件复制到运行侦听器的服务器。</span><span class="sxs-lookup"><span data-stu-id="d9f80-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="d9f80-214">在运行侦听器的主机上：</span><span class="sxs-lookup"><span data-stu-id="d9f80-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="d9f80-215">a.</span><span class="sxs-lookup"><span data-stu-id="d9f80-215">a.</span></span> <span data-ttu-id="d9f80-216">运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d9f80-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="d9f80-217">b.</span><span class="sxs-lookup"><span data-stu-id="d9f80-217">b.</span></span> <span data-ttu-id="d9f80-218">导航到安装侦听器的目录。</span><span class="sxs-lookup"><span data-stu-id="d9f80-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="d9f80-219">默认值为：</span><span class="sxs-lookup"><span data-stu-id="d9f80-219">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="d9f80-220">要确认添加和更新哪些服务器，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d9f80-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="d9f80-221">使用以下命令可以查看所有选项：</span><span class="sxs-lookup"><span data-stu-id="d9f80-221">The following command enables you to view all options:</span></span>
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="d9f80-222">若要查看您导入当前服务器的信息，请运行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="d9f80-222">To see your currently imported server information, run the following script:</span></span> 
  
```
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="d9f80-223">如果您想要监控的企业服务器拓扑-Exchange 服务器，您 Skype 中的服务器，例如-您可以执行运行侦听器的主机上的单服务器导入。</span><span class="sxs-lookup"><span data-stu-id="d9f80-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="d9f80-224">要执行单服务器导入操作，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d9f80-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="d9f80-225">导航到安装侦听器的目录。</span><span class="sxs-lookup"><span data-stu-id="d9f80-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="d9f80-226">默认值为：</span><span class="sxs-lookup"><span data-stu-id="d9f80-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="d9f80-227">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d9f80-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="d9f80-228">对你的部署进行故障排除</span><span class="sxs-lookup"><span data-stu-id="d9f80-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="d9f80-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d9f80-229"></span></span>

<span data-ttu-id="d9f80-230">如果代理无法启动，请检查以下各项：</span><span class="sxs-lookup"><span data-stu-id="d9f80-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="d9f80-231">代理已注册统计信息管理器中？</span><span class="sxs-lookup"><span data-stu-id="d9f80-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="d9f80-p129">	确保遵循导入拓扑的说明。请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)。  </span><span class="sxs-lookup"><span data-stu-id="d9f80-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="d9f80-234">如果代理位于拓扑中未列出的服务器上（例如，SQL AlwaysOn 群集内的节点），你将需要按照[导入拓扑](deploy.md#BKMK_ImportTopology)中的说明手动添加代理。</span><span class="sxs-lookup"><span data-stu-id="d9f80-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="d9f80-235">代理是否可以联系侦听器？</span><span class="sxs-lookup"><span data-stu-id="d9f80-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="d9f80-236">确保侦听器服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="d9f80-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="d9f80-237">如果侦听器服务未运行，请确保 Redis 正在运行，然后尝试重新启动侦听器。</span><span class="sxs-lookup"><span data-stu-id="d9f80-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="d9f80-238">确保端口已打开到侦听器服务，并且代理计算机可以进行通信的端口。</span><span class="sxs-lookup"><span data-stu-id="d9f80-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="d9f80-239">若要确保统计信息管理器收集数据，您可以如下所示检查 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="d9f80-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="d9f80-240">以下命令检索计数器存储名称：</span><span class="sxs-lookup"><span data-stu-id="d9f80-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="d9f80-241">下一个命令检索指定计数器的值：</span><span class="sxs-lookup"><span data-stu-id="d9f80-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="d9f80-242">您可能会看到应用程序事件日志中的所有事件的信息，请参阅[适用于业务服务器 Skype 解决统计信息管理器](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="d9f80-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="d9f80-243">创建自签名证书</span><span class="sxs-lookup"><span data-stu-id="d9f80-243">Create a self-signed certificate</span></span>
<span data-ttu-id="d9f80-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="d9f80-244"></span></span>

<span data-ttu-id="d9f80-245">Microsoft 强烈建议你使用受信任的证书颁发机构签发的证书。</span><span class="sxs-lookup"><span data-stu-id="d9f80-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="d9f80-246">但是，如果你要使用自签名证书以进行测试，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d9f80-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="d9f80-247">以管理员身份登录时，在 PowerShell 控制台中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="d9f80-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="d9f80-248">键入`certlm.msc`。</span><span class="sxs-lookup"><span data-stu-id="d9f80-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="d9f80-249">这将为本地计算机打开证书管理器。</span><span class="sxs-lookup"><span data-stu-id="d9f80-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="d9f80-250">导航到**个人**，然后打开**证书**。</span><span class="sxs-lookup"><span data-stu-id="d9f80-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="d9f80-251">右键单击**StatsManListener-\>所有任务-\>管理私钥...**</span><span class="sxs-lookup"><span data-stu-id="d9f80-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="d9f80-252">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d9f80-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="d9f80-253">在“**输入要选择的对象名称**”框中，键入以下内容：网络服务</span><span class="sxs-lookup"><span data-stu-id="d9f80-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="d9f80-254">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d9f80-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="d9f80-p132">在“**完全控制**”下方，取消选中“**允许**”复选框。（只需要读取权限。）</span><span class="sxs-lookup"><span data-stu-id="d9f80-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="d9f80-257">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d9f80-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="d9f80-258">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="d9f80-258">For more information</span></span>
<span data-ttu-id="d9f80-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="d9f80-259"></span></span>

<span data-ttu-id="d9f80-260">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="d9f80-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="d9f80-261">规划业务 Server 为统计信息管理器中的 Skype</span><span class="sxs-lookup"><span data-stu-id="d9f80-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="d9f80-262">为业务服务器升级的 Skype 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="d9f80-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- [<span data-ttu-id="d9f80-263">解决的 Skype 的统计信息管理器的企业服务器</span><span class="sxs-lookup"><span data-stu-id="d9f80-263">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="d9f80-264">Skype for Business Server 统计信息管理器博客</span><span class="sxs-lookup"><span data-stu-id="d9f80-264">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

