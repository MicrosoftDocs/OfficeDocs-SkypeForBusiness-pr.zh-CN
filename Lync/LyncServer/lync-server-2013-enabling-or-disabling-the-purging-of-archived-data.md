---
title: Lync Server 2013：启用或禁用存档数据的清除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f74963f080c244f375bac0ea00ab152e89cc2723
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用已存档数据的清除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

在 Lync Server 2013 控制面板中，使用存档配置启用和禁用清除和配置清除的实现方式。 这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。

存档配置最初是在部署存档时设置的，但您可以在部署后更改、添加和删除这些配置。 有关如何实施存档配置的详细信息，包括可以指定哪些选项以及存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 若要对驻留在 Lync Server 2013 上的用户使用存档，您必须配置存档策略，以指定是为内部通信启用存档，还是对二者启用存档。 默认情况下，不对内部或外部通信启用存档。 在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。 有关启用存档的详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 中配置和分配存档策略</A>。<BR>如果您在部署了要使用 Microsoft Exchange 集成来存储 Exchange 2013 服务器上的存档数据和文件的存档后决定，并且您的所有用户都驻留在 Exchange 2013 服务器上，则应删除 SQL Server 数据库配置从拓扑中。 您必须使用拓扑生成器执行此操作。 有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 中更改存档数据库选项</A>。



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>为存档启用或禁用清除

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。

4.  在存档配置列表中单击相应的全局、站点或池配置的名称，然后依次单击“编辑”****、“显示详细信息”****，然后执行以下操作：
    
      - 要启用清除，请选中“启用清除存档数据功能”**** 复选框，然后执行下列操作之一：
        
          - 要清除所有记录，请单击“清除超过以下最长持续时间(天)的已导出存档数据和已存储存档数据”****，然后指定天数。
        
          - 要仅清除已导出的数据，请单击“仅清除已导出的存档数据”****。
    
      - 要禁用清除，请清除“启用清除存档数据功能”**** 复选框。

5.  单击“提交”****。

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用存档数据的清除

可以使用 Windows PowerShell 和**set-csarchivingconfiguration** cmdlet 来管理启用和禁用存档数据的自动清除。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>启用对所有存档数据的清除

  - 若要启用清除所有存档数据功能，请将 **EnablePurging** 属性设置为 true ($True)。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    运行此命令后，Lync Server 每天将清除早于为**KeepArchivingDataForDays**属性指定的值的所有存档记录。

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>启用仅清除导出的存档数据

  - 若要将清除限制为将已导出到数据文件的记录存档（通过使用[export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet），您还必须将 PurgeExportedArchivesOnly 属性设置为 True （$True）。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    运行此命令后，Lync Server 将仅清除满足以下两个条件的存档记录：1）它们比为**KeepArchivingDataForDays**属性指定的值更早;和2）使用**export-csarchivingdata** cmdlet 导出它们。

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>禁用对所有存档数据的清除

  - 若要禁用自动清除存档记录功能，请将 **EnablePurging** 属性设置为 False ($False)。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

有关详细信息，包括用于清除存档数据的其他选项，请参阅[set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的存档工作原理](lync-server-2013-how-archiving-works.md)  


[在 Lync Server 2013 中配置和分配存档策略](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[在 Lync Server 2013 中管理组织、网站和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

