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
ms.openlocfilehash: 1078b3c0a28573e84235cbd39a11a6aa84a58b47
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250022"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="bcf9a-103">防病毒扫描排除的 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="bcf9a-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="bcf9a-104">Overview of Business server 防病毒扫描程序与 Skype 的互操作。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="bcf9a-105">本文包含可帮助管理员确定它与 Active Directory 域中的防病毒软件一起使用时正在运行受支持的版本的 Microsoft Windows 的计算机上的潜在不稳定的原因的建议环境或托管的业务环境中。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="bcf9a-106">我们建议您暂时应用这些过程来评估系统。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="bcf9a-107">如果您的系统性能或稳定性通过在本文中所做的建议得到了改善，与防病毒软件供应商联系的说明或更新版本的防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="bcf9a-108">本文包含演示如何帮助低的安全设置或暂时关闭的计算机上的安全功能的信息。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="bcf9a-109">您可以了解特定问题的性质这些更改。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="bcf9a-110">进行这些更改之前，我们建议您对与您的特定环境中实现此变通解决方案相关联的风险评估。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="bcf9a-111">如果实施此变通解决方案，采取任何适当的额外步骤来帮助保护的文件不再正在扫描的防病毒软件的计算机。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="bcf9a-112">若要确保防病毒扫描程序不干扰业务服务器的 Skype 的操作，必须为每个 Skype 业务服务器或服务器角色在其上运行的防病毒扫描中排除特定过程和目录。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="bcf9a-113">应排除以下进程和目录：</span><span class="sxs-lookup"><span data-stu-id="bcf9a-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="bcf9a-114">下面列出的文件夹和文件位置是业务服务器 Skype 的默认位置。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="bcf9a-115">对于您没有使用默认值的任何位置，排除您为组织指定的位置，而不是本主题中指定的默认位置。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcf9a-116">请注意，某些防病毒程序可能需要对排除列表使用绝对路径而不是相对路径。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="bcf9a-117">Skype Business Server 过程：</span><span class="sxs-lookup"><span data-stu-id="bcf9a-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="bcf9a-118">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-118">ABServer.exe</span></span>

  - <span data-ttu-id="bcf9a-119">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="bcf9a-120">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="bcf9a-121">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-121">ChannelService.exe</span></span>

  - <span data-ttu-id="bcf9a-122">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="bcf9a-123">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="bcf9a-124">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="bcf9a-125">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-125">DataProxy.exe</span></span>

  - <span data-ttu-id="bcf9a-126">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="bcf9a-127">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="bcf9a-128">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-128">IMMCUSvc.exe</span></span>

  - <span data-ttu-id="bcf9a-129">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-129">LysSvc.exe</span></span>

  - <span data-ttu-id="bcf9a-130">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-130">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="bcf9a-131">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-131">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="bcf9a-132">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-132">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="bcf9a-133">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-133">MRASSvc.exe</span></span>

  - <span data-ttu-id="bcf9a-134">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-134">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="bcf9a-135">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-135">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="bcf9a-136">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-136">ReplicationApp.exe</span></span>

  - <span data-ttu-id="bcf9a-137">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-137">RtcHost.exe</span></span>

  - <span data-ttu-id="bcf9a-138">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-138">RTCSrv.exe</span></span>

  - <span data-ttu-id="bcf9a-139">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-139">XmppProxy.exe</span></span>

  - <span data-ttu-id="bcf9a-140">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-140">XmppTGW.exe</span></span>

- <span data-ttu-id="bcf9a-141">Windows Fabric Host Service 进程：</span><span class="sxs-lookup"><span data-stu-id="bcf9a-141">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="bcf9a-142">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-142">Fabric.exe</span></span>

  - <span data-ttu-id="bcf9a-143">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-143">FabricDCA.exe</span></span>

  - <span data-ttu-id="bcf9a-144">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-144">FabricHost.exe</span></span>

- <span data-ttu-id="bcf9a-145">IIS 进程：</span><span class="sxs-lookup"><span data-stu-id="bcf9a-145">IIS processes:</span></span>

  - <span data-ttu-id="bcf9a-146">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-146">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="bcf9a-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-147">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="bcf9a-148">SQL Server 后端进程：</span><span class="sxs-lookup"><span data-stu-id="bcf9a-148">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="bcf9a-149">请注意，这些路径特定于 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-149">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="bcf9a-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-150">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="bcf9a-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-151">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="bcf9a-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-152">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="bcf9a-153">SQL Server 前端进程：</span><span class="sxs-lookup"><span data-stu-id="bcf9a-153">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="bcf9a-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-154">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="bcf9a-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="bcf9a-156">Standard Edition 安装 RTC 实例</span><span class="sxs-lookup"><span data-stu-id="bcf9a-156">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="bcf9a-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="bcf9a-157">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="bcf9a-158">目录和文件：</span><span class="sxs-lookup"><span data-stu-id="bcf9a-158">Directories and files:</span></span>

  - <span data-ttu-id="bcf9a-159">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="bcf9a-159">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="bcf9a-160">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="bcf9a-160">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="bcf9a-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="bcf9a-161">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="bcf9a-162">请注意，这些路径特定于 Skype 业务服务器版本。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-162">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="bcf9a-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bcf9a-163">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="bcf9a-164">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="bcf9a-164">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="bcf9a-165">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bcf9a-165">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="bcf9a-166">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bcf9a-166">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="bcf9a-167">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="bcf9a-167">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="bcf9a-p105">文件共享存储（在拓扑生成器中指定）。文件存储在拓扑生成器中指定。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-p105">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="bcf9a-170">SQL Server 数据和日志文件，包括后端数据库、用户存储、存档存储、监控存储和应用程序存储的这些文件。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-170">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="bcf9a-171">可以在拓扑生成器中指定数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-171">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="bcf9a-172">有关每个数据库的数据和日志文件的详细信息，包括默认名称，请参阅[SQL Server 数据和日志文件放置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)部署文档中。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-172">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="bcf9a-173">SQL Server 数据和日志文件，包括那些前端数据库 Skype 业务存储和 RtcDatabase 存储。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-173">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="bcf9a-174">它们通常位于 %localdrive%\CSData 下。</span><span class="sxs-lookup"><span data-stu-id="bcf9a-174">They are normally under %localdrive%\CSData.</span></span>


