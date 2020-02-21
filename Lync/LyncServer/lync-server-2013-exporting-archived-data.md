---
title: Lync Server 2013：导出存档数据
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
ms.openlocfilehash: cc93d529c5f93ad020634d631c94c09e0a94df1a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>从 Lync Server 2013 导出存档数据

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

存档数据库中存档的数据采用的是不可搜索或不可读格式，但是您可以使用 Export-CsArchivingData cmdlet 从数据库提取记录并将它们保存为 Outlook 电子邮件 (EML) 文件。 有关导出存档数据的详细信息，请参阅操作文档中的 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)。

如果启用 Microsoft Exchange 集成，则会在 Exchange 2013 存储中存档数据。 Exchange 2013 中存档的数据是可搜索和可发现的。 有关 Exchange 2013 和 Lync Server 2013 的集成通信支持的详细信息，请参阅可支持性文档中的[Lync server 2013 中的 Exchange Server 和 SharePoint 集成支持](lync-server-2013-exchange-and-sharepoint-integration-support.md)。 有关访问在 Exchange 中存档的数据的详细信息，请参阅 Exchange 2013 文档。

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 导出存档数据

可以使用 Export-CSArchivingData cmdlet 导出存档数据。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

**导出存档数据**

  - 此命令导出自 2012 年 6 月 1 日以来写入存档数据库 atl-sql-001.litwareinc.com 的所有存档数据。 生成的输出文件将存储在文件夹 C：\\ArchivingExports 中。
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**为单个用户导出存档数据**

  - 以下命令为单个用户 (kenmyer@litwareinc.com) 导出存档数据。可以通过包括 UserUri 参数并在其后加上用户 SIP 地址来完成。例如：
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

有关详细信息，请参阅[export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的 Exchange Server 和 SharePoint 集成支持](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[管理 Lync Server 2013 存档](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

