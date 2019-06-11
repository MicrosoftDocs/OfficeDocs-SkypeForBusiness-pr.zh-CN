---
title: Lync Server 2013：发布拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fee3b14776c6cdf6ddd52ada724d3d4a6d6a245a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="32e62-102">在 Lync Server 2013 中发布拓扑</span><span class="sxs-lookup"><span data-stu-id="32e62-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32e62-103">_**主题上次修改时间:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="32e62-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="32e62-104">若要在添加或删除服务器角色时成功发布、启用或禁用拓扑, 您应作为 RTCUniversalServerAdmins 和域管理员组成员的用户登录。</span><span class="sxs-lookup"><span data-stu-id="32e62-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="32e62-105">也可以委派正确的管理员权利和权限。</span><span class="sxs-lookup"><span data-stu-id="32e62-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="32e62-106">有关详细信息, 请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="32e62-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="32e62-107">对于其他配置更改, 仅需要 RTCUniversalServerAdmins 组中的成员身份。</span><span class="sxs-lookup"><span data-stu-id="32e62-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="32e62-108">在拓扑生成器中定义拓扑后, 必须将拓扑发布到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="32e62-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="32e62-109">中央管理存储为定义、设置、维护、管理、描述和操作 Lync Server 2013 部署所需的数据提供可靠的 schematized 存储。</span><span class="sxs-lookup"><span data-stu-id="32e62-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="32e62-110">它还会验证数据, 以帮助确保配置一致性。</span><span class="sxs-lookup"><span data-stu-id="32e62-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="32e62-111">对此配置数据的所有更改都在中央管理存储上进行，这可以消除“不同步”问题。</span><span class="sxs-lookup"><span data-stu-id="32e62-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="32e62-112">数据的只读副本将复制到拓扑中的所有服务器, 包括边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="32e62-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32e62-113">SQL Server 至少需要 20 GB 的可用磁盘空间, 才能成功发布初始拓扑并创建中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="32e62-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="32e62-114">仅适用于企业版: 为了发布拓扑, 基于 SQL Server 的后端服务器必须处于联机状态, 并且存在防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="32e62-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="32e62-115">有关指定防火墙例外的详细信息, 请参阅<A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">了解适用于 Lync server 2013 的 SQL Server 的防火墙要求</A>。</span><span class="sxs-lookup"><span data-stu-id="32e62-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="32e62-116">有关配置 SQL Server 的详细信息, 请参阅<A href="lync-server-2013-configure-sql-server-for-lync-server.md">配置 Lync server 2013 的 SQL Server</A>。</span><span class="sxs-lookup"><span data-stu-id="32e62-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="32e62-117">发布拓扑</span><span class="sxs-lookup"><span data-stu-id="32e62-117">To publish a topology</span></span>

1.  <span data-ttu-id="32e62-118">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="32e62-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="32e62-119">选择以从本地文件中打开拓扑。</span><span class="sxs-lookup"><span data-stu-id="32e62-119">Select to open the topology from a local file.</span></span> <span data-ttu-id="32e62-120">如果您在定义拓扑的计算机上, 该位置将位于您在前面的步骤中保存它的位置。</span><span class="sxs-lookup"><span data-stu-id="32e62-120">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="32e62-121">通常, 这将是配置了拓扑的用户的 "文档" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="32e62-121">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="32e62-122">右键单击 " **Lync Server 2013** " 节点, 然后单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="32e62-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="32e62-123">在“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="32e62-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="32e62-124">在 "**创建数据库**" 页面上, 选择要发布的数据库。</span><span class="sxs-lookup"><span data-stu-id="32e62-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32e62-125">如果你没有创建数据库的相应权限，可以清除这些数据库旁边的复选框，稍后可以由具有相应权限的用户创建数据库。</span><span class="sxs-lookup"><span data-stu-id="32e62-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="32e62-126">有关详细信息, 请参阅<A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署权限</A>。</span><span class="sxs-lookup"><span data-stu-id="32e62-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="32e62-127">也可以单击“**高级**”。</span><span class="sxs-lookup"><span data-stu-id="32e62-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="32e62-128">高级 SQL Server 数据文件放置选项使你可以在以下选项之间进行选择:</span><span class="sxs-lookup"><span data-stu-id="32e62-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="32e62-129">**自动确定数据库文件位置**-此选项通过将日志和数据文件分发到最佳位置, 基于基于 SQL server 的服务器上的磁盘配置确定最佳操作性能。</span><span class="sxs-lookup"><span data-stu-id="32e62-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="32e62-p107">**使用 SQL Server 实例默认值** - 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。</span><span class="sxs-lookup"><span data-stu-id="32e62-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="32e62-133">单击“**确定**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="32e62-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="32e62-134">在 "**选择中央管理服务器**" 页面上, 选择 "前端池"。</span><span class="sxs-lookup"><span data-stu-id="32e62-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="32e62-135">也可以单击“**高级**”。</span><span class="sxs-lookup"><span data-stu-id="32e62-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="32e62-136">高级 SQL Server 数据文件放置选项使你可以选择以下选项:</span><span class="sxs-lookup"><span data-stu-id="32e62-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="32e62-137">**自动确定数据库文件位置**-此选项通过将日志和数据文件分发到最佳位置, 基于基于 SQL server 的服务器上的磁盘配置确定最佳操作性能。</span><span class="sxs-lookup"><span data-stu-id="32e62-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="32e62-p109">**使用 SQL Server 实例默认值** - 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。</span><span class="sxs-lookup"><span data-stu-id="32e62-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="32e62-141">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="32e62-141">Click **OK**.</span></span>

9.  <span data-ttu-id="32e62-142">单击“**下一步**”完成发布过程。</span><span class="sxs-lookup"><span data-stu-id="32e62-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="32e62-143">发布过程完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="32e62-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="32e62-144">成功发布拓扑后, 你可以开始在拓扑中运行 Lync Server 2013 的每台服务器上安装中央管理存储的本地副本。</span><span class="sxs-lookup"><span data-stu-id="32e62-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="32e62-145">我们建议您从第一个前端池开始。</span><span class="sxs-lookup"><span data-stu-id="32e62-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32e62-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32e62-146">See Also</span></span>


[<span data-ttu-id="32e62-147">为 Lync Server 2013 设置前端服务器和前端池</span><span class="sxs-lookup"><span data-stu-id="32e62-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

