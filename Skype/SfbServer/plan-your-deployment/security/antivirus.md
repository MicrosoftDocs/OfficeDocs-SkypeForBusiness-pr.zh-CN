---
title: 防病毒扫描排除的 Skype 业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Overview of Business server 防病毒扫描程序与 Skype 的互操作。
ms.openlocfilehash: 782f7bc6fe004eb5106fa07c93b6f22993849d98
ms.sourcegitcommit: c864a4b5337960deed01ff8c481326dbbd23c960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24975192"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="cf058-103">防病毒扫描排除的 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="cf058-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="cf058-104">Overview of Business server 防病毒扫描程序与 Skype 的互操作。</span><span class="sxs-lookup"><span data-stu-id="cf058-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="cf058-105">本文包含可帮助管理员确定它与 Active Directory 域中的防病毒软件一起使用时正在运行受支持的版本的 Microsoft Windows 的计算机上的潜在不稳定的原因的建议环境或托管的业务环境中。</span><span class="sxs-lookup"><span data-stu-id="cf058-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="cf058-106">我们建议您暂时应用这些过程来评估系统。</span><span class="sxs-lookup"><span data-stu-id="cf058-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="cf058-107">如果您的系统性能或稳定性通过在本文中所做的建议得到了改善，与防病毒软件供应商联系的说明或更新版本的防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="cf058-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="cf058-108">本文包含演示如何帮助低的安全设置或暂时关闭的计算机上的安全功能的信息。</span><span class="sxs-lookup"><span data-stu-id="cf058-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="cf058-109">您可以了解特定问题的性质这些更改。</span><span class="sxs-lookup"><span data-stu-id="cf058-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="cf058-110">进行这些更改之前，我们建议您对与您的特定环境中实现此变通解决方案相关联的风险评估。</span><span class="sxs-lookup"><span data-stu-id="cf058-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="cf058-111">如果实施此变通解决方案，采取任何适当的额外步骤来帮助保护的文件不再正在扫描的防病毒软件的计算机。</span><span class="sxs-lookup"><span data-stu-id="cf058-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="cf058-112">若要确保防病毒扫描程序不干扰业务服务器的 Skype 的操作，必须为每个 Skype 业务服务器或服务器角色在其上运行的防病毒扫描中排除特定过程和目录。</span><span class="sxs-lookup"><span data-stu-id="cf058-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="cf058-113">应排除以下进程和目录：</span><span class="sxs-lookup"><span data-stu-id="cf058-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="cf058-114">下面列出的文件夹和文件位置是业务服务器 Skype 的默认位置。</span><span class="sxs-lookup"><span data-stu-id="cf058-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="cf058-115">对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。</span><span class="sxs-lookup"><span data-stu-id="cf058-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf058-116">请注意，某些防病毒程序可能需要对排除列表使用绝对路径而不是相对路径。</span><span class="sxs-lookup"><span data-stu-id="cf058-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="cf058-117">Skype Business Server 过程：</span><span class="sxs-lookup"><span data-stu-id="cf058-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="cf058-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-118">ABServer.exe</span></span>

  - <span data-ttu-id="cf058-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="cf058-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="cf058-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-121">ChannelService.exe</span></span>

  - <span data-ttu-id="cf058-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="cf058-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="cf058-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="cf058-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-125">DataProxy.exe</span></span>

  - <span data-ttu-id="cf058-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="cf058-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="cf058-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="cf058-129">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="cf058-130">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-130">LysSvc.exe</span></span>

  - <span data-ttu-id="cf058-131">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="cf058-132">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="cf058-133">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="cf058-134">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="cf058-135">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="cf058-136">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="cf058-137">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="cf058-138">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-138">RtcHost.exe</span></span>

  - <span data-ttu-id="cf058-139">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="cf058-140">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="cf058-141">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-141">XmppTGW.exe</span></span>

- <span data-ttu-id="cf058-142">Windows Fabric Host Service 进程：</span><span class="sxs-lookup"><span data-stu-id="cf058-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="cf058-143">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-143">Fabric.exe</span></span>

  - <span data-ttu-id="cf058-144">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="cf058-145">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-145">FabricHost.exe</span></span>

- <span data-ttu-id="cf058-146">IIS 进程：</span><span class="sxs-lookup"><span data-stu-id="cf058-146">IIS processes:</span></span>

  - <span data-ttu-id="cf058-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="cf058-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="cf058-149">SQL Server 后端进程：</span><span class="sxs-lookup"><span data-stu-id="cf058-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf058-150">请注意，这些路径特定于 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="cf058-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="cf058-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="cf058-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="cf058-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="cf058-154">SQL Server 前端进程：</span><span class="sxs-lookup"><span data-stu-id="cf058-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="cf058-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="cf058-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="cf058-157">Standard Edition 安装 RTC 实例</span><span class="sxs-lookup"><span data-stu-id="cf058-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="cf058-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="cf058-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="cf058-159">目录和文件：</span><span class="sxs-lookup"><span data-stu-id="cf058-159">Directories and files:</span></span>

  - <span data-ttu-id="cf058-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="cf058-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="cf058-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="cf058-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="cf058-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="cf058-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf058-163">请注意，这些路径特定于 Skype 业务服务器版本。</span><span class="sxs-lookup"><span data-stu-id="cf058-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="cf058-164">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cf058-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="cf058-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="cf058-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="cf058-166">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="cf058-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="cf058-167">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cf058-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="cf058-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="cf058-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="cf058-p105">文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。</span><span class="sxs-lookup"><span data-stu-id="cf058-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="cf058-171">SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。</span><span class="sxs-lookup"><span data-stu-id="cf058-171">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="cf058-172">可以在拓扑生成器中指定数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="cf058-172">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="cf058-173">有关每个数据库的数据和日志文件的详细信息，包括默认名称，请参阅[SQL Server 数据和日志文件放置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)部署文档中。</span><span class="sxs-lookup"><span data-stu-id="cf058-173">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="cf058-174">SQL Server 数据和日志文件，包括那些前端数据库 Skype 业务存储和 RtcDatabase 存储。</span><span class="sxs-lookup"><span data-stu-id="cf058-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="cf058-175">它们通常位于 %localdrive%\CSData 下。</span><span class="sxs-lookup"><span data-stu-id="cf058-175">They are normally under %localdrive%\CSData.</span></span>


