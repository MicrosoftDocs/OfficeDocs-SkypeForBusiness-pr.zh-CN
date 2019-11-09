---
title: Skype for business 服务器的防病毒扫描排除项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Skype for business Server 的防病毒扫描程序互操作概述。
ms.openlocfilehash: 69fb02d04f27b7444a3b8cadaacafc05654a1c9f
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074624"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="82e9e-103">Skype for business 服务器的防病毒扫描排除项</span><span class="sxs-lookup"><span data-stu-id="82e9e-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="82e9e-104">Skype for business Server 的防病毒扫描程序互操作概述。</span><span class="sxs-lookup"><span data-stu-id="82e9e-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="82e9e-105">为确保防病毒扫描程序不会干扰 Skype for Business Server 的操作，您必须为运行防病毒扫描程序的每个 Skype for business 服务器或服务器角色排除特定的流程和目录。</span><span class="sxs-lookup"><span data-stu-id="82e9e-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="82e9e-106">应排除以下进程和目录：</span><span class="sxs-lookup"><span data-stu-id="82e9e-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="82e9e-107">以下列出的文件夹和文件位置是 Skype for business 服务器的默认位置。</span><span class="sxs-lookup"><span data-stu-id="82e9e-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="82e9e-108">对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。</span><span class="sxs-lookup"><span data-stu-id="82e9e-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82e9e-109">请注意，某些防病毒程序可能需要对排除列表使用绝对路径而不是相对路径。</span><span class="sxs-lookup"><span data-stu-id="82e9e-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="82e9e-110">Skype for business 服务器流程：</span><span class="sxs-lookup"><span data-stu-id="82e9e-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="82e9e-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-111">ABServer.exe</span></span>

  - <span data-ttu-id="82e9e-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="82e9e-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="82e9e-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-114">ChannelService.exe</span></span>

  - <span data-ttu-id="82e9e-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="82e9e-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="82e9e-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="82e9e-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-118">DataProxy.exe</span></span>

  - <span data-ttu-id="82e9e-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="82e9e-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="82e9e-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="82e9e-122">LyncBackupService</span><span class="sxs-lookup"><span data-stu-id="82e9e-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="82e9e-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-123">LysSvc.exe</span></span>

  - <span data-ttu-id="82e9e-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="82e9e-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="82e9e-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="82e9e-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="82e9e-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="82e9e-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="82e9e-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="82e9e-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-131">RtcHost.exe</span></span>

  - <span data-ttu-id="82e9e-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="82e9e-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="82e9e-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-134">XmppTGW.exe</span></span>

- <span data-ttu-id="82e9e-135">Windows Fabric Host Service 进程：</span><span class="sxs-lookup"><span data-stu-id="82e9e-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="82e9e-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-136">Fabric.exe</span></span>

  - <span data-ttu-id="82e9e-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="82e9e-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-138">FabricHost.exe</span></span>

- <span data-ttu-id="82e9e-139">IIS 进程：</span><span class="sxs-lookup"><span data-stu-id="82e9e-139">IIS processes:</span></span>

  - <span data-ttu-id="82e9e-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="82e9e-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="82e9e-142">SQL Server 后端进程：</span><span class="sxs-lookup"><span data-stu-id="82e9e-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="82e9e-143">请注意，这些路径特定于 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="82e9e-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="82e9e-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="82e9e-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="82e9e-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="82e9e-147">SQL Server 前端进程：</span><span class="sxs-lookup"><span data-stu-id="82e9e-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="82e9e-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="82e9e-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="82e9e-150">Standard Edition 安装 RTC 实例</span><span class="sxs-lookup"><span data-stu-id="82e9e-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="82e9e-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="82e9e-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="82e9e-152">目录和文件：</span><span class="sxs-lookup"><span data-stu-id="82e9e-152">Directories and files:</span></span>

  - <span data-ttu-id="82e9e-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="82e9e-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="82e9e-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="82e9e-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="82e9e-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="82e9e-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="82e9e-156">请注意，这些路径特定于 Skype for business 服务器版本。</span><span class="sxs-lookup"><span data-stu-id="82e9e-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="82e9e-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="82e9e-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="82e9e-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="82e9e-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="82e9e-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="82e9e-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="82e9e-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="82e9e-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="82e9e-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="82e9e-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="82e9e-p103">文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。</span><span class="sxs-lookup"><span data-stu-id="82e9e-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="82e9e-p104">SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。可以在拓扑生成器中指定数据库和日志文件。有关每个数据库的数据和日志文件的详细信息（包括默认名称），请参阅部署文档中的 [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="82e9e-p104">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="82e9e-167">SQL Server 数据和日志文件，包括前端数据库、Skype for Business 应用商店和 RtcDatabase 应用商店的文件。</span><span class="sxs-lookup"><span data-stu-id="82e9e-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="82e9e-168">它们通常位于 %localdrive%\CSData 下。</span><span class="sxs-lookup"><span data-stu-id="82e9e-168">They are normally under %localdrive%\CSData.</span></span>


