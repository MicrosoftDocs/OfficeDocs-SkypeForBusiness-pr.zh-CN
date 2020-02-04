---
title: Lync Server 2013：导出已存档的数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5758d5e28610906b743888d25197385ef542717
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="51738-102">从 Lync Server 2013 导出已存档的数据</span><span class="sxs-lookup"><span data-stu-id="51738-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51738-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="51738-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="51738-104">存档数据库中存档的数据采用的是不可搜索或不可读格式，但是您可以使用 Export-CsArchivingData cmdlet 从数据库提取记录并将它们保存为 Outlook 电子邮件 (EML) 文件。</span><span class="sxs-lookup"><span data-stu-id="51738-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="51738-105">有关导出已存档数据的详细信息，请参阅操作文档中的[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) 。</span><span class="sxs-lookup"><span data-stu-id="51738-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="51738-106">如果启用 Microsoft Exchange 集成，数据将存档在 Exchange 2013 存储中。</span><span class="sxs-lookup"><span data-stu-id="51738-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="51738-107">Exchange 2013 中存档的数据是可搜索和可发现的。</span><span class="sxs-lookup"><span data-stu-id="51738-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="51738-108">有关 Exchange 2013 和 Lync Server 2013 的集成通信支持的详细信息，请参阅支持文档中[Lync server 2013 中的 Exchange Server 和 SharePoint 集成支持](lync-server-2013-exchange-and-sharepoint-integration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="51738-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="51738-109">有关访问 Exchange 中存档的数据的详细信息，请参阅 Exchange 2013 文档。</span><span class="sxs-lookup"><span data-stu-id="51738-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="51738-110">使用 Windows PowerShell Cmdlet 导出存档数据</span><span class="sxs-lookup"><span data-stu-id="51738-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="51738-111">可使用 CSArchivingData cmdlet 导出存档数据。</span><span class="sxs-lookup"><span data-stu-id="51738-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="51738-112">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="51738-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="51738-113">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="51738-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="51738-114">**导出存档数据**</span><span class="sxs-lookup"><span data-stu-id="51738-114">**To export archiving data**</span></span>

  - <span data-ttu-id="51738-115">Atl-sql-001.litwareinc.com 自2012年6月1日起，此命令将导出写入到存档数据库的所有存档数据。</span><span class="sxs-lookup"><span data-stu-id="51738-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="51738-116">生成的输出文件将存储在文件夹 C：\\ArchivingExports 中。</span><span class="sxs-lookup"><span data-stu-id="51738-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="51738-117">**导出单个用户的存档数据**</span><span class="sxs-lookup"><span data-stu-id="51738-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="51738-118">以下命令导出单个用户的存档数据： kenmyer@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="51738-118">The following command exports archiving data for a single user: kenmyer@litwareinc.com.</span></span> <span data-ttu-id="51738-119">可以通过包括 UserUri 参数并在其后加上用户 SIP 地址来完成。</span><span class="sxs-lookup"><span data-stu-id="51738-119">This is done by including the UserUri parameter followed by the user’s SIP address.</span></span> <span data-ttu-id="51738-120">例如：</span><span class="sxs-lookup"><span data-stu-id="51738-120">For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="51738-121">有关详细信息，请参阅[CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="51738-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51738-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51738-122">See Also</span></span>


[<span data-ttu-id="51738-123">Lync Server 2013 中的 Exchange Server 和 SharePoint 集成支持</span><span class="sxs-lookup"><span data-stu-id="51738-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="51738-124">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="51738-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="51738-125">管理 Lync Server 2013 存档</span><span class="sxs-lookup"><span data-stu-id="51738-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

