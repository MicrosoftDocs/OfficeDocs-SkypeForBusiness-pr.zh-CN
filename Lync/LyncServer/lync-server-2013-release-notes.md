---
title: Lync Server 2013 发行说明
description: Lync Server 2013 发行说明。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33fabb0912d7ea3defd91014df732368eced909e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555868"
---
# <a name="release-notes-for-lync-server-2013"></a><span data-ttu-id="b180e-103">Lync Server 2013 发行说明</span><span class="sxs-lookup"><span data-stu-id="b180e-103">Release notes for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b180e-104">_**上次修改的主题：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="b180e-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="b180e-105">欢迎使用 Lync Server 2013 发行说明。</span><span class="sxs-lookup"><span data-stu-id="b180e-105">Welcome to the Lync Server 2013 Release Notes.</span></span> <span data-ttu-id="b180e-106">有关 Lync Server 2013 的已知问题的信息，请参阅此文件。</span><span class="sxs-lookup"><span data-stu-id="b180e-106">Refer to this file for information regarding known issues about Lync Server 2013.</span></span>

<div>

## <a name="about-this-document"></a><span data-ttu-id="b180e-107">关于本文档</span><span class="sxs-lookup"><span data-stu-id="b180e-107">About this document</span></span>

<span data-ttu-id="b180e-108">本文档包含在部署和使用 Lync Server 2013 之前应了解的重要信息。</span><span class="sxs-lookup"><span data-stu-id="b180e-108">This document contains important information that you should know before you deploy and use Lync Server 2013.</span></span> <span data-ttu-id="b180e-109">有关 Lync Server 2013 的详细信息，请参阅 [Microsoft Lync server 2013](microsoft-lync-server-2013.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="b180e-109">For details about Lync Server 2013, refer to the [Microsoft Lync Server 2013](microsoft-lync-server-2013.md) documentation.</span></span>

<span data-ttu-id="b180e-110">本文档包含以下各部分：</span><span class="sxs-lookup"><span data-stu-id="b180e-110">This document contains the following sections:</span></span>

  - <span data-ttu-id="b180e-111">Lync 2013 客户端</span><span class="sxs-lookup"><span data-stu-id="b180e-111">Lync 2013 client</span></span>

  - <span data-ttu-id="b180e-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="b180e-112">Lync Server</span></span>

  - <span data-ttu-id="b180e-113">安装</span><span class="sxs-lookup"><span data-stu-id="b180e-113">Installation</span></span>

  - <span data-ttu-id="b180e-114">移动性</span><span class="sxs-lookup"><span data-stu-id="b180e-114">Mobility</span></span>

  - <span data-ttu-id="b180e-115">会议</span><span class="sxs-lookup"><span data-stu-id="b180e-115">Conferencing</span></span>

  - <span data-ttu-id="b180e-116">企业语音</span><span class="sxs-lookup"><span data-stu-id="b180e-116">Enterprise Voice</span></span>

  - <span data-ttu-id="b180e-117">状态</span><span class="sxs-lookup"><span data-stu-id="b180e-117">Presence</span></span>

  - <span data-ttu-id="b180e-118">响应组应用程序和呼叫寄存应用程序</span><span class="sxs-lookup"><span data-stu-id="b180e-118">Response Group Application and Call Park Application</span></span>

  - <span data-ttu-id="b180e-119">Lync Server 控制面板、拓扑生成器和规划工具</span><span class="sxs-lookup"><span data-stu-id="b180e-119">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

  - <span data-ttu-id="b180e-120">本地化</span><span class="sxs-lookup"><span data-stu-id="b180e-120">Localization</span></span>

  - <span data-ttu-id="b180e-121">版权</span><span class="sxs-lookup"><span data-stu-id="b180e-121">Copyright</span></span>

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a><span data-ttu-id="b180e-122">Lync 2013 客户端</span><span class="sxs-lookup"><span data-stu-id="b180e-122">Lync 2013 client</span></span>

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a><span data-ttu-id="b180e-123">如果文件已在另一个应用程序中打开，则在即时消息中转移文件的操作将失败。</span><span class="sxs-lookup"><span data-stu-id="b180e-123">Transferring a file in an instant message fails if the file is open in another application</span></span>

<span data-ttu-id="b180e-124">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-124">**Issue:**</span></span>

<span data-ttu-id="b180e-125">如果尝试通过在即时消息中将文件添加到另一个 Lync 用户来传输文件（如 Word 文档），则传输将显示为 "成功"，但实际上可能无法传输该文件。</span><span class="sxs-lookup"><span data-stu-id="b180e-125">If you attempt to transfer a file, such as a Word document, by including it in an instant message to another Lync user, the transfer will appear to succeed but may actually fail to transfer the file.</span></span> <span data-ttu-id="b180e-126">该文件类型的图标将显示在 Lync 客户端中，但预期的接收器无法打开该文件。</span><span class="sxs-lookup"><span data-stu-id="b180e-126">An icon for the file type will be displayed in the Lync client, but the file cannot be opened by the intended receiver.</span></span> <span data-ttu-id="b180e-127">不会显示任何错误消息，通知您传输未成功。</span><span class="sxs-lookup"><span data-stu-id="b180e-127">No error message is displayed to inform you that the transfer was not successfull.</span></span>

<span data-ttu-id="b180e-128">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-128">**Workaround:**</span></span>

<span data-ttu-id="b180e-129">若要解决此问题，请先关闭打开的文件或已打开的应用程序，然后再尝试在即时消息中传输该文件。</span><span class="sxs-lookup"><span data-stu-id="b180e-129">To work around this issue, close the open file or application that has it open before attempting to transfer the file in an instant message.</span></span>

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="b180e-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="b180e-130">Lync Server</span></span>

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a><span data-ttu-id="b180e-131">如果 Lync Server 存储服务数据复制失败，管理员将需要检查陈旧存储服务队列项的性能计数器</span><span class="sxs-lookup"><span data-stu-id="b180e-131">If Lync Server Storage Service data replication fails, administrators will need to check performance counters for stale Storage Service queue items</span></span>

<span data-ttu-id="b180e-132">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-132">**Issue:**</span></span>

<span data-ttu-id="b180e-133">Lync Server Storage Service 使用 Windows Fabric 进行复制。</span><span class="sxs-lookup"><span data-stu-id="b180e-133">The Lync Server Storage Service uses Windows Fabric for replication.</span></span> <span data-ttu-id="b180e-134">如果在主前端服务器上删除了数据，但在辅助前端服务器上的删除失败，例如，如果前端服务器上出现意外关闭或错误，则数据可以留下且 "孤立"。</span><span class="sxs-lookup"><span data-stu-id="b180e-134">If data is deleted on a primary Front End Server, but the deletion on a secondary Front End Server fails—for example, if there is an unexpected shutdown or error on the Front End Server—data can be left behind and "orphaned."</span></span> <span data-ttu-id="b180e-135">孤立数据会导致性能降低并浪费驱动器空间。</span><span class="sxs-lookup"><span data-stu-id="b180e-135">The orphaned data can cause performance to degrade and waste drive space.</span></span>

<span data-ttu-id="b180e-136">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-136">**Workaround:**</span></span>

<span data-ttu-id="b180e-137">若要解决此问题，如果使用的事件 \_ LYSS \_ DB \_ 空间 \_ 错误 (id = 32058) 和 LYSS \_ DB \_ 空间 \_ 使用 \_ 关键 (id = 32059) 在事件日志中生成，管理员应检查前端服务器上前端服务器的性能计数器 **： LYSS-Storage Service API** ，其名称为 **LYSS-当前存储服务陈旧队列项目数**。</span><span class="sxs-lookup"><span data-stu-id="b180e-137">To work around this issue, if the events LYSS\_DB\_SPACE\_USED\_ERROR (Id=32058) and LYSS\_DB\_SPACE\_USED\_CRITICAL (Id=32059) are generated in the event log, administrators should check the performance counter on the Front End Server under **LS:LYSS - Storage Service API** with a name of **LYSS - Current number of Storage Service stale queue items**.</span></span> <span data-ttu-id="b180e-138">如果此性能计数器具有较高的值（例如，大于50000），则管理员应在 Lync Server 2013 资源工具包中运行 CleanuUpStorageServiceData.exe 工具，这将从池中删除所有孤立数据。</span><span class="sxs-lookup"><span data-stu-id="b180e-138">If this performance counter has a high value—for example, greater than 50,000—then the administrator should run the CleanuUpStorageServiceData.exe tool in the Lync Server 2013 Resource Kit, which will delete all orphaned data from the pool.</span></span> <span data-ttu-id="b180e-139">有关该工具的详细信息，请参阅 Lync Server 2013 资源工具包文档。</span><span class="sxs-lookup"><span data-stu-id="b180e-139">For details about the tool, see the Lync Server 2013 Resource Kit documentation.</span></span>

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a><span data-ttu-id="b180e-140">每当服务器或池的 IP 地址配置发生更改时，都需要重新启动 Lync Server 服务</span><span class="sxs-lookup"><span data-stu-id="b180e-140">Whenever the IP Address configuration is changed for a server or pool, Lync Server services need to be restarted</span></span>

<span data-ttu-id="b180e-141">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-141">**Issue:**</span></span>

<span data-ttu-id="b180e-142">如果为 Lync Server 2013 部署更改了 IP 地址配置（例如，从 IPv4 更改为双栈或从双堆栈更改为 Ipv6），则并非所有服务器组件都会在重新启动服务之前选取配置更改。</span><span class="sxs-lookup"><span data-stu-id="b180e-142">When the IP Address configuration is changed for a Lync Server 2013 deployment, such as changing from IPv4 to Dual Stack, or from Dual Stack to Ipv6, not all server components pick up the configuration change until the services are restarted.</span></span>

<span data-ttu-id="b180e-143">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-143">**Workaround:**</span></span>

<span data-ttu-id="b180e-144">若要解决此问题，请在更改部署的 IP 地址配置后重新启动 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="b180e-144">To work around this issue, restart Lync Server services after changing the IP Address configuration for the deployment.</span></span> <span data-ttu-id="b180e-145">若要执行此操作，请在 Lync Server 命令行管理程序中运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b180e-145">To do so, run the following cmdlets in the Lync Server Management Shell:</span></span>

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a><span data-ttu-id="b180e-146">Lync Server 2013 管理包中不再提供电话拨入式会议综合事务 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b180e-146">The dial-in conferencing synthetic transaction cmdlet is no longer available in the Lync Server 2013 Management Pack</span></span>

<span data-ttu-id="b180e-147">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-147">**Issue:**</span></span>

<span data-ttu-id="b180e-148">Lync Server 2013 管理包中不再提供电话拨入式会议综合事务 cmdlet **test-csdialinconferencing** 。</span><span class="sxs-lookup"><span data-stu-id="b180e-148">The dial-in conferencing synthetic transaction cmdlet **Test-CsDialInConferencing** is no longer available in the Lync Server 2013 Management Pack.</span></span>

<span data-ttu-id="b180e-149">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-149">**Workaround:**</span></span>

<span data-ttu-id="b180e-150">仅在企业内部支持使用电话拨入式会议综合事务 cmdlet **test-csdialinconferencing** 。</span><span class="sxs-lookup"><span data-stu-id="b180e-150">Use of the Dial-In Conferencing Synthetic Transaction cmdlet **Test-CsDialInConferencing** is supported only internally to an enterprise.</span></span>

<span data-ttu-id="b180e-151">管理员可继续使用 Lync Server 命令行管理程序中的 cmdlet 进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="b180e-151">Administrators may continue to use the cmdlet in Lync Server Management Shell for troubleshooting purposes.</span></span> <span data-ttu-id="b180e-152">如果需要，企业还可以开发专用管理包以在内部运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b180e-152">If required, an enterprise can also develop a private management pack to run the cmdlet internally.</span></span>

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a><span data-ttu-id="b180e-153">如果在将日志文件复制到网络共享时网络通信中断，集中日志记录服务将停止</span><span class="sxs-lookup"><span data-stu-id="b180e-153">The Centralized Logging Service stops if network traffic is disrupted when log files are being copied to network share</span></span>

<span data-ttu-id="b180e-154">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-154">**Issue:**</span></span>

<span data-ttu-id="b180e-155">将集中日志记录服务配置为使用网络路径时 (**new-csclsconfiguration** Cmdlet 的 CacheFileNetworkFolder 参数的值是有效的 UNC 路径) ，缓存的日志文件将被复制到网络共享。</span><span class="sxs-lookup"><span data-stu-id="b180e-155">When the Centralized Logging Service is configured to use a network path (the value of the CacheFileNetworkFolder parameter of the **Get-CsClsConfiguration** cmdlet is a valid UNC path), cached log files are copied to the network share.</span></span> <span data-ttu-id="b180e-156">如果在复制文件时网络流量出现中断，则会发生异常，从而导致集中日志记录服务停止。</span><span class="sxs-lookup"><span data-stu-id="b180e-156">If there is a disruption in network traffic while the files are being copied, an exception will occur that will cause the centralized logging service to stop.</span></span>

<span data-ttu-id="b180e-157">该服务配置为自动重新启动三次，因此该服务将从前三个例外中恢复。</span><span class="sxs-lookup"><span data-stu-id="b180e-157">The service is configured to automatically restart up to three times, so the service will recover from the first three exceptions.</span></span>

<span data-ttu-id="b180e-158">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-158">**Workaround:**</span></span>

<span data-ttu-id="b180e-159">此问题尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-159">There is no workaround for this issue.</span></span> <span data-ttu-id="b180e-160">若要确定问题，请从日志中 "Lync Server 集中式日志记录服务代理" 服务意外终止时日志的 "服务控制管理器" 中监视事件 ID 7031 的事件日志。</span><span class="sxs-lookup"><span data-stu-id="b180e-160">To identify the issue, monitor the event log for Event ID 7031 from the "Service Control Manager" that logs when the "Lync Server Centralized Logging Service Agent" service has terminated unexpectedly.</span></span> <span data-ttu-id="b180e-161">如果发生此情况超过三次，请使用 **CsWindowService** cmdlet 手动重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="b180e-161">If this happens more than three times, manually restart the service by using the **Start-CsWindowService** cmdlet.</span></span>

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a><span data-ttu-id="b180e-162">需要手动导入存储服务队列项</span><span class="sxs-lookup"><span data-stu-id="b180e-162">Storage Service Queue Items need to be imported manually</span></span>

<span data-ttu-id="b180e-163">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-163">**Issue:**</span></span>

<span data-ttu-id="b180e-164">Lync Server 2013 在每台前端服务器上的数据库上存储有关会议和即时消息的数据，例如存档的邮件和呼叫详细信息记录 (CDR) 。</span><span class="sxs-lookup"><span data-stu-id="b180e-164">Lync Server 2013 stores data about conferencing and instant messaging, such as archived messages and call detail recording (CDR), on a database on each Front End Server.</span></span> <span data-ttu-id="b180e-165">数据在处理过程中存储在数据库中，然后将其传递到预期的目标。</span><span class="sxs-lookup"><span data-stu-id="b180e-165">The data is stored in the database while it is being processed before being delivered to the intended destination.</span></span> <span data-ttu-id="b180e-166">为了提高性能，Lync Server 2013 定期从本地数据库中导出未在一段较长时间内处理的队列项，并将其保存在文件存储区中。</span><span class="sxs-lookup"><span data-stu-id="b180e-166">To improve performance, Lync Server 2013 periodically exports the queue items from the local database that are not processed for an extended period of time, and saves them on the file store.</span></span> <span data-ttu-id="b180e-167">如果文件存储不可用，项目将存储在每台前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="b180e-167">If the file store is unavailable, the items are stored on each Front End Server.</span></span> <span data-ttu-id="b180e-168">在池故障转移期间，发生相同的操作以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="b180e-168">The same operation occurs to prevent data loss during pool failover.</span></span>

<span data-ttu-id="b180e-169">在导出操作过程中，Lync Server 存储服务会在事件日志中记录包含 32075 (完全刷新操作的事件日志中的每个阶段。) ，32076 (完全刷新已完成) ，32082 (维护级别刷新已完成) ，32083 (维护级别刷新已完成) ，由于填满数据库 (，32089) 刷新发生。</span><span class="sxs-lookup"><span data-stu-id="b180e-169">During the export operation, the Lync Server Storage Service records every stage in the event log with event IDs of 32075 (full flush operation is started), 32076 (full flush is completed), 32082 (maintenance level flush is started), 32083 (maintenance level flush is completed), 32089 (flush occurred due to filling up of database).</span></span> <span data-ttu-id="b180e-170">此数据不会自动导入回系统以进行处理并传递到其最终目标 (SQL Server 或 Exchange Server) 。</span><span class="sxs-lookup"><span data-stu-id="b180e-170">This data will not automatically be imported back to the system to be processed and delivered to its final destination (SQL Server or Exchange Server).</span></span>

<span data-ttu-id="b180e-171">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-171">**Workaround:**</span></span>

<span data-ttu-id="b180e-172">若要将数据导入系统，管理员需要使用 Lync Server 资源工具包中的 ImportStorageServiceData 工具，该工具会将数据添加回要处理的系统并将其传递到最终目标。</span><span class="sxs-lookup"><span data-stu-id="b180e-172">To import the data to the system, administrators will need to use the ImportStorageServiceData tool in the Lync Server Resource Kit, which will add the data back into the system to be processed and delivered to its final destination.</span></span>

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a><span data-ttu-id="b180e-173">如果 UseNormalizationRules 的默认值更改为 False，通讯簿 Web 查询搜索将失败</span><span class="sxs-lookup"><span data-stu-id="b180e-173">Address Book Web Query searches will fail if the default value for UseNormalizationRules is changed to False</span></span>

<span data-ttu-id="b180e-174">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-174">**Issue:**</span></span>

<span data-ttu-id="b180e-175">如果 UseNormalizationRules 的默认值更改为 False，通讯簿 Web 查询搜索将失败。</span><span class="sxs-lookup"><span data-stu-id="b180e-175">If the default value for UseNormalizationRules is changed to False, Address Book Web Query searches will fail.</span></span> <span data-ttu-id="b180e-176">默认值更改后，Lync 客户端用户将无法使用 Lync 通讯簿 web 查询搜索用户。</span><span class="sxs-lookup"><span data-stu-id="b180e-176">After the default value is changed, Lync Client users will not be able to use Lync Address Book web query to search for users.</span></span>

<span data-ttu-id="b180e-177">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-177">**Workaround:**</span></span>

<span data-ttu-id="b180e-178">如果 UseNormalizationRules 的默认值设置为 False，以便用户可以使用在没有 Lync Server 2013 的 Active Directory 域服务中定义的电话号码。应用规范化规则，请通过执行以下操作来解决此问题：</span><span class="sxs-lookup"><span data-stu-id="b180e-178">If the default value for UseNormalizationRules is set to False so that users can use phone numbers as defined in Active Directory Domain Services without Lync Server 2013 applying normalization rules, work around this issue by doing the following:</span></span>

1.  <span data-ttu-id="b180e-179">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b180e-179">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b180e-180">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b180e-180">Do one of the following:</span></span>
    
      - <span data-ttu-id="b180e-181">如果您的部署仅包括 Lync Server 2013 服务器，请在全局级别运行以下 cmdlet，以将 UseNormalizationRules 和 IgnoreGenericRules 的值更改为 True：</span><span class="sxs-lookup"><span data-stu-id="b180e-181">If your deployment includes only Lync Server 2013 servers, run the following cmdlet at the global level to change the values for UseNormalizationRules and IgnoreGenericRules to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="b180e-182">如果您的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通信服务器 2007 R2 的组合，请运行以下 cmdlet，并将其分配给拓扑中的每个 Lync Server 2013 池：</span><span class="sxs-lookup"><span data-stu-id="b180e-182">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="b180e-183">等待 CMS 复制在所有池上进行。</span><span class="sxs-lookup"><span data-stu-id="b180e-183">Wait for CMS replication to occur on all pools.</span></span>

4.  <span data-ttu-id="b180e-184">修改适用于您的部署的电话规范化规则文件以清除内容。</span><span class="sxs-lookup"><span data-stu-id="b180e-184">Modify the phone normalization rules file for your deployment to clear the content.</span></span> <span data-ttu-id="b180e-185">文件位于每个 Lync Server 2013 池的文件共享中。</span><span class="sxs-lookup"><span data-stu-id="b180e-185">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="b180e-186">如果文件不存在，则创建一个名为 "公司 \_ 电话 \_ 号码 \_ 规范化Rules.txt" 的空文件 \_ 。</span><span class="sxs-lookup"><span data-stu-id="b180e-186">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt."</span></span>

5.  <span data-ttu-id="b180e-187">等待几分钟，让所有前端池都能读取新文件。</span><span class="sxs-lookup"><span data-stu-id="b180e-187">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="b180e-188">在部署中的每个 Lync Server 2013 池中运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b180e-188">Run the following cmdlet on each Lync Server 2013 pool in your deployment.</span></span>
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a><span data-ttu-id="b180e-189">每个 Lync 2013 池每天生成一次通讯簿服务器错误事件21054</span><span class="sxs-lookup"><span data-stu-id="b180e-189">Address Book Server error event 21054 is generated once daily for each Lync 2013 pool</span></span>

<span data-ttu-id="b180e-190">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-190">**Issue:**</span></span>

<span data-ttu-id="b180e-191">在每日执行日常维护时，Lync Server 2013 通讯簿服务器将在每天生成错误事件21054。</span><span class="sxs-lookup"><span data-stu-id="b180e-191">Lync Server 2013 Address Book Server will generate error event 21054 once every day when performing daily maintenance.</span></span> <span data-ttu-id="b180e-192">每当管理员运行 **csAddressBook** cmdlet 时，也会生成错误，即使更新成功也是如此。</span><span class="sxs-lookup"><span data-stu-id="b180e-192">The error is also generated every time an administrator runs the **Update-csAddressBook** cmdlet, even when the update is successful.</span></span> <span data-ttu-id="b180e-193">但是，当更新成功时，可以安全地忽略此错误事件。</span><span class="sxs-lookup"><span data-stu-id="b180e-193">However, this error event can safely be ignored when the update is successful.</span></span>

<span data-ttu-id="b180e-194">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-194">**Workaround:**</span></span>

<span data-ttu-id="b180e-195">遇到此错误事件时，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b180e-195">When you encounter this error event, run the following cmdlet:</span></span>

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

<span data-ttu-id="b180e-196">如果 cmdlet 报告没有未索引或被放弃的对象，则可以安全地忽略错误事件21054。</span><span class="sxs-lookup"><span data-stu-id="b180e-196">If the cmdlet reports that there are no unindexed or abandoned objects, the error event 21054 can be safely ignored.</span></span>

<span data-ttu-id="b180e-197">此外，应在 System Center Operations Manager 中禁用 KHI) "通讯簿用户已正确编制索引" (的关键运行状况指示器。</span><span class="sxs-lookup"><span data-stu-id="b180e-197">Additionally, the Key Health Indicator (KHI) "Address Book Users Correctly Indexed" should be turned off in System Center Operations Manager.</span></span>

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a><span data-ttu-id="b180e-198">在边缘池上配置 IPv6 时，请求可能会失败</span><span class="sxs-lookup"><span data-stu-id="b180e-198">Requests may fail when IPv6 is configured on an Edge pool</span></span>

<span data-ttu-id="b180e-199">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-199">**Issue:**</span></span>

<span data-ttu-id="b180e-200">在边缘池上配置 IPv6 时，对边缘池的一些请求可能会失败。</span><span class="sxs-lookup"><span data-stu-id="b180e-200">When IPv6 is configured on an Edge pool, some requests to the Edge pool may fail.</span></span>

<span data-ttu-id="b180e-201">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-201">**Workaround:**</span></span>

<span data-ttu-id="b180e-202">若要解决此问题，请不要使用 IPv6 配置边缘池。</span><span class="sxs-lookup"><span data-stu-id="b180e-202">To work around this issue, do not configure an Edge pool with IPv6.</span></span>

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a><span data-ttu-id="b180e-203">CsPoolFailback cmdlet 可能会在池故障回复期间失败</span><span class="sxs-lookup"><span data-stu-id="b180e-203">The invoke-csPoolFailback cmdlet may fail during pool failback</span></span>

<span data-ttu-id="b180e-204">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-204">**Issue:**</span></span>

<span data-ttu-id="b180e-205">尝试对池进行故障回复时， **csPoolFailback** cmdlet 可能会失败，并出现错误 "未能在重复尝试后完成水合进程"。</span><span class="sxs-lookup"><span data-stu-id="b180e-205">When attempting to fail back a pool, the **invoke-csPoolFailback** cmdlet may fail with the error, "Failed to complete hydration process after repeated attempts."</span></span>

<span data-ttu-id="b180e-206">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-206">**Workaround:**</span></span>

<span data-ttu-id="b180e-207">若要解决此问题，请再次运行 cmdlet，并等待 cmdlet 成功。</span><span class="sxs-lookup"><span data-stu-id="b180e-207">To work around this issue, run the cmdlet again, and wait until the cmdlet succeeds.</span></span> <span data-ttu-id="b180e-208">请注意，故障回复过程可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="b180e-208">Note that the failback process can take several minutes to complete.</span></span> <span data-ttu-id="b180e-209">对于包含20000用户的池，最长可能需要60分钟的时间。</span><span class="sxs-lookup"><span data-stu-id="b180e-209">It may take up to 60 minutes for a pool with 20,000 users.</span></span>

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a><span data-ttu-id="b180e-210">在将前端服务器添加到已建立的池（混合部署、Skype for Business Online）时，可能会发生数据丢失</span><span class="sxs-lookup"><span data-stu-id="b180e-210">Data loss may occur when you add a Front End Server to an already established pool – Hybrid, Skype for Business Online</span></span>

<span data-ttu-id="b180e-211">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-211">**Issue:**</span></span>

<span data-ttu-id="b180e-212">在池具有多台前端服务器的环境中，您可能会遇到此问题，您可以重新启动其中一个前端服务器，也可以添加以前不属于池的新前端服务器。</span><span class="sxs-lookup"><span data-stu-id="b180e-212">You may encounter this issue in an environment where a pool has more than one Front End Server, and you either restart one of the Front End Servers, or add a new Front End Server that was not previously part of the pool.</span></span>

<span data-ttu-id="b180e-213">在为池建立数据存档的稳定分布之前，要存档数据的用户可能会遇到数据丢失的情况。</span><span class="sxs-lookup"><span data-stu-id="b180e-213">Users whose data is being archived may experience data loss until a stable distribution of data archiving is established for the pool.</span></span> <span data-ttu-id="b180e-214">这一期的潜在数据丢失限制为15分钟的人对人员对话和30分钟内的会议。</span><span class="sxs-lookup"><span data-stu-id="b180e-214">This period of potential data loss is limited to 15 minutes for person-to-person conversations, and 30 minutes for conferences.</span></span>

<span data-ttu-id="b180e-215">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-215">**Workaround:**</span></span>

<span data-ttu-id="b180e-216">执行维护时，应将池故障转移到另一个池，然后在服务器上执行维护任务，而不是在池中逐个启动前端服务器。</span><span class="sxs-lookup"><span data-stu-id="b180e-216">When you perform maintenance, instead of starting Front End Servers in the pool one by one, you should fail over the pool to another pool, and then perform maintenance tasks on the servers.</span></span> <span data-ttu-id="b180e-217">您还可以在执行维护任务之前使服务不可用，然后在维护完成后还原可用性。</span><span class="sxs-lookup"><span data-stu-id="b180e-217">You can also make the service unavailable before performing maintenance tasks, and then restore availability when maintenance is complete.</span></span>

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a><span data-ttu-id="b180e-218">管理员不能使用 Get-CsClientAccessLicense cmdlet 获取许可证持有人计数</span><span class="sxs-lookup"><span data-stu-id="b180e-218">Administrators cannot get licensee count by using the Get-CsClientAccessLicense cmdlet</span></span>

<span data-ttu-id="b180e-219">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-219">**Issue:**</span></span>

<span data-ttu-id="b180e-220">管理员无法使用 **CsClientAccessLicense** cmdlet 获取准确的客户端许可证使用情况。</span><span class="sxs-lookup"><span data-stu-id="b180e-220">Administrators cannot get accurate client license usage by using the **Get-CsClientAccessLicense** cmdlet.</span></span>

<span data-ttu-id="b180e-221">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-221">**Workaround:**</span></span>

<span data-ttu-id="b180e-222">若要检查服务器许可证类型，可以运行 **get-csservice** cmdlet 来检索所有数据库的 FDQNs)  (的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="b180e-222">To check the server license type, you can run the **Get-CsService** cmdlet to retrieve the fully qualified domain names (FDQNs) of all databases.</span></span> <span data-ttu-id="b180e-223">如果前端服务器的 FQDN 与后端数据库的 FQDN 相同，则许可证是标准版许可证。</span><span class="sxs-lookup"><span data-stu-id="b180e-223">If the FQDN of the Front End Server is the same as the FQDN of the back-end database, the license is a Standard edition license.</span></span> <span data-ttu-id="b180e-224">否则，许可证为 Enterprise edition 许可证。</span><span class="sxs-lookup"><span data-stu-id="b180e-224">Otherwise, the license is an Enterprise edition license.</span></span>

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a><span data-ttu-id="b180e-225">客户端许可证持有人计数未准确报告</span><span class="sxs-lookup"><span data-stu-id="b180e-225">Client licensee count is not accurately reported</span></span>

<span data-ttu-id="b180e-226">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-226">**Issue:**</span></span>

<span data-ttu-id="b180e-227">在确定客户端许可证计数时，您可能会遇到以下情况：</span><span class="sxs-lookup"><span data-stu-id="b180e-227">When determining client license counts, you may experience the following conditions:</span></span>

1.  <span data-ttu-id="b180e-228">**移动用户的许可证计数不准确**</span><span class="sxs-lookup"><span data-stu-id="b180e-228">**Inaccurate license count for mobile users**</span></span>
    
    <span data-ttu-id="b180e-229">许可证计数基于基于设备的用户的唯一 IP 地址数。</span><span class="sxs-lookup"><span data-stu-id="b180e-229">The license count is based on the number of unique IP addresses for device-based users.</span></span> <span data-ttu-id="b180e-230">许可证计数将通过以下方式进行限制：</span><span class="sxs-lookup"><span data-stu-id="b180e-230">The license count will be limited in the following ways:</span></span>
    
      - <span data-ttu-id="b180e-231">如果用户的 IP 地址在 Lync 会话期间发生更改，则许可证将为 overcounted。</span><span class="sxs-lookup"><span data-stu-id="b180e-231">Licenses will be overcounted if the IP address for the user changes during Lync sessions.</span></span> <span data-ttu-id="b180e-232">当用户从多个位置使用桌面客户端连接到 Lync Server 时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b180e-232">This can occur when a user connects to Lync Server from more than one location with a desktop client.</span></span>
    
      - <span data-ttu-id="b180e-233">如果用户连接到移动客户端，则将 undercounted 许可证，因为无法确定设备的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b180e-233">Licenses will be undercounted if a user connects with a mobile client, because the IP address for the device cannot be determined.</span></span>

2.  <span data-ttu-id="b180e-234">**对 Lync 客户端的公共交换电话网络 (PSTN) 呼叫（lync 客户端呼叫到 PSTN 线路）计算两次许可证，并将 Lync 呼叫转发到 PSTN 线路**</span><span class="sxs-lookup"><span data-stu-id="b180e-234">**Licenses are counted twice for public switched telephone network (PSTN) calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="b180e-235">在以下方案中，将计算两个附加许可证，而不是一个许可证，因为电话号码和 Lync 用户都将进行计数以确定所使用的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="b180e-235">In the following scenarios, two additional licenses will be counted instead of one because both the phone number and the Lync user are counted to determine the number of licenses used.</span></span> <span data-ttu-id="b180e-236">若要获取准确的许可数据，请手动删除由电话号码生成的许可证。</span><span class="sxs-lookup"><span data-stu-id="b180e-236">To obtain accurate licensing data, manually remove the licenses generated by a phone number.</span></span>
    
      - <span data-ttu-id="b180e-237">对 Lync 的 PSTN 电话呼叫</span><span class="sxs-lookup"><span data-stu-id="b180e-237">A PSTN phone call to Lync</span></span>
    
      - <span data-ttu-id="b180e-238">对 PSTN 线路的 Lync 呼叫</span><span class="sxs-lookup"><span data-stu-id="b180e-238">A Lync call to a PSTN line</span></span>
    
      - <span data-ttu-id="b180e-239">对 Lync 的 PSTN 呼叫，然后 Lync 会将呼叫转发到 PSTN 线路。</span><span class="sxs-lookup"><span data-stu-id="b180e-239">A PSTN call to Lync, and then Lync forwards the call to a PSTN line.</span></span> <span data-ttu-id="b180e-240">其中一个 PSTN 线路将计算在内。</span><span class="sxs-lookup"><span data-stu-id="b180e-240">One of the PSTN lines will be counted.</span></span>

3.  <span data-ttu-id="b180e-241">**将不会对登录的 Lync 手机计数许可证**</span><span class="sxs-lookup"><span data-stu-id="b180e-241">**A license will not be counted for a logged-on Lync phone**</span></span>
    
    <span data-ttu-id="b180e-242">当用户使用 Lync 认证的电话时，如果电话登录并保持连接（这将保留其登录状态），则不会将电话计为使用许可证（如果在电话登录后进行许可证查询）。</span><span class="sxs-lookup"><span data-stu-id="b180e-242">When a user uses a Lync-certified phone, if the phone logs in and stays connected, which retains its logon status, the phone will not be counted as using a license if the query for licenses occurs after the phone logged in.</span></span>

4.  <span data-ttu-id="b180e-243">**为 PSTN 电话加入会议而盘点的许可证**</span><span class="sxs-lookup"><span data-stu-id="b180e-243">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="b180e-244">当用户加入带有 PSTN 手机的会议时，将会对加入会议的许可证进行不准确的计数。</span><span class="sxs-lookup"><span data-stu-id="b180e-244">When a user joins a conference with a PSTN phone, a license will inaccurately be counted for joining the conference.</span></span> <span data-ttu-id="b180e-245">但是，使用 PSTN 电话加入会议时无需许可证。</span><span class="sxs-lookup"><span data-stu-id="b180e-245">However, no license is needed to join a conference with a PSTN phone.</span></span>

<span data-ttu-id="b180e-246">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-246">**Workaround:**</span></span>

1.  <span data-ttu-id="b180e-247">**移动用户的许可证计数不准确**</span><span class="sxs-lookup"><span data-stu-id="b180e-247">**Inaccurate license count for mobile users**</span></span>
    
      - <span data-ttu-id="b180e-248">您可以手动标识属于同一设备的 IP 地址，然后在许可证计数中删除其中一个。</span><span class="sxs-lookup"><span data-stu-id="b180e-248">You can manually identify the IP addresses that belong to the same device and then remove one of them in the license count.</span></span>
    
      - <span data-ttu-id="b180e-249">与 Lync 客户端连接的移动设备不存在有关此问题的解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-249">There is no workaround for this issue with mobile devices connecting with Lync client.</span></span>

2.  <span data-ttu-id="b180e-250">**对 Lync 客户端的 PSTN 呼叫进行两次许可证计数，Lync 客户端呼叫 PSTN 线路，并将 Lync 呼叫转发到 PSTN 线路**</span><span class="sxs-lookup"><span data-stu-id="b180e-250">**Licenses are counted twice for PSTN calls to Lync client, Lync client calls to PSTN lines, and Lync calls forwarded to PSTN lines**</span></span>
    
    <span data-ttu-id="b180e-251">你将需要手动标识 PSTN 电话号码并删除为其生成的许可证计数。</span><span class="sxs-lookup"><span data-stu-id="b180e-251">You will need to manually identify the PSTN phone number and remove the license count generated for it.</span></span>

3.  <span data-ttu-id="b180e-252">**许可证不会计数为已登录 Lync 电话**</span><span class="sxs-lookup"><span data-stu-id="b180e-252">**A license will not be counted for a logged-in Lync phone**</span></span>
    
    <span data-ttu-id="b180e-253">您可以将 Lync phone 配置为注销，然后在每三个月的定期时间间隔再次登录。</span><span class="sxs-lookup"><span data-stu-id="b180e-253">You can configure the Lync phone to log off, and then log on again, at a regular interval, such as every 3 months.</span></span>

4.  <span data-ttu-id="b180e-254">**为 PSTN 电话加入会议而盘点的许可证**</span><span class="sxs-lookup"><span data-stu-id="b180e-254">**Licenses counted for PSTN phones joining conferences**</span></span>
    
    <span data-ttu-id="b180e-255">您可以手动标识用于加入会议的 PSTN 电话号码，并删除由电话号码生成的许可证。</span><span class="sxs-lookup"><span data-stu-id="b180e-255">You can manually identify the PSTN phone number that is used to join the conference and remove the license generated by the phone number.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a><span data-ttu-id="b180e-256">升级到 Silverlight 5 后，Lync Server 控制面板在 VMware 环境中停止工作</span><span class="sxs-lookup"><span data-stu-id="b180e-256">The Lync Server Control Panel stops working in a VMware environment after upgrading to Silverlight 5</span></span>

<span data-ttu-id="b180e-257">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-257">**Issue:**</span></span>

<span data-ttu-id="b180e-258">如果在 VMware 环境中使用 Lync Server 控制面板，则在将 Microsoft Silverlight 升级到版本5后，Lync Server 控制面板可能会停止工作。</span><span class="sxs-lookup"><span data-stu-id="b180e-258">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Microsoft Silverlight to version 5.</span></span>

<span data-ttu-id="b180e-259">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-259">**Workaround:**</span></span>

<span data-ttu-id="b180e-260">若要解决此问题，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b180e-260">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="b180e-261">卸载 Silverlight 5，并从安装 Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) 。</span><span class="sxs-lookup"><span data-stu-id="b180e-261">Uninstall Silverlight 5, and install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156).</span></span>

  - <span data-ttu-id="b180e-262">从不是 VMware 虚拟计算机的计算机访问 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b180e-262">Access the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="b180e-263">为此，如果在计算机上安装了 Lync Server 管理工具，则可以从服务器上的 Windows " **开始** " 菜单启动 "Lync server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b180e-263">To do so, you can start the Lync Server Control Panel from the Windows **Start** menu on the server, if the Lync Server Administration tools are installed on the computer.</span></span>
    
    <span data-ttu-id="b180e-264">您还可以使用 web 浏览器访问 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="b180e-264">You can also access the Lync Server Control Panel by using a web browser.</span></span> <span data-ttu-id="b180e-265">该 URL 将类似于 https:// \<frontend\_pool\_fqdn\> /cscp。</span><span class="sxs-lookup"><span data-stu-id="b180e-265">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a><span data-ttu-id="b180e-266">在 Active Directory 中修改用户的可分辨名称后，通讯簿服务中的用户信息未更新</span><span class="sxs-lookup"><span data-stu-id="b180e-266">User information in the Address Book Service is not updated after the distinguished name for the user is modified in Active Directory</span></span>

<span data-ttu-id="b180e-267">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-267">**Issue:**</span></span>

<span data-ttu-id="b180e-268">如果用户的可分辨名称 (也称为 DN) 在 Active Directory 域服务中进行了更改，则任何其他更改都不会在通讯簿服务 (ABS) 中进行更新。</span><span class="sxs-lookup"><span data-stu-id="b180e-268">If a user’s distinguished name (also known as DN) is changed in Active Directory Domain Services, any additional changes will not be updated in the Address Book Service (ABS).</span></span> <span data-ttu-id="b180e-269">这不会影响用户的登录或状态，但如果 SIP 地址也发生更改，则会阻止用户通信，因为搜索将返回过期的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="b180e-269">This does not affect sign-in or presence for the user, but it will prevent communication for the user if the SIP address is also changed, because searches will return an outdated SIP address.</span></span>

<span data-ttu-id="b180e-270">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-270">**Workaround:**</span></span>

<span data-ttu-id="b180e-271">若要解决此问题，请不要更改用户的 DN。</span><span class="sxs-lookup"><span data-stu-id="b180e-271">To work around this issue, do not change a user’s DN.</span></span> <span data-ttu-id="b180e-272">如果将用户的 DN 还原为以前的值，更新将反映在通讯簿服务中。</span><span class="sxs-lookup"><span data-stu-id="b180e-272">If you revert the DN for the user to the previous value, updates will be reflected in the Address Book Service.</span></span>

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a><span data-ttu-id="b180e-273">安装</span><span class="sxs-lookup"><span data-stu-id="b180e-273">Installation</span></span>

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a><span data-ttu-id="b180e-274">使用非 ASCII 字符可能会导致 Lync server 启动失败</span><span class="sxs-lookup"><span data-stu-id="b180e-274">Using non-ASCII characters may result in Lync server failing to start</span></span>

<span data-ttu-id="b180e-275">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-275">**Issue:**</span></span>

<span data-ttu-id="b180e-276">如果目标文件夹名称中包含非 ASCII 字符 (包括 UNICODE、双字节字符集 (DBCS) 、UTF-8 和 UTF-16) ，安装程序将失败。</span><span class="sxs-lookup"><span data-stu-id="b180e-276">Setup will fail if the destination folder name includes non-ASCII characters (including UNICODE, double-byte character set (DBCS), UTF-8, and UTF-16).</span></span> <span data-ttu-id="b180e-277">此外，安装程序可能会成功，但如果以下任一情况中包含非 ASCII 字符，则服务器将不会启动：</span><span class="sxs-lookup"><span data-stu-id="b180e-277">In addition, Setup may succeed but the server will not start if non-ASCII characters are contained in any of the following:</span></span>

  - <span data-ttu-id="b180e-278">计算机名称</span><span class="sxs-lookup"><span data-stu-id="b180e-278">Computer name</span></span>

  - <span data-ttu-id="b180e-279">域名</span><span class="sxs-lookup"><span data-stu-id="b180e-279">Domain name</span></span>

  - <span data-ttu-id="b180e-280">用户名</span><span class="sxs-lookup"><span data-stu-id="b180e-280">User name</span></span>

  - <span data-ttu-id="b180e-281">用户 SIP URI</span><span class="sxs-lookup"><span data-stu-id="b180e-281">User SIP URI</span></span>

  - <span data-ttu-id="b180e-282">服务帐户名称</span><span class="sxs-lookup"><span data-stu-id="b180e-282">Service account name</span></span>

<span data-ttu-id="b180e-283">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-283">**Workaround:**</span></span>

<span data-ttu-id="b180e-284">仅在目标文件夹名称、计算机名称、域名、用户名、用户 SIP URI 和服务帐户名称中使用 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="b180e-284">Use only ASCII characters in the destination folder name, computer name, domain name, user name, user SIP URI, and service account names.</span></span>

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a><span data-ttu-id="b180e-285">当模块在 IIS 7.5 中调用 InsertEntityBody 方法时，在安装 Lync Server 2013 之前必须安装 "堆损坏" 的修补程序。</span><span class="sxs-lookup"><span data-stu-id="b180e-285">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" must be installed prior to installing Lync Server 2013</span></span>

<span data-ttu-id="b180e-286">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-286">**Issue:**</span></span>

<span data-ttu-id="b180e-287">当模块在 IIS 7.5 " ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)) （Microsoft 知识库文章 264886 () 中所述）中的模块调用了" 堆损坏 "时，在 [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) 安装 Lync Server 2013 之前，必须先安装" 堆损坏 "的修补程序。</span><span class="sxs-lookup"><span data-stu-id="b180e-287">The hotfix for "Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5" ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)), described in Microsoft Knowledge Base article 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)), must be installed prior to installing Lync Server 2013.</span></span>

<span data-ttu-id="b180e-288">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-288">**Workaround:**</span></span>

<span data-ttu-id="b180e-289">从 Microsoft 下载中心下载并安装修补程序 [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) 。</span><span class="sxs-lookup"><span data-stu-id="b180e-289">Download and install the hotfix from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602).</span></span>

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a><span data-ttu-id="b180e-290">Lync Server 2013 无法在 ITA Windows Server 2012 操作系统 RTM 版本上安装</span><span class="sxs-lookup"><span data-stu-id="b180e-290">Lync Server 2013 fails to install on ITA Windows Server 2012 OS RTM version</span></span>

<span data-ttu-id="b180e-291">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-291">**Issue:**</span></span>

<span data-ttu-id="b180e-292">由于 Windows Fabric 安装失败，Lync Server 2013 安装将在 ITA Windows Server 2012 上失败。</span><span class="sxs-lookup"><span data-stu-id="b180e-292">Lync Server 2013 installation fails on ITA Windows Server 2012 due to Windows Fabric installation failing.</span></span>

<span data-ttu-id="b180e-293">由于使用 HH： MM： SS 的时间格式创建 Fabric 跟踪，因此 Windows Fabric 安装将失败。</span><span class="sxs-lookup"><span data-stu-id="b180e-293">Windows Fabric installation fails because fabric traces are created with the time format of HH:MM:SS.</span></span> <span data-ttu-id="b180e-294">但是，在 ITA Windows Server 中，时间格式为 HH。MM.SS。</span><span class="sxs-lookup"><span data-stu-id="b180e-294">However, in ITA Windows Server, the time format is HH.MM.SS.</span></span>

<span data-ttu-id="b180e-295">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-295">**Workaround:**</span></span>

<span data-ttu-id="b180e-296">若要解决此问题，请在安装 Lync Server 2013 之前更新系统注册表。</span><span class="sxs-lookup"><span data-stu-id="b180e-296">To work around this issue, update the system registry before installing Lync Server 2013.</span></span> <span data-ttu-id="b180e-297">需要更新的注册表项为： HKEY \_ 用户 \\ 。默认 \\ 控制面板 \\ 国际 \\ sTimeFormat。</span><span class="sxs-lookup"><span data-stu-id="b180e-297">The registry key that needs to be updated is: HKEY\_USERS\\.DEFAULT\\Control Panel\\International\\sTimeFormat.</span></span> <span data-ttu-id="b180e-298">使用 Windows PowerShell 命令行界面将 sTimeFormat 的值更改为 HH： mm： ss，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b180e-298">Change the value of sTimeFormat to HH:mm:ss by using the Windows PowerShell command-line interface as follows:</span></span>

1.  <span data-ttu-id="b180e-299">启动 Windows PowerShell 并运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b180e-299">Start Windows PowerShell and run the following cmdlets:</span></span>
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  <span data-ttu-id="b180e-300">若要查看当前值，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b180e-300">To view the current value, run the following cmdlet:</span></span>
    
        Get-itemproperty $a -Name sTimeFormat
    
    <span data-ttu-id="b180e-301">记下 sTimeFormat 的当前值，以便在安装完成后可以对其进行还原。</span><span class="sxs-lookup"><span data-stu-id="b180e-301">Make note of the current value for sTimeFormat so it can be restored after the installation is complete.</span></span>

3.  <span data-ttu-id="b180e-302">若要设置为新值，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b180e-302">To set to new value, run the following cmdlet:</span></span>
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  <span data-ttu-id="b180e-303">成功安装 Lync Server 2013 后，通过运行以下 cmdlet 还原 sTimeFormat 的原始值：</span><span class="sxs-lookup"><span data-stu-id="b180e-303">After Lync Server 2013 has been successfully installed, restore the original value for the sTimeFormat by running the following cmdlet:</span></span>
    
        - <span data-ttu-id="b180e-304">Set-ItemProperty 在步骤3中指出的 $a 名称 sTimeFormat "<值。</span><span class="sxs-lookup"><span data-stu-id="b180e-304">Set-ItemProperty $a -Name sTimeFormat -Value "<Value noted down in Step 3.</span></span> <span data-ttu-id="b180e-305">以上> "</span><span class="sxs-lookup"><span data-stu-id="b180e-305">above>"</span></span>

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a><span data-ttu-id="b180e-306">移动性</span><span class="sxs-lookup"><span data-stu-id="b180e-306">Mobility</span></span>

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a><span data-ttu-id="b180e-307">服务器故障转移过程中移动客户端的相关问题</span><span class="sxs-lookup"><span data-stu-id="b180e-307">Issues for mobile clients during the server failover process</span></span>

<span data-ttu-id="b180e-308">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-308">**Issue:**</span></span>

<span data-ttu-id="b180e-309">当 Lync Server 发生故障且故障转移过程开始时，以下问题可能会影响移动客户端用户：</span><span class="sxs-lookup"><span data-stu-id="b180e-309">When a Lync Server fails and the failover process begins, the following issues may affect mobile client users:</span></span>

  - <span data-ttu-id="b180e-310">在故障转移开始后，不会有最长10分钟的传入 Lync 呼叫或信号。</span><span class="sxs-lookup"><span data-stu-id="b180e-310">No incoming Lync call or signal for up to 10 minutes after failover begins.</span></span>

  - <span data-ttu-id="b180e-311">无法接受传入聊天请求</span><span class="sxs-lookup"><span data-stu-id="b180e-311">Cannot accept incoming Chat requests</span></span>

  - <span data-ttu-id="b180e-312">如果出现故障的服务器是用户的主服务器，则无法加入会议</span><span class="sxs-lookup"><span data-stu-id="b180e-312">Cannot join meetings if the failed server is the home server for the user</span></span>

<span data-ttu-id="b180e-313">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-313">**Workaround:**</span></span>

<span data-ttu-id="b180e-314">此问题尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-314">There is no workaround for this issue.</span></span> <span data-ttu-id="b180e-315">故障转移过程完成后，将还原正常功能。</span><span class="sxs-lookup"><span data-stu-id="b180e-315">Normal functionality will be restored once the failover process is complete.</span></span>

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a><span data-ttu-id="b180e-316">如果移动用户拒绝来自另一个 Lync 终结点的传入呼叫，则该呼叫将在 Lync 移动客户端上显示为缺少的转换</span><span class="sxs-lookup"><span data-stu-id="b180e-316">If a mobile user declines an incoming call from another Lync endpoint, the call is displayed as a missed conversion on Lync Mobile clients</span></span>

<span data-ttu-id="b180e-317">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-317">**Issue:**</span></span>

<span data-ttu-id="b180e-318">如果移动用户拒绝传入呼叫，并且该呼叫来自另一个 Lync 终结点，则该呼叫将在 Lync 移动客户端中显示为错过的对话，而不是在设备呼叫列表中的呼叫中显示。</span><span class="sxs-lookup"><span data-stu-id="b180e-318">If a mobile user declines an incoming call, and the call originated from another Lync endpoint, the call is displayed as a missed conversation in the Lync Mobile client instead of a call in the device call list.</span></span>

<span data-ttu-id="b180e-319">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-319">**Workaround:**</span></span>

<span data-ttu-id="b180e-320">此问题尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-320">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a><span data-ttu-id="b180e-321">移动客户端在搜索联系人时可能不显示联合联系人的显示名称</span><span class="sxs-lookup"><span data-stu-id="b180e-321">The mobile client may not display a federated contact’s display name when searching for contacts</span></span>

<span data-ttu-id="b180e-322">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-322">**Issue:**</span></span>

<span data-ttu-id="b180e-323">联合联系人的显示名称可能不会显示在某些情况下，例如在联系人列表中搜索联合联系人时。</span><span class="sxs-lookup"><span data-stu-id="b180e-323">The display name for federated contacts may not be displayed in some scenarios, such as when searching for a federated contact in the contact list.</span></span> <span data-ttu-id="b180e-324">当 Lync 移动客户端没有联系人的活动状态订阅时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b180e-324">This can occur when the there is no active presence subscription for the contact from the Lync mobile client.</span></span>

<span data-ttu-id="b180e-325">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-325">**Workaround:**</span></span>

<span data-ttu-id="b180e-326">此问题尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-326">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a><span data-ttu-id="b180e-327">在移动客户端中，作为会议邀请的错过对话中缺少被邀请者和时间戳信息</span><span class="sxs-lookup"><span data-stu-id="b180e-327">In the mobile client, invitee and timestamp information are missing from a missed conversation that is an invitation to a conference</span></span>

<span data-ttu-id="b180e-328">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-328">**Issue:**</span></span>

<span data-ttu-id="b180e-329">在移动客户端中，当错过的对话是会议邀请时，错过的对话邮件中缺少被邀请者和时间戳信息。</span><span class="sxs-lookup"><span data-stu-id="b180e-329">In the mobile client, when a missed conversation is an invitation to a conference, the invitee and timestamp information is missing from the missed conversation message.</span></span>

<span data-ttu-id="b180e-330">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-330">**Workaround:**</span></span>

<span data-ttu-id="b180e-331">此问题尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-331">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a><span data-ttu-id="b180e-332">使用 VoIP 进行呼叫的移动客户端用户无法为其语音邮件在 Exchange 2010 或更早版本中配置的用户留下语音邮件</span><span class="sxs-lookup"><span data-stu-id="b180e-332">Mobile client users making calls using VoIP are not be able to leave voice mail for users whose voice mail is configured in Exchange 2010 or earlier versions</span></span>

<span data-ttu-id="b180e-333">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-333">**Issue:**</span></span>

<span data-ttu-id="b180e-334">如果移动客户端用户使用 VoIP 发出呼叫，则用户将无法为配置为在 Microsoft Exchange Server 2007 或 Microsoft Exchange Server 2010 中使用语音邮件的用户留下语音邮件消息。</span><span class="sxs-lookup"><span data-stu-id="b180e-334">If a mobile client user is using VoIP to place calls, the user will not be able to leave voice mail messages for users configured to use voice mail in Microsoft Exchange Server 2007 or Microsoft Exchange Server 2010.</span></span>

<span data-ttu-id="b180e-335">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-335">**Workaround:**</span></span>

<span data-ttu-id="b180e-336">若要解决此问题，请将 Exchange 2010 与 SP1 或更高版本的 Microsoft Exchange Server 结合使用。</span><span class="sxs-lookup"><span data-stu-id="b180e-336">To work around this issue, use Exchange 2010 with SP1 or later version of Microsoft Exchange Server.</span></span>

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a><span data-ttu-id="b180e-337">对移动客户端上的客户端版本配置使用带 URL 的块时，可能会显示错误消息</span><span class="sxs-lookup"><span data-stu-id="b180e-337">When using Block with URL for Client Version Configuration on mobile clients, an incorrect error message may be displayed</span></span>

<span data-ttu-id="b180e-338">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-338">**Issue:**</span></span>

<span data-ttu-id="b180e-339">在移动客户端上为客户端版本配置使用 **带 URL 的块** 时，如果客户端版本不受支持，则可能会显示不正确的错误消息。</span><span class="sxs-lookup"><span data-stu-id="b180e-339">When using **Block with URL** for Client Version Configuration on mobile clients, an incorrect error message may be displayed when the client version is not supported.</span></span>

<span data-ttu-id="b180e-340">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-340">**Workaround:**</span></span>

<span data-ttu-id="b180e-341">若要解决此问题，请将客户端版本配置配置为使用 **block** 而不是 **block with URL**。</span><span class="sxs-lookup"><span data-stu-id="b180e-341">To work around this issue, configure Client Version Configuration to use **Block** instead of **Block with URL**.</span></span>

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a><span data-ttu-id="b180e-342">会议</span><span class="sxs-lookup"><span data-stu-id="b180e-342">Conferencing</span></span>

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a><span data-ttu-id="b180e-343">在 Lync Server 2013 前端服务器上运行的防病毒软件可能会导致应用程序域回收，这将暂时中断 Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013 客户端的服务</span><span class="sxs-lookup"><span data-stu-id="b180e-343">Antivirus software running on Lync Server 2013 Front End Servers can cause Application Domain recycling, which temporarily interrupts service for Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013 clients</span></span>

<span data-ttu-id="b180e-344">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-344">**Issue:**</span></span>

<span data-ttu-id="b180e-345">防病毒软件可以触发应用程序域重启，这会导致 Lync 移动服务2013和统一通信 (UC) Web API 客户端应用程序 (Lync Web App 2013、Lync Mobile 2010 和 Lync Mobile 2013) 将丢失其状态。</span><span class="sxs-lookup"><span data-stu-id="b180e-345">Antivirus software can trigger application domain restarts, which can result in Lync Mobility Service 2013 and unified communications (UC) Web API client applications (Lync Web App 2013, Lync Mobile 2010, and Lync Mobile 2013) to lose their state.</span></span>

<span data-ttu-id="b180e-346">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-346">**Workaround:**</span></span>

<span data-ttu-id="b180e-347">若要解决此问题，请从防病毒扫描中排除包含 Web 组件和 .NET framework 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b180e-347">To work around this issue, exclude the folders containing Web components and .NET framework from antivirus scanning.</span></span> <span data-ttu-id="b180e-348">有关详细信息，请参阅 Microsoft 知识库文章 312592 "PRB：在 ASP.NET 中使用应用程序重新启动时的随机应用程序重新启动" 错误 "at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) 。</span><span class="sxs-lookup"><span data-stu-id="b180e-348">For details, see Microsoft Knowledge Base article 312592, "PRB: Random application restarts with 'Application is restarting' error in ASP.NET," at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).</span></span>

<span data-ttu-id="b180e-349">应排除以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="b180e-349">The following folders should be excluded:</span></span>

  - <span data-ttu-id="b180e-350">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 组件 \\ Mcx \\ Ext</span><span class="sxs-lookup"><span data-stu-id="b180e-350">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Ext</span></span>

  - <span data-ttu-id="b180e-351">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 组件 \\ Mcx \\ Int</span><span class="sxs-lookup"><span data-stu-id="b180e-351">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Mcx\\Int</span></span>

  - <span data-ttu-id="b180e-352">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 组件 \\ Ucwa \\ Int</span><span class="sxs-lookup"><span data-stu-id="b180e-352">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Int</span></span>

  - <span data-ttu-id="b180e-353">% ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web 组件 \\ Ucwa \\ Ext</span><span class="sxs-lookup"><span data-stu-id="b180e-353">%ProgramFiles%\\Microsoft Lync Server 2013\\Web Components\\Ucwa\\Ext</span></span>

  - <span data-ttu-id="b180e-354">% Windir% \\ Microsoft.NET \\ Framework64 \\ v 4.0.30319 \\ Config</span><span class="sxs-lookup"><span data-stu-id="b180e-354">%Windir%\\Microsoft.NET\\Framework64\\v4.0.30319\\Config</span></span>

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a><span data-ttu-id="b180e-355">必须在 Windows Internet Explorer 中启用 ActiveX 控件或本机 XMLHTTP 支持才能成功加入会议</span><span class="sxs-lookup"><span data-stu-id="b180e-355">ActiveX Controls or native XMLHTTP support must be enabled in Windows Internet Explorer to successfully join conferences</span></span>

<span data-ttu-id="b180e-356">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-356">**Issue:**</span></span>

<span data-ttu-id="b180e-357">如果用户在 Windows Internet Explorer Internet 浏览器设置中禁用了 ActiveX 控件和本机 XMLHTTP 支持，如果选择 Internet Explorer 作为默认浏览器，则该用户将无法加入会议。</span><span class="sxs-lookup"><span data-stu-id="b180e-357">If a user has disabled both ActiveX Controls and native XMLHTTP support in Windows Internet Explorer Internet browser settings, the user will not be able to join a meeting if Internet Explorer is selected as the default browser.</span></span>

<span data-ttu-id="b180e-358">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-358">**Workaround:**</span></span>

<span data-ttu-id="b180e-359">在 Internet Explorer 中启用 ActiveX 控件或 "本机 XMLHTTP 支持"。</span><span class="sxs-lookup"><span data-stu-id="b180e-359">Enable either ActiveX Controls or "native XMLHTTP support" in Internet Explorer.</span></span>

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a><span data-ttu-id="b180e-360">Lync Server Web 会议服务无法从关键模式恢复</span><span class="sxs-lookup"><span data-stu-id="b180e-360">Lync Server Web Conferencing service cannot recover from critical mode</span></span>

<span data-ttu-id="b180e-361">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-361">**Issue:**</span></span>

<span data-ttu-id="b180e-362">如果启用了关键模式进行存档，则在发生系统故障时，关键模式将启动，并且会议将不再适用于参与者。</span><span class="sxs-lookup"><span data-stu-id="b180e-362">If critical mode is turned for archiving, in case of system failures, critical mode will start and the conferences will no longer work for the participants.</span></span> <span data-ttu-id="b180e-363">管理员修复系统故障后 (例如解决数据库问题) ，数据会议服务不会自动恢复，管理员必须手动重新启动会议服务，会议才能继续。</span><span class="sxs-lookup"><span data-stu-id="b180e-363">After the administrator fixes the system failures (such as fixing a database issue), the data conferencing service doesn't automatically recover, and the administrator must manually restart the conferencing service for conferencing to resume.</span></span>

<span data-ttu-id="b180e-364">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-364">**Workaround:**</span></span>

<span data-ttu-id="b180e-365">修复系统故障后，管理员需要手动重新启动会议服务。</span><span class="sxs-lookup"><span data-stu-id="b180e-365">An administrator needs to manually restart the conferencing service after the system failure is fixed.</span></span>

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a><span data-ttu-id="b180e-366">Web 会议服务忽略外部 Office Web App 服务器的 HTTP 代理</span><span class="sxs-lookup"><span data-stu-id="b180e-366">Web Conferencing service ignores the HTTP proxy for external Office Web App Servers</span></span>

<span data-ttu-id="b180e-367">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-367">**Issue:**</span></span>

<span data-ttu-id="b180e-368">如果已将 Office Web Apps Server 外部部署到 Web 会议服务 (也就是说，Internet、外围网络和 Web 会议服务中不包含内部公司网络中) 的服务器，则 Office Web Apps Server 发现将会发生故障。</span><span class="sxs-lookup"><span data-stu-id="b180e-368">If you have deployed an Office Web Apps Server external to the Web Conferencing service (that is, a server that is not in the internal corporate network) in the Internet, perimeter network, and the Web Conferencing service requires an HTTP proxy to connect to this, the Office Web Apps Server discovery will fail.</span></span> <span data-ttu-id="b180e-369">Web 会议服务忽略 HTTP 代理设置，如在 Office Web Apps Server 安装程序的拓扑生成器中定义的那样。</span><span class="sxs-lookup"><span data-stu-id="b180e-369">The Web Conferencing service ignores the HTTP proxy setting, as defined in Topology Builder for Office Web Apps Server setup.</span></span> <span data-ttu-id="b180e-370">因此，Lync 客户端将无法与会议中的其他参与者共享 Microsoft PowerPoint 2010。</span><span class="sxs-lookup"><span data-stu-id="b180e-370">As a result, the Lync client will not be able to do Microsoft PowerPoint 2010 sharing with other participants in the conference.</span></span> <span data-ttu-id="b180e-371">如果要在内部部署 Lync Server 并在内部网络中配置 Office Web Apps Server 内部部署，则不需要代理配置。</span><span class="sxs-lookup"><span data-stu-id="b180e-371">If you are installing Lync Server on-premises and also configure Office Web Apps Server on-premises in the internal network, a proxy configuration is not required.</span></span>

<span data-ttu-id="b180e-372">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-372">**Workaround:**</span></span>

<span data-ttu-id="b180e-373">唯一的解决方法是不需要使用 HTTP 代理与外部 Office Web Apps Server 进行通信的部署配置。</span><span class="sxs-lookup"><span data-stu-id="b180e-373">The only workaround is to not have a deployment configuration that requires the use of HTTP proxy to communicate with an external Office Web Apps Server.</span></span>

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a><span data-ttu-id="b180e-374">不支持将视频添加到音频会议提供商会议</span><span class="sxs-lookup"><span data-stu-id="b180e-374">Adding video to an audio conferencing provider conference is not supported</span></span>

<span data-ttu-id="b180e-375">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-375">**Issue:**</span></span>

<span data-ttu-id="b180e-376">如果用户加入音频会议提供商会议，则不支持添加视频。</span><span class="sxs-lookup"><span data-stu-id="b180e-376">Adding a video is not supported if the user is joined to an audio conferencing provider conference for audio.</span></span>

<span data-ttu-id="b180e-377">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-377">**Workaround:**</span></span>

<span data-ttu-id="b180e-378">此问题尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-378">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a><span data-ttu-id="b180e-379">启用了 IPv6 的拓扑强制使用 Lync Web App Silverlight 插件进行自动更新，以确保屏幕共享功能可从 Lync Web App 工作</span><span class="sxs-lookup"><span data-stu-id="b180e-379">Topologies with IPv6 enabled force the Lync Web App Silverlight plug-in auto-update to ensure screen sharing functionality can work from Lync Web App</span></span>

<span data-ttu-id="b180e-380">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-380">**Issue:**</span></span>

<span data-ttu-id="b180e-381">将拓扑配置为启用 IPv6 时，如果已安装早期版本的屏幕共享插件，则用户无法从 Lync Web App 客户端共享其屏幕。</span><span class="sxs-lookup"><span data-stu-id="b180e-381">When a topology is configured with IPv6 enabled, users cannot share their screen from the Lync Web App client if an earlier version of the screen-sharing plug-in is already installed.</span></span>

<span data-ttu-id="b180e-382">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-382">**Workaround:**</span></span>

<span data-ttu-id="b180e-383">若要在通过 Lync Web App 加入会议时强制更新屏幕共享插件的最新版本，请将 **MinSupportedBuildVersion** 的值从 "4.0.7457.0" 修改为以下两个文件中的 "4.0.7577.380"：</span><span class="sxs-lookup"><span data-stu-id="b180e-383">To force an update to the most recent version of the screen-sharing plug-in when joining meeting via Lync Web App, modify the value of **MinSupportedBuildVersion** from "4.0.7457.0" to "4.0.7577.380" in both of the following files:</span></span>

  - <span data-ttu-id="b180e-384">% ProgramFiles% \\ Microsoft Lync Server 15 \\ Web 组件 \\ 达到 \\ Int \\ 客户端 \\ 插件 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="b180e-384">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Int\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

  - <span data-ttu-id="b180e-385">% ProgramFiles% \\ Microsoft Lync Server 15 \\ Web 组件 \\ 访问 \\ 外部的 \\ 客户端 \\ 插件 \\ReachAppShPluginProperties.xml</span><span class="sxs-lookup"><span data-stu-id="b180e-385">%ProgramFiles%\\Microsoft Lync Server 15\\Web Components\\Reach\\Ext\\Client\\Plugins\\ReachAppShPluginProperties.xml</span></span>

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a><span data-ttu-id="b180e-386">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="b180e-386">Enterprise Voice</span></span>

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a><span data-ttu-id="b180e-387">在某些情况下，在配置为使用 IPv4 和 IPv6 双堆栈的计算机上运行的 Lync 客户端可能不支持依赖于计算机的 IP 子网的功能，如 E911、媒体旁路、呼叫允许控制和基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="b180e-387">In some cases, a Lync client running on a computer configured to use IPv4 and IPv6 dual stack might not support capabilities that rely in the IP subnet of the computer such as E911, Media Bypass, Call Admission Control and Location Based Routing</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b180e-388">本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="b180e-388">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b180e-389">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-389">**Issue:**</span></span>

<span data-ttu-id="b180e-390">当 Lync 客户端在启用了 IPv4 和 IPv6 双协议的计算机上运行，并且基于代理服务器的 DNS 解析时，客户端可以使用计算机的 IPv6 地址登录。</span><span class="sxs-lookup"><span data-stu-id="b180e-390">When a Lync client is running on a computer that is enabled for IPv4 and IPv6 dual stack and based on the DNS resolution of the proxy server, the client may use the IPv6 address of the computer to sign in.</span></span> <span data-ttu-id="b180e-391">执行此操作后，Lync 客户端将仅支持 IPv6 支持的功能，这不会排除 E911、媒体旁路、呼叫允许控制和基于位置的路由。</span><span class="sxs-lookup"><span data-stu-id="b180e-391">After doing so, the Lync Client will support only the capabilities supported for IPv6, which excludes E911, Media Bypass, Call Admission Control and Location Based Routing.</span></span>

<span data-ttu-id="b180e-392">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-392">**Workaround:**</span></span>

<span data-ttu-id="b180e-393">若要解决此问题，请在客户端计算机上禁用 IPv6 支持。</span><span class="sxs-lookup"><span data-stu-id="b180e-393">To work around this issue, disable IPv6 support on the client computer.</span></span>

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a><span data-ttu-id="b180e-394">如果没有为用户配置企业语音，则用户将需要使用 E164 格式从会议拨出</span><span class="sxs-lookup"><span data-stu-id="b180e-394">If Enterprise Voice is not configured for a user, the user will need to use E164 format to dial out from a conference</span></span>

<span data-ttu-id="b180e-395">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-395">**Issue:**</span></span>

<span data-ttu-id="b180e-396">如果没有为用户配置企业语音，则该用户将需要使用 E164 格式以成功从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="b180e-396">If Enterprise Voice is not configured for a user, that user will need to use the E164 format to successfully dial out from a conference.</span></span> <span data-ttu-id="b180e-397">如果未使用 E164 格式，则用户将无法从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="b180e-397">If the E164 format is not used, the user will not be able to dial out from the conference.</span></span>

<span data-ttu-id="b180e-398">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-398">**Workaround:**</span></span>

<span data-ttu-id="b180e-399">若要解决此问题，未启用企业语音的用户应使用 E164 格式的号码从会议拨出。</span><span class="sxs-lookup"><span data-stu-id="b180e-399">To work around this issue, users who are not enabled for Enterprise Voice should dial out from a conference by using numbers in the E164 format.</span></span>

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a><span data-ttu-id="b180e-400">状态</span><span class="sxs-lookup"><span data-stu-id="b180e-400">Presence</span></span>

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a><span data-ttu-id="b180e-401">如果用户在为用户启用统一联系人存储时选择了 "阻止所有邀请和通信"，则状态在应为 "不" 时不会被拒绝</span><span class="sxs-lookup"><span data-stu-id="b180e-401">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be</span></span>

<span data-ttu-id="b180e-402">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-402">**Issue:**</span></span>

<span data-ttu-id="b180e-403">如果用户在为用户启用统一联系人存储时选择了 "阻止所有邀请和通信"，则状态在应为时不会被拒绝。</span><span class="sxs-lookup"><span data-stu-id="b180e-403">If a user has selected "Block all invites and communications" while the unified contact store is turned on for the user, Presence status is not rejected when it should be.</span></span>

<span data-ttu-id="b180e-404">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-404">**Workaround:**</span></span>

<span data-ttu-id="b180e-405">若要解决此问题，您可以为用户禁用统一联系人存储。</span><span class="sxs-lookup"><span data-stu-id="b180e-405">To work around this issue, you can turn off the unified contact store for the user.</span></span> <span data-ttu-id="b180e-406">若要执行此操作，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b180e-406">To do so, run the following cmdlets:</span></span>

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

<span data-ttu-id="b180e-407">例如：</span><span class="sxs-lookup"><span data-stu-id="b180e-407">For example:</span></span>

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a><span data-ttu-id="b180e-408">Office 通信服务器 2007 R2 用户驻留在内部部署中无法查看混合部署中 Skype for Business Online 用户的状态-混合</span><span class="sxs-lookup"><span data-stu-id="b180e-408">Office Communications Server 2007 R2 users homed on-premises are not able to see the Presence status of Skype for Business Online users in hybrid deployments - Hybrid</span></span>

<span data-ttu-id="b180e-409">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-409">**Issue:**</span></span>

<span data-ttu-id="b180e-410">在使用 Lync Server 2013 控制器时，混合部署中可能会发生此问题。</span><span class="sxs-lookup"><span data-stu-id="b180e-410">The issue may occur in a hybrid deployment when you are using a Lync Server 2013 Director.</span></span>

<span data-ttu-id="b180e-411">驻留到 Skype for business Online 的用户的状态显示为本地用户的未知状态。</span><span class="sxs-lookup"><span data-stu-id="b180e-411">Presence status for users homed to Skype for Business Online is displayed as Presence Unknown for on-premises users.</span></span> <span data-ttu-id="b180e-412">此外，托管到 Skype for Business Online 的用户无法查看 Office 通信服务器 R2 本地用户的状态。</span><span class="sxs-lookup"><span data-stu-id="b180e-412">Also, users homed to Skype for Business Online are not able to see presence status for Office Communications Server R2 on-premises users.</span></span>

<span data-ttu-id="b180e-413">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-413">**Workaround:**</span></span>

<span data-ttu-id="b180e-414">若要部分解决此问题，请将 "Home Server (msrtcsip-presencehomeserver) 的 Skype for Business Online 用户更改为指向 Lync Server 2013 本地池，而不是 Lync Server 2013 控制器。</span><span class="sxs-lookup"><span data-stu-id="b180e-414">To partially work around this issue, change the Home Server (msrtcsip-presencehomeserver) of the Skype for Business Online users to point to a Lync Server 2013 on-premises pool instead of the Lync Server 2013 Director.</span></span> <span data-ttu-id="b180e-415">您可以在本地前端服务器上修改此设置。</span><span class="sxs-lookup"><span data-stu-id="b180e-415">You can modify this setting on the on-premises Front End Server.</span></span>

<span data-ttu-id="b180e-416">此替代方法将正确显示托管到 Office 通信服务器 2007 R2 的用户的状态到 Skype for business Online 用户状态。</span><span class="sxs-lookup"><span data-stu-id="b180e-416">This workaround will correctly display the Presence status of users homed to Office Communications Server 2007 R2 to Skype for Business Online users.</span></span>

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a><span data-ttu-id="b180e-417">响应组应用程序、呼叫寄存应用程序和组呼叫应答</span><span class="sxs-lookup"><span data-stu-id="b180e-417">Response Group application, Call Park application, and Group Call Pickup</span></span>

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a><span data-ttu-id="b180e-418">在与检索方建立呼叫的过程中，呼叫者可能会听到一秒的音乐处于保留状态</span><span class="sxs-lookup"><span data-stu-id="b180e-418">A caller might hear one second of music-on-hold during the establishment of a call with the retrieving party</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b180e-419">本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="b180e-419">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b180e-420">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-420">**Issue:**</span></span>

<span data-ttu-id="b180e-421">通过组呼叫应答检索呼叫时，呼叫者在与检索方之间建立呼叫的过程中，可能会听到一秒的音乐处于保留状态。</span><span class="sxs-lookup"><span data-stu-id="b180e-421">When a call is retrieved via Group Call Pickup, the caller might hear one second of music-on-hold during the establishment of the call with the retriever party.</span></span>

<span data-ttu-id="b180e-422">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-422">**Workaround:**</span></span>

<span data-ttu-id="b180e-423">此问题尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-423">There is no workaround for this issue.</span></span>

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a><span data-ttu-id="b180e-424">响应组代理可以通过 Lync Server 2010 代理控制台登录并注销，仅适用于 Lync Server 2010 正式代理组</span><span class="sxs-lookup"><span data-stu-id="b180e-424">A Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only</span></span>

<span data-ttu-id="b180e-425">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-425">**Issue:**</span></span>

<span data-ttu-id="b180e-426">Lync Server 2013 响应组代理可以在 Lync server 2010 代理控制台中登录并注销，2010以仅使用正式代理组。</span><span class="sxs-lookup"><span data-stu-id="b180e-426">A Lync Server 2013 Response Group agent can sign in and sign out through a Lync Server 2010 Agent Console to Lync Server 2010 formal Agent Groups only.</span></span> <span data-ttu-id="b180e-427">在 Lync Server 2010 代理控制台中，用户只能看到他们所属的 Lync Server 2010 响应组。</span><span class="sxs-lookup"><span data-stu-id="b180e-427">In the Lync Server 2010 Agent Console, users can see only the Lync Server 2010 Response Group that they belong to.</span></span> <span data-ttu-id="b180e-428">他们无法看到它们所属的任何 Lync Server 2013 响应组。</span><span class="sxs-lookup"><span data-stu-id="b180e-428">They cannot see any of the Lync Server 2013 Response Groups that they belong to.</span></span>

<span data-ttu-id="b180e-429">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-429">**Workaround:**</span></span>

<span data-ttu-id="b180e-430">如果响应组代理是 Lync Server 2013 用户，并且是 Lync Server 2013 正式代理组的一部分，则用户必须通过浏览器中的 web 链接直接访问 Lync Server 2013 代理控制台，以登录到 Lync Server 2013 代理组并从中注销。</span><span class="sxs-lookup"><span data-stu-id="b180e-430">If the Response Group agent is a Lync Server 2013 user, and part of a Lync Server 2013 formal Agent Group, the user must access the Lync Server 2013 Agent Console directly via a web link in a browser to sign in to and sign out from Lync Server 2013 Agent Groups.</span></span>

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a><span data-ttu-id="b180e-431">Lync Server 2010 响应组代理无法代表 Lync Server 2013 响应组发出呼叫</span><span class="sxs-lookup"><span data-stu-id="b180e-431">A Lync Server 2010 Response Group agent cannot place calls on behalf of a Lync Server 2013 Response Group</span></span>

<span data-ttu-id="b180e-432">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-432">**Issue:**</span></span>

<span data-ttu-id="b180e-433">作为 Lync Server 2013 响应组代理的 Lync Server 2010 用户不能代表响应组发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="b180e-433">A Lync Server 2010 user who is an Agent of a Lync Server 2013 Response Group is not able to place a call on behalf of the Response Group.</span></span> <span data-ttu-id="b180e-434">Lync Server 2013 响应组将不会在 Lync 客户端中提供以发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="b180e-434">The Lync Server 2013 Response Group will not be available in the Lync Client to place a call.</span></span>

<span data-ttu-id="b180e-435">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-435">**Workaround:**</span></span>

<span data-ttu-id="b180e-436">若要解决此问题，必须将 Lync Server 2010 用户移动到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b180e-436">To work around this issue, you must move the Lync Server 2010 user to Lync Server 2013.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a><span data-ttu-id="b180e-437">在将响应组迁移到 Lync Server 2013 之后将其从 Lync 2010 Server 中删除会阻止响应组接受任何传入呼叫</span><span class="sxs-lookup"><span data-stu-id="b180e-437">Removing a Response Group from Lync Server 2010 after it has been migrated to Lync Server 2013 will prevent the Response Group from accepting any incoming calls</span></span>

<span data-ttu-id="b180e-438">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-438">**Issue:**</span></span>

<span data-ttu-id="b180e-439">如果从 lync server 2010 迁移到 Lync Server 2013 的响应组已从 lync server 2010 通过 Lync Server 控制面板或 Lync Server 命令行管理程序删除，则 Lync Server 2013 中的响应组将停止接收任何传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="b180e-439">If a Response Group that has been migrated from Lync Server 2010 to Lync Server 2013 is removed from Lync Server 2010 through the Lync Server Control Panel or the Lync Server Management Shell, the Response Group in Lync Server 2013 will stop receiving any incoming calls.</span></span>

<span data-ttu-id="b180e-440">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-440">**Workaround:**</span></span>

<span data-ttu-id="b180e-441">若要解决此问题，请不要从已从 Lync server 2010 迁移到 Lync Server 2013 的 Lync Server 2010 中删除任何响应组。</span><span class="sxs-lookup"><span data-stu-id="b180e-441">To work around this issue, do not remove any Response Groups from Lync Server 2010 that have been migrated from Lync Server 2010 to Lync Server 2013.</span></span>

<span data-ttu-id="b180e-442">如果已删除响应组，则应在 Lync Server 2013 中重新部署它。</span><span class="sxs-lookup"><span data-stu-id="b180e-442">If the Response Group has already been removed, you should redeploy it in Lync Server 2013.</span></span>

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a><span data-ttu-id="b180e-443">当新的托管工作流在创建时设置为非活动时，工作流的部署将失败</span><span class="sxs-lookup"><span data-stu-id="b180e-443">When a new managed workflow is set to inactive when created, deployment of the workflow will fail</span></span>

<span data-ttu-id="b180e-444">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-444">**Issue:**</span></span>

<span data-ttu-id="b180e-445">当新的托管工作流在创建时设置为非活动时，工作流的部署将失败。</span><span class="sxs-lookup"><span data-stu-id="b180e-445">When a new managed workflow is set to inactive when created, deployment of the workflow will fail.</span></span> <span data-ttu-id="b180e-446">如果工作流在创建时设置为非活动状态，但不会影响在部署后将其设置为非活动状态的工作流，则会遇到此问题。</span><span class="sxs-lookup"><span data-stu-id="b180e-446">This issue is encountered when the workflow is set to inactive when created, but does not affect a workflow that is edited to set it to inactive after is has been deployed.</span></span>

<span data-ttu-id="b180e-447">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-447">**Workaround:**</span></span>

<span data-ttu-id="b180e-448">创建和部署工作流时，将工作流设置为活动状态，然后部署它。</span><span class="sxs-lookup"><span data-stu-id="b180e-448">When creating and deploying a workflow, set the workflow as active and then deploy it.</span></span> <span data-ttu-id="b180e-449">成功部署工作流后，可以对工作流进行编辑并将其设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="b180e-449">After the workflow is successfully deployed, the workflow can be edited and set to inactive.</span></span>

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a><span data-ttu-id="b180e-450">如果响应组已导入到备份池中，则从所有者池删除响应组将阻止备份池的响应组接受在故障转移期间的任何传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="b180e-450">Removing a Response Group from the Owner pool will prevent the Response Group of the Backup pool from accepting any incoming calls during failover if the Response Group has been imported to the Backup pool</span></span>

<span data-ttu-id="b180e-451">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-451">**Issue:**</span></span>

<span data-ttu-id="b180e-452">如果已将主池拥有的响应组导入到备份池中，而不覆盖所有者，并且从所有者池删除了响应组，则在故障转移过程中，备份池中的响应组将不接受任何传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="b180e-452">If a Response Group that is owned by the primary pool has been imported to the backup pool without overwriting the owner, and the Response Group is removed from the owner pool, the Response Group in the Backup pool will not accept any incoming calls during failover.</span></span>

<span data-ttu-id="b180e-453">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-453">**Workaround:**</span></span>

<span data-ttu-id="b180e-454">你将需要在主池中重新部署响应组。</span><span class="sxs-lookup"><span data-stu-id="b180e-454">You will need to redeploy the Response Group in the Primary pool.</span></span> <span data-ttu-id="b180e-455">然后，您需要从主池导出响应组配置，并再次将其导入备份池。</span><span class="sxs-lookup"><span data-stu-id="b180e-455">You will then need to export the Response Group configuration from the Primary pool and import it to the Backup pool again.</span></span>

<span data-ttu-id="b180e-456">您还可以在备份池中重新创建响应组。</span><span class="sxs-lookup"><span data-stu-id="b180e-456">You can also recreate the Response Group in the Backup pool.</span></span> <span data-ttu-id="b180e-457">在这种情况下，备份池将成为响应组的所有者池。</span><span class="sxs-lookup"><span data-stu-id="b180e-457">In this case, the Backup pool will be the owner pool of the Response Group.</span></span>

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a><span data-ttu-id="b180e-458">如果代表响应组执行了检索请求，则无法从呼叫寄存应用程序检索寄存呼叫</span><span class="sxs-lookup"><span data-stu-id="b180e-458">A parked call can't be retrieved from the Call Park application if the retrieve request is done on behalf of a Response Group</span></span>

<span data-ttu-id="b180e-459">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-459">**Issue:**</span></span>

<span data-ttu-id="b180e-460">如果满足以下条件，则对寄存呼叫的检索请求将失败：</span><span class="sxs-lookup"><span data-stu-id="b180e-460">When the following conditions are true, a retrieve request for a parked call will fail:</span></span>

  - <span data-ttu-id="b180e-461">代理是匿名响应组的一部分</span><span class="sxs-lookup"><span data-stu-id="b180e-461">An agent is part of an anonymous Response Group</span></span>

  - <span data-ttu-id="b180e-462">代理尝试通过匿名响应组从呼叫寄存应用程序检索寄存的呼叫</span><span class="sxs-lookup"><span data-stu-id="b180e-462">The agent attempts to retrieve a parked call from the Call Park application through the anonymous Response Group</span></span>

  - <span data-ttu-id="b180e-463">代理尝试通过 "代表呼叫" 选项（或通过 Lync 助理客户端中的相同选项）拨打轨道编号来检索呼叫。</span><span class="sxs-lookup"><span data-stu-id="b180e-463">The agent attempts to retrieve the call by dialing the orbit number through the Call On Behalf option or through the same option in the Lync attendant client</span></span>

<span data-ttu-id="b180e-464">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-464">**Workaround:**</span></span>

<span data-ttu-id="b180e-465">此问题尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-465">There are no workarounds for this issue.</span></span> <span data-ttu-id="b180e-466">应检索寄存的呼叫，而无需代表响应组执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b180e-466">The parked call should be retrieved without doing so on behalf of a Response Group.</span></span>

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a><span data-ttu-id="b180e-467">Lync Server 控制面板、拓扑生成器和规划工具</span><span class="sxs-lookup"><span data-stu-id="b180e-467">Lync Server Control Panel, Topology Builder, and Planning Tool</span></span>

<div>

## <a name="planning-tool-limitations"></a><span data-ttu-id="b180e-468">规划工具限制</span><span class="sxs-lookup"><span data-stu-id="b180e-468">Planning Tool Limitations</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b180e-469">本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="b180e-469">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b180e-470">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-470">**Issue:**</span></span>

<span data-ttu-id="b180e-471">规划部署时，规划工具具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="b180e-471">The Planning Tool has the following limitations when planning for your deployment:</span></span>

  - <span data-ttu-id="b180e-472">最多支持10个中央站点</span><span class="sxs-lookup"><span data-stu-id="b180e-472">There is a maximum of 10 central sites supported</span></span>

  - <span data-ttu-id="b180e-473">每个中央站点最多可以有14个分支站点</span><span class="sxs-lookup"><span data-stu-id="b180e-473">Each central site can have a maximum of 14 branch sites</span></span>

  - <span data-ttu-id="b180e-474">每个中央站点最多可以有240000个用户</span><span class="sxs-lookup"><span data-stu-id="b180e-474">Each central site can have a maximum of 240,000 users</span></span>

<span data-ttu-id="b180e-475">此外，在计算推荐的拓扑时，规划工具不包含以下值：</span><span class="sxs-lookup"><span data-stu-id="b180e-475">In addition, the Planning Tool does not include values for the following when calculating the recommended topology:</span></span>

  - <span data-ttu-id="b180e-476">联机驻留的用户数</span><span class="sxs-lookup"><span data-stu-id="b180e-476">The number of users that are homed online</span></span>

  - <span data-ttu-id="b180e-477">为 XMPP 联盟启用的用户所占的百分比</span><span class="sxs-lookup"><span data-stu-id="b180e-477">The percentage of users that are enabled for XMPP federation</span></span>

  - <span data-ttu-id="b180e-478">使用 Lync Web App 的用户所占的百分比</span><span class="sxs-lookup"><span data-stu-id="b180e-478">Percentage of users that are using Lync Web App</span></span>

<span data-ttu-id="b180e-479">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-479">**Workaround:**</span></span>

<span data-ttu-id="b180e-480">这些问题没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-480">There is no workaround for these issues.</span></span> <span data-ttu-id="b180e-481">有关规划工具的详细信息，请参阅 [使用规划工具为 Lync Server 2013 设计拓扑](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="b180e-481">For more information about the Planning Tool, see [Designing the topology for Lync Server 2013 by using the Planning Tool](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).</span></span>

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a><span data-ttu-id="b180e-482">在更新选项时，规划工具可能不会为边缘网络使用以前定义的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b180e-482">Planning Tool may not use previously defined IP addresses for the Edge network when updating options</span></span>

<span data-ttu-id="b180e-483">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-483">**Issue:**</span></span>

<span data-ttu-id="b180e-484">使用规划工具完成设计后，如果对边缘网络选项进行了更改，则可能会将其他 IP 地址添加到设计中，而不是更新现有的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b180e-484">After you complete your design using the Planning Tool, if you make changes to the Edge Network options, additional IP addresses may be added to the design instead of updating the existing IP addresses.</span></span> <span data-ttu-id="b180e-485">当您查看 Edge 网络图的详细信息时，可能会发生这种情况，请选择 " **单击此处以更新选项**"，然后在 "配置选项" 对话框中选择 "边缘网络 **"。我希望对我的边缘服务器上的边缘服务使用相同的 fqdn 和 IP 地址，而**不是不同的端口。</span><span class="sxs-lookup"><span data-stu-id="b180e-485">This can occur when you are viewing the details of the Edge Network Diagram, select **Click here to update your options**, and then, on the Configuration Options dialog, you select Edge Network select **I want to use the same FQDNs and IP addresses, but different ports for the edge services on my Edge Server**.</span></span> <span data-ttu-id="b180e-486">应用任何更改可能会导致新 IP 地址和边缘服务器添加到设计中。</span><span class="sxs-lookup"><span data-stu-id="b180e-486">Applying any changes may result in new IP addresses and Edge servers being added to the design.</span></span>

<span data-ttu-id="b180e-487">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-487">**Workaround:**</span></span>

<span data-ttu-id="b180e-488">目前尚无解决此问题的方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-488">There is no workaround for this issue at this time.</span></span>

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a><span data-ttu-id="b180e-489">在 Lync Server 控制面板中，"将所有用户移动到池" 可能无法按预期工作</span><span class="sxs-lookup"><span data-stu-id="b180e-489">In Lync Server Control Panel, "Move all users to pool" may not work as expected</span></span>

<span data-ttu-id="b180e-490">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-490">**Issue:**</span></span>

<span data-ttu-id="b180e-491">在使用 Lync Server 控制面板将所有用户从一个池移动到一个复杂的 Active Directory 环境中的另一个池（例如一个具有多个域控制器和父/子域的池）时，可能会返回错误消息 "指定的用户不是旧版用户，请改用 Move-CsUser cmdlet"。</span><span class="sxs-lookup"><span data-stu-id="b180e-491">When using the Lync Server Control Panel to move all users from one pool to another pool in a complex Active Directory environment, such as one with multiple Domain Controllers and parent/child domains, an error message may be returned that states, “Specified user is not a legacy user, use Move-CsUser cmdlet instead.”</span></span> <span data-ttu-id="b180e-492">这是在复杂的 Active Directory 环境中复制时间较长的结果。</span><span class="sxs-lookup"><span data-stu-id="b180e-492">This is a result of longer replication times in complex Active Directory environments.</span></span>

<span data-ttu-id="b180e-493">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-493">**Workaround:**</span></span>

<span data-ttu-id="b180e-494">若要解决此问题，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b180e-494">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="b180e-495">使用 Lync Server 控制面板中的筛选器搜索旧版用户，选择这些用户，然后使用 " **移动选定用户池" 命令** ，而不是 " **将所有用户移动到池**"。</span><span class="sxs-lookup"><span data-stu-id="b180e-495">Use filters in the Lync Server Control Panel to search for legacy users, select those users, and then use the **Move selected users to pool command** instead of **Move all users to pool**.</span></span>

  - <span data-ttu-id="b180e-496">使用 Lync Server 命令行管理程序通过 Lync Server cmdlet 在批处理中移动旧版用户。</span><span class="sxs-lookup"><span data-stu-id="b180e-496">Use the Lync Server Management Shell to move legacy users in batches by using Lync Server cmdlets.</span></span>

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a><span data-ttu-id="b180e-497">在将 Microsoft Silverlight 浏览器插件更新到版本5后，Lync Server 控制面板在 VMware 环境中停止工作</span><span class="sxs-lookup"><span data-stu-id="b180e-497">The Lync Server Control Panel stops working in a VMware environment after the Microsoft Silverlight browser plug-in is updated to version 5</span></span>

<span data-ttu-id="b180e-498">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-498">**Issue:**</span></span>

<span data-ttu-id="b180e-499">如果在 VMware 环境中使用 Lync Server 控制面板，则在将 Silverlight 升级到版本5后，Lync Server 控制面板可能会停止工作。</span><span class="sxs-lookup"><span data-stu-id="b180e-499">If you use the Lync Server Control Panel in a VMware environment, the Lync Server Control Panel may stop working after you upgrade Silverlight to version 5.</span></span>

<span data-ttu-id="b180e-500">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-500">**Workaround:**</span></span>

<span data-ttu-id="b180e-501">若要解决此问题，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b180e-501">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="b180e-502">卸载 Silverlight 5，然后从安装 Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) 。</span><span class="sxs-lookup"><span data-stu-id="b180e-502">Uninstall Silverlight 5, and then install Silverlight 4 from [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0).</span></span>

  - <span data-ttu-id="b180e-503">从不是 VMware 虚拟计算机的计算机打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b180e-503">Open the Lync Server Control Panel from a computer that is not a VMware virtual computer.</span></span>
    
    <span data-ttu-id="b180e-504">若要从远程计算机打开 Lync Server 控制面板，请在计算机上安装 Lync Server 管理工具，然后从 Windows " **开始** " 菜单启动 "Lync server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b180e-504">To open the Lync Server Control Panel from a remote computer, install Lync Server Administration tools on the computer, and then start the Lync Server Control Panel from the Windows **Start** menu.</span></span>
    
    <span data-ttu-id="b180e-505">您还可以通过在 web 浏览器中输入 URL 来打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b180e-505">You can also open the Lync Server Control Panel by entering the URL in a web browser.</span></span> <span data-ttu-id="b180e-506">该 URL 将类似于 https:// \<frontend\_pool\_fqdn\> /cscp。</span><span class="sxs-lookup"><span data-stu-id="b180e-506">The URL will be similar to https://\<frontend\_pool\_fqdn\>/cscp.</span></span>

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a><span data-ttu-id="b180e-507">在拓扑生成器中删除镜像数据库后，管理员无法运行 csMirrorDB cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b180e-507">An administrator cannot run the Uninstall-csMirrorDB cmdlet after removing the mirroring database in Topology Builder</span></span>

<span data-ttu-id="b180e-508">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-508">**Issue:**</span></span>

<span data-ttu-id="b180e-509">当管理员在拓扑生成器中禁用镜像数据库，然后在拓扑生成器中删除镜像数据库时，管理员可以在任务列表中显示一条消息，以运行 **csMirrorDatabase** cmdlet 以删除 SQL Server 中的镜像。</span><span class="sxs-lookup"><span data-stu-id="b180e-509">When an administrator disables a mirroring database in Topology Builder, and then deletes the mirroring database in Topology Builder, a message is displayed in the To do list for the administrator to run the **Uninstall-csMirrorDatabase** cmdlet to remove mirroring from SQL Server.</span></span> <span data-ttu-id="b180e-510">当管理员尝试运行 cmdlet 时，它会失败。</span><span class="sxs-lookup"><span data-stu-id="b180e-510">When the administrator attempts to run the cmdlet, it fails.</span></span>

<span data-ttu-id="b180e-511">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-511">**Workaround:**</span></span>

<span data-ttu-id="b180e-512">若要在拓扑生成器中删除池的 SQL 镜像，必须首先使用 cmdlet 删除 SQL Server 中的镜像。</span><span class="sxs-lookup"><span data-stu-id="b180e-512">To remove SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="b180e-513">随后，您可使用拓扑生成器删除拓扑中的镜像。</span><span class="sxs-lookup"><span data-stu-id="b180e-513">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="b180e-514">若要删除 SQL Server 中的镜像，请使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b180e-514">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="b180e-515">例如，若要删除镜像并删除用户数据库的数据库，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="b180e-515">For example, to remove mirroring and drop the databases for the user databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="b180e-516">*DropExistingDatabasesOnMirror*参数会导致从镜像中删除受影响的数据库。</span><span class="sxs-lookup"><span data-stu-id="b180e-516">The *DropExistingDatabasesOnMirror* parameter causes the affected databases to be deleted from the mirror.</span></span> <span data-ttu-id="b180e-517">然后，若要从拓扑中删除镜像，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b180e-517">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="b180e-518">在拓扑生成器中，右键单击池并单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b180e-518">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="b180e-519">清除 " **启用 SQL 存储镜像** "，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b180e-519">Clear **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="b180e-520">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="b180e-520">Publish the topology.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="b180e-521">只要您对后端数据库镜像关系进行了更改，就必须重新启动池中的所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="b180e-521">Whenever you make a change to a back-end database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span>



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a><span data-ttu-id="b180e-522">当管理员尝试删除具有关联见证存储的前端池的部署时，会在拓扑生成器中返回验证错误。</span><span class="sxs-lookup"><span data-stu-id="b180e-522">Validation errors are returned in Topology Builder when an administrator attempts to remove a deployment with a Front End pool that has an associated witness store</span></span>

<span data-ttu-id="b180e-523">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-523">**Issue:**</span></span>

<span data-ttu-id="b180e-524">如果管理员尝试使用拓扑生成器中的 " **删除部署** " 命令来删除包含具有关联见证存储的前端池的部署，则在拓扑生成器中显示验证错误，并且该操作将不会继续。</span><span class="sxs-lookup"><span data-stu-id="b180e-524">If an administrator attempts to use the **Remove Deployment** command in Topology Builder to remove a deployment that includes a Front End pool with an associated witness store, a validation error is displayed in Topology Builder and the action will not proceed.</span></span>

<span data-ttu-id="b180e-525">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-525">**Workaround:**</span></span>

<span data-ttu-id="b180e-526">若要解决此问题，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b180e-526">To work around this issue, do one of the following:</span></span>

  - <span data-ttu-id="b180e-527">在尝试删除部署之前，请先删除见证存储。</span><span class="sxs-lookup"><span data-stu-id="b180e-527">Remove the witness store before attempting to remove the deployment.</span></span>

  - <span data-ttu-id="b180e-528">为前端池添加见证存储，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="b180e-528">Add a witness store for the Front End pool and then remove it.</span></span>

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a><span data-ttu-id="b180e-529">规划工具和拓扑生成器之间的持久聊天服务器部署信息不一致</span><span class="sxs-lookup"><span data-stu-id="b180e-529">Persistent Chat Server deployment information is inconsistent between the Planning Tool and Topology Builder</span></span>

<span data-ttu-id="b180e-530">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-530">**Issue:**</span></span>

<span data-ttu-id="b180e-531">当启用灾难恢复的情况下，在 Lync Server 2013 中，规划工具会输出持久聊天服务器部署的站点拓扑图，网站拓扑图包含多个 (物理) 站点，在每个站点上均匀分配了持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="b180e-531">When the Lync Server 2013, Planning Tool outputs the site topology diagram for a Persistent Chat Server deployment with disaster recovery enabled, the site topology diagram includes multiple (physical) sites, with evenly assigned Persistent Chat Servers at each site.</span></span> <span data-ttu-id="b180e-532">在拓扑生成器中，所有持久聊天服务器都表示为属于单个 (逻辑) 网站，并列在同一个持久聊天服务器池节点下。</span><span class="sxs-lookup"><span data-stu-id="b180e-532">In Topology Builder, all Persistent Chat Servers are represented as belonging to a single (logical) site, and are listed under the same Persistent Chat Server pool node.</span></span>

<span data-ttu-id="b180e-533">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-533">**Workaround:**</span></span>

<span data-ttu-id="b180e-534">目前，我们没有解决此问题的方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-534">Currently, we do not have a workaround for this issue.</span></span> <span data-ttu-id="b180e-535">用户应分析持久聊天服务器部署的规划工具的输出，并修改计划以满足其特定需求。</span><span class="sxs-lookup"><span data-stu-id="b180e-535">The user should analyze the output of the Planning Tool for the Persistent Chat Server deployment, and modify the plan to meet their specific needs.</span></span>

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a><span data-ttu-id="b180e-536">本地化</span><span class="sxs-lookup"><span data-stu-id="b180e-536">Localization</span></span>

<div>

## <a name="monitoring"></a><span data-ttu-id="b180e-537">监控</span><span class="sxs-lookup"><span data-stu-id="b180e-537">Monitoring</span></span>

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a><span data-ttu-id="b180e-538">在某些情况下，在使用 Lync Server 的东亚版时，部署监控报告向导会显示错误的字符</span><span class="sxs-lookup"><span data-stu-id="b180e-538">The Deploy Monitoring Reports wizard displays incorrect characters under certain circumstances when using the East Asian version of Lync Server</span></span>

<span data-ttu-id="b180e-539">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-539">**Issue:**</span></span>

<span data-ttu-id="b180e-540">在使用东亚语言版本的 Lync Server 2013 时（例如，中文 (简化) 、中文 (传统) 、日语或朝鲜语）在 "系统区域设置" 未设置为东亚语言的操作系统中，"部署监控报告" 向导将显示问号或其他字符，而不是本地化的邮件。</span><span class="sxs-lookup"><span data-stu-id="b180e-540">When using an East Asian version of Lync Server 2013—for example, Chinese (Simplified), Chinese (Traditional), Japanese, or Korean—on an operating system that has the system locale not set to an East Asian language, the Deploy Monitoring Reports wizard will display question marks or other characters instead of localized messages.</span></span>

<span data-ttu-id="b180e-541">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-541">**Workaround:**</span></span>

<span data-ttu-id="b180e-542">若要更正此问题，请将操作系统和 Lync Server 2013 的区域设置为相同的语言，这将正确显示所有邮件。</span><span class="sxs-lookup"><span data-stu-id="b180e-542">To correct this issue, set the locale for the operating system and Lync Server 2013 to the same language, which will display all messages correctly.</span></span>

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="b180e-543">Lync 服务器控制面板</span><span class="sxs-lookup"><span data-stu-id="b180e-543">Lync Server Control Panel</span></span>

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a><span data-ttu-id="b180e-544">在某些情况下，当单击顶部导航栏中的最后一个项目时，Lync Server 控制面板的页面上的第一个项目会消失。</span><span class="sxs-lookup"><span data-stu-id="b180e-544">In certain cases, the first item in the top navigation bar on a page of Lync Server Control Panel disappears when the last item in the top navigation bar is clicked</span></span>

<span data-ttu-id="b180e-545">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-545">**Issue:**</span></span>

<span data-ttu-id="b180e-546">在以下三种情况下，在 Lync Server 控制面板的页面上单击顶部导航栏中的最后一项将导致顶部导航栏中的第一个项目消失：</span><span class="sxs-lookup"><span data-stu-id="b180e-546">There are three known cases where clicking the last item in the top navigation bar on a page of the Lync Server Control Panel will cause the first item in the top navigation bar to disappear:</span></span>

  - <span data-ttu-id="b180e-547">在法语版本中，在页面 "Féderation et accès externe" 中，当单击 "D'accès externe PARTENAIRES" 时，项目 "Stratégie fédérés XMPP" 将消失。</span><span class="sxs-lookup"><span data-stu-id="b180e-547">In the French of version, on the page "Féderation et accès externe," the item "Stratégie d'accès externe" will disappear when "Partenaires fédérés XMPP" is clicked.</span></span>

  - <span data-ttu-id="b180e-548">在德语版本中，在 "客户端" 页上，单击 "Pushbenachrichtigungskonfiguration" 时，项目 "Clientversionskonfiguration" 将消失。</span><span class="sxs-lookup"><span data-stu-id="b180e-548">In the German version, on the "Clients" page, the item "Clientversionskonfiguration" disappears when "Pushbenachrichtigungskonfiguration" is clicked.</span></span>

  - <span data-ttu-id="b180e-549">在俄语版本中，在 "Конфигурациясети" 页上，单击 "Маршрутрегиона" 时，项目 "Глобально" 将消失。</span><span class="sxs-lookup"><span data-stu-id="b180e-549">In the Russian version, on "Конфигурация сети" page, the item "Глобально" disappears when "Маршрут региона" is clicked.</span></span>

<span data-ttu-id="b180e-550">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-550">**Workaround:**</span></span>

<span data-ttu-id="b180e-551">若要解决此问题，请在浏览器中刷新 Lync Server 控制面板的页面。</span><span class="sxs-lookup"><span data-stu-id="b180e-551">To work around this issue, refresh the page of the Lync Server Control Panel in your browser.</span></span> <span data-ttu-id="b180e-552">页面将在浏览器中加载，并显示顶部导航栏中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="b180e-552">The page will load in the browser with all of the items in the top navigation bar displayed.</span></span>

</div>

</div>

<div>

## <a name="address-book"></a><span data-ttu-id="b180e-553">通讯簿</span><span class="sxs-lookup"><span data-stu-id="b180e-553">Address Book</span></span>

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a><span data-ttu-id="b180e-554">通讯簿中的索引在某些语言中无法按预期工作</span><span class="sxs-lookup"><span data-stu-id="b180e-554">Indexing in the Address Book does not work as expected in some languages</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b180e-555">本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="b180e-555">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b180e-556">如果用户的属性包含索引字段，并且该字段只包含无法编制索引的字符，则该用户将不会出现在通讯簿中执行的搜索中。</span><span class="sxs-lookup"><span data-stu-id="b180e-556">If a user’s properties contain an indexed field, and that field contains only characters that cannot be indexed, then the user will not appear in searches performed in the Address Book.</span></span>

<span data-ttu-id="b180e-557">无法对以下字符和区域编制索引：</span><span class="sxs-lookup"><span data-stu-id="b180e-557">The following characters and locales cannot be indexed:</span></span>

  - <span data-ttu-id="b180e-558">大写的西里尔文、希腊语和亚美尼亚字符</span><span class="sxs-lookup"><span data-stu-id="b180e-558">Upper-case Cyrillic, Greek, and Armenian characters</span></span>

  - <span data-ttu-id="b180e-559">大写重音字符</span><span class="sxs-lookup"><span data-stu-id="b180e-559">Upper-case accented characters</span></span>

  - <span data-ttu-id="b180e-560">泰语</span><span class="sxs-lookup"><span data-stu-id="b180e-560">Thai</span></span>

  - <span data-ttu-id="b180e-561">老挝语</span><span class="sxs-lookup"><span data-stu-id="b180e-561">Lao</span></span>

  - <span data-ttu-id="b180e-562">缅甸</span><span class="sxs-lookup"><span data-stu-id="b180e-562">Myanmar</span></span>

  - <span data-ttu-id="b180e-563">梵文</span><span class="sxs-lookup"><span data-stu-id="b180e-563">Devanagari</span></span>

  - <span data-ttu-id="b180e-564">埃塞俄比亚语</span><span class="sxs-lookup"><span data-stu-id="b180e-564">Ethiopic</span></span>

  - <span data-ttu-id="b180e-565">藏语</span><span class="sxs-lookup"><span data-stu-id="b180e-565">Tibetan</span></span>

  - <span data-ttu-id="b180e-566">孟加拉语</span><span class="sxs-lookup"><span data-stu-id="b180e-566">Bengali</span></span>

  - <span data-ttu-id="b180e-567">古吉拉特语</span><span class="sxs-lookup"><span data-stu-id="b180e-567">Gujarati</span></span>

  - <span data-ttu-id="b180e-568">泰卢固语</span><span class="sxs-lookup"><span data-stu-id="b180e-568">Telugu</span></span>

  - <span data-ttu-id="b180e-569">所有其他印度语脚本</span><span class="sxs-lookup"><span data-stu-id="b180e-569">All other Indic scripts</span></span>

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a><span data-ttu-id="b180e-570">Lync Web App、Web 计划程序和 Web 组件</span><span class="sxs-lookup"><span data-stu-id="b180e-570">Lync Web App, Web Scheduler, and Web components</span></span>

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a><span data-ttu-id="b180e-571">Lync Web 计划程序中某些语言的语言回退、拨入、加入启动器、持久聊天室管理和 OCTab 可能无法按预期工作</span><span class="sxs-lookup"><span data-stu-id="b180e-571">Language fallback for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab might not work as expected</span></span>

<span data-ttu-id="b180e-572">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-572">**Issue:**</span></span>

<span data-ttu-id="b180e-573">在 web 浏览器中选择非特定区域设置时 (在 Internet Explorer 中例如，没有进一步规范的语言名称（如 "挪威 \[ no \] " ) ，而不是指定语言、脚本和区域设置的区域设置 (例如 "挪威语、博克马尔语 (挪威) \[ nb-no \] " ) 可能会在 Lync Web 计划程序、电话拨入、加入启动器、持久聊天室管理和 OCTab 中导致意外的显示行为。</span><span class="sxs-lookup"><span data-stu-id="b180e-573">When selecting a neutral locale in a web browser (in Internet Explorer, for example, the language name without further specification, like "Norwegian \[no\]") instead of a locale specifying language, script and locale (such as "Norwegian, Bokmål (Norway) \[nb-NO\]") might lead to unexpected display behavior for certain languages in Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab.</span></span> <span data-ttu-id="b180e-574">例如，当选择以下任一种语言时，用户可能会看到英语页面：</span><span class="sxs-lookup"><span data-stu-id="b180e-574">For example, users might see the English page when one of the following languages is selected:</span></span>

  - <span data-ttu-id="b180e-575">挪威语</span><span class="sxs-lookup"><span data-stu-id="b180e-575">Norwegian</span></span>

  - <span data-ttu-id="b180e-576">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="b180e-576">Portuguese</span></span>

  - <span data-ttu-id="b180e-577">塞尔维亚语</span><span class="sxs-lookup"><span data-stu-id="b180e-577">Serbian</span></span>

<span data-ttu-id="b180e-578">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-578">**Workaround:**</span></span>

<span data-ttu-id="b180e-579">如果要选择非特定区域设置的语言，请始终确保同时使用脚本和/或国家/地区代码在浏览器语言首选项列表中添加具有特定区域设置 (的语言，) 为其他语言。</span><span class="sxs-lookup"><span data-stu-id="b180e-579">If you want to select a language with a neutral locale, always make sure that you also add the language with a specific locale (with script and/or country code) as an additional language in your browser's language preference list.</span></span>

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a><span data-ttu-id="b180e-580">在某些 Web 浏览器中使用 Lync Web 计划程序、电话拨入、加入启动器、持久聊天室管理和 OCTab 时，对阿泽里语和乌兹别克语区域设置的支持有限</span><span class="sxs-lookup"><span data-stu-id="b180e-580">There is limited support for Azeri and Uzbek locales when using Lync Web Scheduler, Dial-In, Join Launcher, Persistent Chat Room Management, and OCTab in some web browsers</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="b180e-581">本节中的信息适用于 Lync Server 2013 的累积更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="b180e-581">The information in this section pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="b180e-582">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-582">**Issue:**</span></span>

<span data-ttu-id="b180e-583">当您使用 Internet Explorer 8 或 Internet Explorer 9，并将浏览器语言设置为阿塞里语 (拉丁语) 或乌兹别克 (拉丁) 时，将以英语或在浏览器中设置的首选语言显示 "拨入" 和 "联接启动器" 页面。</span><span class="sxs-lookup"><span data-stu-id="b180e-583">When you use Internet Explorer 8 or Internet Explorer 9, and set the browser language to Azeri (Latin) or Uzbek (Latin), the Dial-in and Join Launcher pages will be displayed in English or the preferred language set in the browser.</span></span>

<span data-ttu-id="b180e-584">当您使用 Firefox 或 Chrome 浏览器，并将浏览器语言设置为阿塞拜疆语 (拉丁语) 或乌兹别克 (拉丁) ，Lync Web App、Lync Web 计划程序和 RGS OCTab 将显示为英语或浏览器的首选语言集。</span><span class="sxs-lookup"><span data-stu-id="b180e-584">When you use Firefox or Chrome browsers, and you set the browser language to Azeri (Latin) or Uzbek (Latin), the Lync Web App, Lync Web Scheduler, and RGS OCTab will be shown in English or the preferred language set for the browser.</span></span>

<span data-ttu-id="b180e-585">在 Safari 浏览器中不支持乌兹别克 (拉丁语) 区域设置。</span><span class="sxs-lookup"><span data-stu-id="b180e-585">The Uzbek (Latin) locale is not supported in the Safari browser.</span></span>

<span data-ttu-id="b180e-586">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-586">**Workaround:**</span></span>

<span data-ttu-id="b180e-587">这些问题尚无解决方法。</span><span class="sxs-lookup"><span data-stu-id="b180e-587">There is not workaround for these issues.</span></span>

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a><span data-ttu-id="b180e-588">在 Lync Web App 的罗马尼亚版本中，"加入会议来自" 列表缺少下拉箭头</span><span class="sxs-lookup"><span data-stu-id="b180e-588">The drop-down arrow is missing for "Join meeting from" list in the Romanian version of Lync Web App</span></span>

<span data-ttu-id="b180e-589">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-589">**Issue:**</span></span>

<span data-ttu-id="b180e-590">使用罗马尼亚语版本的 Lync Web App 的用户执行以下步骤时，将不会在下拉列表中显示 " **加入会议** " 下拉箭头：</span><span class="sxs-lookup"><span data-stu-id="b180e-590">When a user who is using the Romanian version of Lync Web App performs the following steps, the drop-down arrow is not displayed for **Join meeting** in drop-down list:</span></span>

1.  <span data-ttu-id="b180e-591">在 "**常规**" 选项卡上选择 "**在此计算机上保存我**"。</span><span class="sxs-lookup"><span data-stu-id="b180e-591">Select **Remember me on this computer** on the **General** tab.</span></span>

2.  <span data-ttu-id="b180e-592">选择 " **电话** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b180e-592">Select the **Phone** tab.</span></span>

3.  <span data-ttu-id="b180e-593">单击中的 " **加入会议**" 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="b180e-593">Click the drop-down list for **Join meeting from**.</span></span>
    
    <span data-ttu-id="b180e-594">用户将看不到指示具有默认 **Lync Web 应用程序**的更多选项的箭头，其中包括：不在罗马尼亚语中 **加入音频** (，罗马尼亚，"Număr nou" ) 中的 ") 和 **新数字**" (。</span><span class="sxs-lookup"><span data-stu-id="b180e-594">Users will not see an arrow that indicates that there are more options than the default **Lync Web App**, which include: **Don't join audio** (in Romanian, "Nu se asociaža la componenta audio") and **New number**" (in Romanian, "Număr nou").</span></span>

<span data-ttu-id="b180e-595">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-595">**Workaround:**</span></span>

<span data-ttu-id="b180e-596">尽管不显示此下拉列表的箭头，但用户仍可以通过单击默认值来选择列表中的其他设置。</span><span class="sxs-lookup"><span data-stu-id="b180e-596">Even though the arrow for this drop-down list is not displayed, users can still select the additional settings in the list by clicking on the default value.</span></span>

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a><span data-ttu-id="b180e-597">使用采用土耳其语版本的 Lync Web 计划程序时，在使用 "谁是演示者" 下使用 "我选择的人员" 选项时无法保存会议</span><span class="sxs-lookup"><span data-stu-id="b180e-597">When using the Turkish version of Lync Web Scheduler, a meeting cannot be saved when using the "People I choose" option under "Who is a presenter"</span></span>

<span data-ttu-id="b180e-598">**问题**</span><span class="sxs-lookup"><span data-stu-id="b180e-598">**Issue:**</span></span>

<span data-ttu-id="b180e-599">在土耳其语版本的 Lync Web 计划程序中创建或编辑会议时，不支持在 "谁是演示者" 下使用 "我选择的人员" 选项。</span><span class="sxs-lookup"><span data-stu-id="b180e-599">When creating or editing a meeting in the Turkish version of the Lync Web Scheduler, the option "People I choose" under "Who is a presenter" is not supported.</span></span> <span data-ttu-id="b180e-600">如果选择此选项，则无法保存会议。</span><span class="sxs-lookup"><span data-stu-id="b180e-600">When this option is selected, the meeting can't be saved.</span></span> <span data-ttu-id="b180e-601">而是显示一条错误消息，指示无法将一个或多个人员变为演示者。</span><span class="sxs-lookup"><span data-stu-id="b180e-601">Instead, an error message appears, indicating that one or more people cannot be made presenters.</span></span>

<span data-ttu-id="b180e-602">**规避**</span><span class="sxs-lookup"><span data-stu-id="b180e-602">**Workaround:**</span></span>

<span data-ttu-id="b180e-603">若要解决此问题，用户可以使用默认选项 "我的公司的人员" 或任何其他选择，如 "仅组织者" 或 "所有人（包含我的公司之外的人）"。</span><span class="sxs-lookup"><span data-stu-id="b180e-603">To work around this issue, users can use the default option of "People from my company," or any other choice, such as "Only Organizer" or "Everyone including people outside of my company."</span></span> <span data-ttu-id="b180e-604">组织者在加入会议之后，可以降级或将用户提升为正确的角色。</span><span class="sxs-lookup"><span data-stu-id="b180e-604">The organizer can demote or promote people to their correct roles later, after they have joined the meeting.</span></span>

<span data-ttu-id="b180e-605">或者，了解其他语言的用户可以将其浏览器中的语言选择更改为其他43支持的语言之一，并尝试使用 "用户选择" 选项。</span><span class="sxs-lookup"><span data-stu-id="b180e-605">Alternatively, users who understand another language can change the language selection in their browser to one of the other 43 supported languages and attempt to use the “People I choose” option.</span></span>

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a><span data-ttu-id="b180e-606">版权</span><span class="sxs-lookup"><span data-stu-id="b180e-606">Copyright</span></span>

<span data-ttu-id="b180e-607">本文档支持软件产品的预发布版本，在最终商业版发布之前可能会有重大更改，并且是 Microsoft Corporation 的机密和专有信息。</span><span class="sxs-lookup"><span data-stu-id="b180e-607">This document supports a preliminary release of a software product that may be changed substantially prior to final commercial release, and is the confidential and proprietary information of Microsoft Corporation.</span></span> <span data-ttu-id="b180e-608">本应依照收件人和 Microsoft 之间的保密协议泄露。</span><span class="sxs-lookup"><span data-stu-id="b180e-608">It is disclosed pursuant to a non-disclosure agreement between the recipient and Microsoft.</span></span> <span data-ttu-id="b180e-609">本文档仅用于提供信息，Microsoft 不会在本文档中作出任何明示或暗示的担保。</span><span class="sxs-lookup"><span data-stu-id="b180e-609">This document is provided for informational purposes only and Microsoft makes no warranties, either express or implied, in this document.</span></span> <span data-ttu-id="b180e-610">本文档中的信息（包括 URL 和其他 Internet 网站引用）如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="b180e-610">Information in this document, including URL and other Internet website references, is subject to change without notice.</span></span> <span data-ttu-id="b180e-611">使用本文档的全部风险或结果由用户承担。</span><span class="sxs-lookup"><span data-stu-id="b180e-611">The entire risk of the use or the results from the use of this document remains with the user.</span></span> <span data-ttu-id="b180e-612">除非另有说明，否则此处示例中描述的公司、组织、产品、域名、电子邮件地址、徽标、人员、地点和事件均属虚构。</span><span class="sxs-lookup"><span data-stu-id="b180e-612">Unless otherwise noted, the companies, organizations, products, domain names, email addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="b180e-613">与任何真实公司、组织、产品、域名、电子邮件地址、徽标、人员、地点或事件无任何关联，也不应进行推断。</span><span class="sxs-lookup"><span data-stu-id="b180e-613">No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="b180e-614">遵守所有适用的版权法是用户的责任。</span><span class="sxs-lookup"><span data-stu-id="b180e-614">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="b180e-615">在不限制版权许可的权利的情况下，如果没有得到 Microsoft 公司明确书面许可，本文档的任何部分不可被复制、存储或引进检索系统，或者以任何形式、任何方式（电子、机械、影印、录音或其他）或为任何目的进行传播。</span><span class="sxs-lookup"><span data-stu-id="b180e-615">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="b180e-p162">Microsoft 可能对本文档中涉及的主题拥有专利、专利申请、商标、版权或其他知识产权。除非 Microsoft 的任何书面许可协议中明确表示，否则提供本文档并不表示授权您使用这些专利、商标、版权或其他知识产权。</span><span class="sxs-lookup"><span data-stu-id="b180e-p162">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document. Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>

<span data-ttu-id="b180e-618">© 2012 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="b180e-618">© 2012 Microsoft Corporation.</span></span> <span data-ttu-id="b180e-619">保留所有权利。</span><span class="sxs-lookup"><span data-stu-id="b180e-619">All rights reserved.</span></span>

<span data-ttu-id="b180e-620">Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook 和 SQL Server 是 Microsoft Corporation 在美国和/或其他国家/地区的注册商标或商标。</span><span class="sxs-lookup"><span data-stu-id="b180e-620">Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook, and SQL Server are either registered trademarks or trademarks of Microsoft Corporation in the United States and/or other countries/regions.</span></span>

<span data-ttu-id="b180e-621">其他所有商标均为其各自所有者的财产。</span><span class="sxs-lookup"><span data-stu-id="b180e-621">All other trademarks are property of their respective owners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

