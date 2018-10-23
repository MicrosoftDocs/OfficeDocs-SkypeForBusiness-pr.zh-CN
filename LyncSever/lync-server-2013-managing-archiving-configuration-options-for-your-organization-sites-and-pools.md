---
title: 在 Lync Server 2013 中管理组织、站点和池的存档配置选项
TOCTitle: 在 Lync Server 2013 中管理组织、站点和池的存档配置选项
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204802(v=OCS.15)
ms:contentKeyID: 49312525
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中管理组织、站点和池的存档配置选项

 

_**上一次修改主题：** 2012-11-01_

在 Lync Server 2013 控制面板中，您可使用存档配置指定存档的实施方式。这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可创建和用于指定如何针对特定站点或池实施存档的可选站点级和池级配置。

存档配置最初是在部署存档时设置的，但您可以在部署后更改、添加和删除这些配置。在 Lync Server 2013 控制面板中，可以使用“存档和监控”组的“存档配置”页来管理全局级别、站点级别和池级别的配置。有关如何实施存档配置（包括您可以指定的选项以及存档配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 若要使用存档，您必须配置存档策略以指定是对 Lync Server 2013 上承载的所有用户的内部通信、外部通信、还是对这两者启用存档。默认情况下，不对内部或外部通信启用存档。如果使用 Microsoft Exchange 集成，则您必须启用和配置 Exchange 2013 以支持为 Exchange 2013 上承载的、已将其邮箱置于就地保留状态的所有用户进行存档。<br />
如本节中所述，在启用存档之前，应该为您的部署指定相应存档配置，并且还可以选择为特定站点和池指定相应存档配置。有关启用存档的详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">配置和分配存档策略</a>。



**使用 Lync Server 命令行管理程序 cmdlet 查看存档配置信息**

  - 您还可以使用 Lync ServerWindows PowerShell 和 **Get-CsArchivingConfiguration** cmdlet 查看存档配置信息。您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    在 Lync Server 命令行管理程序中，使用以下命令可查看有关您的所有存档配置设置的信息：
    
        Get-CsArchivingConfiguration

## 本部分内容

  - [创建存档配置以管理特定站点或池的存档](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [启用或禁用 IM 或会议会话的存档](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [启用或禁用存档数据的清除](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [存档失败时启用或禁用临界模式以阻止或允许 IM 和 Web 会议会话](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [启用或禁用与 Exchange 存储的集成](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [删除存档配置](lync-server-2013-deleting-an-archiving-configuration.md)

## 另请参阅

#### 其他资源

[管理 Lync Server 2013 存档](lync-server-2013-managing-archiving.md)

