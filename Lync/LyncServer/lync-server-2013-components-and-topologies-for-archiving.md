---
title: Lync Server 2013：用于存档的组件和拓扑
TOCTitle: 用于存档的组件和拓扑
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204916(v=OCS.15)
ms:contentKeyID: 49312913
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中用于存档的组件和拓扑

 

_**上一次修改主题：** 2012-10-09_

如果要存档 Lync Server 2013 IM 和会议内容，可以在 Lync Server 中实现存档。

## 存档组件

存档功能包括以下组件：

  - **存档代理**。将在每个前端池和 Standard Edition 服务器上自动安装和激活存档代理（也称为“统一数据收集代理”）。尽管会自动激活存档代理，但实际上并不捕获任何消息，除非启用存档并正确配置存档。

  - **存档数据存储**。 Lync Server 2013 的数据存储可以是以下任意一项：
    
      - Exchange 2013 存储。如果启用 Microsoft Exchange 集成选项，驻留在 Exchange 2013 服务器上的用户邮箱将使用 Exchange 2013 存储保存存档数据，但仅当这些邮箱处于就地保留状态时才会如此。
    
      - SQL Server 存储。如果您的部署中有驻留在 Lync Server 2013 上的用户，则可以设置运行受支持版本的 SQL Server 的存档数据库来启用对这些用户的存档。

存档还需要文件存储，但是存档使用与前端服务器或 Standard Edition 服务器相同的文件存储。

有关存档的硬件和软件要求的列表，请参阅可支持性文档中的 [支持的适用于 Lync Server 2013 的硬件](lync-server-2013-supported-hardware.md)和 [Lync Server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。

## 支持的拓扑

您在每个具有需要存档支持的池中部署存档。存档在 企业版 池的 前端服务器中以及 Standard Edition 服务器上运行。存档数据存储可以：

  - 与 Exchange 2013 存储集成

  - 使用单独的 SQL Server 数据库进行部署

如果您的 Exchange 2013 部署未将所有用户包含在 Lync Server 部署中，则必须对其邮箱驻留在 Exchange 2013 服务器上的用户使用 Microsoft Exchange 集成，且必须为所有其他 Lync 用户部署单独的 SQL Server 数据库以用于存档。

## 支持的并置

Lync Server 2013 支持多种并置方案，以便通过一些灵活的方式节省硬件成本，您可以在一台服务器上运行多个组件（如果组织规模较小），也可以将各个组件分布到不同的服务器上（如果组织规模较大，对可伸缩性和性能具有一定要求）。在决定是否并置组件之前，一定要考虑可伸缩性因素。

存档部署在池的 前端服务器上或 Standard Edition 服务器上。有关可在这些位置并置的组件的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中支持的服务器并置](lync-server-2013-supported-server-collocation.md)。

如果您使用单独的 SQL Server 数据库进行存档，那么除了将存储与 Exchange 2013 存储集成，您还可以将存档数据库与以下任何数据库并置：

  - 监控数据库

  - 企业版前端池的后端数据库

> [!NOTE]  
> 承载存档数据库的服务器可承载其他数据库。但当您考虑将存档数据库与其他数据库并置时，您应了解，如果要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议将存档数据库与后端数据库并置。



如果将存档数据库与监控数据库、后端数据库或这两个数据库并置，则可以对任一或所有数据库使用单个 SQL 实例，也可以对每个数据库使用一个单独的 SQL 实例，但有以下限制：

  - 每个 SQL 实例只能包含一个后端数据库，一个监控数据库和一个存档数据库。

有关所有服务器角色和数据库并置的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中支持的服务器并置](lync-server-2013-supported-server-collocation.md)。

