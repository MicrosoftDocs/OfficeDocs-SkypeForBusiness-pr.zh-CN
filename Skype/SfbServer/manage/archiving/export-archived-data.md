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
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="c70f4-103">导出 Business Server Skype 中的存档的数据</span><span class="sxs-lookup"><span data-stu-id="c70f4-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="c70f4-104">**摘要：** 了解如何为业务 Server Skype 导出存档的数据。</span><span class="sxs-lookup"><span data-stu-id="c70f4-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="c70f4-105">存档数据库中存档的数据采用的是不可搜索或不可读格式，但是您可以使用 **Export-CsArchivingData** cmdlet 从数据库提取记录并将它们保存为 Outlook 电子邮件 (EML) 文件。</span><span class="sxs-lookup"><span data-stu-id="c70f4-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="c70f4-106">如果您启用 Microsoft Exchange 集成，存档数据 Exchange 存储中。</span><span class="sxs-lookup"><span data-stu-id="c70f4-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="c70f4-107">可搜索并可供搜索，在 Exchange 存档的数据。</span><span class="sxs-lookup"><span data-stu-id="c70f4-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="c70f4-108">有关访问在 Exchange 存档的数据的详细信息，请参阅 Exchange 文档。</span><span class="sxs-lookup"><span data-stu-id="c70f4-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c70f4-109">导出存档数据，通过使用 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c70f4-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c70f4-110">您可以使用 Export-CSArchivingData cmdlet 导出存档数据。</span><span class="sxs-lookup"><span data-stu-id="c70f4-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="c70f4-p102">以下命令可导出自 2012 年 6 月 1 日以来写入存档数据库 atl-sql-001.contoso.com 的所有存档数据。生成的输出文件将存储在 C:\ArchivingExports 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c70f4-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="c70f4-113">以下命令为单个用户 (kenmyer@contoso.com) 导出存档数据。</span><span class="sxs-lookup"><span data-stu-id="c70f4-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="c70f4-114">这是通过包括用户的 SIP 地址后跟 UserUri 参数。</span><span class="sxs-lookup"><span data-stu-id="c70f4-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="c70f4-115">例如：</span><span class="sxs-lookup"><span data-stu-id="c70f4-115">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="c70f4-116">有关详细信息，请参阅[Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="c70f4-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

