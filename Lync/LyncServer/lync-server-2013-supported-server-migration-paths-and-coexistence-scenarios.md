---
title: Lync Server 2013：支持的服务器迁移路径和共存方案
TOCTitle: 支持的服务器迁移路径和共存方案
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425764(v=OCS.15)
ms:contentKeyID: 49312332
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中支持的服务器迁移路径和共存方案

 

_**上一次修改主题：** 2012-10-16_

Lync Server 2013 支持从以下任意一种环境中进行迁移：

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

不支持从同时运行上述这两个版本的环境中进行迁移。不支持从早期版本（例如 Microsoft Office Communications Server 2007 或 Live Communications Server 2005）进行迁移。如果先前的部署已包括 群聊，则必须单独迁移它。

## 迁移方法

支持所有 Lync Server 拓扑和服务器角色的迁移。可以从一个拓扑迁移到另一拓扑，包括从 Standard Edition Server 迁移到 Enterprise Edition Server。

Lync Server 2013 仅支持以下迁移方法：

   **并行迁移。**在并行迁移中， Lync Server 2013 与现有 Microsoft Lync Server 2010 或 Office Communications Server 2007 R2 部署并排部署，然后将操作转移到新服务器，并将用户移动到 Lync Server 2013。采用这种方法时，在迁移过程中需要使用其他服务器平台（包括硬件和软件），并且新配置中的系统名称和池名称与原配置中的不同。如果需要回滚到先前版本，可以将操作切换回先前的服务器。

不支持在 Active Directory 域服务 林间迁移。

推荐的迁移路径是一种分阶段方法。有关从先前版本迁移（包括相应的组件分阶段部署）的详细信息，请参阅迁移文档中的以下主题：

  - [从 Lync Server 2010 迁移到 Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [从 Office Communications Server 2007 R2 迁移至 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

## 共存方案

Lync Server 2013 可与 Lync Server 2010 部署或 Office Communications Server 2007 R2 部署的组件共存。不支持 Lync Server 2013 与 Lync Server 2010 和 Office Communications Server 2007 R2 两者的并发部署（所有这三种版本的并发部署）。

在先前的 Lync Server 2013 或 Office Communications Server 2007 R2 部署与 Lync Server 2010 新部署临时共存的分阶段迁移过程中，对混合版本路由的支持受到限制。有关详细信息，请参阅迁移文档。

您必须对 Lync Server 2013 数据库实例使用运行 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 的单独且不同的计算机。您不能对用于 Lync Server 2010 或 Office Communications Server 2007 R2 前端池的 Lync Server 2013 前端池使用同一 SQL Server 实例。如果您在 拓扑生成器中为已部署了 Lync Server 2010 或 Office Communications Server 2007 R2 的部署定义并配置 Lync Server 2013，则 拓扑生成器将不允许您定义已在拓扑中使用的 Lync Server 2013 实例。

拓扑生成器将显示以下消息来通知您此问题：“SQL 服务器 \[服务器的 FQDN\] 已包含承载角色 "用户存储" 的 SQL 实例”。

> [!NOTE]  
> 如果要为您的 Lync Server 2013 部署部署新的服务器角色，则应该首先升级现有部署（如迁移文档和部署文档中所述），然后部署新服务器角色（如规划文档和部署文档中所述）。如果要迁移先前版本的群聊，请在完成从 Lync Server 2010 或 Office Communications Server 2007 R2 迁移所有其他组件的过程后，最后迁移群聊。


有关具体的共存要求，以及有关 Lync Server 2010 或 Office Communications Server 2007 R2 与 Lync Server 2013 组件的共存和迁移的其他详细信息，请参阅迁移文档中的 [从 Lync Server 2010 迁移到 Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) 和 [从 Office Communications Server 2007 R2 迁移至 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)。有关客户端的混合版本支持的详细信息，请参阅 [Lync Server 2013 先前部署中支持的客户端](lync-server-2013-supported-clients-from-previous-deployments.md)。

