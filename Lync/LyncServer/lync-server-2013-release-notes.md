---
title: Lync Server 2013 发行说明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a93fabf10355dcc4ba7873921c0aaf35475927c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="ccbf6-102">Lync Server 2013 发行说明</span><span class="sxs-lookup"><span data-stu-id="ccbf6-102">Release notes for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccbf6-103">_**主题上次修改时间:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="ccbf6-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="ccbf6-104">欢迎使用 Lync Server 2013 发行说明。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-104">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="ccbf6-105">有关 Lync Server 2013 的已知问题的信息, 请参阅此文件。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-105">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="ccbf6-106">关于此文档</span><span class="sxs-lookup"><span data-stu-id="ccbf6-106">About this document</span></span>

<span data-ttu-id="ccbf6-107">此文档包含在部署和使用 Lync Server 2013 之前应了解的重要信息。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-107">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="ccbf6-108">有关 Lync Server 2013 的详细信息, 请参阅[Microsoft Lync server 2013](microsoft-lync-server-2013.md)文档。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-108">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="ccbf6-109">本文档包含以下部分:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-109">This document contains the following sections:</span></span>

  - <span data-ttu-id="ccbf6-110">Lync 2013 客户端</span><span class="sxs-lookup"><span data-stu-id="ccbf6-110">Lync 2013 client</span></span>

  - <span data-ttu-id="ccbf6-111">Lync Server</span><span class="sxs-lookup"><span data-stu-id="ccbf6-111">Lync Server</span></span>

  - <span data-ttu-id="ccbf6-112">安装</span><span class="sxs-lookup"><span data-stu-id="ccbf6-112">Installation</span></span>

  - <span data-ttu-id="ccbf6-113">移动性</span><span class="sxs-lookup"><span data-stu-id="ccbf6-113">Mobility</span></span>

  - <span data-ttu-id="ccbf6-114">网络会议</span><span class="sxs-lookup"><span data-stu-id="ccbf6-114">Conferencing</span></span>

  - <span data-ttu-id="ccbf6-115">企业语音</span><span class="sxs-lookup"><span data-stu-id="ccbf6-115">Enterprise Voice</span></span>

  - <span data-ttu-id="ccbf6-116">状态</span><span class="sxs-lookup"><span data-stu-id="ccbf6-116">Presence</span></span>

  - <span data-ttu-id="ccbf6-117">响应组应用程序和呼叫寄存应用程序</span><span class="sxs-lookup"><span data-stu-id="ccbf6-117">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="ccbf6-118">Lync Server 控制面板、拓扑生成器和规划工具</span><span class="sxs-lookup"><span data-stu-id="ccbf6-118">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="ccbf6-119">本地化</span><span class="sxs-lookup"><span data-stu-id="ccbf6-119">Localization</span></span>

  - <span data-ttu-id="ccbf6-120">©</span><span class="sxs-lookup"><span data-stu-id="ccbf6-120">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="ccbf6-121">Lync 2013 客户端</span><span class="sxs-lookup"><span data-stu-id="ccbf6-121">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="ccbf6-122">如果文件已在其他应用程序中打开, 则在即时消息中传输文件将失败</span><span class="sxs-lookup"><span data-stu-id="ccbf6-122">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="ccbf6-123">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-123">**Issue:**</span></span>

<span data-ttu-id="ccbf6-124">如果你尝试将文件 (如 Word 文档) 通过在即时消息中包含到另一个 Lync 用户, 则传输将显示为成功, 但实际上可能无法传输该文件。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-124">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="ccbf6-125">将在 Lync 客户端中显示文件类型的图标, 但该文件不能由预期的接收方打开。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-125">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="ccbf6-126">不会显示任何错误消息, 通知您传送未成功。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-126">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="ccbf6-127">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-127">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-128">若要解决此问题, 请先关闭打开的文件或已打开的应用程序, 然后再尝试在即时消息中传输文件。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-128">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="ccbf6-129">Lync Server</span><span class="sxs-lookup"><span data-stu-id="ccbf6-129">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="ccbf6-130">如果 Lync Server 存储服务数据复制失败, 管理员将需要检查陈旧存储服务队列项的性能计数器</span><span class="sxs-lookup"><span data-stu-id="ccbf6-130">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="ccbf6-131">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-131">**Issue:**</span></span>

<span data-ttu-id="ccbf6-132">Lync Server 存储服务使用 Windows Fabric 进行复制。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-132">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="ccbf6-133">如果在主前端服务器上删除了数据, 但对辅助前端服务器的删除失败, 例如, 如果前端服务器上出现意外关机或错误, 则数据可以留下并 "孤立"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-133">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="ccbf6-134">孤立数据可能导致性能下降并浪费驱动器空间。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-134">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="ccbf6-135">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-135">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-136">若要解决此问题, 如果\_使用\_\_\_的事件 LYSS DB 空间错误 (id = 32058) 和在\_事件\_日志\_中\_生成了关键 (id = 32059) 的 LYSS db 空间, 管理员应检查前端服务器上的性能计数器在**LS: LYSS-** 具有 LYSS 名称的存储服务 API 上 **-当前存储服务陈旧队列项的数量**。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-136">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="ccbf6-137">如果此性能计数器具有较高的值 (例如, 大于 50000), 管理员应在 Lync Server 2013 资源工具包中运行 CleanuUpStorageServiceData 工具, 该工具将删除池中的所有孤立数据。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-137">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="ccbf6-138">有关该工具的详细信息, 请参阅 Lync Server 2013 资源工具包文档。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-138">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="ccbf6-139">每当服务器或池中的 IP 地址配置发生更改时, 都需要重新启动 Lync Server 服务</span><span class="sxs-lookup"><span data-stu-id="ccbf6-139">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="ccbf6-140">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-140">**Issue:**</span></span>

<span data-ttu-id="ccbf6-141">当为 Lync Server 2013 部署更改 IP 地址配置时 (例如从 IPv4 更改为双重堆栈或从双堆栈更改到 Ipv6) 时, 并非所有服务器组件都将获取配置更改, 直到重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-141">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="ccbf6-142">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-142">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-143">要解决此问题, 请在更改部署的 IP 地址配置后重新启动 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-143">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="ccbf6-144">若要执行此操作, 请在 Lync Server 命令行管理程序中运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-144">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```
    Stop-CsWindowsService -graceful
   ```

   ```
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="ccbf6-145">Lync Server 2013 管理包中不再提供电话拨入式会议合成事务 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ccbf6-145">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="ccbf6-146">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-146">**Issue:**</span></span>

<span data-ttu-id="ccbf6-147">Lync Server 2013 管理包中不再提供电话拨入式会议综合事务 cmdlet **CsDialInConferencing** 。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-147">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="ccbf6-148">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-148">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-149">仅在企业内部支持使用电话拨入式会议综合事务 cmdlet **Test CsDialInConferencing** 。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-149">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="ccbf6-150">管理员可以继续使用 Lync Server Management Shell 中的 cmdlet 进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-150">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="ccbf6-151">如果需要, 企业还可以开发专用管理包以在内部运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-151">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="ccbf6-152">如果在将日志文件复制到网络共享时网络流量中断, 集中式日志记录服务将停止</span><span class="sxs-lookup"><span data-stu-id="ccbf6-152">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="ccbf6-153">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-153">**Issue:**</span></span>

<span data-ttu-id="ccbf6-154">将集中式日志记录服务配置为使用网络路径 ( **CsClsConfiguration** Cmdlet 的 CacheFileNetworkFolder 参数的值是有效的 UNC 路径) 时, 缓存的日志文件将被复制到网络共享。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-154">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="ccbf6-155">如果复制文件时网络流量中断, 则会发生异常, 导致集中式日志记录服务停止。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-155">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="ccbf6-156">该服务配置为自动重启三次, 因此服务将从前三个例外中恢复。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-156">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="ccbf6-157">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-157">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-158">此问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-158">There is no workaround for this issue.</span></span> <span data-ttu-id="ccbf6-159">若要确定此问题, 请从记录 "Lync Server 集中式日志记录服务代理" 服务意外终止的 "服务控制管理器" 监视事件 ID 7031 的事件日志。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-159">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="ccbf6-160">如果发生此情况超过三次, 请使用**CsWindowService** cmdlet 手动重启该服务。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-160">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="ccbf6-161">需要手动导入存储服务队列项</span><span class="sxs-lookup"><span data-stu-id="ccbf6-161">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="ccbf6-162">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-162">**Issue:**</span></span>

<span data-ttu-id="ccbf6-163">Lync Server 2013 存储有关会议和即时消息的数据, 例如已存档的邮件和呼叫详细记录 (CDR), 位于每个前端服务器上的数据库中。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-163">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="ccbf6-164">数据在被处理后将存储在数据库中, 然后再传递到预期的目标。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-164">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="ccbf6-165">为了提高性能, Lync Server 2013 定期从本地数据库导出未在长时间处理的队列项, 并将其保存在文件存储中。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-165">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="ccbf6-166">如果文件存储不可用, 项目将存储在每台前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-166">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="ccbf6-167">发生同样的操作以防止池故障转移期间的数据丢失。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-167">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="ccbf6-168">在导出操作过程中, Lync Server 存储服务将记录事件日志中的每个阶段, 事件 Id 为 32075 (完全刷新操作已启动)、32076 (完全刷新)、32082 (已启动维护级别刷新)、32083 (维护级别刷新)已完成), 32089 (由于填充数据库而发生刷新)。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-168">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="ccbf6-169">此数据不会自动导入回系统以进行处理并传递到其最终目标 (SQL Server 或 Exchange Server)。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-169">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="ccbf6-170">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-170">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-171">要将数据导入到系统, 管理员需要使用 Lync Server 资源工具包中的 ImportStorageServiceData 工具, 该工具会将数据重新添加到系统中, 以便进行处理并传递到最终目标。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-171">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="ccbf6-172">如果 UseNormalizationRules 的默认值更改为 False, 则通讯簿 Web 查询搜索将失败</span><span class="sxs-lookup"><span data-stu-id="ccbf6-172">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="ccbf6-173">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-173">**Issue:**</span></span>

<span data-ttu-id="ccbf6-174">如果 UseNormalizationRules 的默认值更改为 "否", 通讯簿 Web 查询搜索将失败。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-174">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="ccbf6-175">默认值更改后, Lync 客户端用户将无法使用 Lync 通讯簿 web 查询搜索用户。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-175">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="ccbf6-176">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-176">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-177">如果 UseNormalizationRules 的默认值设置为 False, 以便用户可以使用在没有 Lync Server 2013 的 Active Directory 域服务中定义的电话号码应用规范化规则, 请执行下列操作以解决此问题:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-177">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="ccbf6-178">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-178">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ccbf6-179">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="ccbf6-179">Do one of the following:</span></span>
    
      - <span data-ttu-id="ccbf6-180">如果你的部署仅包括 Lync Server 2013 服务器, 请在全局级别上运行以下 cmdlet, 将 UseNormalizationRules 和 IgnoreGenericRules 的值更改为 True:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-180">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="ccbf6-181">如果你的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通信服务器 2007 R2 的组合, 请运行以下 cmdlet, 并将其分配给拓扑中的每个 Lync Server 2013 池:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-181">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="ccbf6-182">等待 CMS 复制在所有池上进行。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-182">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="ccbf6-183">修改你的部署的电话规范化规则文件以清除内容。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-183">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="ccbf6-184">该文件位于每个 Lync Server 2013 池的文件共享中。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-184">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="ccbf6-185">如果文件不存在, 则创建一个名为 "\_公司电话\_号码\_规范化\_规则 .txt" 的空文件。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-185">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="ccbf6-186">请等待几分钟, 让所有前端池读取新文件。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-186">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="ccbf6-187">在部署中的每个 Lync Server 2013 池中运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-187">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="ccbf6-188">每个 Lync 2013 池每天生成一个通讯簿服务器错误事件21054</span><span class="sxs-lookup"><span data-stu-id="ccbf6-188">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="ccbf6-189">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-189">**Issue:**</span></span>

<span data-ttu-id="ccbf6-190">在执行日常维护时, Lync Server 2013 通讯簿服务器每天会生成错误事件21054一次。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-190">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="ccbf6-191">此错误也会在每次管理员运行**csAddressBook** cmdlet 时生成, 即使更新成功也是如此。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-191">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="ccbf6-192">但是, 更新成功后, 可以安全地忽略此错误事件。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-192">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="ccbf6-193">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-193">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-194">遇到此错误事件时, 请运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-194">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="ccbf6-195">如果 cmdlet 报告没有未索引或已放弃的对象, 则可以安全地忽略错误事件21054。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-195">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="ccbf6-196">此外, "System Center Operations Manager" 中应关闭 "正确索引的通讯簿用户" 的关键运行状况指示器 (KHI) "。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-196">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="ccbf6-197">在边缘池上配置 IPv6 时, 请求可能失败</span><span class="sxs-lookup"><span data-stu-id="ccbf6-197">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="ccbf6-198">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-198">**Issue:**</span></span>

<span data-ttu-id="ccbf6-199">在 Edge 池上配置 IPv6 时, 对边缘池的某些请求可能会失败。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-199">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="ccbf6-200">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-200">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-201">要解决此问题, 请不要使用 IPv6 配置边缘池。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-201">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="ccbf6-202">CsPoolFailback cmdlet 在池故障回复期间可能失败</span><span class="sxs-lookup"><span data-stu-id="ccbf6-202">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="ccbf6-203">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-203">**Issue:**</span></span>

<span data-ttu-id="ccbf6-204">尝试故障恢复池时, **csPoolFailback** cmdlet 可能会失败, 出现错误 "无法在重复尝试后完成 hydration 进程"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-204">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="ccbf6-205">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-205">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-206">若要解决此问题, 请再次运行 cmdlet, 然后等到 cmdlet 成功。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-206">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="ccbf6-207">请注意, 故障回复过程可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-207">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="ccbf6-208">对于包含20000用户的池, 最多可能需要60分钟。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-208">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="ccbf6-209">将前端服务器添加到已建立的池-混合版、Skype for business Online 时可能会发生数据丢失问题</span><span class="sxs-lookup"><span data-stu-id="ccbf6-209">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="ccbf6-210">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-210">**Issue:**</span></span>

<span data-ttu-id="ccbf6-211">在池具有多个前端服务器的环境中, 你可能会遇到此问题, 你可以重新启动其中一个前端服务器, 或者添加以前不属于该池的新前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-211">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="ccbf6-212">数据存档的用户可能会在为池建立稳定的数据存档之前遇到数据丢失。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-212">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="ccbf6-213">此期的潜在数据丢失时间限制为15分钟, 供人员与人员对话, 而30分钟用于会议。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-213">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="ccbf6-214">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-214">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-215">执行维护时, 应将池故障转移到另一个池中, 然后在服务器上执行维护任务, 而不是在池中逐个启动前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-215">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="ccbf6-216">您也可以在执行维护任务之前使服务不可用, 然后在维护完成后恢复可用性。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-216">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="ccbf6-217">管理员无法通过使用 CsClientAccessLicense cmdlet 获取许可证持有人的计数</span><span class="sxs-lookup"><span data-stu-id="ccbf6-217">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="ccbf6-218">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-218">**Issue:**</span></span>

<span data-ttu-id="ccbf6-219">管理员无法使用**CsClientAccessLicense** cmdlet 获取准确的客户许可证使用情况。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-219">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="ccbf6-220">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-220">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-221">若要检查服务器许可证类型, 可以运行**CsService** cmdlet 以检索所有数据库的完全限定的域名 (FDQNs)。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-221">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="ccbf6-222">如果前端服务器的 FQDN 与后端数据库的 FQDN 相同, 则许可证是标准版许可证。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-222">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="ccbf6-223">否则, 许可证是企业版许可证。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-223">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="ccbf6-224">客户许可证持有人计数未准确报告</span><span class="sxs-lookup"><span data-stu-id="ccbf6-224">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="ccbf6-225">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-225">**Issue:**</span></span>

<span data-ttu-id="ccbf6-226">确定客户许可证计数时, 你可能会遇到以下情况:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-226">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="ccbf6-227">**移动用户的不准确许可证计数**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-227">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="ccbf6-228">许可证计数基于基于设备的用户的唯一 IP 地址的数量。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-228">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="ccbf6-229">许可证计数将按以下方式受到限制:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-229">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="ccbf6-230">如果用户的 IP 地址在 Lync 会话期间发生更改, 将 overcounted 许可证。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-230">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="ccbf6-231">当用户使用桌面客户端从多个位置连接到 Lync 服务器时, 可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-231">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="ccbf6-232">如果用户使用移动客户端连接, 将 undercounted 许可证, 因为无法确定设备的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-232">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="ccbf6-233">**对于 Lync 客户端、Lync 客户端调用 PSTN 线路以及将 Lync 呼叫转发到 PSTN 线路的公共交换电话网络 (PSTN) 呼叫, 许可证均计入两次。**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-233">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="ccbf6-234">在以下情况下, 将对两个附加许可证 (而不是一个许可证) 进行计数, 因为将对电话号码和 Lync 用户进行计数以确定所用的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-234">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="ccbf6-235">若要获取准确的授权数据, 请手动删除由电话号码生成的许可证。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-235">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="ccbf6-236">对 Lync 的 PSTN 电话呼叫</span><span class="sxs-lookup"><span data-stu-id="ccbf6-236">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="ccbf6-237">对 PSTN 线路的 Lync 呼叫</span><span class="sxs-lookup"><span data-stu-id="ccbf6-237">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="ccbf6-238">对 Lync 的 PSTN 呼叫, 然后 Lync 将呼叫转发到 PSTN 线路。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-238">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="ccbf6-239">将对其中一个 PSTN 线路进行计数。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-239">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="ccbf6-240">**将不会对已登录 Lync 手机的许可证进行计数**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-240">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="ccbf6-241">当用户使用 Lync 认证的电话时, 如果手机登录并保持连接 (这将保留其登录状态), 则不会将手机计为使用许可证 (如果在手机登录后出现许可证的查询)。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-241">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="ccbf6-242">**为 PSTN 手机加入会议而计数的许可证**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-242">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="ccbf6-243">当用户使用 PSTN 手机加入会议时, 许可证将不准确地计入加入会议的许可证。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-243">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="ccbf6-244">但是, 使用 PSTN 手机加入会议时无需许可证。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-244">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="ccbf6-245">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-245">**Workaround:**</span></span>

1.  <span data-ttu-id="ccbf6-246">**移动用户的不准确许可证计数**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-246">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="ccbf6-247">你可以手动标识属于同一设备的 IP 地址, 然后在许可证计数中删除其中一个。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-247">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="ccbf6-248">与 Lync 客户端连接的移动设备不存在此问题的解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-248">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="ccbf6-249">**对于 Lync 客户端、Lync 客户端调用 PSTN 线路以及将 Lync 呼叫转发到 PSTN 线路, 许可证将计入两次: PSTN 呼叫。**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-249">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="ccbf6-250">你将需要手动标识 PSTN 电话号码并删除为其生成的许可证计数。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-250">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="ccbf6-251">**不会对已登录 Lync 手机的许可证进行计数**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-251">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="ccbf6-252">您可以将 Lync phone 配置为注销, 然后再按常规间隔 (如每3个月) 登录。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-252">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="ccbf6-253">**为 PSTN 手机加入会议而计数的许可证**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-253">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="ccbf6-254">你可以手动标识用于加入会议的 PSTN 电话号码, 并删除由电话号码生成的许可证。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-254">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="ccbf6-255">升级到 Silverlight 5 后, Lync Server 控制面板在 VMware 环境中停止工作</span><span class="sxs-lookup"><span data-stu-id="ccbf6-255">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="ccbf6-256">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-256">**Issue:**</span></span>

<span data-ttu-id="ccbf6-257">如果在 VMware 环境中使用 Lync Server 控制面板, 则在将 Microsoft Silverlight 升级到版本5后, Lync Server 控制面板可能会停止工作。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-257">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="ccbf6-258">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-258">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-259">若要解决此问题, 请执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-259">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="ccbf6-260">卸载 Silverlight 5, 然后从[https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)安装 silverlight 4。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-260">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="ccbf6-261">从不是 VMware 虚拟计算机的计算机访问 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-261">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="ccbf6-262">为此, 如果在计算机上安装了 Lync Server 管理工具, 则可以从服务器上的 Windows "**开始**" 菜单启动 Lync server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-262">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="ccbf6-263">您也可以使用 web 浏览器访问 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-263">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="ccbf6-264">该 URL 将类似于\<https://前端\_池\_fqdn/cscp.\></span><span class="sxs-lookup"><span data-stu-id="ccbf6-264">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="ccbf6-265">在 Active Directory 中修改了用户的识别名后, 通讯簿服务中的用户信息不会更新</span><span class="sxs-lookup"><span data-stu-id="ccbf6-265">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="ccbf6-266">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-266">**Issue:**</span></span>

<span data-ttu-id="ccbf6-267">如果在 Active Directory 域服务中更改了用户的可分辨名称 (也称为 DN), 则不会在通讯簿服务 (ABS) 中更新任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-267">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="ccbf6-268">这不会影响用户的登录或状态, 但如果 SIP 地址也发生更改, 它将阻止用户进行通信, 因为搜索将返回过期的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-268">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="ccbf6-269">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-269">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-270">若要解决此问题, 请不要更改用户的 DN。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-270">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="ccbf6-271">如果将用户的 DN 还原为以前的值, 更新将反映在通讯簿服务中。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-271">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="ccbf6-272">安装</span><span class="sxs-lookup"><span data-stu-id="ccbf6-272">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="ccbf6-273">使用非 ASCII 字符可能会导致 Lync 服务器启动失败</span><span class="sxs-lookup"><span data-stu-id="ccbf6-273">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="ccbf6-274">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-274">**Issue:**</span></span>

<span data-ttu-id="ccbf6-275">如果目标文件夹名称包含非 ASCII 字符 (包括 UNICODE、双字节字符集 (DBCS)、UTF-8 和 UTF-16), 则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-275">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="ccbf6-276">此外, 安装可能会成功, 但如果以下任何一项中包含非 ASCII 字符, 则服务器不会启动:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-276">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="ccbf6-277">计算机名</span><span class="sxs-lookup"><span data-stu-id="ccbf6-277">Computer name</span></span>

  - <span data-ttu-id="ccbf6-278">域名</span><span class="sxs-lookup"><span data-stu-id="ccbf6-278">Domain name</span></span>

  - <span data-ttu-id="ccbf6-279">用户名</span><span class="sxs-lookup"><span data-stu-id="ccbf6-279">User name</span></span>

  - <span data-ttu-id="ccbf6-280">用户 SIP URI</span><span class="sxs-lookup"><span data-stu-id="ccbf6-280">User SIP URI</span></span>

  - <span data-ttu-id="ccbf6-281">服务帐户名称</span><span class="sxs-lookup"><span data-stu-id="ccbf6-281">Service account name</span></span>

<span data-ttu-id="ccbf6-282">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-282">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-283">仅在目标文件夹名称、计算机名称、域名、用户名、用户 SIP URI 和服务帐户名称中使用 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-283">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="ccbf6-284">当模块调用 IIS 7.5 中的 InsertEntityBody 方法时, 出现堆损坏问题的修复程序必须在安装 Lync Server 2013 之前安装</span><span class="sxs-lookup"><span data-stu-id="ccbf6-284">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="ccbf6-285">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-285">**Issue:**</span></span>

<span data-ttu-id="ccbf6-286">当模块调用 IIS 7.5[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)() 中所述的 InsertEntityBody 方法 (如 Microsoft 知识库文章 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)) 中所述), 在安装 Lync Server 2013 之前, 必须先安装 "堆损坏" 的修复程序。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-286">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="ccbf6-287">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-287">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-288">从 Microsoft 下载中心下载并安装修补程序[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-288">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="ccbf6-289">Lync Server 2013 无法在 ITA Windows Server 2012 操作系统 RTM 版本上安装</span><span class="sxs-lookup"><span data-stu-id="ccbf6-289">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="ccbf6-290">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-290">**Issue:**</span></span>

<span data-ttu-id="ccbf6-291">由于 Windows Fabric 安装失败, Lync Server 2013 安装在 ITA Windows Server 2012 上失败。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-291">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="ccbf6-292">由于创建的结构跟踪的时间格式为 HH: MM: SS, 因此 Windows Fabric 安装失败。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-292">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="ccbf6-293">但是, 在 ITA Windows Server 中, 时间格式为 HH。MM.SS。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-293">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="ccbf6-294">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-294">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-295">要解决此问题, 请在安装 Lync Server 2013 之前更新系统注册表。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-295">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="ccbf6-296">需要更新的注册表项为: HKEY\_用户。\\默认\\控制面板\\国际\\sTimeFormat。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-296">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="ccbf6-297">使用 Windows PowerShell 命令行界面将 sTimeFormat 的值更改为 HH: mm: ss, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-297">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="ccbf6-298">启动 Windows PowerShell 并运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-298">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="ccbf6-299">若要查看当前值, 请运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-299">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="ccbf6-300">记下 sTimeFormat 的当前值, 以便在安装完成后可以恢复它。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-300">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="ccbf6-301">若要设置为新值, 请运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-301">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="ccbf6-302">成功安装 Lync Server 2013 后, 通过运行以下 cmdlet 还原 sTimeFormat 的原始值:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-302">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="ccbf6-303">ItemProperty 在步骤3中记下的 "设置-$a 名称" <值。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-303">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="ccbf6-304">上方> "</span><span class="sxs-lookup"><span data-stu-id="ccbf6-304">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="ccbf6-305">移动性</span><span class="sxs-lookup"><span data-stu-id="ccbf6-305">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="ccbf6-306">服务器故障转移过程中移动客户端的问题</span><span class="sxs-lookup"><span data-stu-id="ccbf6-306">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="ccbf6-307">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-307">**Issue:**</span></span>

<span data-ttu-id="ccbf6-308">当 Lync 服务器失败并且故障转移过程开始时, 以下问题可能会影响移动客户端用户:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-308">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="ccbf6-309">在故障转移开始后, 没有传入 Lync 呼叫或最长10分钟的信号。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-309">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="ccbf6-310">无法接受传入的聊天请求</span><span class="sxs-lookup"><span data-stu-id="ccbf6-310">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="ccbf6-311">如果故障服务器是用户的主服务器, 则无法加入会议</span><span class="sxs-lookup"><span data-stu-id="ccbf6-311">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="ccbf6-312">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-312">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-313">此问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-313">There is no workaround for this issue.</span></span> <span data-ttu-id="ccbf6-314">故障转移过程完成后, 将恢复正常功能。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-314">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="ccbf6-315">如果移动用户拒绝来自另一个 Lync 终结点的传入呼叫, 则该呼叫将在 Lync 移动客户端上显示为错过的转换</span><span class="sxs-lookup"><span data-stu-id="ccbf6-315">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="ccbf6-316">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-316">**Issue:**</span></span>

<span data-ttu-id="ccbf6-317">如果移动用户拒绝传入呼叫, 并且该呼叫来自另一个 Lync 终结点, 则该呼叫将在 Lync 移动客户端中显示为错过的对话, 而不是在设备呼叫列表中的呼叫中显示。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-317">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="ccbf6-318">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-318">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-319">此问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-319">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="ccbf6-320">在搜索联系人时, 移动客户端可能不会显示联盟联系人的显示名称</span><span class="sxs-lookup"><span data-stu-id="ccbf6-320">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="ccbf6-321">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-321">**Issue:**</span></span>

<span data-ttu-id="ccbf6-322">联盟联系人的显示名称可能不会在某些情况下显示, 例如当在联系人列表中搜索联盟联系人时。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-322">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="ccbf6-323">当 Lync 移动客户端没有联系人的活动状态订阅时, 可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-323">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="ccbf6-324">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-324">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-325">此问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-325">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="ccbf6-326">在移动客户端中, 错过的对话 (即会议邀请) 缺少被邀请者和时间戳信息</span><span class="sxs-lookup"><span data-stu-id="ccbf6-326">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="ccbf6-327">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-327">**Issue:**</span></span>

<span data-ttu-id="ccbf6-328">在移动客户端中, 当错过的对话是会议邀请时, 错过的对话消息中缺少被邀请者和时间戳信息。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-328">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="ccbf6-329">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-329">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-330">此问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-330">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="ccbf6-331">使用 VoIP 进行呼叫的移动客户端用户无法为在 Exchange 2010 或更早版本中配置的用户留下语音邮件</span><span class="sxs-lookup"><span data-stu-id="ccbf6-331">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="ccbf6-332">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-332">**Issue:**</span></span>

<span data-ttu-id="ccbf6-333">如果移动客户端用户使用 VoIP 进行呼叫, 用户将无法为配置为在 Microsoft Exchange Server 2007 或 Microsoft Exchange Server 2010 中使用语音邮件的用户留下语音邮件消息。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-333">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="ccbf6-334">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-334">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-335">若要解决此问题, 请将 Exchange 2010 与 SP1 或更高版本的 Microsoft Exchange Server 配合使用。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-335">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="ccbf6-336">对移动客户端上的客户端版本配置使用带 URL 的块时, 可能会显示错误消息</span><span class="sxs-lookup"><span data-stu-id="ccbf6-336">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="ccbf6-337">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-337">**Issue:**</span></span>

<span data-ttu-id="ccbf6-338">当对移动客户端上的客户端版本配置使用**带 URL 的块**时, 可能会在客户端版本不受支持时显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-338">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="ccbf6-339">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-339">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-340">要解决此问题, 请将客户端版本配置配置为使用 "**阻止**", 而不是 "使用**URL 阻止**"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-340">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="ccbf6-341">网络会议</span><span class="sxs-lookup"><span data-stu-id="ccbf6-341">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="ccbf6-342">在 Lync Server 2013 前端服务器上运行的防病毒软件可能会导致应用程序域循环, 这会暂时中断 Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013 客户端的服务</span><span class="sxs-lookup"><span data-stu-id="ccbf6-342">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="ccbf6-343">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-343">**Issue:**</span></span>

<span data-ttu-id="ccbf6-344">防病毒软件可以触发应用程序域重启, 这可能会导致 Lync 移动服务2013和统一通信 (UC) Web API 客户端应用程序 (Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013) 丢失其状态。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-344">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="ccbf6-345">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-345">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-346">若要解决此问题, 请从防病毒扫描中排除包含 Web 组件和 .NET framework 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-346">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="ccbf6-347">有关详细信息, 请参阅 Microsoft 知识库文章 312592: "PRB: 在 ASP.NET 中重新启动并重新启动应用程序时发生错误" 错误[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-347">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="ccbf6-348">应排除下列文件夹:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-348">The following folders should be excluded:</span></span>

  - <span data-ttu-id="ccbf6-349">% ProgramFiles%\\Microsoft Lync Server 2013\\Web 组件\\Mcx\\Ext</span><span class="sxs-lookup"><span data-stu-id="ccbf6-349">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="ccbf6-350">% ProgramFiles%\\Microsoft Lync Server 2013\\Web 组件\\Mcx\\Int</span><span class="sxs-lookup"><span data-stu-id="ccbf6-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="ccbf6-351">% ProgramFiles%\\Microsoft Lync Server 2013\\Web 组件\\Ucwa\\Int</span><span class="sxs-lookup"><span data-stu-id="ccbf6-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="ccbf6-352">% ProgramFiles%\\Microsoft Lync Server 2013\\Web 组件\\Ucwa\\Ext</span><span class="sxs-lookup"><span data-stu-id="ccbf6-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="ccbf6-353">% Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\Config</span><span class="sxs-lookup"><span data-stu-id="ccbf6-353">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="ccbf6-354">必须在 Windows Internet Explorer 中启用 ActiveX 控件或本机 XMLHTTP 支持才能成功加入会议</span><span class="sxs-lookup"><span data-stu-id="ccbf6-354">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="ccbf6-355">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-355">**Issue:**</span></span>

<span data-ttu-id="ccbf6-356">如果用户在 Windows Internet Explorer Internet 浏览器设置中禁用了 ActiveX 控件和本机 XMLHTTP 支持, 则如果将 Internet Explorer 选作默认浏览器, 用户将无法加入会议。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-356">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="ccbf6-357">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-357">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-358">在 Internet Explorer 中启用 ActiveX 控件或 "本机 XMLHTTP 支持"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-358">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="ccbf6-359">Lync Server Web 会议服务无法从关键模式恢复</span><span class="sxs-lookup"><span data-stu-id="ccbf6-359">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="ccbf6-360">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-360">**Issue:**</span></span>

<span data-ttu-id="ccbf6-361">如果关键模式已启用存档, 则在系统发生故障时, 将启动关键模式, 并且会议将不再适用于参与者。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-361">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="ccbf6-362">管理员修复了系统故障 (如修复数据库问题) 后, 数据会议服务不会自动恢复, 管理员必须手动重启会议服务才能继续会议。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-362">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="ccbf6-363">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-363">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-364">修复系统故障后, 管理员需要手动重启会议服务。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-364">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="ccbf6-365">网络会议服务忽略外部 Office Web App 服务器的 HTTP 代理</span><span class="sxs-lookup"><span data-stu-id="ccbf6-365">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="ccbf6-366">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-366">**Issue:**</span></span>

<span data-ttu-id="ccbf6-367">如果你已在 Internet、外围网络和 Web 会议服务中部署了 Web 会议服务外部的 Office Web Apps 服务器 (即不在内部公司网络中的服务器), 则需要 HTTP 代理来连接到该服务器,Office Web Apps 服务器发现将失败。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-367">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="ccbf6-368">Web 会议服务忽略 HTTP 代理设置, 如 Office Web App Server 安装程序的拓扑生成器中所定义。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-368">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="ccbf6-369">因此, Lync 客户端将无法与会议中的其他参与者共享 Microsoft PowerPoint 2010。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-369">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="ccbf6-370">如果你在本地安装 Lync Server, 并且还在内部网络中配置 Office Web Apps 本地服务器, 则不需要代理配置。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-370">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="ccbf6-371">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-371">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-372">唯一的解决方法是不需要使用 HTTP 代理与外部 Office Web Apps 服务器通信的部署配置。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-372">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="ccbf6-373">不支持向音频会议提供商会议添加视频</span><span class="sxs-lookup"><span data-stu-id="ccbf6-373">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="ccbf6-374">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-374">**Issue:**</span></span>

<span data-ttu-id="ccbf6-375">如果用户已加入音频会议提供商会议, 则不支持添加视频。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-375">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="ccbf6-376">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-376">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-377">此问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-377">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="ccbf6-378">启用了 IPv6 的拓扑强制使用 Lync Web App Silverlight 插件自动更新, 以确保可以从 Lync Web App 运行屏幕共享功能</span><span class="sxs-lookup"><span data-stu-id="ccbf6-378">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="ccbf6-379">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-379">**Issue:**</span></span>

<span data-ttu-id="ccbf6-380">当拓扑配置为启用 IPv6 时, 如果已安装早期版本的屏幕共享插件, 则用户无法从 Lync Web App 客户端共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-380">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="ccbf6-381">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-381">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-382">若要在通过 Lync Web App 加入会议时强制更新屏幕共享插件的最新版本, 请在以下两个文件中将**MinSupportedBuildVersion**的值从 "4.0.7457.0" 更改为 "4.0.7577.380":</span><span class="sxs-lookup"><span data-stu-id="ccbf6-382">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="ccbf6-383">% ProgramFiles%\\Microsoft Lync Server 15\\Web 组件\\连接\\到\\Int\\客户\\端插件 ReachAppShPluginProperties</span><span class="sxs-lookup"><span data-stu-id="ccbf6-383">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="ccbf6-384">% ProgramFiles%\\Microsoft Lync Server 15\\Web 组件\\访问\\外部\\的\\客户\\端插件 ReachAppShPluginProperties</span><span class="sxs-lookup"><span data-stu-id="ccbf6-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="ccbf6-385">企业语音</span><span class="sxs-lookup"><span data-stu-id="ccbf6-385">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="ccbf6-386">在某些情况下, 在配置为使用 IPv4 和 IPv6 双堆栈的计算机上运行的 Lync 客户端可能不支持依赖于计算机的 IP 子网的功能, 例如 E911、媒体绕过、呼叫许可控制和基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="ccbf6-386">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ccbf6-387">本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-387">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ccbf6-388">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-388">**Issue:**</span></span>

<span data-ttu-id="ccbf6-389">当 Lync 客户端运行在启用了 IPv4 和 IPv6 双堆栈且基于代理服务器的 DNS 解析的计算机上时, 客户端可以使用计算机的 IPv6 地址登录。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-389">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="ccbf6-390">执行此操作后, Lync 客户端将仅支持 IPv6 支持的功能, 不包括 E911、媒体旁路、呼叫许可控制和基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-390">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="ccbf6-391">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-391">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-392">若要解决此问题, 请在客户端计算机上禁用 IPv6 支持。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-392">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="ccbf6-393">如果没有为用户配置企业语音, 用户将需要使用 E164 格式从会议拨出</span><span class="sxs-lookup"><span data-stu-id="ccbf6-393">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="ccbf6-394">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-394">**Issue:**</span></span>

<span data-ttu-id="ccbf6-395">如果没有为用户配置企业语音, 则该用户需要使用 E164 格式成功从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-395">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="ccbf6-396">如果未使用 E164 格式, 则用户无法从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-396">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="ccbf6-397">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-397">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-398">若要解决此问题, 未启用企业语音的用户应使用 E164 格式的数字拨出会议。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-398">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="ccbf6-399">状态</span><span class="sxs-lookup"><span data-stu-id="ccbf6-399">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="ccbf6-400">如果用户已选择 "阻止所有邀请和通信", 而 "统一联系人存储" 为用户打开, 则状态不会被拒绝</span><span class="sxs-lookup"><span data-stu-id="ccbf6-400">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="ccbf6-401">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-401">**Issue:**</span></span>

<span data-ttu-id="ccbf6-402">如果用户已选择 "阻止所有邀请和通信", 而统一联系人存储为用户打开, 则状态不会被拒绝。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-402">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="ccbf6-403">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-403">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-404">若要解决此问题, 您可以为用户关闭 "统一联系人存储"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-404">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="ccbf6-405">若要执行此操作, 请运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-405">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="ccbf6-406">例如：</span><span class="sxs-lookup"><span data-stu-id="ccbf6-406">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="ccbf6-407">Office 通信服务器 2007 R2 用户在混合部署中无法看到 Skype for business Online 用户的状态-混合</span><span class="sxs-lookup"><span data-stu-id="ccbf6-407">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="ccbf6-408">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-408">**Issue:**</span></span>

<span data-ttu-id="ccbf6-409">使用 Lync Server 2013 控制器时, 混合部署中可能会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-409">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="ccbf6-410">托管到 Skype for business Online 的用户的状态显示为本地用户的未知状态。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-410">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="ccbf6-411">此外, 托管到 Skype for Business Online 的用户无法查看 Office 通讯服务器 R2 本地用户的状态。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-411">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="ccbf6-412">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-412">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-413">若要解决此问题, 请将 Skype for business Online 用户的主服务器 (msrtcsip-presencehomeserver) 更改为指向 Lync Server 2013 本地池, 而不是 Lync Server 2013 Director。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-413">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="ccbf6-414">你可以在本地前端服务器上修改此设置。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-414">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="ccbf6-415">此解决方法将正确显示托管到 Office 的 Office 通信服务器 2007 R2 到 Skype for business Online 用户的状态。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-415">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="ccbf6-416">响应组应用程序、呼叫驻留应用程序和组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="ccbf6-416">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="ccbf6-417">在与检索方进行通话期间, 呼叫者可能会听到一秒钟的音乐暂停</span><span class="sxs-lookup"><span data-stu-id="ccbf6-417">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ccbf6-418">本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-418">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ccbf6-419">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-419">**Issue:**</span></span>

<span data-ttu-id="ccbf6-420">通过组呼叫拾取检索呼叫时, 呼叫者在与检索方进行通话的过程中, 可能会听到一秒钟的音乐暂停。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-420">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="ccbf6-421">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-421">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-422">此问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-422">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="ccbf6-423">响应组代理只能通过 Lync Server 2010 代理2010控制台登录和注销, 仅限正式代理组</span><span class="sxs-lookup"><span data-stu-id="ccbf6-423">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="ccbf6-424">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-424">**Issue:**</span></span>

<span data-ttu-id="ccbf6-425">Lync Server 2013 响应组代理可以通过 Lync Server 2010 代理2010控制台登录并注销, 仅限正式代理组。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-425">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="ccbf6-426">在 Lync Server 2010 代理控制台中, 用户只能看到其所属的 Lync Server 2010 响应组。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-426">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="ccbf6-427">他们无法看到它们所属的任何 Lync Server 2013 响应组。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-427">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="ccbf6-428">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-428">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-429">如果响应组代理是 Lync Server 2013 用户, 并且是 Lync Server 2013 正式代理组的一部分, 则用户必须直接通过浏览器中的 web 链接访问 Lync Server 2013 代理控制台, 以便从 Lync Server 2013 代理组登录和注销。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-429">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="ccbf6-430">Lync Server 2010 响应组代理无法代表 Lync Server 2013 响应组发出呼叫</span><span class="sxs-lookup"><span data-stu-id="ccbf6-430">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="ccbf6-431">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-431">**Issue:**</span></span>

<span data-ttu-id="ccbf6-432">作为 Lync Server 2013 响应组代理的 Lync Server 2010 用户无法代表该响应组发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-432">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="ccbf6-433">Lync Server 2013 响应组在 Lync 客户端中将不可用来发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-433">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="ccbf6-434">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-434">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-435">若要解决此问题, 必须将 Lync Server 2010 用户移动到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-435">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="ccbf6-436">在迁移到 Lync Server 2013 之后从 Lync Server 2010 中删除响应组将会阻止该响应组接受任何传入呼叫</span><span class="sxs-lookup"><span data-stu-id="ccbf6-436">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="ccbf6-437">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-437">**Issue:**</span></span>

<span data-ttu-id="ccbf6-438">如果从 lync server 2010 迁移到 Lync server 2013 的响应组已从 Lync server 2010 通过 Lync Server 控制面板或 Lync Server 管理外壳删除, 则 Lync Server 2013 中的 "响应" 组将停止接收任何传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-438">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="ccbf6-439">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-439">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-440">若要解决此问题, 请不要从 lync server 2010 中删除已从 Lync Server 2010 迁移到 Lync Server 2013 的任何响应组。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-440">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="ccbf6-441">如果响应组已删除, 则应在 Lync Server 2013 中重新部署它。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-441">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="ccbf6-442">当新的托管工作流在创建时设置为 "非活动" 时, 工作流的部署将失败</span><span class="sxs-lookup"><span data-stu-id="ccbf6-442">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="ccbf6-443">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-443">**Issue:**</span></span>

<span data-ttu-id="ccbf6-444">当新的托管工作流在创建时设置为 "非活动" 时, 工作流的部署将失败。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-444">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="ccbf6-445">当工作流在创建时设置为 "非活动" 时遇到此问题, 但不会影响已编辑的工作流, 以便在部署后将其设置为 "非活动"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-445">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="ccbf6-446">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-446">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-447">创建和部署工作流时, 将工作流设置为 "活动", 然后部署它。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-447">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="ccbf6-448">成功部署工作流后, 可以编辑工作流并将其设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-448">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="ccbf6-449">如果响应组已导入到备份池中, 则从所有者池删除响应组将阻止备份池的响应组在故障转移期间接受任何传入调用</span><span class="sxs-lookup"><span data-stu-id="ccbf6-449">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="ccbf6-450">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-450">**Issue:**</span></span>

<span data-ttu-id="ccbf6-451">如果已将主池拥有的响应组导入到备份池中, 而不覆盖所有者, 并且该响应组已从所有者池中删除, 则在故障转移过程中, 备份池中的响应组不会接受任何传入调用。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-451">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="ccbf6-452">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-452">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-453">你将需要在主池中重新部署响应组。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-453">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="ccbf6-454">然后, 你将需要从主池中导出响应组配置, 并再次将其导入到备份池。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-454">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="ccbf6-455">您也可以在备份池中重新创建响应组。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-455">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="ccbf6-456">在这种情况下, 备份池将是响应组的所有者池。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-456">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="ccbf6-457">如果检索请求是代表响应组执行的, 则无法从呼叫寄存应用程序检索寄存通话</span><span class="sxs-lookup"><span data-stu-id="ccbf6-457">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="ccbf6-458">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-458">**Issue:**</span></span>

<span data-ttu-id="ccbf6-459">当满足以下条件时, 对寄存调用的检索请求将失败:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-459">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="ccbf6-460">代理是匿名响应组的一部分</span><span class="sxs-lookup"><span data-stu-id="ccbf6-460">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="ccbf6-461">工程师尝试通过匿名响应组从呼叫寄存应用程序检索寄存的呼叫</span><span class="sxs-lookup"><span data-stu-id="ccbf6-461">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="ccbf6-462">工程师通过在 "代表呼叫" 选项或通过 Lync 助理客户端中的相同选项拨打 "轨道" 编号, 尝试检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-462">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="ccbf6-463">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-463">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-464">此问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-464">There are no workarounds for this issue.</span></span> <span data-ttu-id="ccbf6-465">应检索停用呼叫, 而无需代表响应组执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-465">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="ccbf6-466">Lync Server 控制面板、拓扑生成器和规划工具</span><span class="sxs-lookup"><span data-stu-id="ccbf6-466">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="ccbf6-467">规划工具限制</span><span class="sxs-lookup"><span data-stu-id="ccbf6-467">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ccbf6-468">本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-468">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ccbf6-469">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-469">**Issue:**</span></span>

<span data-ttu-id="ccbf6-470">规划部署时, 规划工具具有下列限制:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-470">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="ccbf6-471">最多支持10个中央站点</span><span class="sxs-lookup"><span data-stu-id="ccbf6-471">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="ccbf6-472">每个中心网站最多可以有14个分支网站</span><span class="sxs-lookup"><span data-stu-id="ccbf6-472">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="ccbf6-473">每个中心网站最多可以有240000个用户</span><span class="sxs-lookup"><span data-stu-id="ccbf6-473">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="ccbf6-474">此外, 在计算推荐的拓扑时, 计划工具不包含以下值:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-474">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="ccbf6-475">联机的用户数</span><span class="sxs-lookup"><span data-stu-id="ccbf6-475">The number of users that are homed online</span></span>

  - <span data-ttu-id="ccbf6-476">为 XMPP 联盟启用的用户百分比</span><span class="sxs-lookup"><span data-stu-id="ccbf6-476">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="ccbf6-477">使用 Lync Web App 的用户百分比</span><span class="sxs-lookup"><span data-stu-id="ccbf6-477">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="ccbf6-478">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-478">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-479">这些问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-479">There is no workaround for these issues.</span></span> <span data-ttu-id="ccbf6-480">有关规划工具的详细信息, 请参阅[使用规划工具设计 Lync Server 2013 的拓扑](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-480">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="ccbf6-481">在更新选项时, 计划工具可能不会使用以前为 Edge 网络定义的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="ccbf6-481">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="ccbf6-482">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-482">**Issue:**</span></span>

<span data-ttu-id="ccbf6-483">使用计划工具完成设计后, 如果对 Edge 网络选项进行了更改, 则可能会将其他 IP 地址添加到设计中, 而不是更新现有的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-483">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="ccbf6-484">如果你查看 Edge 网络图表的详细信息, 请选择 "**单击此处以更新你的选项**", 然后在 "配置选项" 对话框中选择 "边缘网络" 选择 **"我希望使用相同的 fqdn 和 IP 地址", 但边缘服务器上的边缘服务的不同端口**。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-484">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="ccbf6-485">如果应用任何更改, 可能会导致新 IP 地址和边缘服务器添加到设计中。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-485">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="ccbf6-486">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-486">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-487">目前尚无解决此问题的方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-487">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="ccbf6-488">在 Lync Server 控制面板中, "将所有用户移至池" 可能无法按预期工作</span><span class="sxs-lookup"><span data-stu-id="ccbf6-488">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="ccbf6-489">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-489">**Issue:**</span></span>

<span data-ttu-id="ccbf6-490">使用 Lync Server 控制面板将所有用户从一个池移动到一个复杂的 Active Directory 环境中的另一个池 (如具有多个域控制器和父/子域的一个池) 时, 可能会返回错误消息, 指出 "指定的用户不是旧用户, 请改用 Move-csuser cmdlet。 "</span><span class="sxs-lookup"><span data-stu-id="ccbf6-490">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="ccbf6-491">这是在复杂的活动目录环境中复制时间较长的结果。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-491">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="ccbf6-492">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-492">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-493">若要解决此问题, 请执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-493">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="ccbf6-494">在 Lync Server 控制面板中使用筛选器搜索旧版用户, 选择这些用户, 然后使用 "**移动所选用户池" 命令**, 而不是**将所有用户移到 "池**"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-494">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="ccbf6-495">使用 lync server Management Shell, 使用 Lync Server cmdlet 以批处理方式移动旧版用户。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-495">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="ccbf6-496">Microsoft Silverlight 浏览器插件更新到版本5后, Lync Server 控制面板在 VMware 环境中停止工作</span><span class="sxs-lookup"><span data-stu-id="ccbf6-496">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="ccbf6-497">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-497">**Issue:**</span></span>

<span data-ttu-id="ccbf6-498">如果您在 VMware 环境中使用 Lync Server 控制面板, 则在将 Silverlight 升级到版本5后, Lync Server 控制面板可能会停止工作。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-498">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="ccbf6-499">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-499">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-500">若要解决此问题, 请执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-500">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="ccbf6-501">卸载 Silverlight 5, 然后从[https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)安装 silverlight 4。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-501">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="ccbf6-502">从不是 VMware 虚拟计算机的计算机上打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-502">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="ccbf6-503">若要从远程计算机打开 Lync Server 控制面板, 请在计算机上安装 Lync Server 管理工具, 然后从 Windows "**开始**" 菜单启动 "lync server" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-503">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="ccbf6-504">您也可以通过在 web 浏览器中输入 URL 来打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-504">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="ccbf6-505">该 URL 将类似于\<https://前端\_池\_fqdn/cscp.\></span><span class="sxs-lookup"><span data-stu-id="ccbf6-505">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="ccbf6-506">在拓扑生成器中删除镜像数据库后, 管理员无法运行 csMirrorDB cmdlet</span><span class="sxs-lookup"><span data-stu-id="ccbf6-506">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="ccbf6-507">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-507">**Issue:**</span></span>

<span data-ttu-id="ccbf6-508">当管理员在拓扑生成器中禁用镜像数据库, 然后在拓扑生成器中删除镜像数据库时, 管理员的待办事项列表中将显示一条消息以运行**csMirrorDatabase** cmdlet 以删除从 SQL Server 进行镜像。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-508">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="ccbf6-509">管理员尝试运行 cmdlet 时失败。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-509">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="ccbf6-510">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-510">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-511">若要删除拓扑生成器中的池的 SQL 镜像, 必须首先使用 cmdlet 在 SQL Server 中删除该镜像。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-511">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="ccbf6-512">随后，你可以使用拓扑生成器删除拓扑中的镜像。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-512">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="ccbf6-513">要删除 SQL Server 中的镜像，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ccbf6-513">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="ccbf6-514">例如, 若要删除镜像并除去用户数据库的数据库, 请键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-514">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="ccbf6-515">*DropExistingDatabasesOnMirror*参数会导致将受影响的数据库从镜像中删除。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-515">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="ccbf6-516">然后，要从拓扑中删除镜像，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ccbf6-516">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="ccbf6-517">在拓扑生成器中，右键单击该池并单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-517">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="ccbf6-518">清除 "**启用 SQL 应用商店镜像**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-518">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="ccbf6-519">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-519">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="ccbf6-520">当您对后端数据库镜像关系进行更改时, 您必须重新启动池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-520">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="ccbf6-521">当管理员尝试删除具有关联见证存储的前端池的部署时, 将在拓扑生成器中返回验证错误</span><span class="sxs-lookup"><span data-stu-id="ccbf6-521">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="ccbf6-522">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-522">**Issue:**</span></span>

<span data-ttu-id="ccbf6-523">如果管理员尝试使用拓扑生成器中的 "**删除部署**" 命令来删除包含具有关联见证存储的前端池的部署, 则拓扑生成器中将显示一个验证错误, 并且该操作不会继续.</span><span class="sxs-lookup"><span data-stu-id="ccbf6-523">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="ccbf6-524">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-524">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-525">若要解决此问题, 请执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-525">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="ccbf6-526">请先删除见证应用商店, 然后再尝试删除该部署。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-526">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="ccbf6-527">为前端池添加见证存储, 然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-527">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="ccbf6-528">计划工具和拓扑生成器之间的持久聊天服务器部署信息不一致</span><span class="sxs-lookup"><span data-stu-id="ccbf6-528">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="ccbf6-529">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-529">**Issue:**</span></span>

<span data-ttu-id="ccbf6-530">当启用灾难恢复的情况下, 当 Lync Server 2013、计划工具为持久聊天服务器部署输出站点拓扑图时, 网站拓扑图包括多个 (物理) 站点, 每个站点都分配有均匀的持久聊天服务器现场.</span><span class="sxs-lookup"><span data-stu-id="ccbf6-530">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="ccbf6-531">在拓扑生成器中, 所有持久聊天服务器都表示为属于单个 (逻辑) 网站, 并在同一个永久聊天服务器池节点下列出。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-531">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="ccbf6-532">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-532">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-533">目前, 我们对此问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-533">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="ccbf6-534">用户应分析持久聊天服务器部署的计划工具的输出, 并修改计划以满足其特定需求。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-534">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="ccbf6-535">本地化</span><span class="sxs-lookup"><span data-stu-id="ccbf6-535">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="ccbf6-536">监控</span><span class="sxs-lookup"><span data-stu-id="ccbf6-536">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="ccbf6-537">在某些情况下, "部署监视报表向导" 显示不正确的字符, 因为使用的是东亚版 Lync Server</span><span class="sxs-lookup"><span data-stu-id="ccbf6-537">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="ccbf6-538">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-538">**Issue:**</span></span>

<span data-ttu-id="ccbf6-539">使用东亚版 Lync Server 2013 (例如, 简体中文)、中文 (繁体)、日语或朝鲜语-在系统区域设置为东亚语言的操作系统上, "部署监视报告" 向导将显示问号或其他字符而不是本地化消息。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-539">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="ccbf6-540">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-540">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-541">若要更正此问题, 请将操作系统和 Lync Server 2013 的区域设置设置为相同的语言, 这将正确显示所有消息。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-541">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="ccbf6-542">Lync Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="ccbf6-542">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="ccbf6-543">在某些情况下, 当单击顶部导航栏中的最后一个项目时, "Lync Server 控制面板" 页面上顶部导航栏中的第一个项目将消失</span><span class="sxs-lookup"><span data-stu-id="ccbf6-543">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="ccbf6-544">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-544">**Issue:**</span></span>

<span data-ttu-id="ccbf6-545">在以下三种已知情况下, 在 Lync Server 控制面板的页面上单击顶部导航栏中的最后一个项目将导致顶部导航栏中的第一个项目消失:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-545">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="ccbf6-546">在法语版本中, 在 "Féderation et accès externe" 页面上, 当单击 "D'accès externe PARTENAIRES" 时, 项目 "Stratégie fédérés XMPP" 将消失。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-546">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="ccbf6-547">在德语版本中的 "客户端" 页面上, 单击 "Pushbenachrichtigungskonfiguration" 时, 项目 "Clientversionskonfiguration" 消失。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-547">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="ccbf6-548">在俄语版本中的 "Конфигурациясети" 页面上, 单击 "Маршрутрегиона" 时, 项目 "Глобально" 消失。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-548">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="ccbf6-549">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-549">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-550">要解决此问题, 请在浏览器中刷新 Lync Server 控制面板的页面。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-550">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="ccbf6-551">将在浏览器中加载页面, 并显示顶部导航栏中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-551">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="ccbf6-552">通讯簿</span><span class="sxs-lookup"><span data-stu-id="ccbf6-552">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="ccbf6-553">在某些语言中, 通讯簿中的索引不会按预期工作</span><span class="sxs-lookup"><span data-stu-id="ccbf6-553">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ccbf6-554">本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-554">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ccbf6-555">如果用户的属性包含索引字段, 并且该字段仅包含无法索引的字符, 则该用户将不会出现在通讯簿中执行的搜索中。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-555">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="ccbf6-556">以下字符和区域设置无法进行索引:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-556">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="ccbf6-557">小写字母、希腊语和亚美尼亚语字符</span><span class="sxs-lookup"><span data-stu-id="ccbf6-557">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="ccbf6-558">大写字符</span><span class="sxs-lookup"><span data-stu-id="ccbf6-558">Upper-case accented characters</span></span>

  - <span data-ttu-id="ccbf6-559">泰语</span><span class="sxs-lookup"><span data-stu-id="ccbf6-559">Thai</span></span>

  - <span data-ttu-id="ccbf6-560">老挝</span><span class="sxs-lookup"><span data-stu-id="ccbf6-560">Lao</span></span>

  - <span data-ttu-id="ccbf6-561">缅甸</span><span class="sxs-lookup"><span data-stu-id="ccbf6-561">Myanmar</span></span>

  - <span data-ttu-id="ccbf6-562">梵文</span><span class="sxs-lookup"><span data-stu-id="ccbf6-562">Devanagari</span></span>

  - <span data-ttu-id="ccbf6-563">文</span><span class="sxs-lookup"><span data-stu-id="ccbf6-563">Ethiopic</span></span>

  - <span data-ttu-id="ccbf6-564">藏文</span><span class="sxs-lookup"><span data-stu-id="ccbf6-564">Tibetan</span></span>

  - <span data-ttu-id="ccbf6-565">孟加拉语</span><span class="sxs-lookup"><span data-stu-id="ccbf6-565">Bengali</span></span>

  - <span data-ttu-id="ccbf6-566">古吉拉特语</span><span class="sxs-lookup"><span data-stu-id="ccbf6-566">Gujarati</span></span>

  - <span data-ttu-id="ccbf6-567">泰卢固语</span><span class="sxs-lookup"><span data-stu-id="ccbf6-567">Telugu</span></span>

  - <span data-ttu-id="ccbf6-568">所有其他印度语脚本</span><span class="sxs-lookup"><span data-stu-id="ccbf6-568">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="ccbf6-569">Lync Web App、Web 计划程序和 Web 组件</span><span class="sxs-lookup"><span data-stu-id="ccbf6-569">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="ccbf6-570">Lync Web 计划程序中某些语言的语言回退、拨入、加入启动器、持久聊天室管理和 OCTab 可能不会按预期工作</span><span class="sxs-lookup"><span data-stu-id="ccbf6-570">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="ccbf6-571">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-571">**Issue:**</span></span>

<span data-ttu-id="ccbf6-572">在 web 浏览器中选择非特定区域设置 (例如, 在 Internet Explorer 中, 在不进一步规范的情况下使用语言\[名称\], 例如 "挪威语 no"), 而不是指定语言、脚本和区域设置的区域设置 (如 "挪威语、博克马尔语 (挪威) \[NB-NO\]") 可能会导致在 Lync Web 计划程序、拨入、加入启动器、持续聊天室管理和 OCTab 中出现意外的显示行为。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-572">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="ccbf6-573">例如, 当选择以下语言之一时, 用户可能会看到英语页面:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-573">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="ccbf6-574">挪威语</span><span class="sxs-lookup"><span data-stu-id="ccbf6-574">Norwegian</span></span>

  - <span data-ttu-id="ccbf6-575">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="ccbf6-575">Portuguese</span></span>

  - <span data-ttu-id="ccbf6-576">塞尔维亚语</span><span class="sxs-lookup"><span data-stu-id="ccbf6-576">Serbian</span></span>

<span data-ttu-id="ccbf6-577">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-577">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-578">如果要选择具有非特定区域设置的语言, 请始终确保你还可以在浏览器语言首选项列表中添加具有特定区域设置的语言 (使用脚本和/或国家/地区代码) 作为另一种语言。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-578">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="ccbf6-579">在某些 Web 浏览器中使用 Lync Web 计划程序、拨入、加入启动器、持续聊天室管理和 OCTab 时, 对阿塞拜疆语和乌兹别克语区域的支持有限。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-579">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ccbf6-580">本节中的信息与 2013 年 2 月版 Lync Server 2013 累积更新相关。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-580">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="ccbf6-581">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-581">**Issue:**</span></span>

<span data-ttu-id="ccbf6-582">使用 Internet Explorer 8 或 Internet Explorer 9 并将浏览器语言设置为阿塞拜疆语 (拉丁语) 或乌兹别克语 (拉丁文) 时, 将以英语或在浏览器中设置的首选语言显示 "拨入" 和 "加入" 启动器页面。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-582">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="ccbf6-583">使用 Firefox 或 Chrome 浏览器时, 如果将浏览器语言设置为 "阿塞拜疆语 (拉丁语)" 或 "乌兹别克语 (拉丁文)", 则 Lync Web App、Lync Web 计划程序和 RGS OCTab 将显示为英语或浏览器的首选语言集。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-583">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="ccbf6-584">在 Safari 浏览器中不支持 "乌兹别克语 (拉丁语)" 区域设置。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-584">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="ccbf6-585">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-585">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-586">这些问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-586">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="ccbf6-587">Lync Web App 的罗马尼亚语版本中的 "加入会议来自" 列表缺少下拉箭头</span><span class="sxs-lookup"><span data-stu-id="ccbf6-587">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="ccbf6-588">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-588">**Issue:**</span></span>

<span data-ttu-id="ccbf6-589">当使用罗马尼亚语版本的 Lync Web App 的用户执行以下步骤时, 下拉列表中不显示 "**加入会议**" 下拉箭头:</span><span class="sxs-lookup"><span data-stu-id="ccbf6-589">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="ccbf6-590">在 "**常规**" 选项卡上选择 "**在此计算机上保存我**"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-590">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="ccbf6-591">选择 "**电话**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-591">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="ccbf6-592">单击 "**加入会议**" 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-592">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="ccbf6-593">用户将看不到指示有比默认**Lync Web 应用**更多的选项, 其中包括:**不加入音频**(在罗马尼亚语、"Nu se asociaža la componenta 音频") 和**新号码**"(在罗马尼亚语中," Număr nou ")。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-593">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="ccbf6-594">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-594">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-595">即使不显示此下拉列表的箭头, 用户仍然可以通过单击默认值来选择列表中的其他设置。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-595">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="ccbf6-596">使用使用土耳其版本的 Lync Web 计划程序时, 当使用 "谁是演示者" 下的 "用户选择" 选项时, 无法保存会议</span><span class="sxs-lookup"><span data-stu-id="ccbf6-596">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="ccbf6-597">**事项**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-597">**Issue:**</span></span>

<span data-ttu-id="ccbf6-598">在土耳其语版本的 Lync Web 计划程序中创建或编辑会议时, 不支持 "谁是演示者" 下的选项 "我选择的人员"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-598">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="ccbf6-599">选中此选项时, 无法保存会议。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-599">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="ccbf6-600">而是显示一条错误消息, 指示无法将一个或多个人员变为演示者。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-600">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="ccbf6-601">**规避**</span><span class="sxs-lookup"><span data-stu-id="ccbf6-601">**Workaround:**</span></span>

<span data-ttu-id="ccbf6-602">若要解决此问题, 用户可以使用默认选项 "来自我的公司的人员" 或任何其他选择, 如 "仅组织者" 或 "每个人 (包括我的公司外的人)"。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-602">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="ccbf6-603">稍后, 组织者可以在加入会议后降级或将其提升到其正确的角色。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-603">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="ccbf6-604">或者, 了解其他语言的用户可以将其浏览器中的语言选择更改为其他43支持的语言之一, 并尝试使用 "我选择的人员" 选项。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-604">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="ccbf6-605">©</span><span class="sxs-lookup"><span data-stu-id="ccbf6-605">Copyright</span></span>

<span data-ttu-id="ccbf6-606">本文档支持软件产品的预发布版本, 该版本可能会在最终商业版发布之前显著更改, 并且是 Microsoft Corporation 的机密和专有信息。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-606">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="ccbf6-607">本协议依照收件人和 Microsoft 之间的保密协议披露。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-607">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="ccbf6-608">本文档仅供提供信息之用, Microsoft 对本文档不作任何明示或暗示的担保。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-608">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="ccbf6-609">本文档中的信息 (包括 URL 和其他互联网网站参考) 如有更改, 恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-609">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="ccbf6-610">使用本文档的全部风险或结果由用户承担。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-610">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="ccbf6-611">除非另有说明, 否则此处的示例中所描述的公司、组织、产品、域名、电子邮件地址、徽标、人员、地点和事件均属虚构。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-611">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="ccbf6-612">无意与任何真实公司、组织、产品、域名、电子邮件地址、徽标、人员、地点或事件相关联, 也不应进行推断。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-612">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="ccbf6-613">遵守所有适用的著作权法是用户的责任。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-613">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="ccbf6-614">在不限制版权所辖权利的情况下, 本文档的任何部分均不得被复制、存储或引入检索系统, 或者以任何形式或通过任何形式 (电子、机械、影印、录音或其他方式) 进行传输, 或者出于任何目的而进行传播。没有 Microsoft Corporation 的明确书面许可。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-614">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="ccbf6-615">Microsoft 可能拥有本文档中所涉及主题的专利、专利应用程序、商标、版权或其他知识产权权利。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-615">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="ccbf6-616">除非 Microsoft 的任何书面许可协议中明确提供, 否则提供本文档不会向您提供这些专利、商标、版权或其他知识产权的任何许可证。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-616">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="ccbf6-617">© 2012 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-617">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="ccbf6-618">保留所有权利。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-618">All rights reserved.</span></span>

<span data-ttu-id="ccbf6-619">Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook 和 SQL Server 是 Microsoft Corporation 在美国和/或其他国家/地区的注册商标或商标。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-619">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="ccbf6-620">所有其他商标均为其各自所有者的财产。</span><span class="sxs-lookup"><span data-stu-id="ccbf6-620">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

