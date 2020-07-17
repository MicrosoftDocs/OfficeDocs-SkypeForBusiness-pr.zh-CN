---
title: 删除存档服务器的 SQL Server 数据库
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c84c15aea6be5ddcc30c357fec5971bf9786c25
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="3e33d-102">删除存档服务器的 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="3e33d-102">Remove the SQL Server database for an Archiving server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e33d-103">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3e33d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3e33d-104">删除 Microsoft Lync Server 2010 存档服务器后，可以删除托管池数据的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="3e33d-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="3e33d-105">使用以下过程从拓扑生成器中删除定义，然后从数据库服务器中删除数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="3e33d-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="3e33d-106">使用拓扑生成器删除 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="3e33d-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="3e33d-107">在 Lync Server 2013 前端服务器上，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="3e33d-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="3e33d-108">在拓扑生成器中，依次导航到 "**共享组件**" 和 " **SQL server 存储**"，右键单击与已删除或重新配置的存档服务器关联的 SQL Server 实例，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="3e33d-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="3e33d-109">发布拓扑，然后检查复制状态。</span><span class="sxs-lookup"><span data-stu-id="3e33d-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="3e33d-110">从 SQL Server 中删除数据库文件</span><span class="sxs-lookup"><span data-stu-id="3e33d-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="3e33d-111">若要删除 SQL Server 上的数据库，您必须是要从中删除数据库文件的 SQL Server 的 SQL Server sysadmins 组的成员。
</span><span class="sxs-lookup"><span data-stu-id="3e33d-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="3e33d-112">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="3e33d-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="3e33d-113">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="3e33d-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="3e33d-114">其中， \<FQDN\> 是数据库服务器的完全限定的域名（FQDN）， \<instance\> 是指定的数据库实例（如果定义了一个实例）。</span><span class="sxs-lookup"><span data-stu-id="3e33d-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="3e33d-115">当 **Uninstall-CsDataBase** cmdlet 提示您确认操作时，请阅读信息，然后按 **Y**（或按 Enter 键）继续，或者如果您想要停止该 cmdlet（也就是，在出现错误的情况下），请按 **N**，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="3e33d-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

