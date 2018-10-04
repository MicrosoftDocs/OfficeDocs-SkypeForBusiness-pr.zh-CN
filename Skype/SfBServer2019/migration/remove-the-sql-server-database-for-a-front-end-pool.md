---
title: 删除前端池的 SQL Server 数据库
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 删除前端池或重新配置要使用不同的数据库的池后，您可以删除承载池数据的 SQL Server 数据库。 使用以下过程可从拓扑生成器中，删除定义，然后删除数据库服务器的数据库和日志文件。
ms.openlocfilehash: 35c9429fc16aef886945f8b0adcd5894ce40b834
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373124"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="c3fd6-104">删除前端池的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="c3fd6-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="c3fd6-105">删除前端池或重新配置要使用不同的数据库的池后，您可以删除承载池数据的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="c3fd6-106">使用以下过程可从拓扑生成器中，删除定义，然后删除数据库服务器的数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="c3fd6-107">若要删除使用拓扑生成器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="c3fd6-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="c3fd6-108">从业务 Server 2019 前端服务器的 Skype，打开拓扑生成器并下载现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="c3fd6-109">在拓扑生成器中，导航到**共享组件**，然后选择**SQL Server 存储**，右键单击与已删除的或重新配置前端池关联的 SQL Server 实例，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="c3fd6-110">发布拓扑，，然后检查复制状态。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="c3fd6-111">若要从 SQL server 中删除用户和应用程序数据库</span><span class="sxs-lookup"><span data-stu-id="c3fd6-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="c3fd6-112">若要删除 SQL server 上的数据库，您必须在其中删除数据库文件的 SQL server 的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="c3fd6-113">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="c3fd6-114">若要删除池用户存储的数据库，请键入：</span><span class="sxs-lookup"><span data-stu-id="c3fd6-114">To remove the database for the pool user store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="c3fd6-115">其中_\<FQDN\>_ 是数据库服务器的完全限定的域名 (FQDN) 和_\<实例\>_ 是命名的数据库实例 （如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="c3fd6-116">若要删除池应用程序存储的数据库，请键入：</span><span class="sxs-lookup"><span data-stu-id="c3fd6-116">To remove the database for the pool application store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="c3fd6-117">其中_\<FQDN\>_ 是数据库服务器的 FQDN 和_\<实例\>_ 是命名的数据库实例 （如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="c3fd6-118">当**卸载 CsDataBase** cmdlet 提示您确认操作时，读取信息，并按 Y （或 Enter） 以继续，或按 N，然后按 Enter，如果您想要停止 cmdlet （如果有错误）。</span><span class="sxs-lookup"><span data-stu-id="c3fd6-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

