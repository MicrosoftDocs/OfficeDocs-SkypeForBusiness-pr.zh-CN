---
title: 导出 Business Server Skype 中的存档的数据
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 摘要： 了解如何为业务 Server Skype 导出存档的数据。
ms.openlocfilehash: 7def9d2ea287c95695784161db72937ff4f2d5a4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890120"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>导出 Business Server Skype 中的存档的数据

**摘要：** 了解如何为业务 Server Skype 导出存档的数据。
  
存档数据库中存档的数据采用的是不可搜索或不可读格式，但是您可以使用 **Export-CsArchivingData** cmdlet 从数据库提取记录并将它们保存为 Outlook 电子邮件 (EML) 文件。
  
如果您启用 Microsoft Exchange 集成，存档数据 Exchange 存储中。 可搜索并可供搜索，在 Exchange 存档的数据。 有关访问在 Exchange 存档的数据的详细信息，请参阅 Exchange 文档。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>导出存档数据，通过使用 Windows PowerShell Cmdlet

您可以使用 Export-CSArchivingData cmdlet 导出存档数据。 
  
以下命令可导出自 2012 年 6 月 1 日以来写入存档数据库 atl-sql-001.contoso.com 的所有存档数据。生成的输出文件将存储在 C:\ArchivingExports 文件夹中。
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

以下命令为单个用户 (kenmyer@contoso.com) 导出存档数据。 这是通过包括用户的 SIP 地址后跟 UserUri 参数。 例如： 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

有关详细信息，请参阅[Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet 的帮助主题。
  

