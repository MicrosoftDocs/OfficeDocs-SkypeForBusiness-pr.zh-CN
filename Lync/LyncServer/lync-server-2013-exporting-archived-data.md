---
title: 在 Lync Server 2013 中导出存档数据
TOCTitle: 在 Lync Server 2013 中导出存档数据
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204657(v=OCS.15)
ms:contentKeyID: 49311931
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中导出存档数据

 

_**上一次修改主题：** 2013-02-23_

存档数据库中存档的数据采用的是不可搜索或不可读格式，但是您可以使用 Export-CsArchivingData cmdlet 从数据库提取记录并将它们保存为 Outlook 电子邮件 (EML) 文件。有关导出存档数据的详细信息，请参阅操作文档中的 [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)。

如果启用 Microsoft Exchange 集成，数据将存档在 Exchange 2013 存储中。存档在 Exchange 2013 中的数据可搜索并且可检测到。有关对集成的 Exchange 2013 和 Lync Server 2013 通信的支持的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的 Exchange Server 和 SharePoint 集成支持](lync-server-2013-exchange-and-sharepoint-integration-support.md)。有关访问存档在 Exchange 中的数据的详细信息，请参阅 Exchange 2013 文档。

## 使用 Lync Server 命令行管理程序 Cmdlet 导出存档数据

可以使用 Export-CSArchivingData cmdlet 导出存档数据。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

**导出存档数据**

  - 此命令导出自 2012 年 6 月 1 日以来写入存档数据库 atl-sql-001.litwareinc.com 的所有存档数据。生成的输出文件将存储在 C:\\ArchivingExports 文件夹中。
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**为单个用户导出存档数据**

  - 以下命令为单个用户 (kenmyer@litwareinc.com) 导出存档数据。可以通过包括 UserUri 参数并在其后加上用户 SIP 地址来完成。例如：
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

有关详细信息，请参阅 [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData) cmdlet 的帮助主题。

## 另请参阅

#### 概念

[Lync Server 2013 中的 Exchange Server 和 SharePoint 集成支持](lync-server-2013-exchange-and-sharepoint-integration-support.md)  

#### 其他资源

[Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)  
[管理 Lync Server 2013 存档](lync-server-2013-managing-archiving.md)

