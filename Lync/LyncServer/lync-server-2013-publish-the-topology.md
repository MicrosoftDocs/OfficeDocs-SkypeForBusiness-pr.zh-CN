---
title: Lync Server 2013：发布拓扑
description: Lync Server 2013：发布拓扑。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453fe186a02c88a5dcd7308096b661058fc04aa6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547718"
---
# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="45de2-103">在 Lync Server 2013 中发布拓扑</span><span class="sxs-lookup"><span data-stu-id="45de2-103">Publish the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45de2-104">_**上次修改的主题：** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="45de2-104">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="45de2-105">若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="45de2-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="45de2-106">还有可能委派相应的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="45de2-106">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="45de2-107">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="45de2-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="45de2-108">对于其他配置更改，只需要 RTCUniversalServerAdmins 组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="45de2-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="45de2-109">在拓扑生成器中定义拓扑之后，必须将拓扑发布到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="45de2-109">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="45de2-110">中央管理存储为定义、设置、维护、管理、描述和运行 Lync Server 2013 部署所需的数据提供了一个强健的架构化存储。</span><span class="sxs-lookup"><span data-stu-id="45de2-110">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="45de2-111">它还会验证数据，以帮助确保配置的一致性。</span><span class="sxs-lookup"><span data-stu-id="45de2-111">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="45de2-112">对此配置数据所做的所有更改都将发生在中央管理存储中，从而消除了 "不同步" 问题。</span><span class="sxs-lookup"><span data-stu-id="45de2-112">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="45de2-113">数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="45de2-113">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="45de2-114">SQL Server 至少需要 20 GB 的可用磁盘空间，才能成功发布初始拓扑并创建中央管理服务器。</span><span class="sxs-lookup"><span data-stu-id="45de2-114">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="45de2-115">仅限 Enterprise Edition：为了发布该拓扑，基于 SQL Server 的后端服务器必须处于联机状态，并且可以通过启用的防火墙例外规则访问。</span><span class="sxs-lookup"><span data-stu-id="45de2-115">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="45de2-116">有关指定防火墙例外的详细信息，请参阅 <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">了解使用 Lync server 2013 的 SQL Server 的防火墙要求</A>。</span><span class="sxs-lookup"><span data-stu-id="45de2-116">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="45de2-117">有关配置 SQL Server 的详细信息，请参阅 <A href="lync-server-2013-configure-sql-server-for-lync-server.md">CONFIGURE SQL server For Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="45de2-117">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="45de2-118">发布拓扑</span><span class="sxs-lookup"><span data-stu-id="45de2-118">To publish a topology</span></span>

1.  <span data-ttu-id="45de2-119">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="45de2-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="45de2-p104">选择从本地文件打开拓扑。如果位于定义拓扑的计算机上，则将位于前面步骤中所保存的位置。通常，这是配置该拓扑的用户的“文档”文件夹。</span><span class="sxs-lookup"><span data-stu-id="45de2-p104">Select to open the topology from a local file. If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps. Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="45de2-123">右键单击 " **Lync Server 2013** " 节点，然后单击 " **发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="45de2-123">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="45de2-124">在“发布拓扑”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de2-124">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="45de2-125">在“创建数据库”\*\*\*\* 页上，选择要发布的数据库。</span><span class="sxs-lookup"><span data-stu-id="45de2-125">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45de2-126">如果您没有创建数据库的相应权限，可以清除这些数据库旁边的复选框，稍后可以由具有相应权限的用户创建数据库。</span><span class="sxs-lookup"><span data-stu-id="45de2-126">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="45de2-127">有关详细信息，请参阅 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中的 SQL Server 部署权限</A>。</span><span class="sxs-lookup"><span data-stu-id="45de2-127">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="45de2-128">也可以单击“高级”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de2-128">Optionally click **Advanced**.</span></span> <span data-ttu-id="45de2-129">通过 "高级 SQL Server 数据文件放置" 选项，您可以在以下选项之间进行选择：</span><span class="sxs-lookup"><span data-stu-id="45de2-129">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="45de2-130">**自动确定数据库文件位置** – 此选项将通过向最佳位置分发日志和数据文件，根据基于 SQL Server 的服务器上的磁盘配置确定最佳运行性能。</span><span class="sxs-lookup"><span data-stu-id="45de2-130">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="45de2-p107">**使用 SQL Server 实例默认值** – 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。</span><span class="sxs-lookup"><span data-stu-id="45de2-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="45de2-134">单击“确定”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de2-134">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="45de2-135">在 " **选择中央管理服务器** " 页上，选择一个前端池。</span><span class="sxs-lookup"><span data-stu-id="45de2-135">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="45de2-136">也可以单击“高级”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de2-136">Optionally click **Advanced**.</span></span> <span data-ttu-id="45de2-137">利用 "高级 SQL Server 数据文件放置" 选项，您可以在以下选项之间进行选择：</span><span class="sxs-lookup"><span data-stu-id="45de2-137">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="45de2-138">**自动确定数据库文件位置** – 此选项将通过向最佳位置分发日志和数据文件，根据基于 SQL Server 的服务器上的磁盘配置确定最佳运行性能。</span><span class="sxs-lookup"><span data-stu-id="45de2-138">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="45de2-p109">**使用 SQL Server 实例默认值** – 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。</span><span class="sxs-lookup"><span data-stu-id="45de2-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="45de2-142">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de2-142">Click **OK**.</span></span>

9.  <span data-ttu-id="45de2-143">单击“下一步”\*\*\*\* 完成发布过程。</span><span class="sxs-lookup"><span data-stu-id="45de2-143">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="45de2-144">发布过程完成后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de2-144">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="45de2-145">成功发布拓扑后，您可以开始在拓扑中运行 Lync Server 2013 的每台服务器上安装中央管理存储的本地副本。</span><span class="sxs-lookup"><span data-stu-id="45de2-145">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="45de2-146">我们建议您从第一个前端池开始。</span><span class="sxs-lookup"><span data-stu-id="45de2-146">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="45de2-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45de2-147">See Also</span></span>


[<span data-ttu-id="45de2-148">为 Lync Server 2013 设置前端服务器和前端池</span><span class="sxs-lookup"><span data-stu-id="45de2-148">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

