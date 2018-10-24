---
title: Lync Server 2013：存档技术要求
TOCTitle: 存档技术要求
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205059(v=OCS.15)
ms:contentKeyID: 49313510
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的存档技术要求

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 的技术要求如下：

  - 基础结构要求。

  - 存档所必须安装的必备软件。

  - 存档的数据存储要求。

  - 存档部署的缩放要求和注意事项。

  - 存档数据库的性能要求和注意事项。

> [!NOTE]  
> 本 Lync Server 2013 版本中未提供缩放和性能信息。


## 基础结构要求

Lync Server 2013 的存档基础结构要求与 Lync Server 2013 的部署要求相同。有关详细信息，请参阅规划文档中的 [确定 Lync Server 2013 的基础结构要求](lync-server-2013-determining-your-infrastructure-requirements.md)。

## 存档必备组件

Lync Server 2013 简化了存档必备组件，原因如下：

  - 存档服务器不再是服务器角色。相反，统一数据收集代理在池中的前端服务器和 Standard Edition 服务器上运行以捕获存档数据，因此您无需针对存档设置单独的系统平台。

  - 存档使用 Lync Server 2013 文件存储临时存储会议内容文件，因此您无需针对存档设置单独的文件存储。

  - 在 Lync Server 2013 中，无需消息队列。

## 存档的数据存储要求

此外，您需要为存档存储设置基础结构。这包括以下一个或两个存储：

  - **Microsoft Exchange 存储**。会议内容文件（如 PowerPoint 演示文稿）将作为附件存档。如果您要使用 Microsoft Exchange 集成，以便将 Lync 存档数据与 Exchange 合规性数据存储在一起，则必须对 Exchange 部署使用 Exchange 2013 并确保最大存储大小支持会议内容文件的存储。如果使用 Microsoft Exchange 集成选项部署存档，则只有驻留在您的 Exchange 2013 服务器上的用户才可将 Lync 存档数据与 Exchange 2013 合规性数据存储在一起。您必须先部署 Exchange 2013，然后才能使用 Microsoft Exchange 集成选项部署和启用存档。如果选择使用 Exchange 2013 存储，则无需部署用于存档的单独 SQL Server 数据库，除非您有 Lync 用户不驻留在您的 Exchange 2013 服务器上。

  - **用于存档的 SQL Server 数据库存储**。若要支持不在 Exchange 2013 服务器上的用户，或者如果您不想使用 Microsoft Exchange 集成选项，则必须使用 SQL Server 数据库部署存档存储。 Lync Server 2013 支持以下 64 位版本的 SQL Server：
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    > [!NOTE]
    > Microsoft SQL Server 2008 R2 Express 和 Microsoft SQL Server 2012 Express 不支持存档。不支持 32 位版本的 SQL Server。有关其他 SQL Server 要求和限制，请参阅规划文档或可支持性文档中的 <a href="lync-server-2013-database-software-support.md">Lync Server 2013 中的数据库软件支持</a>。
    
    您必须先设置 SQL Server 平台，然后才能部署和启用存档。如果用于发布拓扑的帐户具有适当的管理员权限，则可在发布拓扑时创建存档数据库 (LcsLog)。您稍后还可创建数据库（包括在安装过程中）。有关 SQL Server 的详细信息，请参阅 SQL Server 技术中心 ( [http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0x804))。

