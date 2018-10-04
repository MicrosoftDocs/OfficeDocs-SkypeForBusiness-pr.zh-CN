---
title: 向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 摘要： 阅读本主题可了解如何向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器。
ms.openlocfilehash: ff2486db39546e88c4a75e27875a84a2c3b939ae
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371980"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a><span data-ttu-id="9f52f-103">向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="9f52f-103">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>
 
<span data-ttu-id="9f52f-104">**摘要：** 阅读本主题可了解如何向您 Skype 业务服务器 2015年拓扑添加持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="9f52f-104">**Summary:** Read this topic to learn how to add Persistent Chat Server to your Skype for Business Server 2015 topology.</span></span>
  
<span data-ttu-id="9f52f-105">您计划部署持久聊天服务器的每台服务器上安装必备软件后，您可以使用拓扑生成器以：</span><span class="sxs-lookup"><span data-stu-id="9f52f-105">After you install the prerequisite software on each server on which you plan to deploy Persistent Chat Server, you use Topology Builder to:</span></span> 
  
- <span data-ttu-id="9f52f-106">更新拓扑以包含持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="9f52f-106">Update your topology to include Persistent Chat Server</span></span>
    
- <span data-ttu-id="9f52f-107">发布更新的拓扑</span><span class="sxs-lookup"><span data-stu-id="9f52f-107">Publish the updated topology</span></span>
    
> [!NOTE] 
> <span data-ttu-id="9f52f-108">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="9f52f-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9f52f-109">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="9f52f-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="9f52f-110">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="9f52f-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="9f52f-111">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="9f52f-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="update-your-topology-to-include-persistent-chat-server"></a><span data-ttu-id="9f52f-112">更新拓扑以包含持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="9f52f-112">Update your topology to include Persistent Chat Server</span></span>

<span data-ttu-id="9f52f-113">安装无需灾难恢复配置单个持久聊天服务器池执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9f52f-113">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="9f52f-114">有关配置高可用性和灾难恢复的扩展持久聊天服务器池，请参阅[配置高可用性和灾难恢复对于 Persistent Chat Server in Skype 的业务服务器 2015年](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="9f52f-114">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span>
  
<span data-ttu-id="9f52f-115">若要部署多个持久聊天服务器池，请为每个池重复相同的过程。</span><span class="sxs-lookup"><span data-stu-id="9f52f-115">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>
  
1. <span data-ttu-id="9f52f-116">业务服务器运行 Skype 的计算机上或在其上 Skype 的安装了 Business Server 管理工具，使用登录本地 Users 组 （或具有同等用户权限的帐户） 的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="9f52f-116">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9f52f-117">您可以使用本地用户组的成员的帐户定义拓扑，但要发布拓扑，需要安装 Skype 业务服务器，必须使用**Domain Admins**组和**的成员的帐户RTCUniversalServerAdmins**组，并在您打算对于 Persistent Chat Server 文件存储 （以便该拓扑生成器可以配置所需的 Dacl），使用的文件存储上具有完全控制权限 （读取、 写入和修改） 或使用的帐户同等的权限。</span><span class="sxs-lookup"><span data-stu-id="9f52f-117">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install Skype for Business Server, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="9f52f-118">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="9f52f-118">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="9f52f-119">在控制台树中，导航到**持久聊天池**节点，并展开该选择 Skype 对于业务服务器池，或右键单击节点并选择**新的持久聊天池**。</span><span class="sxs-lookup"><span data-stu-id="9f52f-119">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Skype for Business Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="9f52f-120">您必须定义池的完全限定的域名 (FQDN)，并指示该池将是单服务器池或多服务器池部署。</span><span class="sxs-lookup"><span data-stu-id="9f52f-120">You must define the pool's fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="9f52f-121">您可选择“**多计算机池**”或“**单计算机池**”。</span><span class="sxs-lookup"><span data-stu-id="9f52f-121">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="9f52f-122">如果您打算持久聊天服务器池中有多个前端服务器，请选择前者。</span><span class="sxs-lookup"><span data-stu-id="9f52f-122">Choose the former if you are planning to have more than one Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="9f52f-123">现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="9f52f-123">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="9f52f-124">如果选择多计算机池，输入单个前端服务器组成该池的名称。</span><span class="sxs-lookup"><span data-stu-id="9f52f-124">If you choose a multiple computer pool, enter the names of the individual Front End Servers that comprise the pool.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9f52f-125">如果要在 Standard Edition server 上安装持久聊天服务器角色，则 FQDN 需要与 Standard Edition server 的 FQDN 匹配。</span><span class="sxs-lookup"><span data-stu-id="9f52f-125">If the Persistent Chat Server role is being installed on a Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span> 
  
4. <span data-ttu-id="9f52f-126">定义持久聊天服务器池的一个简单的**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="9f52f-126">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="9f52f-127">可以自定义客户端，使用的显示名称，尤其是在有多个持久聊天服务器池区分聊天室时。</span><span class="sxs-lookup"><span data-stu-id="9f52f-127">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools to differentiate rooms.</span></span>
    
5. <span data-ttu-id="9f52f-128">定义持久聊天服务器用于与 Skype 业务 Server 前端服务器进行通信的端口。</span><span class="sxs-lookup"><span data-stu-id="9f52f-128">Define the port used by the Persistent Chat Server to communicate with Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="9f52f-129">默认端口为 5041。</span><span class="sxs-lookup"><span data-stu-id="9f52f-129">The default port is 5041.</span></span>
    
6. <span data-ttu-id="9f52f-130">如果您的组织需要合规性支持，请选中“**启用合规性**”复选框。</span><span class="sxs-lookup"><span data-stu-id="9f52f-130">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="9f52f-131">如果选择了，与持久聊天服务器前端服务器相同的计算机上安装持久聊天服务器合规性服务。</span><span class="sxs-lookup"><span data-stu-id="9f52f-131">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="9f52f-132">系统会提示您选择 SQL Server 后端服务器持久聊天服务器合规性更高版本。</span><span class="sxs-lookup"><span data-stu-id="9f52f-132">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>
    
7. <span data-ttu-id="9f52f-133">分配持久聊天服务器池的站点关联。</span><span class="sxs-lookup"><span data-stu-id="9f52f-133">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="9f52f-134">选择**默认为此池用于网站\<SiteName\>** 复选框或**使用此池作为所有站点的默认设置**将此持久聊天服务器池指定为当前网站或所有网站的默认池。</span><span class="sxs-lookup"><span data-stu-id="9f52f-134">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="9f52f-135">当业务客户端 Skype 用于创建和管理聊天室时，以便它可以将聊天室创建和管理操作路由到该池的聊天室创建和管理体验中使用与用户的站点关联的默认池。</span><span class="sxs-lookup"><span data-stu-id="9f52f-135">When the Skype for Business client is used to create and manage rooms, the default pool associated with the user's site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="9f52f-136">这仅适用于具有多个持久聊天服务器池部署，并且想要使用的持久聊天服务器的聊天室创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="9f52f-136">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9f52f-137">您可以自定义使用持久聊天服务器软件开发工具包 (SDK) 的聊天室创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="9f52f-137">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span> 
  
8. <span data-ttu-id="9f52f-138">通过执行以下某项操作来定义**SQL 存储用于持久聊天服务器后端 （其中存储聊天室内容）** ：</span><span class="sxs-lookup"><span data-stu-id="9f52f-138">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
   - <span data-ttu-id="9f52f-139">若要使用现有的 SQL Server 存储，请在下拉列表中，单击您想要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="9f52f-139">To use an existing SQL Server store, in the drop-down list, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="9f52f-140">若要指定新的 SQL Server 数据库，请单击**新建**，在**定义新的 SQL 存储**，请执行以下：</span><span class="sxs-lookup"><span data-stu-id="9f52f-140">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
   - <span data-ttu-id="9f52f-141">在**SQL Server FQDN**中，指定要在其创建新的 SQL Server 数据库的 SQL Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f52f-141">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
   - <span data-ttu-id="9f52f-142">选择“**默认实例**”以使用默认实例，或指定其他实例，选择“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="9f52f-142">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="9f52f-143">有关如何配置 SQL Server 备份数据库的灾难恢复的详细信息，请参阅[配置高可用性和灾难恢复对于 Persistent Chat Server in Skype 的业务服务器 2015年](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="9f52f-143">For details about how to configure SQL Server backup databases for disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
9. <span data-ttu-id="9f52f-144">如果启用合规性，请定义 SQL Server 合规性存储。</span><span class="sxs-lookup"><span data-stu-id="9f52f-144">Define the SQL Server compliance store if you enabled Compliance.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9f52f-145">有关如何配置 SQL Server 镜像的高可用性对于 Persistent Chat Server 数据库和持久聊天服务器合规性数据库的详细信息，请参阅[配置高可用性和灾难恢复 for Persistent Chat Server in Skype为业务服务器 2015年](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="9f52f-145">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
10. <span data-ttu-id="9f52f-146">定义文件存储。</span><span class="sxs-lookup"><span data-stu-id="9f52f-146">Define the file store.</span></span> <span data-ttu-id="9f52f-147">文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。</span><span class="sxs-lookup"><span data-stu-id="9f52f-147">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="9f52f-148">对于多服务器持久聊天服务器拓扑，这必须是通用命名约定 (UNC) 路径;对于单服务器持久聊天服务器拓扑，它可以是本地文件路径。</span><span class="sxs-lookup"><span data-stu-id="9f52f-148">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="9f52f-149">若要使用现有文件存储，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="9f52f-149">To use an existing file store, perform the following steps:</span></span>
    
    - <span data-ttu-id="9f52f-150">在“**文件服务器 FQDN**”中，指定要在其上创建新的文件存储的计算机的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f52f-150">In **File Server FQDN**, specify the FQDN of the machine on which you want to create the new file store.</span></span>
    
    - <span data-ttu-id="9f52f-151">在“**文件共享**”中，指定要使用的文件存储。</span><span class="sxs-lookup"><span data-stu-id="9f52f-151">In **File Share**, specify the file store that you want to use.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="9f52f-152">您可以在之前您创建的文件存储，但您必须中定义的位置定义发布拓扑之前创建的文件存储在拓扑生成器中定义的文件存储。</span><span class="sxs-lookup"><span data-stu-id="9f52f-152">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span> <span data-ttu-id="9f52f-153">如果文件存储不存在，则发布拓扑的尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="9f52f-153">If the file store doesn't already exist, attempts to publish the topology will fail.</span></span> 
  
11. <span data-ttu-id="9f52f-154">选择要为此持久聊天服务器池用作下一个跃点的前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="9f52f-154">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="9f52f-155">这是将能够将持久聊天服务器请求路由到此池中的前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="9f52f-155">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>
    
12. <span data-ttu-id="9f52f-156">若要保存配置，请单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="9f52f-156">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="9f52f-157">持久聊天服务器池出现在拓扑生成器附带有特定的池设置。</span><span class="sxs-lookup"><span data-stu-id="9f52f-157">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="9f52f-158">若要发布更新后已向其添加持久聊天服务器的拓扑，请参阅 Publish 更新的拓扑。</span><span class="sxs-lookup"><span data-stu-id="9f52f-158">To publish your updated topology to which you've added Persistent Chat Server, see Publish the updated topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9f52f-159">使用拓扑生成器中已打开，您可以继续执行步骤 3 中发布更新的拓扑以开始发布更新后的拓扑。</span><span class="sxs-lookup"><span data-stu-id="9f52f-159">With Topology Builder already open, you can proceed to step 3 in Publish the updated topology to begin publishing your updated topology.</span></span> 
  
## <a name="publish-the-updated-topology"></a><span data-ttu-id="9f52f-160">发布更新的拓扑</span><span class="sxs-lookup"><span data-stu-id="9f52f-160">Publish the updated topology</span></span>
<span data-ttu-id="9f52f-161"><a name="BKMK_PublishTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="9f52f-161"></span></span>

<span data-ttu-id="9f52f-162">更新之后您在拓扑生成器中的拓扑，您必须将发布拓扑中央管理存储之前，您可以配置和使用 Business Server Skype。</span><span class="sxs-lookup"><span data-stu-id="9f52f-162">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Skype for Business Server.</span></span> <span data-ttu-id="9f52f-163">数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。</span><span class="sxs-lookup"><span data-stu-id="9f52f-163">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>
  
<span data-ttu-id="9f52f-164">发布拓扑之前，对于 Persistent Chat Server 安装数据库。</span><span class="sxs-lookup"><span data-stu-id="9f52f-164">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="9f52f-165">使用拓扑生成器来安装数据库选择**操作**和**安装数据库**。</span><span class="sxs-lookup"><span data-stu-id="9f52f-165">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>
  
1. <span data-ttu-id="9f52f-166">业务服务器运行 Skype 的计算机上或在其上 Skype 的安装了 Business Server 管理工具，使用登录**以 Domain Admins**组和**RTCUniversalServerAdmins**组的成员的帐户且具有完全控制权限 （读取、 写入和修改） 上的文件存储用于对于 Persistent Chat Server 文件存储 （以便该拓扑生成器可以配置所需的随机访问控制列表 (Dacl)），或使用具有等效用户的帐户权限。</span><span class="sxs-lookup"><span data-stu-id="9f52f-166">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>
    
2. <span data-ttu-id="9f52f-167">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="9f52f-167">Start Topology Builder.</span></span> <span data-ttu-id="9f52f-168">选择“**从本地文件打开拓扑**”（如果在本地保存它）。</span><span class="sxs-lookup"><span data-stu-id="9f52f-168">Select **Open Topology from a local file** if you saved it locally.</span></span>
    
3. <span data-ttu-id="9f52f-169">在控制台树中，右键单击**业务服务器 2015年的 Skype**，，然后单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="9f52f-169">In the console tree, right-click **Skype for Business Server 2015**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="9f52f-170">在“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9f52f-170">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="9f52f-171">在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="9f52f-171">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    

