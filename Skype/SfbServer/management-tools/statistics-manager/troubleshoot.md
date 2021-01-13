---
title: 对 Skype for Business Server 的统计信息管理器进行故障排除
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 摘要：阅读本主题，解决 Skype for Business Server 统计信息管理器的部署问题。
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821772"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="8c1d0-103">对 Skype for Business Server 的统计信息管理器进行故障排除</span><span class="sxs-lookup"><span data-stu-id="8c1d0-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="8c1d0-104">**摘要：** 阅读本主题，解决 Skype for Business Server 统计信息管理器的部署问题。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="8c1d0-105">本主题介绍如何通过描述您可能在应用程序事件日志中看到的事件以及可能采取的相应操作来排查统计信息管理器部署问题。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="8c1d0-106">本主题包含以下各部分：</span><span class="sxs-lookup"><span data-stu-id="8c1d0-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="8c1d0-107">代理事件</span><span class="sxs-lookup"><span data-stu-id="8c1d0-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="8c1d0-108">侦听器事件</span><span class="sxs-lookup"><span data-stu-id="8c1d0-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="8c1d0-109">网站问题</span><span class="sxs-lookup"><span data-stu-id="8c1d0-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="8c1d0-110">代理事件</span><span class="sxs-lookup"><span data-stu-id="8c1d0-110">Agent events</span></span>
<span data-ttu-id="8c1d0-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="8c1d0-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="8c1d0-112">**1000** — 无法在作业对象 (设置) 限制程序 — 未知原因</span><span class="sxs-lookup"><span data-stu-id="8c1d0-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="8c1d0-113">**1001** — 在进程上不允许进程限制 (可能已经在作业对象对象) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="8c1d0-114">代理在 Windows 作业对象内部运行，以自动限制其内存占用。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="8c1d0-115">如果代理不会启动，并且这些事件条目存在于事件日志中，则作业对象无法在服务器上实例化。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="8c1d0-116">若要处理此情况，可以通过更改以下项中的值来删除上限配置文件：</span><span class="sxs-lookup"><span data-stu-id="8c1d0-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="8c1d0-117">搜索"MaxProcessMemoryMB"，将值更改为"0"，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8c1d0-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="8c1d0-118">如果进行了此更改，代理通常仍将占用 100 MB 的内存，但是不会强制限制为 \< 默认为 300 MB。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="8c1d0-119">如果进行了此更改，我们建议密切监视内存使用率，以确保代理不会在其主机上占用大量内存。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="8c1d0-120">**2000** — 客户端初始化失败</span><span class="sxs-lookup"><span data-stu-id="8c1d0-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="8c1d0-121">**2001**— 无法连接到任何源 IP 上的服务</span><span class="sxs-lookup"><span data-stu-id="8c1d0-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="8c1d0-122">如果代理无法连接到侦听器计算机，请检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="8c1d0-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="8c1d0-123">确保侦听器服务在侦听器计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="8c1d0-124">如果没有，请确保 Redis 正在该服务器上运行，然后重新启动侦听器服务。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="8c1d0-125">检查侦听器计算机上统计信息管理器事件日志，以确保统计信息管理器侦听器服务本身没有问题。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="8c1d0-126">使用 telnet 等连接工具验证从代理计算机到正确端口上的侦听器的连接。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="8c1d0-127">如果没有，请确保在侦听器计算机上为侦听器计算机连接到专用/公共/域 (类型的网络类型启用传入防火墙) 。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="8c1d0-128">如果侦听器计算机未加入域，则网络可能列为公用网络，在这种情况下，随统计信息管理器一起安装的防火墙规则在默认情况下将不适用。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="8c1d0-129">**4000** — 无法从侦听器下载服务器信息 (未知原因) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="8c1d0-130">**4001** — 侦听器拓扑中找不到服务器</span><span class="sxs-lookup"><span data-stu-id="8c1d0-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="8c1d0-131">如果服务器成功连接到侦听器，但服务器未添加到侦听器缓存中的拓扑，则会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="8c1d0-132">解决方案选项：</span><span class="sxs-lookup"><span data-stu-id="8c1d0-132">Resolution options:</span></span>
    
  - <span data-ttu-id="8c1d0-133">确保按照导入拓扑的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="8c1d0-134">请参阅["导入拓扑"。](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="8c1d0-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="8c1d0-135">如果代理位于拓扑 (中未列出的服务器上，例如 SQL AlwaysOn 群集) 中的节点，则需要按照导入拓扑中的说明手动添加[代理。](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="8c1d0-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="8c1d0-136">**4002** — 侦听器密码无效</span><span class="sxs-lookup"><span data-stu-id="8c1d0-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="8c1d0-137">代理尝试使用的加密密码与侦听器本身的服务密码不匹配。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="8c1d0-138">卸载代理，然后使用正确的服务密码重新安装它。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="8c1d0-139">**4003** — 证书指纹不匹配</span><span class="sxs-lookup"><span data-stu-id="8c1d0-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="8c1d0-140">安装时为代理给定的证书指纹与侦听器当前使用的证书上的指纹不匹配，因此连接将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="8c1d0-141">卸载代理，然后使用正确的证书指纹重新安装它。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="8c1d0-142">**4004** — 无效响应或 HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="8c1d0-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="8c1d0-143">侦听器未响应预期状态。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="8c1d0-144">如果连接已代理，请检查代理配置。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="8c1d0-145">检查侦听器计算机的 StatsMan 日志，了解其配置问题。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="8c1d0-146">**4005** — 无法取消序列化 XML</span><span class="sxs-lookup"><span data-stu-id="8c1d0-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="8c1d0-147">侦听器服务器上服务器信息已损坏，或者代理计算机和侦听器计算机之间可能有版本不匹配。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="8c1d0-148">确保版本匹配，并检查侦听器事件日志中的问题。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="8c1d0-149">侦听器事件</span><span class="sxs-lookup"><span data-stu-id="8c1d0-149">Listener events</span></span>
<span data-ttu-id="8c1d0-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="8c1d0-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="8c1d0-151">**10000** — 启动失败 未知 (无法恢复，服务将停止/崩溃，) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="8c1d0-152">**10001** — 配置问题</span><span class="sxs-lookup"><span data-stu-id="8c1d0-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="8c1d0-153">通常，当 [listener_install_location]\PerfAgentListener.exe.config 文件已手动修改并且应用程序无法读取时，将会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="8c1d0-154">**10002** — HTTP 侦听器初始化错误</span><span class="sxs-lookup"><span data-stu-id="8c1d0-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="8c1d0-155">在安装期间未正确设置 URL ACL 或 SSL 证书无效时，通常会记录此事件。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="8c1d0-156">确保配置中的证书有效。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="8c1d0-157">如果是，请根据部署统计信息管理器 [中的说明重新安装侦听器](deploy.md#BKMK_Deploy)。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="8c1d0-158">**10003** — Redis 失败</span><span class="sxs-lookup"><span data-stu-id="8c1d0-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="8c1d0-159">**10004** — 缓存基础结构故障</span><span class="sxs-lookup"><span data-stu-id="8c1d0-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="8c1d0-160">**10007** — (中存储的设置) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="8c1d0-161">侦听器无法联系 Redis 或从缓存检索格式良好的数据，并且无法启动。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="8c1d0-162">确保在服务器上正确启动和配置 Redis 服务。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="8c1d0-163">**10005** — 服务器信息检索/分析</span><span class="sxs-lookup"><span data-stu-id="8c1d0-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="8c1d0-164">Redis 缓存中的拓扑信息无效。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="8c1d0-165">首先，尝试重新启动 Redis 和侦听器。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="8c1d0-166">如果错误仍然存在，请参阅" [导入拓扑以](deploy.md#BKMK_ImportTopology) 重新创建拓扑数据"。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="8c1d0-167">**10100** — Redis PING 中断</span><span class="sxs-lookup"><span data-stu-id="8c1d0-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="8c1d0-168">**10101** — Redis PING (每隔 60 秒中断一次) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="8c1d0-169">**30100** — 已还原 Redis PING 中断</span><span class="sxs-lookup"><span data-stu-id="8c1d0-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="8c1d0-170">当侦听器无法连接到 Redis 时，将记录这些记录。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="8c1d0-171">确保 Redis 已启动，并且侦听器和 Redis 之间的网络连接可用。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="8c1d0-172">**10200** — Redis 写入中断</span><span class="sxs-lookup"><span data-stu-id="8c1d0-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="8c1d0-173">**10201** — Redis Write 中断 (每隔 60 秒) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="8c1d0-174">**30100** — Redis 写入中断已解决</span><span class="sxs-lookup"><span data-stu-id="8c1d0-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="8c1d0-175">当侦听器无法写入 Redis 缓存时，将记录这些记录。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="8c1d0-176">确保 Redis 已启动，并且侦听器和 Redis 之间的网络连接可用。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="8c1d0-177">**30000** — 成功启动</span><span class="sxs-lookup"><span data-stu-id="8c1d0-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="8c1d0-178">每次启动侦听器时记录。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="8c1d0-179">**22000** — 统计信息管理器代理初始化成功。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="8c1d0-180">**23000** — EventLogQueryManager 初始化 (或失败后成功) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="8c1d0-181">**24000** — 首次初始化 serverinfo (失败或失败后) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="8c1d0-182">**25000** — 侦听器在未能发布或首次成功发布 (后重新联机) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="8c1d0-183">**5000** — 用于发布数据的侦听器脱机启动</span><span class="sxs-lookup"><span data-stu-id="8c1d0-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="8c1d0-184">**5001** - 侦听器在长时间内仍处于脱机状态</span><span class="sxs-lookup"><span data-stu-id="8c1d0-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="8c1d0-185">这些事件可用于监视/警报/清除问题。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="8c1d0-186">网站问题</span><span class="sxs-lookup"><span data-stu-id="8c1d0-186">Website issues</span></span>
<span data-ttu-id="8c1d0-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="8c1d0-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="8c1d0-188">Chrome 中的重复登录提示 - 这是已在版本 1.1 中解决的 Bug。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="8c1d0-189">如果你在 Chrome 浏览器中看到重复的登录提示，请确保你已升级到最新版本的统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="8c1d0-190">若要验证您正在运行的网站的版本，请运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="8c1d0-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="8c1d0-191">在文件资源管理器中， (默认目录) </span><span class="sxs-lookup"><span data-stu-id="8c1d0-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="8c1d0-192">右键单击StatsManHubWebSite.dll并查看其属性。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="8c1d0-193">如果在 KHI 横向视图或计数器详细信息视图中找不到计算机，请确保它是站点和池的成员。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="8c1d0-194">如果不是，将不会显示在这些视图中。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="8c1d0-195">有关为拓扑中的服务器定义站点和池的信息，请参阅"[导入拓扑"。](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="8c1d0-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="8c1d0-196">产品版本将显示在"说明"详细信息中。</span><span class="sxs-lookup"><span data-stu-id="8c1d0-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="8c1d0-197">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="8c1d0-197">For more information</span></span>
<span data-ttu-id="8c1d0-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="8c1d0-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="8c1d0-199">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="8c1d0-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="8c1d0-200">Skype for Business Server 的统计信息管理器规划</span><span class="sxs-lookup"><span data-stu-id="8c1d0-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="8c1d0-201">部署 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="8c1d0-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="8c1d0-202">更新 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="8c1d0-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
