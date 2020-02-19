---
title: Lync Server 2013：创建存档配置以管理特定网站或池的存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c23afb99e20e8e23582664568eba4fb0b7b841
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a>在 Lync Server 2013 中创建存档配置，以管理特定网站或池的存档

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

在 Lync Server 2013 控制面板中，可以使用存档配置来控制如何在部署中实施存档。 这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。

存档配置最初是在部署存档时设置的，但您可以在部署后更改、添加和删除这些配置。 有关如何实施存档配置的详细信息，包括可以指定哪些选项以及存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 若要使用存档，您必须配置存档策略，以指定是为内部通信启用存档，还是为外部通信启用存档，还是对驻留在 Lync Server 2013 上的用户启用存档。 默认情况下，不会为内部或外部通信启用存档。 在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。 有关启用存档的详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 中配置和分配存档策略</A>。<BR>如果您在部署了要使用 Microsoft Exchange 集成来存储 Exchange 2013 服务器上的存档数据和文件的存档后决定，并且您的所有用户都驻留在 Exchange 2013 服务器上，则应删除 SQL Server 数据库配置从拓扑中。 您必须使用拓扑生成器执行此操作。 有关详细信息，请参阅操作文档中的在<A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 中更改存档数据库选项</A>。



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a>为站点或池创建存档配置

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。

4.  在“存档配置”**** 页上，单击“新建”****，然后执行下列操作之一：
    
      - 要创建站点存档配置，请单击“站点配置”****，然后在“选择站点”**** 中，选择要为存档配置的站点。
    
      - 要创建池存档配置，请单击“池配置”****，然后在“选择池”**** 中，选择要为存档配置的池。

5.  在“新建存档设置”**** 的“存档设置”**** 下拉列表框中，执行下列操作之一：
    
      - 若要只为即时消息 (IM) 会话启用存档，请单击“存档 IM 会话”****。
    
      - 若要为 IM 会话和 Web 会议启用存档，请单击“存档 IM 和 Web 会议会话”****。
    
      - 若要为策略禁用存档，请单击“禁用存档”****。

6.  另请在“新建存档设置”**** 中，执行下列操作：
    
      - 要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息 (IM) 或 Web 会议会话”**** 复选框。
    
      - 若要使用 Microsoft Exchange Server 存储存档数据，请单击 " **Microsoft exchange 集成**" 复选框。
    
      - 若要启用数据清除，请选中“启用存档数据清除”**** 复选框，然后执行下列操作之一：
        
          - 要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”****，然后指定天数。
        
          - 要限制仅清除已导出的存档数据，请单击“仅清除导出的存档数据”****。

7.  单击“提交”****。

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建存档配置设置

可以使用 Windows PowerShell 和 Set-csarchivingconfiguration cmdlet 创建存档配置设置。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a>为网站创建新的存档配置设置集合

  - 以下命令为 Redmond 站点创建一个新的存档配置设置集合：
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a>创建仅允许 IM 存档的新的存档配置设置集合

  - 由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建默认情况下允许存档即时消息会话的存档配置设置集合，仅需使用如下命令：
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a>在创建存档配置设置时指定多个属性值

  - 可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为存档即时消息会话并阻止不可用的存档服务的即时消息：
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

有关详细信息，请参阅[set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的存档工作原理](lync-server-2013-how-archiving-works.md)  


[在 Lync Server 2013 中管理组织、网站和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

