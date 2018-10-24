---
title: 配置主管理服务器
TOCTitle: 配置主管理服务器
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204844(v=OCS.15)
ms:contentKeyID: 49312696
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置主管理服务器

 

_**上一次修改主题：** 2016-12-08_

若要充分利用 Microsoft Lync Server 2013 中包含的新的运行状况监控功能，管理员必须先指定一台计算机来用作主要管理服务器；然后，您必须在此计算机上安装 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。此外，必须安装 SQL Server 的受支持版本以用作 Operations Manager 后端数据库。如果使用的是 System Center Operations Manager 2012，则可将以下任一版本的 SQL Server 用作后端数据库：

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

如果使用的是 System Center Operations Manager 2007 R2，则建议您安装 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。还可以将 SQL Server 2008 R2 用作 System Center Operations Manager 2007 R2 的后端数据库。有关将 SQL Server 2008 R2 配置为使用 System Center Operations Manager 2007 R2 的详细信息，请参阅本文档的附录 1。

在安装 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 时，您需要安装此产品的所有组件，包括：

  - 操作数据库

  - 服务器

  - 控制台

  - Windows PowerShell cmdlet

  - Web 控制台

  - 报告

  - 数据仓库

本文档将不会详细讨论这些组件及其安装。有关 System Center Operations Manager 2007 R2 的详细信息，请参阅 Operations Manager 2007 R2 文档（网址为 [http://go.microsoft.com/fwlink/?linkid=257526\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=257526%26clcid=0x804)）和 System Center Operations Manager 2012 文档（网址为 [http://go.microsoft.com/fwlink/?linkid=257527\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=257527%26clcid=0x804)）。如果您打算将 SQL Server 2005 或 SQL Server 2008 Service Pack 1 用作后端数据库，则应按这些说明进行操作。

如果使用的是 System Center Operations Manager 2012，则可将 SQL Server 2012 用作后端数据库。有关 SQL Server 2012 的详细信息，请参阅 SQL Server 2012 联机丛书，网址为 [http://go.microsoft.com/fwlink/?linkid=257528\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=257528%26clcid=0x804)。

请记住，每个 Lync Server 部署只能包含一个主管理服务器。此外，在可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 时，将无法同时运行这两个应用程序 - 您必须选择二者之一。例如，如果您运行的是 System Center Operations Manager 2012，则所有 System Center 代理也必须运行 System Center Operations Manager 2012。您不能同时让一些代理运行 System Center Operations Manager 2012，另一些代理运行 System Center Operations Manager 2007 R2。

