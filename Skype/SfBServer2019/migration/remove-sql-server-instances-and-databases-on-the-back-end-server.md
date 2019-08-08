---
title: 删除后端服务器上的 SQL Server 实例和数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 删除依赖于这些数据库的服务器或在将服务器重新配置为使用另一个数据库之后, 将删除该 Microsoft SQL Server 数据库和实例。 当你注销当前 SQL Server 或重新配置当前服务器时, 你需要执行本主题中的过程, 使其呈现数据库过时或不可用。
ms.openlocfilehash: 6c526499e3036c9a10b8dc92ccc519f21ae8bc96
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244199"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="299aa-104">删除后端服务器上的 SQL Server 实例和数据库</span><span class="sxs-lookup"><span data-stu-id="299aa-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="299aa-105">删除依赖于这些数据库的服务器或在将服务器重新配置为使用另一个数据库之后, 将删除该 Microsoft SQL Server 数据库和实例。</span><span class="sxs-lookup"><span data-stu-id="299aa-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="299aa-106">当你注销当前 SQL Server 或重新配置当前服务器时, 你需要执行本主题中的过程, 使其呈现数据库过时或不可用。</span><span class="sxs-lookup"><span data-stu-id="299aa-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="299aa-107">若要删除存档服务器或监视服务器的数据库或实例, 必须首先删除服务器角色。</span><span class="sxs-lookup"><span data-stu-id="299aa-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="299aa-108">同样, 若要删除前端池的实例或数据库, 必须首先删除或重新配置从属服务器角色。</span><span class="sxs-lookup"><span data-stu-id="299aa-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="299aa-109">这些过程不区分 collocated 数据库或服务器的单独实例。</span><span class="sxs-lookup"><span data-stu-id="299aa-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="299aa-110">数据库的 collocation 不会影响这些过程。</span><span class="sxs-lookup"><span data-stu-id="299aa-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="299aa-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="299aa-111">In this section</span></span>

- [<span data-ttu-id="299aa-112">删除前端池的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="299aa-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="299aa-113">删除监控服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="299aa-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="299aa-114">删除存档服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="299aa-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

