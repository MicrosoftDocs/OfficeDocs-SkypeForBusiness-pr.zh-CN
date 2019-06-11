---
title: Lync Server 2013：向拓扑添加持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8985ee2fd28a81f3630e4f80c0ac4dd5a23d4475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="20b4e-102">在 Lync Server 2013 中向拓扑添加持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="20b4e-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20b4e-103">_**主题上次修改时间:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="20b4e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="20b4e-104">你必须将 Lync Server 2013 和拓扑中的持久聊天服务器支持合并到你的拓扑中, 然后才能配置你的部署以支持永久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="20b4e-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="20b4e-105">本主题中的信息介绍了如何使用拓扑生成器将持久聊天服务器支持添加到现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="20b4e-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="20b4e-106">将持久聊天服务器添加到拓扑</span><span class="sxs-lookup"><span data-stu-id="20b4e-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="20b4e-107">若要在不使用灾难恢复配置的情况下安装单个持久聊天服务器池, 请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="20b4e-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="20b4e-108">有关为高可用性和灾难恢复配置延长的持久聊天服务器池, 请参阅在部署文档中[为 Lync server 2013 中的高可用性和灾难恢复配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="20b4e-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="20b4e-109">若要部署多个持久聊天服务器池, 请为每个池重复相同的过程。</span><span class="sxs-lookup"><span data-stu-id="20b4e-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="20b4e-110">在运行 Lync Server 2013 或安装了 Lync Server 管理工具的计算机上, 使用作为本地用户组成员的帐户 (或具有等效用户权限的帐户) 登录。</span><span class="sxs-lookup"><span data-stu-id="20b4e-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="20b4e-111">你可以通过使用属于本地用户组的成员的帐户定义拓扑, 但要发布安装 Lync Server 2013 服务器所需的拓扑, 你必须使用<STRONG>域管理员</STRONG>组和 RTCUniversalS 的成员帐户。 <STRONG>erverAdmins</STRONG>组, 并且具有对永久聊天服务器文件存储中使用的文件存储的完全控制权限 (即读取、写入和修改), 以便拓扑生成器可以配置所需的 dacl, 或帐户具有等效权利。</span><span class="sxs-lookup"><span data-stu-id="20b4e-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="20b4e-112">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="20b4e-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="20b4e-113">在控制台树中, 导航到 "**持久聊天池**" 节点并展开它以选择持久聊天服务器池, 或者右键单击该节点, 然后选择 "**新建持久聊天池**"。</span><span class="sxs-lookup"><span data-stu-id="20b4e-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="20b4e-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span><span class="sxs-lookup"><span data-stu-id="20b4e-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="20b4e-115">您可选择“**多计算机池**”或“**单计算机池**”。</span><span class="sxs-lookup"><span data-stu-id="20b4e-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="20b4e-116">如果计划在持久聊天服务器池中安装多台持久聊天服务器前端服务器, 请选择前者。</span><span class="sxs-lookup"><span data-stu-id="20b4e-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="20b4e-117">现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="20b4e-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="20b4e-118">如果您选择多台计算机池, 请输入组成池的单个持久聊天服务器前端服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="20b4e-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="20b4e-119">如果在 Lync Server 2013&nbsp;标准版服务器上安装持久聊天服务器角色, FQDN 需要与标准版服务器的 fqdn 相匹配。</span><span class="sxs-lookup"><span data-stu-id="20b4e-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="20b4e-120">为持久聊天服务器池定义一个简单的**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="20b4e-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="20b4e-121">显示名称可由自定义客户端使用, 尤其是当存在多个持久聊天服务器池时, 可以使用它们来区分房间。</span><span class="sxs-lookup"><span data-stu-id="20b4e-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="20b4e-122">定义持久聊天服务器用于与 Lync Server 前端服务器通信的端口。</span><span class="sxs-lookup"><span data-stu-id="20b4e-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="20b4e-123">默认端口为 5041。</span><span class="sxs-lookup"><span data-stu-id="20b4e-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="20b4e-124">如果您的组织需要合规性支持，请选中“**启用合规性**”复选框。</span><span class="sxs-lookup"><span data-stu-id="20b4e-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="20b4e-125">如果选择此项, 持久聊天服务器合规性服务将与持久聊天服务器前端服务器安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="20b4e-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="20b4e-126">系统将提示你选择 SQL Server 后端服务器, 以便在以后持续聊天服务器合规性。</span><span class="sxs-lookup"><span data-stu-id="20b4e-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="20b4e-127">为持久聊天服务器池分配网站相关性。</span><span class="sxs-lookup"><span data-stu-id="20b4e-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="20b4e-128">选中 "**将此池用作网站\<的 SiteName\>默认值**" 复选框, 或**将此池用作所有网站的默认值**将此持久聊天服务器池指定为当前网站或所有网站的默认池。</span><span class="sxs-lookup"><span data-stu-id="20b4e-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="20b4e-129">当 Lync 2013 客户端用于创建和管理会议室时, 聊天室创建和管理体验将使用与用户的网站关联的默认池, 以便它可以将会议室创建和管理操作路由到该池。</span><span class="sxs-lookup"><span data-stu-id="20b4e-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="20b4e-130">这仅适用于已部署多个持久聊天服务器池的情况, 并且希望使用持久聊天服务器的聊天室创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="20b4e-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="20b4e-131">可以使用持久聊天服务器软件开发工具包 (SDK) 自定义聊天室创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="20b4e-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="20b4e-132">有关如何为灾难恢复配置 SQL Server 备份数据库的详细信息, 请参阅在部署文档中将<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">持久聊天服务器配置为适用于 Lync server 2013 的高可用性和灾难恢复</A>。</span><span class="sxs-lookup"><span data-stu-id="20b4e-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="20b4e-133">通过执行下列操作之一, 定义**持久聊天服务器后端的 SQL 应用商店 (存储聊天室内容)** :</span><span class="sxs-lookup"><span data-stu-id="20b4e-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="20b4e-134">若要使用现有 SQL Server 数据库, 请在下拉列表中单击要使用的 SQL Server 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="20b4e-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="20b4e-135">若要指定新的 SQL Server 数据库, 请单击 "**新建**", 然后在 "**定义新的 SQL 存储**" 中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="20b4e-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="20b4e-136">在**SQL SERVER FQDN**中, 指定要在其上创建新的 sql server 数据库的 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="20b4e-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="20b4e-137">选择“**默认实例**”以使用默认实例，或指定其他实例，选择“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="20b4e-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="20b4e-138">如果已启用合规性, 请定义 SQL Server 合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="20b4e-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="20b4e-139">有关如何将 SQL Server 镜像配置为持久聊天服务器数据库和持久聊天服务器合规性数据库的高可用性的详细信息, 请参阅<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">在 Lync 中配置持久聊天服务器以实现高可用性和灾难恢复</A>部署文档中的服务器2013。</span><span class="sxs-lookup"><span data-stu-id="20b4e-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="20b4e-140">定义文件存储。</span><span class="sxs-lookup"><span data-stu-id="20b4e-140">Define the file store.</span></span> <span data-ttu-id="20b4e-141">文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。</span><span class="sxs-lookup"><span data-stu-id="20b4e-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="20b4e-142">在多服务器持久聊天服务器拓扑的情况下, 这必须是通用命名约定 (UNC) 路径;对于单服务器持久聊天服务器拓扑, 它可以是本地文件路径。</span><span class="sxs-lookup"><span data-stu-id="20b4e-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="20b4e-143">若要使用现有文件存储，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="20b4e-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="20b4e-144">在 "**文件服务器 FQDN**" 中, 指定要在其中创建新文件存储的文件存储的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="20b4e-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="20b4e-145">在“**文件共享**”中，指定要使用的文件存储。</span><span class="sxs-lookup"><span data-stu-id="20b4e-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="20b4e-146">你可以在创建文件存储之前在拓扑生成器中定义文件存储, 但你必须在发布拓扑之前在定义的位置创建文件存储。</span><span class="sxs-lookup"><span data-stu-id="20b4e-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="20b4e-147">选择要用作此持久聊天服务器池的下一跃点的前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="20b4e-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="20b4e-148">这是可以将持久聊天服务器请求路由到此池的前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="20b4e-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="20b4e-149">若要保存配置，请单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="20b4e-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="20b4e-150">持久聊天服务器池显示在拓扑生成器中, 附带你的特定池设置。</span><span class="sxs-lookup"><span data-stu-id="20b4e-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="20b4e-151">若要立即发布您的持久聊天服务器的更新拓扑, 请参阅部署文档中的[Lync Server 2013 中的 "发布更新的拓扑](lync-server-2013-publish-the-updated-topology.md)"。</span><span class="sxs-lookup"><span data-stu-id="20b4e-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="20b4e-152">拓扑生成器已打开, 你可以继续在<A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 中发布已更新拓扑</A>的步骤3以开始发布更新的拓扑。</span><span class="sxs-lookup"><span data-stu-id="20b4e-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

