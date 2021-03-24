---
title: Skype for Business Server 的防病毒扫描排除项
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 防病毒扫描程序与 Skype for Business Server 的互操作概述。
ms.openlocfilehash: 64646304b98de075fd9af0a82096da8c0bff2f12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104238"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="e539f-103">Skype for Business Server 的防病毒扫描排除项</span><span class="sxs-lookup"><span data-stu-id="e539f-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="e539f-104">防病毒扫描程序与 Skype for Business Server 的互操作概述。</span><span class="sxs-lookup"><span data-stu-id="e539f-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="e539f-105">为了确保防病毒扫描程序不会干扰 Skype for Business Server 的运行，必须排除运行防病毒扫描程序的每个 Skype for Business Server 服务器或服务器角色的特定进程和目录。</span><span class="sxs-lookup"><span data-stu-id="e539f-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="e539f-106">应排除以下进程和目录：</span><span class="sxs-lookup"><span data-stu-id="e539f-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="e539f-107">下面列出的文件夹和文件位置是 Skype for Business Server 的默认位置。</span><span class="sxs-lookup"><span data-stu-id="e539f-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="e539f-108">对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。</span><span class="sxs-lookup"><span data-stu-id="e539f-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e539f-109">请注意，某些防病毒程序可能需要其排除列表的绝对路径而非相对路径。</span><span class="sxs-lookup"><span data-stu-id="e539f-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="e539f-110">Skype for Business Server 进程：</span><span class="sxs-lookup"><span data-stu-id="e539f-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="e539f-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-111">ABServer.exe</span></span>

  - <span data-ttu-id="e539f-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="e539f-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="e539f-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-114">ChannelService.exe</span></span>

  - <span data-ttu-id="e539f-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="e539f-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="e539f-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="e539f-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-118">DataProxy.exe</span></span>

  - <span data-ttu-id="e539f-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="e539f-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="e539f-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="e539f-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="e539f-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-123">LysSvc.exe</span></span>

  - <span data-ttu-id="e539f-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="e539f-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="e539f-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="e539f-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="e539f-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="e539f-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="e539f-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="e539f-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-131">RtcHost.exe</span></span>

  - <span data-ttu-id="e539f-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="e539f-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="e539f-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-134">XmppTGW.exe</span></span>

- <span data-ttu-id="e539f-135">Windows Fabric 主机服务进程：</span><span class="sxs-lookup"><span data-stu-id="e539f-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="e539f-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-136">Fabric.exe</span></span>

  - <span data-ttu-id="e539f-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="e539f-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-138">FabricHost.exe</span></span>

- <span data-ttu-id="e539f-139">IIS 进程：</span><span class="sxs-lookup"><span data-stu-id="e539f-139">IIS processes:</span></span>

  - <span data-ttu-id="e539f-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="e539f-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="e539f-142">SQL Server Back-End过程：</span><span class="sxs-lookup"><span data-stu-id="e539f-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="e539f-143">请注意，这些路径特定于SQL Server版本。</span><span class="sxs-lookup"><span data-stu-id="e539f-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="e539f-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="e539f-145">%ProgramFiles%\Microsoft SQL Server\MSRS11。MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="e539f-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="e539f-147">SQL Server Front-End过程：</span><span class="sxs-lookup"><span data-stu-id="e539f-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="e539f-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="e539f-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="e539f-150">Standard Edition 安装 RTC 实例</span><span class="sxs-lookup"><span data-stu-id="e539f-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="e539f-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="e539f-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="e539f-152">目录和文件：</span><span class="sxs-lookup"><span data-stu-id="e539f-152">Directories and files:</span></span>

  - <span data-ttu-id="e539f-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="e539f-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="e539f-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="e539f-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="e539f-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="e539f-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="e539f-156">请注意，这些路径特定于 Skype for Business Server 版本。</span><span class="sxs-lookup"><span data-stu-id="e539f-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="e539f-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e539f-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="e539f-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="e539f-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="e539f-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e539f-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="e539f-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e539f-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="e539f-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="e539f-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="e539f-p103">文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。</span><span class="sxs-lookup"><span data-stu-id="e539f-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="e539f-164">SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。</span><span class="sxs-lookup"><span data-stu-id="e539f-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="e539f-165">可以在拓扑生成器中指定数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="e539f-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="e539f-166">有关每个数据库的数据和日志文件的详细信息（包括默认名称），请参阅部署文档中的 [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)。</span><span class="sxs-lookup"><span data-stu-id="e539f-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span>

  - <span data-ttu-id="e539f-167">SQL Server数据和日志文件，包括前端数据库、Skype for Business 存储和 RtcDatabase 存储的日志文件。</span><span class="sxs-lookup"><span data-stu-id="e539f-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="e539f-168">它们通常在 %localdrive%\CSData 下。</span><span class="sxs-lookup"><span data-stu-id="e539f-168">They are normally under %localdrive%\CSData.</span></span>