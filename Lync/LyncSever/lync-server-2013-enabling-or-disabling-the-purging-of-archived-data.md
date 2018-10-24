---
title: 启用或禁用存档数据的清除
TOCTitle: 启用或禁用存档数据的清除
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520968(v=OCS.15)
ms:contentKeyID: 49312317
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用或禁用存档数据的清除

 

_**上一次修改主题：** 2013-02-23_

在 Lync Server 2013 控制面板中，可以使用存档配置启用和禁用清除功能，以及配置如何实现清除。其中包括以下存档配置：

  - 您部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用于指定如何为特定站点或池实现存档的可选站点级和池级配置。

可以在部署存档时初步设置存档配置，但可以在部署后更改、添加和删除配置。有关如何实施存档配置（包括您可以指定的选项以及存档配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 若要对驻留在 Lync Server 2013 上的用户使用存档，您必须配置存档策略以指定是对内部通信、外部通信、还是对这两者启用存档。默认情况下，不对内部或外部通信启用存档。在启用任何策略中的存档之前，您应该按本节中所述为您的部署（或者为特定站点和池）指定相应的存档配置。有关启用存档的详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">配置和分配存档策略</a>。<br />
如果您决定在部署存档后使用 Microsoft Exchange 集成在 Exchange 2013 服务器上存储存档数据和文件，并且您的所有用户均驻留在 Exchange 2013 服务器上，那么您应该从拓扑中删除 SQL Server 数据库配置。您必须使用拓扑生成器执行此操作。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-changing-archiving-database-options.md">在 Lync Server 2013 中更改存档数据库选项</a>。



## 为存档启用或禁用清除

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档配置”。

4.  在存档配置列表中单击相应的全局、站点或池配置的名称，然后依次单击“编辑”、“显示详细信息”，然后执行以下操作：
    
      - 要启用清除，请选中“启用清除存档数据功能”复选框，然后执行下列操作之一：
        
          - 要清除所有记录，请单击“清除超过以下最长持续时间(天)的已导出存档数据和已存储存档数据”，然后指定天数。
        
          - 要仅清除已导出的数据，请单击“仅清除已导出的存档数据”。
    
      - 要禁用清除，请清除“启用清除存档数据功能”复选框。

5.  单击“提交”。

## 使用 Lync Server 命令行管理程序 Cmdlet 启用或禁用清除存档数据功能

在启用或禁用自动清除存档数据功能时，也可以使用 Windows PowerShell 和 **Set-CsArchivingConfiguration** cmdlet 管理此过程。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话来运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 启用清除所有存档数据功能

  - 若要启用清除所有存档数据功能，请将 **EnablePurging** 属性设置为 true ($True)。例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    运行此命令后，Lync Server 每天都会清除早于为 **KeepArchivingDataForDays** 属性指定的值的所有存档记录。

## 启用仅清除导出的存档数据功能

  - 如果仅清除已使用 [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData) cmdlet 导出至数据文件的存档记录，您还必须将 PurgeExportedArchivesOnly 属性设置为 True ($True)。例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    运行此命令后，Lync Server 将仅清除满足以下两个条件的存档记录：1) 它们早于为 **KeepArchivingDataForDays** 属性指定的值，且 2) 已使用 **Export-CsArchivingData** cmdlet 导出这些记录。

## 禁用清除所有存档数据功能

  - 若要禁用自动清除存档记录功能，请将 **EnablePurging** 属性设置为 False ($False)。例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

有关详细信息，包括清除存档数据的其他选项，请参阅 [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet 的帮助主题。

## 另请参阅

#### 概念

[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)  

#### 其他资源

[配置和分配存档策略](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[在 Lync Server 2013 中管理组织、站点和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

