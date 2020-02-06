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
# <a name="back-up-response-group-service-rgs-data"></a>备份响应组服务（RGS）数据

通过 Skype for Business Server 2019 （7月累积更新），我们提供了包括 RGS 数据作为标准备份的一部分的功能。

## <a name="rgs-data-replication"></a>RGS 数据复制

若要尝试 RGS 数据复制功能，请按照以下步骤操作：

1. 在配对池的所有前端（FEs）上安装七月累积更新。
1. 在配对池的两个成员上安装 RGS 数据库：
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. 在两个池上运行以下 cmdlet，将现有的 RGS 数据复制到备份表中，以便可以由 RGSBackupService 选取数据：
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. 启用 RGSBackupService （这将在全球范围内启用 RGSBackupService。 如果此参数设置为 true，RGSBackupService 将开始同步配对的池上的 RGS 数据（这两个池都需要是 CU1）。 请等待几分钟，让其开始。 最初，RGS BackupService 状态将为 NotInitialized。）：
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. 若要检查 BackupServiceStatus：
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. 若要跨池检查 DataReplication，请使用这些 cmdlet （这些 cmdlet 仅显示所有者池数据）：
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. 要检查所有者池 RGS 数据及其备份数据，请执行以下操作：
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. 通过对工作流进行音频呼叫来验证工作流功能。
1. 故障转移你的 RGS 所有者池。
1. 通过对工作流进行音频呼叫来验证工作流功能。
1. 故障回复池。
1. 在源池中更新 RGS 数据并执行另一个故障转移以检查更改是否反映在备份池上。 RGS 的行为方式与故障转移前的行为方式相同。

> [!TIP]
> 建议在大量数据上执行这些步骤，并经常进行故障切换和 failbacks。 此外，还应复制在此 CU 更新之后创建的任何新 RGS。

## <a name="rgs-cmdlets"></a>RGS cmdlet

- 若要检查 BackupServiceStatus （导出状态应为 "最终" 或 "稳定" 状态。 导入状态应处于 "正常" 状态。 应启用 RGSBackupservice。）：
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- 在备份池中完全同步 RGS 数据（这将同步备份池中的完整 RGS 数据。）：
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- 若要完全同步备份池中的 RGS 数据打开（这将同步备份池中的完整 RGS 数据）：
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- 若要同步备份池中的 RGS 增量数据（这将仅同步针对 RGS 的备份池中的增量数据。）：
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- 同步包括 RGS 的所有模块数据：
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- 禁用 RGSBackupService （这将在全球范围内禁用 RGSBackupService。 如果此参数设置为 true，将对所有配对的池禁用 RGSBackupService。）：
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
