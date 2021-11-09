---
title: 导出存档数据Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 摘要：了解如何导出存档数据Skype for Business Server。
ms.openlocfilehash: ef9ffca2612adb088f9d06cdbaad809f72278595
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856779"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>导出存档数据Skype for Business Server

**摘要：** 了解如何导出存档数据以用于Skype for Business Server。
  
存档数据库中存档的数据不可搜索或不可读格式，但您可以使用 **Export-CsArchivingData** cmdlet 从数据库中提取记录并将其另存为 Outlook 电子邮件 (EML) 文件。
  
如果启用 Microsoft Exchange集成，数据将存档在Exchange存储中。 存档在Exchange的数据可搜索和发现。 有关访问已存档在 Exchange 中数据的详细信息，请参阅Exchange文档。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 导出Windows PowerShell数据

可以使用 cmdlet 导出存档Export-CSArchivingData数据。 
  
以下命令导出自 2012 年 6 月 1 以来写入 atl-sql-001.contoso.com 数据库的所有存档数据。 生成的输出文件将存储在 C:\ArchivingExports 文件夹中。
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

以下命令导出单个用户的存档数据：kenmyer@contoso.com。 这是通过包括 UserUri 参数后跟用户 SIP 地址完成。 例如： 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

有关详细信息，请参阅 [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet 的帮助主题。
