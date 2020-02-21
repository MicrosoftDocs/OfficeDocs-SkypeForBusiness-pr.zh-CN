---
title: Lync Server 2013：将持久聊天服务器添加到拓扑中
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ae7ca7e475fd106608dea09fedf250ef541a5c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="eb1cd-102">在 Lync Server 2013 中向拓扑添加持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="eb1cd-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb1cd-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="eb1cd-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="eb1cd-104">您必须将 Lync Server 2013 与拓扑中的持久聊天服务器支持结合在一起，然后才能将部署配置为支持持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="eb1cd-105">本主题中的信息介绍如何使用拓扑生成器将持久聊天服务器支持添加到现有拓扑中。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="eb1cd-106">将持久聊天服务器添加到拓扑中</span><span class="sxs-lookup"><span data-stu-id="eb1cd-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="eb1cd-107">执行以下步骤以在不进行灾难恢复配置的情况下安装单个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="eb1cd-108">有关为高可用性和灾难恢复配置延伸的持久聊天服务器池，请参阅部署文档中的在[Lync server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="eb1cd-109">若要部署多个持久聊天服务器池，请为每个池重复相同的过程。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="eb1cd-110">在运行 Lync Server 2013 或安装了 Lync Server 管理工具的计算机上，使用属于本地 Users 组成员的帐户（或具有等效用户权限的帐户）登录。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb1cd-111">您可以通过使用属于本地用户组成员的帐户来定义拓扑，但要发布安装 Lync Server 2013 服务器所需的拓扑，您必须使用属于<STRONG>Domain Admins</STRONG>组和<STRONG>RTCUniversalServerAdmins</STRONG>组成员的帐户，并且对要用于持久聊天服务器文件存储的文件存储具有完全控制权限（即读取、写入和修改）（即，以便拓扑生成器可以配置所需的 dacl）。，或具有等效权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="eb1cd-112">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="eb1cd-113">在控制台树中，导航到 "**持久聊天池**" 节点并展开它以选择持久聊天服务器池，或者右键单击该节点，然后选择 "**新建持久聊天池**"。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="eb1cd-114">您必须定义该池的完全限定的域名 (FQDN)，并指示该池是单服务器池部署还是多服务器池部署。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="eb1cd-115">您可选择“多计算机池”\*\*\*\* 或“单计算机池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="eb1cd-116">如果计划在持久聊天服务器池中安装多台持久聊天服务器前端服务器，请选择前者。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="eb1cd-117">现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="eb1cd-118">如果选择 "多计算机池"，请输入构成池的单个持久聊天服务器前端服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb1cd-119">如果在 Lync Server 2013&nbsp;Standard edition server 上安装持久聊天服务器角色，则 fqdn 需要与 Standard edition SERVER 的 fqdn 匹配。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="eb1cd-120">为持久聊天服务器池定义一个简单的**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="eb1cd-121">自定义客户端可以使用显示名称，尤其是在有多个持久聊天服务器池时，要区分房间。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="eb1cd-122">定义持久聊天服务器用于与 Lync Server 前端服务器进行通信的端口。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="eb1cd-123">默认端口为 5041。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="eb1cd-124">如果您的组织需要合规性支持，请选中“启用合规性”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="eb1cd-125">如果选择此项，持久聊天服务器合规性服务将安装在与持久聊天服务器前端服务器相同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="eb1cd-126">随后系统会提示你选择一个 SQL Server 后端服务器来实现持久聊天服务器兼容性。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="eb1cd-127">为持久聊天服务器池分配网站相关性。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="eb1cd-128">选中 "**将此池用作网站\<SiteName\>的默认值**" 复选框，或**将此池用作所有网站的默认值**，以将此持久聊天服务器池指定为当前网站或所有网站的默认池。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="eb1cd-129">在使用 Lync 2013 客户端创建和管理会议室时，会使用与用户网站相关联的默认池来创建和管理体验，以便它可以将会议室创建和管理操作路由到该池。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="eb1cd-130">这仅适用于部署了多个持久聊天服务器池的情况，并且想要使用持久聊天服务器的会议室创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb1cd-131">您可以使用持久聊天服务器软件开发工具包（SDK）自定义会议室创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="eb1cd-132">有关如何为灾难恢复配置 SQL Server 备份数据库的详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复</A>。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="eb1cd-133">通过执行以下操作之一，定义**持久聊天服务器后端的 SQL 存储（其中存储了聊天室内容）** ：</span><span class="sxs-lookup"><span data-stu-id="eb1cd-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="eb1cd-134">若要使用现有的 SQL Server 数据库，请在下拉列表中单击要使用的 SQL Server 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="eb1cd-135">若要指定新的 SQL Server 数据库，请单击 "**新建**"，并在 "**定义新的 sql 存储**" 中执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eb1cd-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="eb1cd-136">在 " **SQL SERVER FQDN**" 中，指定要在其上创建新 sql server 数据库的 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="eb1cd-137">选择“默认实例”\*\*\*\* 以使用默认实例，或指定其他实例，选择“命名实例”\*\*\*\*，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="eb1cd-138">如果启用了合规性，则定义 SQL Server 合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb1cd-139">有关如何为持久聊天服务器数据库和持久聊天服务器合规性数据库的高可用性配置 SQL Server 镜像的详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复</A>。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="eb1cd-140">定义文件存储。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-140">Define the file store.</span></span> <span data-ttu-id="eb1cd-141">文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="eb1cd-142">在多服务器持久聊天服务器拓扑的情况下，这必须是通用命名约定（UNC）路径;对于单服务器持久聊天服务器拓扑，它可以是本地文件路径。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="eb1cd-143">若要使用现有文件存储，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="eb1cd-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="eb1cd-144">在“文件服务器 FQDN”\*\*\*\* 中，指定要在其上创建新的文件存储的文件存储的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="eb1cd-145">在“文件共享”\*\*\*\* 中，指定要使用的文件存储。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="eb1cd-146">您可以在拓扑生成器中定义文件存储，然后再创建文件存储，但您必须在发布拓扑之前定义的定义位置中创建文件存储。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="eb1cd-147">选择要用作此持久聊天服务器池的下一个跃点的前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="eb1cd-148">这是能够将持久聊天服务器请求路由到此池的前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="eb1cd-149">若要保存配置，请单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="eb1cd-150">持久聊天服务器池在拓扑生成器中显示，附带您的特定池设置。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="eb1cd-151">若要立即发布已永久聊天服务器的更新的拓扑，请参阅部署文档中的在[Lync Server 2013 中发布更新后的拓扑](lync-server-2013-publish-the-updated-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb1cd-152">已打开拓扑生成器，您可以继续在<A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013 中发布更新后的拓扑</A>中的步骤3，以开始发布更新的拓扑。</span><span class="sxs-lookup"><span data-stu-id="eb1cd-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

