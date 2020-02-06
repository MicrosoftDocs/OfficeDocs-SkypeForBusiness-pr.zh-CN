---
title: 对 Skype for Business Server 的统计信息管理器进行故障排除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 摘要：阅读本主题以对 Skype for business 服务器的统计信息管理器部署进行故障排除。
ms.openlocfilehash: a787297b25b983303e65f398dfb7b275ae044944
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816211"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="2f16a-103">对 Skype for Business Server 的统计信息管理器进行故障排除</span><span class="sxs-lookup"><span data-stu-id="2f16a-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="2f16a-104">**摘要：** 阅读本主题以对 Skype for business 服务器的统计信息管理器部署进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="2f16a-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="2f16a-105">本主题介绍了如何通过描述你在应用程序事件日志中可能会看到的事件以及你可能采取的相应操作来解决你的统计信息管理器部署。</span><span class="sxs-lookup"><span data-stu-id="2f16a-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="2f16a-106">本主题包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="2f16a-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="2f16a-107">代理事件</span><span class="sxs-lookup"><span data-stu-id="2f16a-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="2f16a-108">侦听器事件</span><span class="sxs-lookup"><span data-stu-id="2f16a-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="2f16a-109">网站问题</span><span class="sxs-lookup"><span data-stu-id="2f16a-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="2f16a-110">代理事件</span><span class="sxs-lookup"><span data-stu-id="2f16a-110">Agent events</span></span>
<span data-ttu-id="2f16a-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="2f16a-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="2f16a-112">**1000** - 无法设置处理器限制器（作业对象） - 未知原因</span><span class="sxs-lookup"><span data-stu-id="2f16a-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="2f16a-113">**1001** -流程不允许进程限制（可能已在作业对象内）</span><span class="sxs-lookup"><span data-stu-id="2f16a-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="2f16a-114">代理在 Windows 作业对象内以运行以自动限制其内存使用量。</span><span class="sxs-lookup"><span data-stu-id="2f16a-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="2f16a-115">如果代理无法启动，并且这些事件条目在事件日志中存在，则作业对象无法在在服务器上实例化。</span><span class="sxs-lookup"><span data-stu-id="2f16a-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="2f16a-116">要解决此问题，可以通过更改配置文件中的值来取消内存上限：</span><span class="sxs-lookup"><span data-stu-id="2f16a-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="2f16a-117">搜索 "MaxProcessMemoryMB" 并将值更改为 "0"，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2f16a-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```console
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="2f16a-118">如果进行此更改，则该代理通常仍会占用\< 100 mb 的内存，但它不会被强制限制为 300 mb （默认值）。</span><span class="sxs-lookup"><span data-stu-id="2f16a-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="2f16a-119">如果进行此更改，我们建议密切监视内存使用情况，以确保代理在其主机上不占用大量内存。</span><span class="sxs-lookup"><span data-stu-id="2f16a-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="2f16a-120">**2000** - 客户端初始化失败</span><span class="sxs-lookup"><span data-stu-id="2f16a-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="2f16a-121">**2001** - 无法在任何源 IP 上建立与该服务的连接</span><span class="sxs-lookup"><span data-stu-id="2f16a-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="2f16a-122">如果代理无法连接到侦听器计算机，请检查以下各项：</span><span class="sxs-lookup"><span data-stu-id="2f16a-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
1. <span data-ttu-id="2f16a-123">确保侦听器服务正在侦听器计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="2f16a-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="2f16a-124">否则，请确保 Redis 正在服务器上运行，然后重新启动侦听器服务。</span><span class="sxs-lookup"><span data-stu-id="2f16a-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
    
    <span data-ttu-id="2f16a-125">检查侦听器计算机上的统计信息管理器事件日志，以确保统计信息管理器服务本身没有问题。</span><span class="sxs-lookup"><span data-stu-id="2f16a-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
    
2. <span data-ttu-id="2f16a-126">使用连接工具（例如 telnet）验证正确端口上从代理计算机到侦听器的连接。</span><span class="sxs-lookup"><span data-stu-id="2f16a-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
    
    <span data-ttu-id="2f16a-127">否则，请确保根据侦听器计算机连接到的网络类型（专用/公共/域）在侦听器计算机上启用传入防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="2f16a-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="2f16a-128">如果监听器计算机未加入域，则网络可能被列为 public，并且在这种情况下，使用 "统计信息管理器" 安装的防火墙规则默认情况下不会应用。</span><span class="sxs-lookup"><span data-stu-id="2f16a-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="2f16a-129">**4000** - 无法从侦听器下载服务器信息（未知原因）</span><span class="sxs-lookup"><span data-stu-id="2f16a-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="2f16a-130">**4001** - 在侦听器拓扑未找到服务器</span><span class="sxs-lookup"><span data-stu-id="2f16a-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="2f16a-131">如果服务器成功连接到侦听器，但未将服务器添加到侦听器缓存中的拓扑中，将发生此错误。</span><span class="sxs-lookup"><span data-stu-id="2f16a-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="2f16a-132">解决办法选项：</span><span class="sxs-lookup"><span data-stu-id="2f16a-132">Resolution options:</span></span>
    
  - <span data-ttu-id="2f16a-p107">	确保遵循导入拓扑的说明。请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)。  </span><span class="sxs-lookup"><span data-stu-id="2f16a-p107">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="2f16a-135">如果代理位于拓扑中未列出的服务器上（例如，SQL AlwaysOn 群集内的节点），你将需要按照[导入拓扑](deploy.md#BKMK_ImportTopology)中的说明手动添加代理。</span><span class="sxs-lookup"><span data-stu-id="2f16a-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="2f16a-136">**4002** - 无效侦听器密码</span><span class="sxs-lookup"><span data-stu-id="2f16a-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="2f16a-137">代理尝试使用的加密密码与侦听器上的服务密码不匹配。</span><span class="sxs-lookup"><span data-stu-id="2f16a-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="2f16a-138">请卸载代理，然后使用正确的服务密码重新安装。</span><span class="sxs-lookup"><span data-stu-id="2f16a-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="2f16a-139">**4003** - 证书指纹不匹配</span><span class="sxs-lookup"><span data-stu-id="2f16a-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="2f16a-140">在安装时为代理提供的证书指纹与侦听器当前使用的证书上的指纹不匹配，因此该连接将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="2f16a-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="2f16a-141">请卸载代理，然后使用正确的证书指纹重新安装。</span><span class="sxs-lookup"><span data-stu-id="2f16a-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="2f16a-142">**4004** - 无效响应或 HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="2f16a-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="2f16a-143">侦听器未以预期的状态响应。  </span><span class="sxs-lookup"><span data-stu-id="2f16a-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="2f16a-144">如果连接使用代理，请检查代理配置。</span><span class="sxs-lookup"><span data-stu-id="2f16a-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="2f16a-145">检查监听器计算机的 StatsMan 日志中是否存在其配置问题。</span><span class="sxs-lookup"><span data-stu-id="2f16a-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="2f16a-146">**4005** - 无法将 XML 反序列化</span><span class="sxs-lookup"><span data-stu-id="2f16a-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="2f16a-147">侦听器服务器上的服务器信息已损坏，或者代理与侦听器计算机之间可能存在版本不匹配的情况。</span><span class="sxs-lookup"><span data-stu-id="2f16a-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="2f16a-148">请确保版本匹配，并检查侦听器事件日志了解相关问题。</span><span class="sxs-lookup"><span data-stu-id="2f16a-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="2f16a-149">侦听器事件</span><span class="sxs-lookup"><span data-stu-id="2f16a-149">Listener events</span></span>
<span data-ttu-id="2f16a-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="2f16a-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="2f16a-151">**10000** - 启动失败未知原因（这些错误无法恢复，因此服务将停止/失败）</span><span class="sxs-lookup"><span data-stu-id="2f16a-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="2f16a-152">**10001** - 配置问题</span><span class="sxs-lookup"><span data-stu-id="2f16a-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="2f16a-153">通常，当 [listener_install_location]\PerfAgentListener.exe.config 文件被手动修改而无法由应用程序读取时，会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="2f16a-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="2f16a-154">**10002** - HTTP 侦听器初始化错误</span><span class="sxs-lookup"><span data-stu-id="2f16a-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="2f16a-155">当 URL ACL 在安装期间未正确设置或 SSL 证书无效时，通常会记录此事件。</span><span class="sxs-lookup"><span data-stu-id="2f16a-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="2f16a-156">请确保配置中的证书有效。</span><span class="sxs-lookup"><span data-stu-id="2f16a-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="2f16a-157">如果证书有效，请根据[部署统计信息管理器](deploy.md#BKMK_Deploy)中的说明重新安装侦听器。</span><span class="sxs-lookup"><span data-stu-id="2f16a-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="2f16a-158">**10003** - Redis 故障</span><span class="sxs-lookup"><span data-stu-id="2f16a-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="2f16a-159">**10004** - 缓存基础结构故障</span><span class="sxs-lookup"><span data-stu-id="2f16a-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="2f16a-160">**10007** - 设置（存储在 redis 中）</span><span class="sxs-lookup"><span data-stu-id="2f16a-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="2f16a-161">侦听器无法联系 Redis，或者无法从缓存中检索到格式正确的数据，因此无法启动。</span><span class="sxs-lookup"><span data-stu-id="2f16a-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="2f16a-162">请确保 Redis 服务已启动并且在服务器上正确配置。</span><span class="sxs-lookup"><span data-stu-id="2f16a-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="2f16a-163">**10005** - 服务器信息检索/解析</span><span class="sxs-lookup"><span data-stu-id="2f16a-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="2f16a-164">Redis 缓存中的拓扑信息无效。</span><span class="sxs-lookup"><span data-stu-id="2f16a-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="2f16a-165">首先，尝试重新启动 Redis 和侦听器。</span><span class="sxs-lookup"><span data-stu-id="2f16a-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="2f16a-166">如果错误仍然存在，请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)重新创建拓扑数据。</span><span class="sxs-lookup"><span data-stu-id="2f16a-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="2f16a-167">**10100** - Redis PING 中断</span><span class="sxs-lookup"><span data-stu-id="2f16a-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="2f16a-168">**10101** - Redis PING 连续中断（每隔 60 秒）</span><span class="sxs-lookup"><span data-stu-id="2f16a-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="2f16a-169">**30100** - Redis PING 中断已恢复</span><span class="sxs-lookup"><span data-stu-id="2f16a-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="2f16a-170">当侦听器无法连接到 Redis 时，将记录这些数据。</span><span class="sxs-lookup"><span data-stu-id="2f16a-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="2f16a-171">请确保 Redis 已启动并且侦听器与 Redis 网络之间的连接可用。</span><span class="sxs-lookup"><span data-stu-id="2f16a-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="2f16a-172">**10200** - Redis 写入中断</span><span class="sxs-lookup"><span data-stu-id="2f16a-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="2f16a-173">**10201** - Redis 写入中断连续发生（每隔 60 秒）</span><span class="sxs-lookup"><span data-stu-id="2f16a-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="2f16a-174">**30100** - Redis 写入中断已解决</span><span class="sxs-lookup"><span data-stu-id="2f16a-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="2f16a-175">当侦听器无法写入 Redis 缓存时，将记录这些数据。</span><span class="sxs-lookup"><span data-stu-id="2f16a-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="2f16a-176">请确保 Redis 已启动并且侦听器与 Redis 网络之间的连接可用。</span><span class="sxs-lookup"><span data-stu-id="2f16a-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="2f16a-177">**30000** - 已成功启动</span><span class="sxs-lookup"><span data-stu-id="2f16a-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="2f16a-178">侦听器每次启动时记录。</span><span class="sxs-lookup"><span data-stu-id="2f16a-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="2f16a-179">**22000** -统计信息管理器代理的初始化已成功。</span><span class="sxs-lookup"><span data-stu-id="2f16a-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="2f16a-180">**23000** - EventLogQueryManager 的初始化成功（首次或失败之后）</span><span class="sxs-lookup"><span data-stu-id="2f16a-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="2f16a-181">**24000** - serverinfo 的初始化成功（首次或失败之后）</span><span class="sxs-lookup"><span data-stu-id="2f16a-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="2f16a-182">**25000** - 侦听器在无法开机自检（或首先成功开机自检）之后恢复联机</span><span class="sxs-lookup"><span data-stu-id="2f16a-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="2f16a-183">**5000** - 侦听器启动脱机对数据进行开机自检</span><span class="sxs-lookup"><span data-stu-id="2f16a-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="2f16a-184">**5001** - 侦听器在长时间内仍脱机</span><span class="sxs-lookup"><span data-stu-id="2f16a-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="2f16a-185">这些事件可用于监控/警示/清除问题。</span><span class="sxs-lookup"><span data-stu-id="2f16a-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="2f16a-186">网站问题</span><span class="sxs-lookup"><span data-stu-id="2f16a-186">Website issues</span></span>
<span data-ttu-id="2f16a-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="2f16a-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="2f16a-188">Chrome 中的重复登录提示-这是已在版本1.1 中解决的 bug。</span><span class="sxs-lookup"><span data-stu-id="2f16a-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="2f16a-189">如果在 Chrome 浏览器中看到重复的登录提示，请确保已升级到最新版本的统计信息管理器。</span><span class="sxs-lookup"><span data-stu-id="2f16a-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="2f16a-190">要验证你正在运行的网站的版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2f16a-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="2f16a-191">	在文件资源管理器中，打开默认目录</span><span class="sxs-lookup"><span data-stu-id="2f16a-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="2f16a-192">右键单击 StatsManHubWebSite.dll 并查看其属性。</span><span class="sxs-lookup"><span data-stu-id="2f16a-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="2f16a-193">如果在 KHI 的“横向”视图或“计数器详细信息”视图中找不到某台计算机，确保它是某个站点和池的成员。</span><span class="sxs-lookup"><span data-stu-id="2f16a-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="2f16a-194">否则，它将不会出现在这些视图中。</span><span class="sxs-lookup"><span data-stu-id="2f16a-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="2f16a-195">有关为拓扑中的服务器定义站点和池的信息，请参阅[导入拓扑](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="2f16a-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="2f16a-196">产品版本将在“说明”详细信息中显示。</span><span class="sxs-lookup"><span data-stu-id="2f16a-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="2f16a-197">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="2f16a-197">For more information</span></span>
<span data-ttu-id="2f16a-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="2f16a-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="2f16a-199">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2f16a-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="2f16a-200">Skype for Business Server 的统计信息管理器规划</span><span class="sxs-lookup"><span data-stu-id="2f16a-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="2f16a-201">部署 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="2f16a-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="2f16a-202">更新 Skype for Business Server 的统计信息管理器</span><span class="sxs-lookup"><span data-stu-id="2f16a-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
