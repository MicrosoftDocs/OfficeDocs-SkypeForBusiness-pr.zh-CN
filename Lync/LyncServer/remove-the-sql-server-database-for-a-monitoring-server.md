---
title: 删除监控服务器的 SQL Server 数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdb2888a6c3dc7cc5dd4e3b77b70310a405f607d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="bade2-102">删除监控服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="bade2-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bade2-103">_**主题上次修改时间:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="bade2-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="bade2-104">删除 Microsoft Lync Server 2010 监视服务器之后, 你可以删除托管了服务器数据的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="bade2-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="bade2-105">使用以下过程从拓扑生成器中删除定义, 然后从数据库服务器中删除数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="bade2-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="bade2-106">使用拓扑生成器删除 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="bade2-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="bade2-107">在 Lync Server 2013 前端服务器上, 打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="bade2-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="bade2-108">在拓扑生成器中, 导航到 "**共享组件**", 然后导航到 " **sql server 存储**", 右键单击与删除或重新配置的监视服务器相关联的 SQL server 实例, 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="bade2-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="bade2-109">发布拓扑, 然后检查复制状态。</span><span class="sxs-lookup"><span data-stu-id="bade2-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="bade2-110">从 SQL Server 中删除数据库文件</span><span class="sxs-lookup"><span data-stu-id="bade2-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="bade2-111">若要删除基于 SQL Server 的服务器上的数据库, 您必须是要从中删除数据库文件的 SQL Server 服务器的 SQL Server sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="bade2-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="bade2-112">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="bade2-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="bade2-113">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="bade2-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="bade2-114">其中\<FQDN\>是数据库服务器的完全限定的域名 (fqdn), \<实例\>是可选的命名数据库实例。</span><span class="sxs-lookup"><span data-stu-id="bade2-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="bade2-115">当**CsDataBase** cmdlet 提示你确认操作时, 请阅读信息, 然后按 " **Y** " (或按 enter) 继续操作, 或者按 N, 然后按 N, 然后按 N, 然后按**N** , 然后按 enter 以停止 cmdlet (也就是万一出现错误)。</span><span class="sxs-lookup"><span data-stu-id="bade2-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

