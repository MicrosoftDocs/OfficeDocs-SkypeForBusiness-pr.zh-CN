---
title: 在 Skype for Business 服务器中导出存档的数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 摘要：了解如何导出 Skype for Business 服务器的存档数据。
ms.openlocfilehash: 0d48441290eda49ad6b7fecd63d15d74b25148fe
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991567"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>在 Skype for Business 服务器中导出存档的数据

**摘要：** 了解如何导出 Skype for Business 服务器的存档数据。
  
存档数据库中存档的数据采用的是不可搜索或不可读格式，但是您可以使用 **Export-CsArchivingData** cmdlet 从数据库提取记录并将它们保存为 Outlook 电子邮件 (EML) 文件。
  
如果启用 Microsoft Exchange 集成，则会将数据存档在 Exchange 存储中。 Exchange 中存档的数据是可搜索和可发现的。 有关访问 Exchange 中存档的数据的详细信息，请参阅 Exchange 文档。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 导出存档数据

您可以使用 Export-CSArchivingData cmdlet 导出存档数据。 
  
以下命令可导出自 2012 年 6 月 1 日以来写入存档数据库 atl-sql-001.contoso.com 的所有存档数据。生成的输出文件将存储在 C:\ArchivingExports 文件夹中。
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

以下命令为单个用户 (kenmyer@contoso.com) 导出存档数据。 通过包含 UserUri 参数，后跟用户的 SIP 地址，即可完成此操作。 例如： 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

有关详细信息，请参阅[CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet 的帮助主题。
  

