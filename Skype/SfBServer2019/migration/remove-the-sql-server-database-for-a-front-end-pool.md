---
title: 删除前端池的 SQL Server 数据库
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
description: 删除前端池或将池重新配置为使用其他数据库之后，可以删除承载池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753404"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="dea13-104">删除前端池的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="dea13-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="dea13-105">删除前端池或将池重新配置为使用其他数据库之后，可以删除承载池数据的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="dea13-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="dea13-106">使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="dea13-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="dea13-107">使用拓扑生成器删除 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="dea13-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="dea13-108">在 Skype for Business Server 2019 前端服务器中，打开拓扑生成器并下载现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="dea13-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="dea13-109">在拓扑生成器中，依次导航到 "**共享组件**" 和 " **SQL server 存储**"，右键单击与已删除或重新配置的前端池关联的 SQL Server 实例，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="dea13-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="dea13-110">发布拓扑，然后检查复制状态。</span><span class="sxs-lookup"><span data-stu-id="dea13-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="dea13-111">从 SQL server 中删除用户数据库和应用程序数据库</span><span class="sxs-lookup"><span data-stu-id="dea13-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="dea13-112">若要删除 SQL server 上的数据库，您必须是要在其中删除数据库文件的 SQL server 的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="dea13-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="dea13-113">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="dea13-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="dea13-114">若要删除池用户存储的数据库，请键入：</span><span class="sxs-lookup"><span data-stu-id="dea13-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="dea13-115">其中， _\<FQDN\>_ 是数据库服务器的完全限定的域名（FQDN）， _\<instance\>_ 是指定的数据库实例（如果定义了一个实例）。</span><span class="sxs-lookup"><span data-stu-id="dea13-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="dea13-116">若要删除池应用程序存储的数据库，请键入：</span><span class="sxs-lookup"><span data-stu-id="dea13-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="dea13-117">其中， _\<FQDN\>_ 是数据库服务器的 FQDN， _\<instance\>_ 是指定的数据库实例（如果定义了一个实例）。</span><span class="sxs-lookup"><span data-stu-id="dea13-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="dea13-118">当 CsDataBase cmdlet 提示您确认操作时，请阅读**相关**信息，然后按 "Y" （或 enter）继续，或者按 N，然后按 enter 以停止 cmdlet （如果有错误）。</span><span class="sxs-lookup"><span data-stu-id="dea13-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

