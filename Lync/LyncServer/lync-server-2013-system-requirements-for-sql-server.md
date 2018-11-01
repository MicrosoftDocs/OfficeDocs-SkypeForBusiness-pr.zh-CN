---
title: Lync Server 2013：SQL Server 的系统要求
TOCTitle: SQL Server 的系统要求
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205112(v=OCS.15)
ms:contentKeyID: 49313724
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中 SQL Server 的系统要求

 

_**上一次修改主题：** 2013-10-25_

部署 Enterprise Edition 服务器之前，在满足硬件要求的专用计算机上安装 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012。有关硬件要求的详细信息，请参阅可支持性文档中的[适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。有关软件要求的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。有关部署必需的权限的信息，请参阅[Lync Server 2013 中 SQL Server 的部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。

创建前端池之前，您还必须将 Windows 防火墙配置为允许 Lync Server 2013 通过特定端口访问 SQL Server，方式为使用 SQL Server 配置管理器为服务器定义端口并在高级安全 Windows 防火墙中打开端口。

