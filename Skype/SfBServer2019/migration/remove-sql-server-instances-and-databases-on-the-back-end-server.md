---
title: 删除后端服务器上的 SQL Server 实例和数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您删除的 Microsoft SQL Server 数据库和实例后删除的服务器运行的是相关的用户、 或之后重新配置为使用另一个数据库的服务器。 您需要执行本主题中的步骤，停用当前的 SQL Server 或重新配置当前服务器的方式，它将呈现数据库已过时或不可用时。
ms.openlocfilehash: 531d4c06daa7dacd2a616244c13207b3e79dca4c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898738"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="c9f54-104">删除后端服务器上的 SQL Server 实例和数据库</span><span class="sxs-lookup"><span data-stu-id="c9f54-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="c9f54-105">您删除的 Microsoft SQL Server 数据库和实例后删除的服务器运行的是相关的用户、 或之后重新配置为使用另一个数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="c9f54-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="c9f54-106">您需要执行本主题中的步骤，停用当前的 SQL Server 或重新配置当前服务器的方式，它将呈现数据库已过时或不可用时。</span><span class="sxs-lookup"><span data-stu-id="c9f54-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="c9f54-107">若要删除的存档服务器或监控服务器数据库或实例，必须首先删除服务器角色。</span><span class="sxs-lookup"><span data-stu-id="c9f54-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="c9f54-108">同样，若要删除的实例或前端池数据库，必须首先删除或重新配置相关的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="c9f54-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="c9f54-109">这些过程的服务器都并置的数据库或单独实例之间没有区别。</span><span class="sxs-lookup"><span data-stu-id="c9f54-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="c9f54-110">过程不受数据库并置。</span><span class="sxs-lookup"><span data-stu-id="c9f54-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c9f54-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="c9f54-111">In this section</span></span>

- [<span data-ttu-id="c9f54-112">删除前端池的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="c9f54-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="c9f54-113">删除监控服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="c9f54-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="c9f54-114">删除存档服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="c9f54-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

