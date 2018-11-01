---
title: 启用或禁用 IM 或会议会话的存档
TOCTitle: 启用或禁用 IM 或会议会话的存档
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182567(v=OCS.15)
ms:contentKeyID: 49313877
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用或禁用 IM 或会议会话的存档

 

_**上一次修改主题：** 2012-10-10_

在 Lync Server 2013 控制面板中，您可以使用存档配置来启用和禁用 IM、会议会话或这两者的存档。这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。

您最初在部署存档时设置存档配置，但您可以在部署后更改、添加和删除配置。有关如何实现存档配置（包括可指定的选项以及存档配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 要使用存档，则必须配置存档策略以指定是对内部通信、外部通信还是驻留在 Lync Server 2013 上的用户启用存档策略。默认情况下，不会为内部或外部通信启用存档。在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。有关启用存档的详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">配置和分配存档策略</a>。<br />
如果您在部署存档后决定要使用 Microsoft Exchange 集成在 Exchange 2013 服务器上存储存档数据和文件以及所有用户驻留在 Exchange 2013 服务器上，则应从拓扑中删除 SQL Server 数据库配置。必须使用拓扑生成器执行此操作。有关详细信息，请参阅操作文档中的<a href="lync-server-2013-changing-archiving-database-options.md">在 Lync Server 2013 中更改存档数据库选项</a>。



## 启用或禁用 IM 或会议会话的存档

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档配置”。

4.  从存档配置列表中选择相应的全局、站点或池策略，单击“编辑”，再单击“显示详细信息”，然后执行下列操作：
    
      - 若要只为即时消息 (IM) 会话启用存档，请单击“存档 IM 会话”。
    
      - 若要同时为 IM 会话和会议启用存档，请单击“存档 IM 和会议会话”。
    
      - 若要为策略禁用存档，请单击“禁用存档”。

5.  单击“提交”。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中管理组织、站点和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[配置和分配存档策略](lync-server-2013-configuring-and-assigning-archiving-policies.md)

