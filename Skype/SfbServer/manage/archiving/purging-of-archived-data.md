---
title: 在 Skype for Business 服务器中管理已存档数据的清除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 摘要：了解如何管理 Skype for business 服务器的存档数据清除。
ms.openlocfilehash: f168f7fe744ef388de246cbcd2dd9de0fc2ef805
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991607"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>在 Skype for Business 服务器中管理已存档数据的清除

**摘要：** 了解如何管理 Skype for business 服务器的存档数据清除。
  
存档数据库不是为了长期保留，而 Skype for Business 服务器不提供用于存档数据的电子发现（搜索）解决方案，因此需要将数据移动到其他存储。 Skype for Business 服务器提供了一种会话导出工具，可用于将存档的数据导出到可搜索的脚本中。 您需要定义何时清除已存档和已导出的数据。 
  
有关使用**CsArchivingData** cmdlet 导出数据的详细信息，请参阅[在 Skype for Business 服务器中导出存档的数据](export-archived-data.md)。
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>使用控制面板管理数据的清除

要使用控制面板管理存档数据的清除：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
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
    
例如，以下命令可启用所有存档数据的清除。 运行此命令后，Skype for Business 服务器将清除早于为 KeepArchivingDataForDays 参数指定的值的所有存档记录。 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

以下命令限制清除到已导出到数据文件的已存档记录（通过使用**CSArchivingData** cmdlet）。 还必须将 PurgeExportedArchivesOnly 参数设置为 True （$True）：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

运行此命令后，Skype for Business 服务器将仅清除满足两个条件的存档记录：1）它们比为 KeepArchivingDataForDays 参数指定的值更早;和2）已使用**CsArchivingData** cmdlet 导出它们。
  
若要禁用自动清除存档记录功能，请将  EnablePurging 参数设置为 False ($False)。
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

以下示例使用**CsArchivingDatabasePurge** cmdlet 从 atl-sql-001.contoso.com 上的存档数据库中清除超过24小时的所有记录。 为确保删除所有记录，包括尚未导出的记录，请将 PurgeExportedArchivesOnly 参数设置为 False ($False)。
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
