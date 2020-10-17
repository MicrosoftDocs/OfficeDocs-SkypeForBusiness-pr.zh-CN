---
title: 删除后端服务器上的 SQL Server 实例和数据库
description: 删除后端服务器上的 SQL Server 实例和数据库。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c87426a3496e6def2ad65775f5dadb1a0141ae3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551278"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>删除后端服务器上的 SQL Server 实例和数据库

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

删除依赖于这些服务器的运行 Lync Server 2010 的服务器后，或者在将运行 Lync Server 2010 的服务器重新配置为使用另一个数据库之后，删除这些服务器数据库和实例。 当您停用当前 SQL Server 或重新配置运行 Lync Server 2010 的当前服务器时，您需要执行本主题中的过程，以使其呈现数据库已过时或不可用。

若要删除存档服务器或监视服务器的数据库或实例，必须首先删除该服务器角色。 同样，若要删除前端池的实例或数据库，必须首先删除或重新配置相关的服务器角色。 在并置的数据库或单独的服务器实例之间，这些过程没有差别。 这些过程不受数据库并置的影响。

<div>

## <a name="in-this-section"></a>本部分内容

  - [删除前端池的 SQL Server 数据库](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [删除监控服务器的 SQL Server 数据库](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [删除存档服务器的 SQL Server 数据库](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

