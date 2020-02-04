---
title: Lync Server 2013：为 Lync Server 配置 SQL Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efdd9d8fa7b010b420c7c532d422c9b52b6d69ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>为 Lync Server 2013 配置 SQL Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-08-12_

本部分中的主题讨论如何部署和配置 SQL Server 以在 Lync Server 的企业部署中使用。 标准版服务器使用 collocated SQL server Express 版本的 SQL Server Express 版本，该版本适合于标准版服务器的工作负荷。

Lync Server 2013 中央管理存储为池中的所有企业版服务器保留用户数据，并且设计为位于基于 SQL Server 的后端服务器上。 作为集中的存储库，中央管理存储无法与任何其他 Lync Server 2013 角色安装在同一台计算机上。 中央管理存储不能驻留在池中的企业版服务器上。 第一次发布拓扑并选择创建数据库时，将自动创建中央管理存储。 指定为后端服务器的计算机必须已运行 SQL Server 数据库软件，才能成功安装。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 的 SQL Server 数据和日志文件放置](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [在 Lync Server 2013 中配置 SQL Server](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013 中 SQL Server 的部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [在 Lync Server 2013 中使用 Lync Server 命令行管理程序安装数据库](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [了解 SQL Server 与 Lync Server 2013 一起使用时的防火墙要求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [配置 Lync Server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

