---
title: Standard Edition 服务器部署中的 Lync Server 2013 服务器并置
TOCTitle: Standard Edition 服务器部署中的服务器并置
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398131(v=OCS.15)
ms:contentKeyID: 49311899
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的 Standard Edition 服务器部署中的服务器并置

 

_**上一次修改主题：** 2013-01-20_

本节介绍了您可在 Lync Server 2013 Standard Edition 服务器部署中并置的服务器角色、数据库和文件共享。

## 服务器角色

在 Lync Server 2013 中，A/V 会议服务、中介服务、监控和存档并置在 Standard Edition 服务器上，但需要进行额外配置才能启用它们。

可以将受信任应用程序服务器与 Standard Edition 服务器并置。

以下服务器角色必须分别部署在不同的计算机上：

  - 控制器

  - 边缘服务器

  - 中介服务器（如果未与 Standard Edition 服务器并置）

  - Office Web Apps Server

## 数据库

默认情况下，SQL Server Express 后端数据库并置在 Standard Edition 服务器上。您不能将其移动到单独的计算机。此外，您不能在 Standard Edition 服务器上并置其他数据库。如果您选择在 Standard Edition 服务器上部署 持久聊天服务器，则可以在相同 Standard Edition 服务器上并置持久聊天数据库和持久聊天合规性数据库。

您还可以在一个单独的数据库服务器上并置以下每个数据库：

  - 监控数据库

  - 存档数据库

  - Enterprise Edition 前端池的后端数据库

您可以在单一的 SQL 实例中并置上述任意或所有数据库，或针对每个数据库使用一个单独的 SQL 实例，但有以下限制：

  - 每个 SQL 实例只能包含一个后端数据库（用于 Enterprise Edition 前端池）、一个监控数据库、一个存档数据库、一个持久聊天数据库以及一个持久聊天合规性数据库。

  - 无论这些数据库使用同一个 SQL Server 实例还是使用单独的 SQL Server 实例，数据库服务器仅支持一个 Enterprise Edition 前端池、一个存档服务器、一个监控服务器、一个 持久聊天数据库以及一个 持久聊天合规性数据库，而不能支持它们中的多个。

可以并置文件共享与数据库，如本节后面所述。

> [!NOTE]  
> 在 Lync Server 2013 中，可以选择为您的部署中的部分或所有用户将监控和存档存储与 Exchange 2013 存储集成。但您无法将任何运行 Lync Server 的服务器或组件部署到与 Exchange 存储相同的服务器上。



> [!IMPORTANT]
> 尽管支持并置数据库，但数据库的大小增长非常快。例如，当您考虑将存档数据库与其他数据库并置时，您应了解，如果您要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议并置多个数据库，特别是将存档数据库、 持久聊天数据库和 持久聊天合规性数据库与企业池的后端数据库并置。


## 文件共享

文件共享可以是独立的服务器，也可以并置到与以下任何或所有项相同的服务器：

  - 数据库服务器，包括企业版前端池的后端服务器

  - 存档数据库

  - 监控数据库

  - 持久聊天 数据库

  - 持久聊天合规性数据库

单个文件共享可用于多个前端池、Standard Edition 服务器（全部位于同一站点）。

> [!NOTE]  
> 在 Lync Server 2013 中，监控和存档功能使用 Lync Server 文件共享作为 Standard Edition 服务器。



## 其他组件

反向代理服务器并不是 Lync Server 2013 组件，它只是您想支持联盟用户共享 Web 内容时需要在部署中使用的服务器。因此，您无法将它与任何 Lync Server 2013 服务器角色一起并置。但是，您可以通过在组织中用于支持其他应用程序的现有反向代理服务器上配置反向代理支持来为 Lync Server 2013 部署实现该支持。

不能将任何 Exchange UM 组件或 SharePoint 组件与任何 Lync Server 2013 角色并置。

