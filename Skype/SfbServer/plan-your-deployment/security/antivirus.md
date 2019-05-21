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
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296971"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="5d9e3-103">Skype for business 服务器的防病毒扫描排除项</span><span class="sxs-lookup"><span data-stu-id="5d9e3-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="5d9e3-104">Skype for business Server 的防病毒扫描程序互操作概述。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="5d9e3-105">本文包含的建议可帮助管理员确定当运行受支持的 Microsoft Windows 版本的计算机与 Active Directory 域中的防病毒软件一起使用时, 该计算机可能不稳定的原因环境中或托管企业环境中。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="5d9e3-106">我们建议你临时应用这些过程来评估系统。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="5d9e3-107">如果你的系统性能或稳定性由本文所做的建议改进, 请与防病毒软件供应商联系, 了解有关的防病毒软件的更新版本。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="5d9e3-108">本文包含的信息介绍了如何帮助降低安全设置或如何暂时关闭计算机上的安全功能。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="5d9e3-109">你可以进行这些更改以了解特定问题的性质。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="5d9e3-110">在进行这些更改之前, 我们建议你评估与在你的特定环境中实施此解决方法相关的风险。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="5d9e3-111">如果你实现此解决方法, 请采取任何适当的附加步骤来帮助保护计算机, 以查找你的防病毒软件不再扫描的文件。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="5d9e3-112">为确保防病毒扫描程序不会干扰 Skype for Business Server 的操作, 您必须为运行防病毒扫描程序的每个 Skype for business 服务器或服务器角色排除特定的流程和目录。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="5d9e3-113">应排除以下进程和目录：</span><span class="sxs-lookup"><span data-stu-id="5d9e3-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="5d9e3-114">以下列出的文件夹和文件位置是 Skype for business 服务器的默认位置。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="5d9e3-115">对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d9e3-116">请注意，某些防病毒程序可能需要对排除列表使用绝对路径而不是相对路径。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="5d9e3-117">Skype for business 服务器流程:</span><span class="sxs-lookup"><span data-stu-id="5d9e3-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="5d9e3-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-118">ABServer.exe</span></span>

  - <span data-ttu-id="5d9e3-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="5d9e3-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="5d9e3-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-121">ChannelService.exe</span></span>

  - <span data-ttu-id="5d9e3-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="5d9e3-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="5d9e3-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="5d9e3-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-125">DataProxy.exe</span></span>

  - <span data-ttu-id="5d9e3-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="5d9e3-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="5d9e3-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="5d9e3-129">LyncBackupService</span><span class="sxs-lookup"><span data-stu-id="5d9e3-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="5d9e3-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-130">LysSvc.exe</span></span>

  - <span data-ttu-id="5d9e3-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="5d9e3-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="5d9e3-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="5d9e3-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="5d9e3-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="5d9e3-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="5d9e3-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="5d9e3-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-138">RtcHost.exe</span></span>

  - <span data-ttu-id="5d9e3-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="5d9e3-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="5d9e3-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-141">XmppTGW.exe</span></span>

- <span data-ttu-id="5d9e3-142">Windows Fabric Host Service 进程：</span><span class="sxs-lookup"><span data-stu-id="5d9e3-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="5d9e3-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-143">Fabric.exe</span></span>

  - <span data-ttu-id="5d9e3-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="5d9e3-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-145">FabricHost.exe</span></span>

- <span data-ttu-id="5d9e3-146">IIS 进程：</span><span class="sxs-lookup"><span data-stu-id="5d9e3-146">IIS processes:</span></span>

  - <span data-ttu-id="5d9e3-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="5d9e3-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="5d9e3-149">SQL Server 后端进程：</span><span class="sxs-lookup"><span data-stu-id="5d9e3-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d9e3-150">请注意，这些路径特定于 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="5d9e3-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="5d9e3-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="5d9e3-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="5d9e3-154">SQL Server 前端进程：</span><span class="sxs-lookup"><span data-stu-id="5d9e3-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="5d9e3-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="5d9e3-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="5d9e3-157">Standard Edition 安装 RTC 实例</span><span class="sxs-lookup"><span data-stu-id="5d9e3-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="5d9e3-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="5d9e3-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="5d9e3-159">目录和文件：</span><span class="sxs-lookup"><span data-stu-id="5d9e3-159">Directories and files:</span></span>

  - <span data-ttu-id="5d9e3-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="5d9e3-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="5d9e3-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="5d9e3-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="5d9e3-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="5d9e3-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="5d9e3-163">请注意, 这些路径特定于 Skype for business 服务器版本。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="5d9e3-164">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d9e3-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="5d9e3-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="5d9e3-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="5d9e3-166">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d9e3-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="5d9e3-167">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5d9e3-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="5d9e3-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="5d9e3-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="5d9e3-p105">文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="5d9e3-p106">SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。可以在拓扑生成器中指定数据库和日志文件。有关每个数据库的数据和日志文件的详细信息（包括默认名称），请参阅部署文档中的 [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-p106">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store. Database and log files can be specified in Topology Builder. For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="5d9e3-174">SQL Server 数据和日志文件, 包括前端数据库、Skype for Business 应用商店和 RtcDatabase 应用商店的文件。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="5d9e3-175">它们通常位于 %localdrive%\CSData 下。</span><span class="sxs-lookup"><span data-stu-id="5d9e3-175">They are normally under %localdrive%\CSData.</span></span>


