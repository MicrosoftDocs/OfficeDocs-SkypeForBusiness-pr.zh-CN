---
title: 删除监控服务器的 SQL Server 数据库
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
description: 删除监视服务器后，可以删除托管服务器数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753324"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="d1849-104">删除监控服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="d1849-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="d1849-105">删除监视服务器后，可以删除托管服务器数据的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="d1849-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="d1849-106">使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="d1849-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="d1849-107">使用拓扑生成器删除 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="d1849-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="d1849-108">在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="d1849-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="d1849-109">在拓扑生成器中，依次导航到 "**共享组件**" 和 " **SQL server 存储**"，右键单击与已删除或重新配置的监视服务器相关联的 SQL Server 实例，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="d1849-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="d1849-110">发布拓扑，然后检查复制状态。</span><span class="sxs-lookup"><span data-stu-id="d1849-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="d1849-111">从 SQL Server 中删除数据库文件</span><span class="sxs-lookup"><span data-stu-id="d1849-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="d1849-112">要删除基于 SQL Server 的服务器上的数据库，您必须是从其中删除数据库文件的 SQL Server 服务器的 SQL Server sysadmin 组成员。</span><span class="sxs-lookup"><span data-stu-id="d1849-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="d1849-113">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="d1849-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="d1849-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="d1849-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="d1849-115">其中， _\<FQDN\>_ 是数据库服务器的完全限定的域名（FQDN）， _\<instance\>_ 是可选的命名数据库实例。</span><span class="sxs-lookup"><span data-stu-id="d1849-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="d1849-116">当 CsDataBase cmdlet 提示您确认操作时，请阅读**相关**信息，然后按 "Y" （或 enter）继续，或者按 N，然后按 enter 以停止 cmdlet （如果有错误）。</span><span class="sxs-lookup"><span data-stu-id="d1849-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

