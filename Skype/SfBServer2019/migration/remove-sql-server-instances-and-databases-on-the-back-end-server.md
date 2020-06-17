---
title: 删除后端服务器上的 SQL Server 实例和数据库
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 删除依赖于这些数据库和实例的服务器，或者在将服务器重新配置为使用另一个数据库之后，删除这些服务器数据库和实例。 当您停用当前 SQL Server 或重新配置当前服务器时，您需要执行本主题中的过程，使其呈现数据库已过时或不可用。
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752154"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="84a9f-104">删除后端服务器上的 SQL Server 实例和数据库</span><span class="sxs-lookup"><span data-stu-id="84a9f-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="84a9f-105">删除依赖于这些数据库和实例的服务器，或者在将服务器重新配置为使用另一个数据库之后，删除这些服务器数据库和实例。</span><span class="sxs-lookup"><span data-stu-id="84a9f-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="84a9f-106">当您停用当前 SQL Server 或重新配置当前服务器时，您需要执行本主题中的过程，使其呈现数据库已过时或不可用。</span><span class="sxs-lookup"><span data-stu-id="84a9f-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="84a9f-107">若要删除存档服务器或监视服务器的数据库或实例，必须首先删除该服务器角色。</span><span class="sxs-lookup"><span data-stu-id="84a9f-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="84a9f-108">同样，若要删除前端池的实例或数据库，必须首先删除或重新配置相关的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="84a9f-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="84a9f-109">在并置的数据库或单独的服务器实例之间，这些过程没有差别。</span><span class="sxs-lookup"><span data-stu-id="84a9f-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="84a9f-110">这些过程不受数据库并置的影响。</span><span class="sxs-lookup"><span data-stu-id="84a9f-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="84a9f-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="84a9f-111">In this section</span></span>

- [<span data-ttu-id="84a9f-112">删除前端池的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="84a9f-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="84a9f-113">删除监控服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="84a9f-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="84a9f-114">删除存档服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="84a9f-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

