---
title: 设置存档存储
TOCTitle: 设置存档存储
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205392(v=OCS.15)
ms:contentKeyID: 49314778
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 设置存档存储

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 的存档存储包括以下内容：

  - **数据存储**存储 IM 内容需要数据存储。

  - **文件存储**存储会议内容数据存储和文件存储需要文件存储。

## 设置数据存储

设置用于 Lync Server 2013 存档的数据存储的要求取决于您希望采用的存储存档数据的方式：

  - 将 Lync Server 2013 存档与 Exchange 部署集成以使用 Exchange 存储来存储存档数据。

  - 设置单独的 SQL Server 数据库服务器以存储存档数据。

## 为存档数据设置 Exchange 存储

为存档数据设置 Exchange 存储要求 Exchange 部署正在运行 Exchange 2013。此外，用户邮箱必须驻留在 Exchange 2013 服务器上，且其邮箱必须处于就地保留状态。有关配置 Exchange 2013 的详细信息，请参阅 Exchange 产品文档。

## 为存档数据设置 SQL Server 数据库服务器存储

Lync Server 2013 存档要求使用 SQL Server 数据库软件存储已存档数据，除非您将部署与 Exchange 集成。

对于 SQL Server 存档数据库，您必须在承载此存档数据库的计算机上安装 SQL Server。您可使用用于前端池的后端数据库的同一 SQL 实例。为实现最佳性能，应当在独立于中央管理存储的计算机上部署存档数据库。有关并置 Lync Server 2013 组件的详细信息，请参阅可支持性文档中的[Lync Server 2013 中支持的服务器并置](lync-server-2013-supported-server-collocation.md)。

每个数据库服务器必须运行支持的 SQL Server 版本。有关受支持版本的详细信息，请参阅规划文档中的[Lync Server 2013 中的存档技术要求](lync-server-2013-technical-requirements-for-archiving.md)。

您必须先设置 SQL Server 平台，然后才能部署和启用存档。如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。您稍后还可创建数据库（包括在安装过程中）。有关 SQL Server 的详细信息，请参阅 SQL Server 技术中心 ([http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0x804))。

> [!NOTE]  
> 确保 SQL Server 代理服务启动类型为“自动”，并且 SQL Server 代理服务正在针对容纳存档数据库的 SQL 实例运行，以便默认存档 SQL Server 维护作业在 SQL Server 代理服务的控制下按计划运行。



## 设置文件存储

存档使用您在设置前端池或 Standard Edition Server 时指定的 Lync Server 2013 文件共享。无法更改用于存档的文件共享。有关支持的文件存储系统的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md)。

