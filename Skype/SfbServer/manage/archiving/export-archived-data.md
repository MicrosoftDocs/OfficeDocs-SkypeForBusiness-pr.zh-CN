---
title: 在 Skype for Business Server 中导出存档数据
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
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 摘要：了解如何导出 Skype for Business Server 的存档数据。
ms.openlocfilehash: e69c283304395d697e99ef0607e2aec1eb7960e4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095376"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="5f569-103">在 Skype for Business Server 中导出存档数据</span><span class="sxs-lookup"><span data-stu-id="5f569-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="5f569-104">**摘要：** 了解如何导出 Skype for Business Server 的存档数据。</span><span class="sxs-lookup"><span data-stu-id="5f569-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="5f569-105">存档数据库中存档的数据不可搜索或不可读，但您可以使用 **Export-CsArchivingData** cmdlet 从数据库中提取记录并将其另存为 Outlook 电子邮件 (EML) 文件。</span><span class="sxs-lookup"><span data-stu-id="5f569-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="5f569-106">如果启用 Microsoft Exchange 集成，数据将存档在 Exchange 存储中。</span><span class="sxs-lookup"><span data-stu-id="5f569-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="5f569-107">Exchange 中存档的数据可搜索和发现。</span><span class="sxs-lookup"><span data-stu-id="5f569-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="5f569-108">有关访问 Exchange 中存档的数据的详细信息，请参阅 Exchange 文档。</span><span class="sxs-lookup"><span data-stu-id="5f569-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5f569-109">使用 Cmdlet 导出Windows PowerShell数据</span><span class="sxs-lookup"><span data-stu-id="5f569-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5f569-110">可以使用 cmdlet 导出存档Export-CSArchivingData数据。</span><span class="sxs-lookup"><span data-stu-id="5f569-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="5f569-111">以下命令导出自 2012 年 6 月 1 以来写入 atl-sql-001.contoso.com 数据库的所有存档数据。</span><span class="sxs-lookup"><span data-stu-id="5f569-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="5f569-112">生成的输出文件将存储在 C:\ArchivingExports 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5f569-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="5f569-113">以下命令导出单个用户的存档数据：kenmyer@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5f569-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="5f569-114">这是通过包括 UserUri 参数后跟用户 SIP 地址完成。</span><span class="sxs-lookup"><span data-stu-id="5f569-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="5f569-115">例如：</span><span class="sxs-lookup"><span data-stu-id="5f569-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="5f569-116">有关详细信息，请参阅 [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5f569-116">For more information, see the help topic for the [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
