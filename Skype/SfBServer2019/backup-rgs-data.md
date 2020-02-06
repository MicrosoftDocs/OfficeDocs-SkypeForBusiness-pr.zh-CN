---
title: 在 Skype for Business Server 2019 中备份响应组服务（RGS）数据
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 了解如何在 Skype for Business Server 2019 中备份响应组服务（RGS）数据。
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824066"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="bdb0f-103">备份响应组服务（RGS）数据</span><span class="sxs-lookup"><span data-stu-id="bdb0f-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="bdb0f-104">通过 Skype for Business Server 2019 （7月累积更新），我们提供了包括 RGS 数据作为标准备份的一部分的功能。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="bdb0f-105">RGS 数据复制</span><span class="sxs-lookup"><span data-stu-id="bdb0f-105">RGS data replication</span></span>

<span data-ttu-id="bdb0f-106">若要尝试 RGS 数据复制功能，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="bdb0f-107">在配对池的所有前端（FEs）上安装七月累积更新。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="bdb0f-108">在配对池的两个成员上安装 RGS 数据库：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="bdb0f-109">在两个池上运行以下 cmdlet，将现有的 RGS 数据复制到备份表中，以便可以由 RGSBackupService 选取数据：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="bdb0f-110">启用 RGSBackupService （这将在全球范围内启用 RGSBackupService。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="bdb0f-111">如果此参数设置为 true，RGSBackupService 将开始同步配对的池上的 RGS 数据（这两个池都需要是 CU1）。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="bdb0f-112">请等待几分钟，让其开始。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="bdb0f-113">最初，RGS BackupService 状态将为 NotInitialized。）：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="bdb0f-114">若要检查 BackupServiceStatus：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="bdb0f-115">若要跨池检查 DataReplication，请使用这些 cmdlet （这些 cmdlet 仅显示所有者池数据）：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="bdb0f-116">要检查所有者池 RGS 数据及其备份数据，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="bdb0f-117">通过对工作流进行音频呼叫来验证工作流功能。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="bdb0f-118">故障转移你的 RGS 所有者池。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="bdb0f-119">通过对工作流进行音频呼叫来验证工作流功能。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="bdb0f-120">故障回复池。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-120">Failback the pool.</span></span>
1. <span data-ttu-id="bdb0f-121">在源池中更新 RGS 数据并执行另一个故障转移以检查更改是否反映在备份池上。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="bdb0f-122">RGS 的行为方式与故障转移前的行为方式相同。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="bdb0f-123">建议在大量数据上执行这些步骤，并经常进行故障切换和 failbacks。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="bdb0f-124">此外，还应复制在此 CU 更新之后创建的任何新 RGS。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="bdb0f-125">RGS cmdlet</span><span class="sxs-lookup"><span data-stu-id="bdb0f-125">RGS cmdlets</span></span>

- <span data-ttu-id="bdb0f-126">若要检查 BackupServiceStatus （导出状态应为 "最终" 或 "稳定" 状态。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="bdb0f-127">导入状态应处于 "正常" 状态。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="bdb0f-128">应启用 RGSBackupservice。）：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="bdb0f-129">在备份池中完全同步 RGS 数据（这将同步备份池中的完整 RGS 数据。）：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="bdb0f-130">若要完全同步备份池中的 RGS 数据打开（这将同步备份池中的完整 RGS 数据）：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="bdb0f-131">若要同步备份池中的 RGS 增量数据（这将仅同步针对 RGS 的备份池中的增量数据。）：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="bdb0f-132">同步包括 RGS 的所有模块数据：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="bdb0f-133">禁用 RGSBackupService （这将在全球范围内禁用 RGSBackupService。</span><span class="sxs-lookup"><span data-stu-id="bdb0f-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="bdb0f-134">如果此参数设置为 true，将对所有配对的池禁用 RGSBackupService。）：</span><span class="sxs-lookup"><span data-stu-id="bdb0f-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
