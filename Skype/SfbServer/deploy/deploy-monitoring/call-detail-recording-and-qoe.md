---
title: 配置 Skype for Business Server 中的 "呼叫详细记录" 和 "体验质量" 设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: '摘要: 了解如何在 Skype for Business 服务器中配置 CDR 和 QoE。'
ms.openlocfilehash: d2f86654e852a2126fc611e820f95b8ebad5259a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239958"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>配置 Skype for Business Server 中的 "呼叫详细记录" 和 "体验质量" 设置
 
**摘要:** 了解如何在 Skype for Business 服务器中配置 CDR 和 QoE。
  
使用 Skype for business Server 的 SQL Server Reporting Services 报表配置 CDR 和 QoE 监视。
  
## <a name="configure-cdr-and-qoe"></a>配置 CDR 和 QoE

将监视存储与前端池关联后, 设置监视存储, 然后安装并配置 SQL Server Reporting Services 和监视报告, 您可以管理呼叫详细记录 (CDR) 和体验质量 (QoE)使用 Skype for Business Server 命令行管理程序进行监视。 Skype for Business Server Management Shell cmdlet 允许你为特定网站或整个 Skype for Business Server 部署启用和禁用 CDR 和/或 QoE 监视;使用如下所示的命令即可完成此操作:
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

安装 Skype for Business 服务器时, 你还将为 CDR 和 QoE 安装全局配置设置的预定义集合。 下表显示了呼叫详细记录使用的一些较常用设置的默认值：
  
|**属性**|**说明**|**默认值**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |指示是否启用 CDR。如果为 True，将收集所有 CDR 记录并写入监控数据库。  <br/> |True  <br/> |
|EnablePurging  <br/> |指示是否定期从数据库中删除 CDR 记录。如果为 True，则将在属性 KeepCallDetailForDays（对于 CDR 记录）和 KeepErrorReportForDays（对于 CDR 错误）指定的时间段后删除记录。如果为 False，则将无限期保留 CDR 记录。  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |指示 CDR 记录在数据库中保留的天数；超过指定天数的任何记录将自动删除。但是，只有在启用了清除时才会发生这种情况。  <br/> KeepCallDetailForDays 可以设置为 1 到 2562 天（大约 7 年）之间的任意整数值。  <br/> |60 天  <br/> |
|KeepErrorReportForDays  <br/> |指示保留 CDR 错误报告的天数；超过指定天数的任何报告将自动删除。 CDR 错误报告是由客户端应用程序 (如 Skype for Business 服务器) 上传的诊断报告。  <br/> 您可以将此属性设置为 1 到 2562 天之间的任意整数值。  <br/> |60 天  <br/> |
   
类似地，此表中也显示了选定 QoE 设置的默认值：
  
|**属性**|**说明**|**默认值**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |指示是否启用 QoE 监控。如果为 True，将收集所有 QoE 记录并写入监控数据库。  <br/> |True  <br/> |
|EnablePurging  <br/> |指示是否定期从数据库中删除 QoE 记录。如果为 True，则将在属性 KeepQoEDataForDays 指定的时间段后删除记录。如果为 False，则将无限期保留 QoE 记录。  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |指示 QoE 记录在数据库中保留的天数；超过指定天数的任何记录将自动删除。但是，只有在启用了清除时才会发生这种情况。  <br/> 可将 KeepCallDetailForDays 设置为 1 到 2562 天之间的任意整数值。  <br/> |60 天  <br/> |
   
如果您需要修改这些全局设置，可以使用 Set-CsCdrConfiguration 和 Set-CsQoEConfiguration cmdlet 来完成。 例如, 此命令 (从 Skype for Business Server Management Shell 中运行) 在全局范围内禁用 CDR 监视;通过将 EnableCDR 属性设置为 False 来完成此操作 ($False):
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

请注意，禁用监控不会从前端池解除监控存储关联，也不卸载或以其他方式影响后端监控数据库。 当你使用 Skype for Business Server Management Shell 禁用 CDR 或 QoE 监视时, 你确实确实会暂时停止 Skype for Business 服务器收集和存档监视数据。 如果要恢复收集和存档 CDR 数据，只需要将 EnableCDR 属性重新设置为 True ($True) 即可：
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

类似地，以下命令在全局范围内禁止清除 QoE 记录：
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

除了全局设置，也可将 CDR 和 QoE 配置设置分配给站点范围。这样，在实施监控时可提供更大的管理灵活性；例如，管理员可以对 Redmond 站点启用 CDR 监控，而对 Dublin 站点禁用 CDR 监控。要在站点范围创建新的 CDR 配置设置，请使用类似如下的命令：
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

请记住，在站点范围配置的设置优先于在全局范围配置的设置。例如，假设在全局范围启用了 CDR 监控，但在站点范围（对于 Redmond 站点）禁用了 CDR 监控。这意味着将不为 Redmond 站点中的用户存档呼叫详细记录信息。但是，其他站点中的用户（即，由全局设置而非 Redmond 站点设置管理的用户）的呼叫详细记录仍将存档。
  
可以使用类似如下的命令在站点范围创建新的 QoE 配置设置：
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

有关详细信息, 请在 Skype for Business 服务器管理外壳程序中键入以下命令:
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
