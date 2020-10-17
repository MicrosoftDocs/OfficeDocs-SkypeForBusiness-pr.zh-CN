---
title: Lync Server 2013：防病毒扫描排除
description: Lync Server 2013：防病毒扫描排除项。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561908"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="db00c-103">Lync Server 2013 的防病毒扫描排除</span><span class="sxs-lookup"><span data-stu-id="db00c-103">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db00c-104">_**上次修改的主题：** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="db00c-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="db00c-105">若要确保防病毒扫描程序不会干扰 Lync Server 2013 的操作，必须排除在其上运行防病毒扫描程序的每个 Lync Server 2013 服务器或服务器角色的特定进程和目录。</span><span class="sxs-lookup"><span data-stu-id="db00c-105">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="db00c-106">应排除以下进程和目录：</span><span class="sxs-lookup"><span data-stu-id="db00c-106">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db00c-107">下面列出的文件夹和文件位置是 Lync Server 2013 的默认位置。</span><span class="sxs-lookup"><span data-stu-id="db00c-107">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="db00c-108">对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。</span><span class="sxs-lookup"><span data-stu-id="db00c-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="db00c-109">请注意，某些防病毒程序可能需要其排除列表的绝对（而不是相对路径）。</span><span class="sxs-lookup"><span data-stu-id="db00c-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="db00c-110">Lync Server 2013 进程：</span><span class="sxs-lookup"><span data-stu-id="db00c-110">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="db00c-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-111">ABServer.exe</span></span>
    
      - <span data-ttu-id="db00c-112">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-112">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="db00c-113">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-113">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="db00c-114">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-114">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="db00c-115">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-115">ChannelService.exe</span></span>
    
      - <span data-ttu-id="db00c-116">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-116">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="db00c-117">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-117">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="db00c-118">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-118">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="db00c-119">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-119">DataProxy.exe</span></span>
    
      - <span data-ttu-id="db00c-120">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-120">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="db00c-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-121">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="db00c-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-122">LysSvc.exe</span></span>
    
      - <span data-ttu-id="db00c-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-123">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="db00c-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-124">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="db00c-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-125">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="db00c-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-126">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="db00c-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-127">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="db00c-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-128">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="db00c-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-129">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="db00c-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-130">RtcHost.exe</span></span>
    
      - <span data-ttu-id="db00c-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-131">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="db00c-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-132">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="db00c-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-133">XmppTGW.exe</span></span>

  - <span data-ttu-id="db00c-134">Windows Fabric 主机服务进程：</span><span class="sxs-lookup"><span data-stu-id="db00c-134">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="db00c-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-135">Fabric.exe</span></span>
    
      - <span data-ttu-id="db00c-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-136">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="db00c-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-137">FabricHost.exe</span></span>

  - <span data-ttu-id="db00c-138">IIS 进程：</span><span class="sxs-lookup"><span data-stu-id="db00c-138">IIS processes:</span></span>
    
      - <span data-ttu-id="db00c-139">% systemroot% \\ system32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-139">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="db00c-140">% systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-140">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="db00c-141">SQL Server Back-End 进程：</span><span class="sxs-lookup"><span data-stu-id="db00c-141">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="db00c-142">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-142">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="db00c-143">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSRS11。MSSQLSERVER \\ Reporting Services \\ ReportServer \\ Bin \\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-143">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="db00c-144">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSAS11。MSSQLSERVER \\ OLAP \\ Bin \\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-144">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="db00c-145">SQL Server Front-End 进程：</span><span class="sxs-lookup"><span data-stu-id="db00c-145">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="db00c-146">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="db00c-147">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="db00c-147">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="db00c-148">目录和文件：</span><span class="sxs-lookup"><span data-stu-id="db00c-148">Directories and files:</span></span>
    
      - <span data-ttu-id="db00c-149">% systemroot% \\ System32 \\ 日志日志</span><span class="sxs-lookup"><span data-stu-id="db00c-149">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="db00c-150">% systemroot% \\ SysWow64 \\ 日志日志</span><span class="sxs-lookup"><span data-stu-id="db00c-150">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="db00c-151">% systemroot% \\ Microsoft.NET \\ 程序集 \\ GAC \_ MSIL</span><span class="sxs-lookup"><span data-stu-id="db00c-151">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="db00c-152">% programfiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db00c-152">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="db00c-153">% programfiles% \\ 公共文件 \\ Microsoft Lync Server 2013 \\ 观察程序节点</span><span class="sxs-lookup"><span data-stu-id="db00c-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="db00c-154">% programfiles% \\ 通用文件 \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db00c-154">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="db00c-155">% 系统驱动器% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="db00c-155">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="db00c-156">文件共享存储（在拓扑生成器中指定）。</span><span class="sxs-lookup"><span data-stu-id="db00c-156">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="db00c-157">文件存储在拓扑生成器中指定。</span><span class="sxs-lookup"><span data-stu-id="db00c-157">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="db00c-158">SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。</span><span class="sxs-lookup"><span data-stu-id="db00c-158">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="db00c-159">可以在拓扑生成器中指定数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="db00c-159">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="db00c-160">有关每个数据库的数据和日志文件的详细信息（包括默认名称），请参阅部署文档中 [的适用于 Lync server 2013 的 SQL Server 数据和日志文件放置](lync-server-2013-sql-server-data-and-log-file-placement.md) 。</span><span class="sxs-lookup"><span data-stu-id="db00c-160">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="db00c-161">SQL Server 数据和日志文件，包括用于前端数据库、Lync 存储和 RtcDatabase 存储的文件。</span><span class="sxs-lookup"><span data-stu-id="db00c-161">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="db00c-162">它们通常位于% localdrive% \\ CSData。</span><span class="sxs-lookup"><span data-stu-id="db00c-162">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

