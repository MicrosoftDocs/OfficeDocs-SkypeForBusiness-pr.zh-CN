---
title: 删除存档服务器的 SQL Server 数据库
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 删除存档服务器后，您可以删除承载池数据的 SQL Server 数据库。 使用以下过程可从拓扑生成器中，删除定义，然后删除数据库服务器的数据库和日志文件。
ms.openlocfilehash: c82f718cf86de653f6c1340d38e21e96cbaa150d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027961"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="bcb05-104">删除存档服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="bcb05-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="bcb05-105">删除存档服务器后，您可以删除承载池数据的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="bcb05-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="bcb05-106">使用以下过程可从拓扑生成器中，删除定义，然后删除数据库服务器的数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="bcb05-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="bcb05-107">若要删除使用拓扑生成器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="bcb05-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="bcb05-108">在业务 Server 2019 前端服务器的 Skype，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="bcb05-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="bcb05-109">在拓扑生成器中，导航到**共享组件**，然后选择**SQL Server 存储**，右键单击 SQL Server 实例关联的已删除或重新配置存档服务器，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="bcb05-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="bcb05-110">发布拓扑，并检查复制状态。</span><span class="sxs-lookup"><span data-stu-id="bcb05-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="bcb05-111">若要从 SQL Server 中删除数据库文件</span><span class="sxs-lookup"><span data-stu-id="bcb05-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="bcb05-112">若要删除 SQL Server 上的数据库，您必须在其中删除数据库文件的 SQL Server 的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="bcb05-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="bcb05-113">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="bcb05-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="bcb05-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bcb05-114">At the command line, type the following:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="bcb05-115">其中_\<FQDN\>_ 是数据库服务器的完全限定的域名 (FQDN) 和_\<实例\>_ 是命名的数据库实例 （如果已定义）。</span><span class="sxs-lookup"><span data-stu-id="bcb05-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="bcb05-116">当**卸载 CsDataBase** cmdlet 提示您确认操作时，读取信息，并按 Y （或 Enter） 以继续，或按 N，然后按 Enter，如果您想要停止 cmdlet （如果有错误）。</span><span class="sxs-lookup"><span data-stu-id="bcb05-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

