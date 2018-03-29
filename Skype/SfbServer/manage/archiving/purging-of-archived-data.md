---
title: 在 Skype for Business Server 2015 中管理存档数据的清除
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 摘要： 了解如何管理为 Skype 业务服务器 2015年的已存档数据的清除。
ms.openlocfilehash: caeddcd927c20f0622cbd45b6d93abb2bf5d6618
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理存档数据的清除

**摘要：**了解如何管理为 Skype 业务服务器 2015年的已存档数据的清除。
  
存档数据库不适合长期保留，和业务服务器 2015年的 Skype 不提供电子邮件发现 （搜索） 解决方案的已存档数据，因此数据需要移动到其他存储。 Skype 业务服务器提供了一种会话导出工具，可用于将已存档的数据导出到可搜索的抄本。 您需要定义何时清除已存档和已导出的数据。 
  
有关使用**导出 CsArchivingData** cmdlet 导出数据的详细信息，请参阅[导出存档的数据业务服务器 2015年的 Skype](export-archived-data.md)。
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>使用控制面板管理数据的清除

要使用控制面板管理存档数据的清除：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档配置**”。
    
4. 单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，再单击“**显示详细信息**”，然后执行以下操作：
    
   - 要启用清除，请选中“**启用清除存档数据功能**”复选框，然后执行下列操作之一：
    
     - 要清除所有记录，请单击“**清除超过以下最长持续时间（天）的已导出存档数据和已存储存档数据**”，然后指定天数。
    
     - 要仅清除已导出的数据，请单击“**仅清除已导出的存档数据**”。
    
   - 要禁用清除，请清除“**启用清除存档数据功能**”复选框。
    
5. 单击“**提交**”。
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>使用 Windows PowerShell 管理数据的清除

您可以使用以下 Windows PowerShell cmdlet 管理存档数据的清除：
  
- **Set-CsArchivingConfiguration** cmdlet 和 EnablePurging 参数允许您启用或禁用存档数据的清除。
    
- **Invoke-CsArchivingDatabasePurge** 可让您手动清除存档数据库中的记录。
    
例如，以下命令可启用所有存档数据的清除。 运行此命令后，Skype 业务服务器会清除早于指定 KeepArchivingDataForDays 参数的值的所有存档记录。 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

以下命令将限制到已存档的记录 （通过使用**导出 CSArchivingData** cmdlet） 导出到一个数据文件清除。 此外必须 PurgeExportedArchivesOnly 参数设置为 True ($True):
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

运行此命令后，Skype 业务服务器仅清除存档记录满足两个条件： 1) 它们是早于 KeepArchivingDataForDays 参数，则为指定的值并且，2） 导出使用**导出 CsArchivingData** cmdlet。
  
若要禁用自动清除存档记录功能，请将  EnablePurging 参数设置为 False ($False)。
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

下面的示例使用**Invoke CsArchivingDatabasePurge** cmdlet 从 atl 的 sql 001.contoso.com 上的存档数据库中清除所有记录超过 24 小时。若要确保所有记录都被都删除，包括那些尚未导出，将 PurgeExportedArchivesOnly 参数设置为 False ($False):
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```