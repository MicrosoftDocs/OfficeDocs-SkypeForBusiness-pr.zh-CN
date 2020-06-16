---
title: 删除后端服务器上的 SQL Server 实例和数据库
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
ms.openlocfilehash: dbd5a681be1395038116be32b3267be07213af1b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="3f1ab-102">删除后端服务器上的 SQL Server 实例和数据库</span><span class="sxs-lookup"><span data-stu-id="3f1ab-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f1ab-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3f1ab-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3f1ab-104">删除依赖于这些服务器的运行 Lync Server 2010 的服务器后，或者在将运行 Lync Server 2010 的服务器重新配置为使用另一个数据库之后，删除这些服务器数据库和实例。</span><span class="sxs-lookup"><span data-stu-id="3f1ab-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="3f1ab-105">当您停用当前 SQL Server 或重新配置运行 Lync Server 2010 的当前服务器时，您需要执行本主题中的过程，以使其呈现数据库已过时或不可用。</span><span class="sxs-lookup"><span data-stu-id="3f1ab-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="3f1ab-106">若要删除存档服务器或监视服务器的数据库或实例，必须首先删除该服务器角色。</span><span class="sxs-lookup"><span data-stu-id="3f1ab-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="3f1ab-107">同样，若要删除前端池的实例或数据库，必须首先删除或重新配置相关的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="3f1ab-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="3f1ab-108">在并置的数据库或单独的服务器实例之间，这些过程没有差别。</span><span class="sxs-lookup"><span data-stu-id="3f1ab-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="3f1ab-109">这些过程不受数据库并置的影响。</span><span class="sxs-lookup"><span data-stu-id="3f1ab-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3f1ab-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="3f1ab-110">In This Section</span></span>

  - [<span data-ttu-id="3f1ab-111">删除前端池的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="3f1ab-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="3f1ab-112">删除监控服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="3f1ab-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="3f1ab-113">删除存档服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="3f1ab-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

