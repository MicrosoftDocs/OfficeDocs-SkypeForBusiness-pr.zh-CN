---
title: 删除存档服务器的 SQL Server 数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 删除存档服务器后, 可以删除托管了池数据的 SQL Server 数据库。 使用以下过程从拓扑生成器中删除定义, 然后从数据库服务器中删除数据库和日志文件。
ms.openlocfilehash: 975252ee991df507f02bc490d1d2ef2614f3b475
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307103"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="e281e-104">删除存档服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="e281e-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="e281e-105">删除存档服务器后, 可以删除托管了池数据的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="e281e-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="e281e-106">使用以下过程从拓扑生成器中删除定义, 然后从数据库服务器中删除数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="e281e-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="e281e-107">使用拓扑生成器删除 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="e281e-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="e281e-108">在 Skype for Business 服务器2019前端服务器上, 打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="e281e-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="e281e-109">在拓扑生成器中, 导航到 "**共享组件**", 然后导航到 " **sql server 存储**", 右键单击与已删除或重新配置的存档服务器相关联的 SQL Server 实例, 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e281e-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="e281e-110">发布拓扑, 然后检查复制状态。</span><span class="sxs-lookup"><span data-stu-id="e281e-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="e281e-111">从 SQL Server 中删除数据库文件</span><span class="sxs-lookup"><span data-stu-id="e281e-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="e281e-112">若要删除 SQL Server 上的数据库, 您必须是要删除数据库文件的 SQL Server 的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="e281e-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="e281e-113">打开 Skype for Business 服务器命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="e281e-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="e281e-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e281e-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="e281e-115">其中_ \<FQDN\> _是数据库服务器的完全限定的域名 (fqdn), _ \<实例\> _是指定的数据库实例 (即, 如果定义了一个实例)。</span><span class="sxs-lookup"><span data-stu-id="e281e-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="e281e-116">当**CsDataBase** cmdlet 提示你确认操作时, 请阅读信息, 然后按 "Y" (或 enter) 继续操作, 或者按 N, 然后按 N, 然后按 enter 以停止 cmdlet (如果存在错误)。</span><span class="sxs-lookup"><span data-stu-id="e281e-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

