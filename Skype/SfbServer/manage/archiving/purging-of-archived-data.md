---
title: 管理存档数据的清除Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 摘要：了解如何管理存档数据的清除Skype for Business Server。
ms.openlocfilehash: f6eafbacedc715dc3684a16eb17cd5e1b1ae59923046af5cf180e92bbf6a2266
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307073"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>管理存档数据的清除Skype for Business Server

**摘要：** 了解如何管理存档数据的清除以用于Skype for Business Server。
  
存档数据库不用于长期保留，Skype for Business Server 不提供存档数据的电子发现 (搜索) 解决方案，因此需要将数据移动到其他存储。 Skype for Business Server提供了可用于将存档数据导出到可搜索脚本的会话导出工具。 您需要定义何时清除存档和导出的数据。 
  
有关使用 **Export-CsArchivingData** cmdlet 导出数据的信息，请参阅 Export [archived data in Skype for Business Server](export-archived-data.md)。
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>使用控制面板管理数据的清除

若要使用控制面板管理存档数据的清除：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 在存档配置列表中单击相应的全局、站点或池配置的名称，然后依次单击“编辑”、“显示详细信息”，然后执行以下操作：
    
   - 要启用清除，请选中“启用清除存档数据功能”复选框，然后执行下列操作之一：
    
     - 要清除所有记录，请单击“清除超过以下最长持续时间(天)的已导出存档数据和已存储存档数据”，然后指定天数。
    
     - 要仅清除已导出的数据，请单击“仅清除已导出的存档数据”。
    
   - 要禁用清除，请清除“启用清除存档数据功能”复选框。
    
5. 单击“提交”。
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>使用数据清除管理Windows PowerShell

您可以使用以下 cmdlet 管理存档数据的清除Windows PowerShell cmdlet：
  
- **Set-CsArchivingConfiguration** cmdlet 和 EnablePurging 参数允许您启用或禁用存档数据的清除。
    
- **Invoke-CsArchivingDatabasePurge** 允许您手动清除存档数据库中的记录。
    
例如，以下命令可启用清除所有存档数据。 运行此命令后，Skype for Business Server将清除所有比 KeepArchivingDataForDays 参数指定的值更旧的存档记录。 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

以下命令限制使用 **Export-CSArchivingData** cmdlet (导出到数据文件存档记录的清除) 。 还必须将 PurgeExportedArchivesOnly 参数设置为 True ($True) ：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

运行此命令后，Skype for Business Server将仅清除满足以下两个条件的存档记录：1) 比为 KeepArchivingDataForDays 参数指定的值大;和 2) **Export-CsArchivingData** cmdlet 导出它们。
  
若要禁用自动清除存档记录，请设置 EnablePurging 参数为 False ($False) ：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

以下示例使用 **Invoke-CsArchivingDatabasePurge** cmdlet 从 atl-sql-001.contoso.com 上的存档数据库中清除所有超过 24 小时的记录。 为确保删除所有记录（包括尚未导出的记录），PurgeExportedArchivesOnly 参数设置为 False ($False) ：
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
