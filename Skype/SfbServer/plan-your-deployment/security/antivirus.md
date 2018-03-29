---
title: Skype for Business Server 2015 防病毒扫描排除项
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 与业务服务器 2015 Skype 防病毒扫描程序的概述。
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a><span data-ttu-id="22fb2-103">Skype for Business Server 2015 防病毒扫描排除项</span><span class="sxs-lookup"><span data-stu-id="22fb2-103">Antivirus scanning exclusions for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="22fb2-104">与业务服务器 2015 Skype 防病毒扫描程序的概述。</span><span class="sxs-lookup"><span data-stu-id="22fb2-104">Overview of antivirus scanner interoperation with Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="22fb2-105">若要确保防病毒扫描程序不会干扰业务服务器 2015年的 Skype 的操作，必须为每个 Skype 业务服务器 2015年服务器或服务器角色在其上运行的防病毒扫描排除特定的流程和目录。</span><span class="sxs-lookup"><span data-stu-id="22fb2-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server 2015, you must exclude specific processes and directories for each Skype for Business Server 2015 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="22fb2-106">应排除以下进程和目录：</span><span class="sxs-lookup"><span data-stu-id="22fb2-106">The following processes and directories should be excluded:</span></span>
  
> [!NOTE]
> <span data-ttu-id="22fb2-107">下面列出的文件夹和文件位置是业务服务器 2015 Skype 的默认位置。</span><span class="sxs-lookup"><span data-stu-id="22fb2-107">Folder and file locations listed below are the default locations for Skype for Business Server 2015.</span></span> <span data-ttu-id="22fb2-108">对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。</span><span class="sxs-lookup"><span data-stu-id="22fb2-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="22fb2-109">请注意，某些防病毒程序可能需要对排除列表使用绝对路径而不是相对路径。</span><span class="sxs-lookup"><span data-stu-id="22fb2-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span> 
  
- <span data-ttu-id="22fb2-110">Skype 的业务服务器 2015年进程：</span><span class="sxs-lookup"><span data-stu-id="22fb2-110">Skype for Business Server 2015 processes:</span></span>
    
  - <span data-ttu-id="22fb2-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-111">ABServer.exe</span></span>
    
  - <span data-ttu-id="22fb2-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-112">ASMCUSvc.exe</span></span>
    
  - <span data-ttu-id="22fb2-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-113">AVMCUSvc.exe</span></span>
    
  - <span data-ttu-id="22fb2-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-114">ChannelService.exe</span></span>
    
  - <span data-ttu-id="22fb2-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-115">ClsAgent.exe</span></span>
    
  - <span data-ttu-id="22fb2-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-116">ComplianceService.exe</span></span>
    
  - <span data-ttu-id="22fb2-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-117">DataMCUSvc.exe</span></span>
    
  - <span data-ttu-id="22fb2-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-118">DataProxy.exe</span></span>
    
  - <span data-ttu-id="22fb2-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-119">FileTransferAgent.exe</span></span>
    
  - <span data-ttu-id="22fb2-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-120">HealthAgent.exe</span></span>
    
  - <span data-ttu-id="22fb2-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-121">IMMCUSvc.exe</span></span>
    
  - <span data-ttu-id="22fb2-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-122">LysSvc.exe</span></span>
    
  - <span data-ttu-id="22fb2-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-123">MasterReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="22fb2-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-124">MediaRelaySvc.exe</span></span>
    
  - <span data-ttu-id="22fb2-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-125">MediationServerSvc.exe</span></span>
    
  - <span data-ttu-id="22fb2-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-126">MRASSvc.exe</span></span>
    
  - <span data-ttu-id="22fb2-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-127">OcsAppServerHost.exe</span></span>
    
  - <span data-ttu-id="22fb2-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-128">ReplicaReplicatorAgent.exe</span></span>
    
  - <span data-ttu-id="22fb2-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-129">ReplicationApp.exe</span></span>
    
  - <span data-ttu-id="22fb2-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-130">RtcHost.exe</span></span>
    
  - <span data-ttu-id="22fb2-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-131">RTCSrv.exe</span></span>
    
  - <span data-ttu-id="22fb2-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-132">XmppProxy.exe</span></span>
    
  - <span data-ttu-id="22fb2-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-133">XmppTGW.exe</span></span>
    
- <span data-ttu-id="22fb2-134">Windows Fabric Host Service 进程：</span><span class="sxs-lookup"><span data-stu-id="22fb2-134">Windows Fabric Host Service processes:</span></span>
    
  - <span data-ttu-id="22fb2-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-135">Fabric.exe</span></span>
    
  - <span data-ttu-id="22fb2-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-136">FabricDCA.exe</span></span>
    
  - <span data-ttu-id="22fb2-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-137">FabricHost.exe</span></span>
    
- <span data-ttu-id="22fb2-138">IIS 进程：</span><span class="sxs-lookup"><span data-stu-id="22fb2-138">IIS processes:</span></span>
    
  - <span data-ttu-id="22fb2-139">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-139">%systemroot%\system32\inetsrv\w3wp.exe</span></span>
    
  - <span data-ttu-id="22fb2-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-140">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>
    
- <span data-ttu-id="22fb2-141">SQL Server 后端进程：</span><span class="sxs-lookup"><span data-stu-id="22fb2-141">SQL Server Back-End processes:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22fb2-142">请注意，这些路径特定于 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="22fb2-142">Note that these paths are specific to SQL Server version.</span></span> 
  
  - <span data-ttu-id="22fb2-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-143">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="22fb2-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-144">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>
    
  - <span data-ttu-id="22fb2-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-145">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>
    
- <span data-ttu-id="22fb2-146">SQL Server 前端进程：</span><span class="sxs-lookup"><span data-stu-id="22fb2-146">SQL Server Front-End processes:</span></span>
    
  - <span data-ttu-id="22fb2-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-147">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="22fb2-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>
    
  - <span data-ttu-id="22fb2-149">Standard Edition 安装 RTC 实例</span><span class="sxs-lookup"><span data-stu-id="22fb2-149">Standard Edition Installation RTC Instance</span></span> 
    
  - <span data-ttu-id="22fb2-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="22fb2-150">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>
    
- <span data-ttu-id="22fb2-151">目录和文件：</span><span class="sxs-lookup"><span data-stu-id="22fb2-151">Directories and files:</span></span>
    
  - <span data-ttu-id="22fb2-152">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="22fb2-152">%systemroot%\System32\LogFiles</span></span>
    
  - <span data-ttu-id="22fb2-153">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="22fb2-153">%systemroot%\SysWow64\LogFiles</span></span>
    
  - <span data-ttu-id="22fb2-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="22fb2-154">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>
    
  - <span data-ttu-id="22fb2-155">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="22fb2-155">%programfiles%\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="22fb2-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="22fb2-156">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>
    
  - <span data-ttu-id="22fb2-157">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="22fb2-157">%programfiles%\Common Files\Skype for Business Server 2015</span></span>
    
  - <span data-ttu-id="22fb2-158">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="22fb2-158">%programfiles%\Common Files\Skype for Business Online</span></span>
    
  - <span data-ttu-id="22fb2-159">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="22fb2-159">%SystemDrive%\RtcReplicaRoot</span></span>
    
  - <span data-ttu-id="22fb2-p103">文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。</span><span class="sxs-lookup"><span data-stu-id="22fb2-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>
    
  - <span data-ttu-id="22fb2-162">SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。</span><span class="sxs-lookup"><span data-stu-id="22fb2-162">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="22fb2-163">可以在拓扑生成器中指定数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="22fb2-163">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="22fb2-164">有关每个数据库的数据和日志文件的详细信息，包括默认名称，请参阅[SQL Server 数据和日志文件位置](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)中部署文档。</span><span class="sxs-lookup"><span data-stu-id="22fb2-164">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>
    
  - <span data-ttu-id="22fb2-165">SQL Server 数据文件和日志文件，包括前端数据库，Skype 业务存储和 RtcDatabase 存储。</span><span class="sxs-lookup"><span data-stu-id="22fb2-165">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="22fb2-166">它们通常位于 %localdrive%\CSData 下。</span><span class="sxs-lookup"><span data-stu-id="22fb2-166">They are normally under %localdrive%\CSData.</span></span>
    

