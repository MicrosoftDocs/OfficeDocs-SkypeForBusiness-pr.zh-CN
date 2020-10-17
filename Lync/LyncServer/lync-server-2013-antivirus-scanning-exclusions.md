---
title: Lync Server 2013：防病毒扫描排除
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
ms.openlocfilehash: 4b67f1472bbb8225bf952b5b678bcae8401d211d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508969"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="b1ac1-102">Lync Server 2013 的防病毒扫描排除</span><span class="sxs-lookup"><span data-stu-id="b1ac1-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1ac1-103">_**上次修改的主题：** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="b1ac1-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="b1ac1-104">若要确保防病毒扫描程序不会干扰 Lync Server 2013 的操作，必须排除在其上运行防病毒扫描程序的每个 Lync Server 2013 服务器或服务器角色的特定进程和目录。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="b1ac1-105">应排除以下进程和目录：</span><span class="sxs-lookup"><span data-stu-id="b1ac1-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1ac1-106">下面列出的文件夹和文件位置是 Lync Server 2013 的默认位置。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="b1ac1-107">对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b1ac1-108">请注意，某些防病毒程序可能需要其排除列表的绝对（而不是相对路径）。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="b1ac1-109">Lync Server 2013 进程：</span><span class="sxs-lookup"><span data-stu-id="b1ac1-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="b1ac1-110">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="b1ac1-111">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="b1ac1-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="b1ac1-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="b1ac1-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="b1ac1-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="b1ac1-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="b1ac1-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="b1ac1-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="b1ac1-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="b1ac1-120">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="b1ac1-121">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="b1ac1-122">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="b1ac1-123">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="b1ac1-124">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="b1ac1-125">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="b1ac1-126">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="b1ac1-127">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="b1ac1-128">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="b1ac1-129">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="b1ac1-130">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="b1ac1-131">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="b1ac1-132">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="b1ac1-133">Windows Fabric 主机服务进程：</span><span class="sxs-lookup"><span data-stu-id="b1ac1-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="b1ac1-134">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="b1ac1-135">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="b1ac1-136">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-136">FabricHost.exe</span></span>

  - <span data-ttu-id="b1ac1-137">IIS 进程：</span><span class="sxs-lookup"><span data-stu-id="b1ac1-137">IIS processes:</span></span>
    
      - <span data-ttu-id="b1ac1-138">% systemroot% \\ system32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="b1ac1-139">% systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="b1ac1-140">SQL Server Back-End 进程：</span><span class="sxs-lookup"><span data-stu-id="b1ac1-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="b1ac1-141">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="b1ac1-142">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSRS11。MSSQLSERVER \\ Reporting Services \\ ReportServer \\ Bin \\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="b1ac1-143">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSAS11。MSSQLSERVER \\ OLAP \\ Bin \\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="b1ac1-144">SQL Server Front-End 进程：</span><span class="sxs-lookup"><span data-stu-id="b1ac1-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="b1ac1-145">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="b1ac1-146">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11。RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="b1ac1-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="b1ac1-147">目录和文件：</span><span class="sxs-lookup"><span data-stu-id="b1ac1-147">Directories and files:</span></span>
    
      - <span data-ttu-id="b1ac1-148">% systemroot% \\ System32 \\ 日志日志</span><span class="sxs-lookup"><span data-stu-id="b1ac1-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="b1ac1-149">% systemroot% \\ SysWow64 \\ 日志日志</span><span class="sxs-lookup"><span data-stu-id="b1ac1-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="b1ac1-150">% systemroot% \\ Microsoft.NET \\ 程序集 \\ GAC \_ MSIL</span><span class="sxs-lookup"><span data-stu-id="b1ac1-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="b1ac1-151">% programfiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1ac1-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="b1ac1-152">% programfiles% \\ 公共文件 \\ Microsoft Lync Server 2013 \\ 观察程序节点</span><span class="sxs-lookup"><span data-stu-id="b1ac1-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="b1ac1-153">% programfiles% \\ 通用文件 \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1ac1-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="b1ac1-154">% 系统驱动器% \\ RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="b1ac1-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="b1ac1-155">文件共享存储（在拓扑生成器中指定）。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="b1ac1-156">文件存储在拓扑生成器中指定。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="b1ac1-157">SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="b1ac1-158">可以在拓扑生成器中指定数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="b1ac1-159">有关每个数据库的数据和日志文件的详细信息（包括默认名称），请参阅部署文档中 [的适用于 Lync server 2013 的 SQL Server 数据和日志文件放置](lync-server-2013-sql-server-data-and-log-file-placement.md) 。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b1ac1-160">SQL Server 数据和日志文件，包括用于前端数据库、Lync 存储和 RtcDatabase 存储的文件。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="b1ac1-161">它们通常位于% localdrive% \\ CSData。</span><span class="sxs-lookup"><span data-stu-id="b1ac1-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

