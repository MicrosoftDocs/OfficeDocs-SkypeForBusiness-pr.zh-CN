---
title: 删除前端池的 SQL Server 数据库
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a6aba3f084be6c40d5019af5da37f1a682f6eb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="82153-102">删除前端池的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="82153-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82153-103">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="82153-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="82153-104">删除 Microsoft Lync Server 2010 前端池或将池重新配置为使用其他数据库之后，可以删除托管池数据的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="82153-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="82153-105">使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="82153-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="82153-106">使用拓扑生成器删除 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="82153-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="82153-107">在 Lync Server 2013 前端服务器中，打开拓扑生成器并下载现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="82153-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="82153-108">在拓扑生成器中，依次导航到 "**共享组件**" 和 " **SQL server 存储**"，右键单击与已删除或重新配置的前端池关联的 SQL Server 实例，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="82153-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="82153-109">发布拓扑，然后检查复制状态。</span><span class="sxs-lookup"><span data-stu-id="82153-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="82153-110">从 SQL Server 中删除用户和应用程序数据库</span><span class="sxs-lookup"><span data-stu-id="82153-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="82153-111">若要删除 SQL Server 上的数据库，您必须是要从中删除数据库文件的 SQL Server 的 SQL Server sysadmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="82153-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="82153-112">打开 Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="82153-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="82153-113">若要删除池用户存储的数据库，请键入：</span><span class="sxs-lookup"><span data-stu-id="82153-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="82153-114">其中\<FQDN\>是数据库服务器的完全限定域名（FQDN）， \<实例\>是命名的数据库实例（如果定义了一个实例）。</span><span class="sxs-lookup"><span data-stu-id="82153-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="82153-115">若要删除池应用程序存储的数据库，请键入：</span><span class="sxs-lookup"><span data-stu-id="82153-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="82153-116">其中\<fqdn\>是数据库服务器的 fqdn， \<实例\>是命名的数据库实例（如果定义了一个实例）。</span><span class="sxs-lookup"><span data-stu-id="82153-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="82153-117">当 **Uninstall-CsDataBase** cmdlet 提示您确认操作时，请阅读信息，然后按 **Y**（或按 Enter 键）继续，或者如果您想要停止该 cmdlet（也就是，在出现错误的情况下），请按 **N**，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="82153-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

