---
title: 在 Skype for Business Server 2015 中导出存档数据
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 摘要： 了解如何导出业务服务器 2015年的 Skype 已存档的数据。
ms.openlocfilehash: f5fe222589efa5ce6e8e21151817042497fb6cc6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="export-archived-data-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中导出存档数据

**摘要：**了解如何为 Skype 业务服务器 2015年导出存档的数据。
  
存档数据库中存档的数据采用的是不可搜索或不可读格式，但是您可以使用 **Export-CsArchivingData** cmdlet 从数据库提取记录并将它们保存为 Outlook 电子邮件 (EML) 文件。
  
如果您启用 Microsoft Exchange 集成，存档数据在 Exchange 存储中。 在 Exchange 存档的数据是可检索和可检测到。 在 Exchange 存档的数据访问的详细信息，请参阅 Exchange 文档。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell Cmdlet 存档数据导出

您可以使用 Export-CSArchivingData cmdlet 导出存档数据。 
  
以下命令可导出自 2012 年 6 月 1 日以来写入存档数据库 atl-sql-001.contoso.com 的所有存档数据。生成的输出文件将存储在 C:\ArchivingExports 文件夹中。
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

下面的命令导出为单个用户的数据存档： kenmyer@contoso.com。这是包括 UserUri 参数跟用户的 SIP 地址。 例如： 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

有关详细信息，请参阅[导出 CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet 的帮助主题。
  

