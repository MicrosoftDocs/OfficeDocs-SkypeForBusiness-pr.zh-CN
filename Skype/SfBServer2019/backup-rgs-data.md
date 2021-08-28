---
title: 备份 响应组服务 (2019) RGS Skype for Business Server数据
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 了解如何在 响应组服务 (2019) 备份 RGS Skype for Business Server数据。
ms.openlocfilehash: 7e3e4116a281584da7afc1807fe58e79d2528183
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581156"
---
# <a name="back-up-response-group-service-rgs-data"></a>备份响应组服务 (RGS) 数据

在 2019 Skype for Business Server 2019 年 7 月累积更新中，我们包含了将 RGS 数据作为标准备份的一部分的能力。

## <a name="rgs-data-replication"></a>RGS 数据复制

若要尝试 RGS 数据复制功能，请按照以下步骤操作：

1. 在配对池的所有前端 FES (7) 累积更新。
1. 在配对池的两个成员上安装 RGS 数据库：
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. 在两个池上运行以下 cmdlet 以将现有 RGS 数据复制到备份表，以便 RGSBackupService 可以选取数据：
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. 启用 RGSBackupService (这将全局启用 RGSBackupService。 如果此参数设置为 true，则 RGSBackupService 将开始同步配对池中的 RGS 数据 (两个池都需要为 CU1) 。 等待几分钟以开始。 最初，RGS BackupService 状态将为 NotInitialized.) ：
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. 检查 BackupServiceStatus：
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. 若要检查跨池的 DataReplication，请使用以下 cmdlet (这些 cmdlet 仅显示所有者池) ：
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. 检查所有者池 RGS 数据及其备份数据：
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. 通过向工作流进行音频调用来验证工作流功能。
1. 对 RGS 所有者池进行故障转移。
1. 通过向工作流进行音频调用来验证工作流功能。
1. 故障回复池。
1. 更新源池上的 RGS 数据并执行另一个故障转移，以检查更改是否反映在备份池上。 RGS 的行为方式应该与故障转移前的行为方式相同。

> [!TIP]
> 建议您对大量数据执行这些步骤，并频繁进行故障转移和故障回复。 还应复制在此 CU 更新后创建的任何新 RGS。

## <a name="rgs-cmdlets"></a>RGS cmdlet

- 若要检查 BackupServiceStatus (导出状态应保持"最终"或"稳定"状态。 导入状态应该为"正常"状态。 应启用 RGSBackupservice。) ：
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- 若要完全同步备份池上的 RGS 数据 (这将同步备份池上的完整 RGS 数据。) ：
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- 若要完全同步备份池上的 RGS 文件存储 (这将同步备份池上的完整 RGS 数据。) ：
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- 若要同步备份池上的 RGS 增量数据 (这将仅同步备份池中 RGS 的增量数据。) ：
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- 同步包括 RGS 在内的所有模块数据：
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- 若要禁用 RGSBackupService (这将全局禁用 RGSBackupService。 如果此参数设置为 true，将在所有配对池上禁用 RGSBackupService。) ：
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
