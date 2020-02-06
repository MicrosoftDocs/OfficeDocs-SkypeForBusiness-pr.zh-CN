---
title: 将持久聊天服务器添加到 Skype for business Server 2015 拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 摘要：阅读本主题，了解如何将持久聊天服务器添加到 Skype for business Server 2015 拓扑。
ms.openlocfilehash: 733d75e954c75cecfab38e0a2f1294c6e20984c1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794110"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a><span data-ttu-id="90a2c-103">将持久聊天服务器添加到 Skype for business Server 2015 拓扑</span><span class="sxs-lookup"><span data-stu-id="90a2c-103">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>
 
<span data-ttu-id="90a2c-104">**摘要：** 阅读本主题，了解如何将持久聊天服务器添加到 Skype for business Server 2015 拓扑。</span><span class="sxs-lookup"><span data-stu-id="90a2c-104">**Summary:** Read this topic to learn how to add Persistent Chat Server to your Skype for Business Server 2015 topology.</span></span>
  
<span data-ttu-id="90a2c-105">在计划部署持久聊天服务器的每台服务器上安装必备软件后，可使用拓扑生成器执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="90a2c-105">After you install the prerequisite software on each server on which you plan to deploy Persistent Chat Server, you use Topology Builder to:</span></span> 
  
- <span data-ttu-id="90a2c-106">更新拓扑以包含持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="90a2c-106">Update your topology to include Persistent Chat Server</span></span>
    
- <span data-ttu-id="90a2c-107">发布更新的拓扑</span><span class="sxs-lookup"><span data-stu-id="90a2c-107">Publish the updated topology</span></span>
    
> [!NOTE] 
> <span data-ttu-id="90a2c-108">Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="90a2c-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="90a2c-109">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="90a2c-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="90a2c-110">有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="90a2c-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="90a2c-111">如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="90a2c-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="update-your-topology-to-include-persistent-chat-server"></a><span data-ttu-id="90a2c-112">更新拓扑以包含持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="90a2c-112">Update your topology to include Persistent Chat Server</span></span>

<span data-ttu-id="90a2c-113">若要在不使用灾难恢复配置的情况下安装单个持久聊天服务器池，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="90a2c-113">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="90a2c-114">有关为高可用性和灾难恢复配置延长的持久聊天服务器池，请参阅[在 Skype for Business server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="90a2c-114">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span>
  
<span data-ttu-id="90a2c-115">若要部署多个持久聊天服务器池，请为每个池重复相同的过程。</span><span class="sxs-lookup"><span data-stu-id="90a2c-115">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>
  
1. <span data-ttu-id="90a2c-116">在运行 Skype for Business 服务器或安装了 Skype for business 服务器管理工具的计算机上，使用属于本地 Users 组的成员（或具有等效用户权限的帐户）登录。</span><span class="sxs-lookup"><span data-stu-id="90a2c-116">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90a2c-117">你可以使用本地 Users 组的成员帐户定义拓扑，但要发布拓扑，若要安装 Skype for Business 服务器，你必须使用属于**域管理员**组和**RTCUniversalServerAdmins**组的成员，并且在你要用于永久聊天服务器文件存储的文件存储上具有完全控制权限（读取、写入和修改），以便拓扑生成器可以配置所需的 dacl，或具有等效项的帐户使用权.</span><span class="sxs-lookup"><span data-stu-id="90a2c-117">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install Skype for Business Server, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="90a2c-118">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="90a2c-118">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="90a2c-119">在控制台树中，导航到 "**持久聊天池**" 节点并展开它以选择 Skype For business 服务器池，或者右键单击该节点，然后选择 "**新建持久聊天池**"。</span><span class="sxs-lookup"><span data-stu-id="90a2c-119">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Skype for Business Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="90a2c-120">必须定义池的完全限定的域名（FQDN），并指示池是单服务器池还是多服务器池部署。</span><span class="sxs-lookup"><span data-stu-id="90a2c-120">You must define the pool's fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="90a2c-121">您可选择“**多计算机池**”或“**单计算机池**”。</span><span class="sxs-lookup"><span data-stu-id="90a2c-121">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="90a2c-122">如果计划在持久聊天服务器池中安装多台前端服务器，请选择前者。</span><span class="sxs-lookup"><span data-stu-id="90a2c-122">Choose the former if you are planning to have more than one Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="90a2c-123">现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="90a2c-123">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="90a2c-124">如果你选择多台计算机池，请输入组成池的单个前端服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="90a2c-124">If you choose a multiple computer pool, enter the names of the individual Front End Servers that comprise the pool.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="90a2c-125">如果在标准版服务器上安装持久聊天服务器角色，则 FQDN 需要与标准版服务器的 FQDN 相匹配。</span><span class="sxs-lookup"><span data-stu-id="90a2c-125">If the Persistent Chat Server role is being installed on a Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span> 
  
4. <span data-ttu-id="90a2c-126">为持久聊天服务器池定义一个简单的**显示名称**。</span><span class="sxs-lookup"><span data-stu-id="90a2c-126">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="90a2c-127">显示名称可由自定义客户端使用，特别是当存在多个持久聊天服务器池来区分房间时。</span><span class="sxs-lookup"><span data-stu-id="90a2c-127">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools to differentiate rooms.</span></span>
    
5. <span data-ttu-id="90a2c-128">定义持久聊天服务器用于与 Skype for business 服务器前端服务器通信的端口。</span><span class="sxs-lookup"><span data-stu-id="90a2c-128">Define the port used by the Persistent Chat Server to communicate with Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="90a2c-129">默认端口为 5041。</span><span class="sxs-lookup"><span data-stu-id="90a2c-129">The default port is 5041.</span></span>
    
6. <span data-ttu-id="90a2c-130">如果您的组织需要合规性支持，请选中“**启用合规性**”复选框。</span><span class="sxs-lookup"><span data-stu-id="90a2c-130">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="90a2c-131">如果选择此项，持久聊天服务器合规性服务将与持久聊天服务器前端服务器安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="90a2c-131">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="90a2c-132">系统将提示你选择 SQL Server 后端服务器，以便在以后持续聊天服务器合规性。</span><span class="sxs-lookup"><span data-stu-id="90a2c-132">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>
    
7. <span data-ttu-id="90a2c-133">为持久聊天服务器池分配网站相关性。</span><span class="sxs-lookup"><span data-stu-id="90a2c-133">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="90a2c-134">选中 "**将此池用作网站\<的 SiteName\>默认值**" 复选框，或**将此池用作所有网站的默认值**将此持久聊天服务器池指定为当前网站或所有网站的默认池。</span><span class="sxs-lookup"><span data-stu-id="90a2c-134">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="90a2c-135">当使用 Skype for Business 客户端创建和管理会议室时，聊天室创建和管理体验将使用与用户的网站关联的默认池，以便它可以将会议室创建和管理操作路由到该池。</span><span class="sxs-lookup"><span data-stu-id="90a2c-135">When the Skype for Business client is used to create and manage rooms, the default pool associated with the user's site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="90a2c-136">这仅适用于已部署多个持久聊天服务器池的情况，并且希望使用持久聊天服务器的聊天室创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="90a2c-136">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="90a2c-137">可以使用持久聊天服务器软件开发工具包（SDK）自定义聊天室创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="90a2c-137">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span> 
  
8. <span data-ttu-id="90a2c-138">通过执行下列操作之一，定义**持久聊天服务器后端的 SQL 应用商店（存储聊天室内容）** ：</span><span class="sxs-lookup"><span data-stu-id="90a2c-138">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
   - <span data-ttu-id="90a2c-139">若要使用现有的 SQL Server 应用商店，请在下拉列表中单击要使用的 SQL Server 应用商店的名称。</span><span class="sxs-lookup"><span data-stu-id="90a2c-139">To use an existing SQL Server store, in the drop-down list, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="90a2c-140">若要指定新的 SQL Server 数据库，请单击 "**新建**"，然后在 "**定义新的 SQL 存储**" 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="90a2c-140">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
   - <span data-ttu-id="90a2c-141">在**SQL SERVER FQDN**中，指定要在其上创建新的 sql server 数据库的 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="90a2c-141">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
   - <span data-ttu-id="90a2c-142">选择“**默认实例**”以使用默认实例，或指定其他实例，选择“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="90a2c-142">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="90a2c-143">有关如何为灾难恢复配置 SQL Server 备份数据库的详细信息，请参阅[在 Skype for Business server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="90a2c-143">For details about how to configure SQL Server backup databases for disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
9. <span data-ttu-id="90a2c-144">如果已启用合规性，请定义 SQL Server 合规性存储。</span><span class="sxs-lookup"><span data-stu-id="90a2c-144">Define the SQL Server compliance store if you enabled Compliance.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="90a2c-145">有关如何为持久聊天服务器数据库和持久聊天服务器合规性数据库配置 SQL Server 镜像的详细信息，请参阅[在 Skype for Business server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="90a2c-145">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
10. <span data-ttu-id="90a2c-146">定义文件存储。</span><span class="sxs-lookup"><span data-stu-id="90a2c-146">Define the file store.</span></span> <span data-ttu-id="90a2c-147">文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。</span><span class="sxs-lookup"><span data-stu-id="90a2c-147">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="90a2c-148">在多服务器持久聊天服务器拓扑的情况下，这必须是通用命名约定（UNC）路径;对于单服务器持久聊天服务器拓扑，它可以是本地文件路径。</span><span class="sxs-lookup"><span data-stu-id="90a2c-148">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="90a2c-149">若要使用现有文件存储，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="90a2c-149">To use an existing file store, perform the following steps:</span></span>
    
    - <span data-ttu-id="90a2c-150">在“**文件服务器 FQDN**”中，指定要在其上创建新的文件存储的计算机的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="90a2c-150">In **File Server FQDN**, specify the FQDN of the machine on which you want to create the new file store.</span></span>
    
    - <span data-ttu-id="90a2c-151">在“**文件共享**”中，指定要使用的文件存储。</span><span class="sxs-lookup"><span data-stu-id="90a2c-151">In **File Share**, specify the file store that you want to use.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="90a2c-152">你可以在创建文件存储之前在拓扑生成器中定义文件存储，但你必须在发布拓扑之前在定义的位置创建文件存储。</span><span class="sxs-lookup"><span data-stu-id="90a2c-152">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span> <span data-ttu-id="90a2c-153">如果文件存储不存在，则发布拓扑的尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="90a2c-153">If the file store doesn't already exist, attempts to publish the topology will fail.</span></span> 
  
11. <span data-ttu-id="90a2c-154">选择要用作此持久聊天服务器池的下一跃点的前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="90a2c-154">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="90a2c-155">这是可以将持久聊天服务器请求路由到此池的前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="90a2c-155">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>
    
12. <span data-ttu-id="90a2c-156">若要保存配置，请单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="90a2c-156">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="90a2c-157">持久聊天服务器池显示在拓扑生成器中，附带你的特定池设置。</span><span class="sxs-lookup"><span data-stu-id="90a2c-157">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="90a2c-158">若要发布已添加持久聊天服务器的已更新拓扑，请参阅发布更新后的拓扑。</span><span class="sxs-lookup"><span data-stu-id="90a2c-158">To publish your updated topology to which you've added Persistent Chat Server, see Publish the updated topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90a2c-159">拓扑生成器已打开，你可以继续在发布更新拓扑中的步骤3以开始发布更新的拓扑。</span><span class="sxs-lookup"><span data-stu-id="90a2c-159">With Topology Builder already open, you can proceed to step 3 in Publish the updated topology to begin publishing your updated topology.</span></span> 
  
## <a name="publish-the-updated-topology"></a><span data-ttu-id="90a2c-160">发布更新的拓扑</span><span class="sxs-lookup"><span data-stu-id="90a2c-160">Publish the updated topology</span></span>
<span data-ttu-id="90a2c-161"><a name="BKMK_PublishTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="90a2c-161"><a name="BKMK_PublishTopology"> </a></span></span>

<span data-ttu-id="90a2c-162">在拓扑生成器中更新拓扑后，必须先将拓扑发布到中央管理存储，然后才能配置和使用 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="90a2c-162">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Skype for Business Server.</span></span> <span data-ttu-id="90a2c-163">数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。</span><span class="sxs-lookup"><span data-stu-id="90a2c-163">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>
  
<span data-ttu-id="90a2c-164">在发布拓扑之前，请安装持久聊天服务器的数据库。</span><span class="sxs-lookup"><span data-stu-id="90a2c-164">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="90a2c-165">使用拓扑生成器，通过选择 "**操作**" 并**安装数据库**来安装数据库。</span><span class="sxs-lookup"><span data-stu-id="90a2c-165">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>
  
1. <span data-ttu-id="90a2c-166">在运行 Skype for Business 服务器的计算机上，或者在其上安装了 Skype for business Server 管理工具的计算机上，使用属于 "**域管理员**" 组和 " **RTCUniversalServerAdmins** " 组的成员的帐户登录，并且具有对永久聊天服务器文件存储使用的文件存储区的 "完全控制" 权限（读取、写入和修改），以便拓扑生成器可以配置所需的随机访问控制列表（dacl）或具有等效用户的帐户使用权.</span><span class="sxs-lookup"><span data-stu-id="90a2c-166">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>
    
2. <span data-ttu-id="90a2c-167">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="90a2c-167">Start Topology Builder.</span></span> <span data-ttu-id="90a2c-168">选择“**从本地文件打开拓扑**”（如果在本地保存它）。</span><span class="sxs-lookup"><span data-stu-id="90a2c-168">Select **Open Topology from a local file** if you saved it locally.</span></span>
    
3. <span data-ttu-id="90a2c-169">在控制台树中，右键单击 " **Skype For Business Server 2015**"，然后单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="90a2c-169">In the console tree, right-click **Skype for Business Server 2015**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="90a2c-170">在“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="90a2c-170">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="90a2c-171">在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="90a2c-171">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    

