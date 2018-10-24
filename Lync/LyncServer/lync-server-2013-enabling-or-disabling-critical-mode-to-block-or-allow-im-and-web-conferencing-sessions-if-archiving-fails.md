---
title: 存档失败时启用或禁用临界模式以阻止或允许 IM 和 Web 会议会话
TOCTitle: 存档失败时启用或禁用临界模式以阻止或允许 IM 和 Web 会议会话
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182609(v=OCS.15)
ms:contentKeyID: 49314817
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 存档失败时启用或禁用临界模式以阻止或允许 IM 和 Web 会议会话

 

_**上一次修改主题：** 2013-02-23_

在 Lync Server 2013 控制面板中，可使用存档配置启用和禁用临界模式。这包括下列存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。

您最初在部署存档时设置存档配置，但可以在部署后更改、添加和删除配置。有关如何实现存档配置（包括您可以指定的选项和存档配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 若要使用存档，则必须配置存档策略以指定为驻留在 Lync Server 2013 上的用户是对内部通信、外部通信还是这两者启用存档策略。默认情况下，不会为内部或外部通信启用存档。在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。有关启用存档的详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">配置和分配存档策略</a>。<br />
如果您在部署存档后决定要使用 Exchange Server 集成在 Exchange 2013 服务器上存储存档数据和文件以及所有用户驻留在 Exchange 2013 服务器上，则应从拓扑中删除 SQL Server 数据库配置。必须使用拓扑生成器执行此操作。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-changing-archiving-database-options.md">在 Lync Server 2013 中更改存档数据库选项</a>。



## 启用或禁用存档失败时阻止 IM 和 Web 会议会话的功能

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档配置”。

4.  单击存档配置列表中相应的全局、站点或池配置的名称，单击“编辑”，再单击“显示详细信息”，然后执行以下操作：

5.  要设置存档在失败时的行为方式，请选中或清除“存档失败时阻止即时消息(IM)或 Web 会议会话”复选框。

6.  单击“提交”。

## 通过使用 Lync ServerWindows PowerShell Cmdlet 启用和禁用临界模式

可使用 **Set-CsArchivingConfiguration** cmdlet 启用或禁用临界模式。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 启用临界模式

  - 要启用临界模式，请将 BlockOnArchiveFailure 属性的值设置为 True ($True)。例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

## 禁用临界模式

  - 要禁用临界模式，请将 BlockOnArchiveFailure 属性的值设置为 False ($False)。例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

有关更多信息，请参阅[Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[在 Lync Server 2013 中更改存档数据库选项](lync-server-2013-changing-archiving-database-options.md)  

#### 概念

[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)  

#### 其他资源

[在 Lync Server 2013 中管理组织、站点和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

