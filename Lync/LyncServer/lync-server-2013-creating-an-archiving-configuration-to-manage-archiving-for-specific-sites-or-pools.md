---
title: 创建存档配置以管理特定站点或池的存档
TOCTitle: 创建存档配置以管理特定站点或池的存档
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205251(v=OCS.15)
ms:contentKeyID: 49314182
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建存档配置以管理特定站点或池的存档

 

_**上一次修改主题：** 2013-02-23_

在 Lync Server 2013 控制面板中，您使用存档配置控制在部署中实现存档的方式。其中包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 可以进行创建并用于指定为特定站点或池实现存档的方式的可选站点级和池级配置。

您最初在部署存档时设置存档配置，但您可以在部署后更改、添加和删除配置。有关如何实现存档配置（包括您可以指定的选项和存档配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 若要使用存档，则必须配置存档策略以指定是对内部通信、外部通信还是对驻留在 Lync Server 2013 中的用户的这两种通信启用存档策略。默认情况下，不会为内部或外部通信启用存档。在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。有关启用存档的详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">配置和分配存档策略</a>。<br />
如果您在部署存档后决定要使用 Microsoft Exchange 集成在 Exchange 2013 服务器上存储存档数据和文件以及所有用户驻留在 Exchange 2013 服务器上，则应从拓扑中删除 SQL Server 数据库配置。必须使用拓扑生成器执行此操作。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-changing-archiving-database-options.md">在 Lync Server 2013 中更改存档数据库选项</a>。



## 为站点或池创建存档配置

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档配置”。

4.  在“存档配置”页上，单击“新建”，然后执行下列操作之一：
    
      - 要创建站点存档配置，请单击“站点配置”，然后在“选择站点”中，选择要为存档配置的站点。
    
      - 要创建池存档配置，请单击“池配置”，然后在“选择池”中，选择要为存档配置的池。

5.  在“新建存档设置”的“存档设置”下拉列表框中，执行下列操作之一：
    
      - 若要只为即时消息 (IM) 会话启用存档，请单击“存档 IM 会话”。
    
      - 若要为 IM 会话和 Web 会议启用存档，请单击“存档 IM 和 Web 会议会话”。
    
      - 若要为策略禁用存档，请单击“禁用存档”。

6.  另请在“新建存档设置”中，执行下列操作：
    
      - 要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息 (IM) 或 Web 会议会话”复选框。
    
      - 若要使用 Microsoft Exchange Server 存储存档数据，请单击“Microsoft Exchange 集成”复选框。
    
      - 若要启用数据清除，请选中“启用存档数据清除”复选框，然后执行下列操作之一：
        
          - 要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”，然后指定天数。
        
          - 要限制仅清除已导出的存档数据，请单击“仅清除导出的存档数据”。

7.  单击“提交”。

## 使用 Lync Server Cmdlet 创建存档配置设置

还可以使用 Windows PowerShell Windows PowerShell 和 New-CsArchivingConfiguration cmdlet 创建存档配置设置。 可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 为站点创建新的存档配置设置集合

  - 以下命令为 Redmond 站点创建一个新的存档配置设置集合：
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

## 创建新的仅允许 IM 存档的存档配置设置集合

  - 由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建默认情况下允许存档即时消息会话的存档配置设置集合，仅需使用如下命令：
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

## 创建存档配置设置时指定多个属性值

  - 可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为存档即时消息会话并阻止不可用的存档服务的即时消息：
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

有关详细信息，请参阅 [New-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingConfiguration) cmdlet 的帮助主题。

## 另请参阅

#### 概念

[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)  

#### 其他资源

[在 Lync Server 2013 中管理组织、站点和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

