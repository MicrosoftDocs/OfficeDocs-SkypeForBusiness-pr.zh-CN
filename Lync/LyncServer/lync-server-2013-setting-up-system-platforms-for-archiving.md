---
title: 为存档设置系统平台
TOCTitle: 为存档设置系统平台
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204768(v=OCS.15)
ms:contentKeyID: 49312363
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为存档设置系统平台

 

_**上一次修改主题：** 2012-10-09_

在开始部署存档之前，您必须在满足系统要求的硬件上安装必要的操作系统以及任何其他必备软件：

  - **Lync Server 2013 平台**   Lync Server 2013 部署不使用存档服务器。但是，统一数据收集代理会在前端服务器和 Standard Edition 服务器上运行以捕获要存档的数据，所以不需要单独的系统平台来承载存档功能。

  - **数据存储平台**   在 Lync Server 2013 中，您可以使用以下任一种方式存储数据：
    
      - **Microsoft Exchange 集成**   如果您要使用 Exchange 2013 部署存储 Lync Server 2013 存档数据，那么除了设置一个单独的数据库用于存储存档数据外，您的 Exchange 部署还必须运行 Exchange 2013。有关为 Exchange 2013 设置系统平台的详细信息，请参阅 Exchange 产品文档。
    
      - **SQL Server** 如果您要使用单独的 SQL Server 数据库存储存档数据，那么除使用 Microsoft Exchange 集成外，您还必须在部署存档之前为数据库设置系统平台。具体的系统平台要求取决于您是将 Microsoft SQL Server 2008 R2 还是将 Microsoft SQL Server 2012 用于存档数据库。有关为这些数据库设置系统平台的详细信息，请参阅 Microsoft SQL Server 2008 R2 和 Microsoft SQL Server 2012 产品文档。

  - **文件服务器平台**   Lync Server 2013 在您设置前端服务器或 Standard Edition 服务器时为文件存储指定的相同位置存储 Lync Server 存档文件。您无法为存档文件存储指定其他位置，所以不需要单独的系统平台存档文件存储。如果您使用 Microsoft Exchange 集成，那么对于驻留在 Exchange 服务器上的用户，会将存档的 Lync 通信的 Exchange 2013 文件存储在这些 Exchange 2013 服务器上。

