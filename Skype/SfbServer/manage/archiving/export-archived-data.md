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
description: '摘要: 了解如何导出 Skype for Business 服务器的存档数据。'
ms.openlocfilehash: 6914b4c32c22165b551bb56ece8d7b3b9c21fdbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286135"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="0dc33-103">在 Skype for Business 服务器中导出存档的数据</span><span class="sxs-lookup"><span data-stu-id="0dc33-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="0dc33-104">**摘要:** 了解如何导出 Skype for Business 服务器的存档数据。</span><span class="sxs-lookup"><span data-stu-id="0dc33-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="0dc33-105">存档数据库中存档的数据采用的是不可搜索或不可读格式，但是您可以使用 **Export-CsArchivingData** cmdlet 从数据库提取记录并将它们保存为 Outlook 电子邮件 (EML) 文件。</span><span class="sxs-lookup"><span data-stu-id="0dc33-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="0dc33-106">如果启用 Microsoft Exchange 集成, 则会将数据存档在 Exchange 存储中。</span><span class="sxs-lookup"><span data-stu-id="0dc33-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="0dc33-107">Exchange 中存档的数据是可搜索和可发现的。</span><span class="sxs-lookup"><span data-stu-id="0dc33-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="0dc33-108">有关访问 Exchange 中存档的数据的详细信息, 请参阅 Exchange 文档。</span><span class="sxs-lookup"><span data-stu-id="0dc33-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0dc33-109">使用 Windows PowerShell Cmdlet 导出存档数据</span><span class="sxs-lookup"><span data-stu-id="0dc33-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0dc33-110">您可以使用 Export-CSArchivingData cmdlet 导出存档数据。</span><span class="sxs-lookup"><span data-stu-id="0dc33-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="0dc33-p102">以下命令可导出自 2012 年 6 月 1 日以来写入存档数据库 atl-sql-001.contoso.com 的所有存档数据。生成的输出文件将存储在 C:\ArchivingExports 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0dc33-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="0dc33-113">以下命令为单个用户 (kenmyer@contoso.com) 导出存档数据。</span><span class="sxs-lookup"><span data-stu-id="0dc33-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="0dc33-114">通过包含 UserUri 参数, 后跟用户的 SIP 地址, 即可完成此操作。</span><span class="sxs-lookup"><span data-stu-id="0dc33-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="0dc33-115">例如：</span><span class="sxs-lookup"><span data-stu-id="0dc33-115">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="0dc33-116">有关详细信息, 请参阅[CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0dc33-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

