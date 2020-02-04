---
title: 删除后端服务器上的 SQL Server 实例和数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11439dd9fd339c3620b3e6288526459f45a2a542
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>删除后端服务器上的 SQL Server 实例和数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

删除依赖于这些服务器的运行 Lync Server 2010 的服务器后，或者在将运行 Lync Server 2010 的服务器重新配置为使用另一个数据库之后，删除 Microsoft SQL Server 数据库和实例。 如果你在终止当前 SQL Server 或以某种方式重新配置运行 Lync Server 2010 的当前服务器，以使数据库过时或不可用，则需要执行本主题中的过程。

若要删除存档服务器或监视服务器的数据库或实例，必须首先删除服务器角色。 同样，若要删除前端池的实例或数据库，必须首先删除或重新配置从属服务器角色。 这些过程不区分 collocated 数据库或服务器的单独实例。 数据库的 collocation 不会影响这些过程。

<div>

## <a name="in-this-section"></a>本节内容

  - [删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [删除监控服务器的 SQL Server 数据库](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [删除存档服务器的 SQL Server 数据库](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

