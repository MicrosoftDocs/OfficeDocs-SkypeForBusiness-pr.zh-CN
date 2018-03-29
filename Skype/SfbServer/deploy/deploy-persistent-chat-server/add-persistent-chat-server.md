---
title: 持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 摘要： 阅读本主题，以了解如何将持久聊天服务器添加到您的业务服务器 2015年拓扑 Skype。
ms.openlocfilehash: 3d00e24dbe8f25b2a1887b8c1c79a63bda3471f2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a><span data-ttu-id="10225-103">持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑</span><span class="sxs-lookup"><span data-stu-id="10225-103">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>
 
<span data-ttu-id="10225-104">**摘要：**阅读本主题，以了解如何将持久聊天服务器添加到您的业务服务器 2015年拓扑 Skype。</span><span class="sxs-lookup"><span data-stu-id="10225-104">**Summary:** Read this topic to learn how to add Persistent Chat Server to your Skype for Business Server 2015 topology.</span></span>
  
<span data-ttu-id="10225-105">您打算部署持续聊天服务器每个服务器上安装必备软件后，您将使用到拓扑生成器：</span><span class="sxs-lookup"><span data-stu-id="10225-105">After you install the prerequisite software on each server on which you plan to deploy Persistent Chat Server, you use Topology Builder to:</span></span> 
  
- <span data-ttu-id="10225-106">更新拓扑以包含持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="10225-106">Update your topology to include Persistent Chat Server</span></span>
    
- <span data-ttu-id="10225-107">发布更新的拓扑</span><span class="sxs-lookup"><span data-stu-id="10225-107">Publish the updated topology</span></span>
    
## <a name="update-your-topology-to-include-persistent-chat-server"></a><span data-ttu-id="10225-108">更新拓扑以包含持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="10225-108">Update your topology to include Persistent Chat Server</span></span>

<span data-ttu-id="10225-109">执行以下步骤来安装单个持久聊天服务器池没有灾难恢复配置。</span><span class="sxs-lookup"><span data-stu-id="10225-109">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="10225-110">配置高可用性和灾难恢复的拉伸永久聊天服务器池，请参阅[配置高可用性和业务服务器 2015年的 Skype 的持久聊天服务器的灾难恢复](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="10225-110">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span>
  
<span data-ttu-id="10225-111">若要部署多个持久性聊天服务器池，请为每个池重复相同的过程。</span><span class="sxs-lookup"><span data-stu-id="10225-111">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>
  
1. <span data-ttu-id="10225-112">运行 Skype 业务服务器的计算机上或在其上 Skype 的安装业务服务器管理工具，使用登录的帐户是本地用户组 （或具有相当的用户权限的帐户） 的成员。</span><span class="sxs-lookup"><span data-stu-id="10225-112">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="10225-113">您可以通过使用本地用户组的成员帐户定义拓扑，但若要发布一个拓扑结构，才能为企业服务器安装 Skype，必须使用**域管理员**组和**的成员的帐户RTCUniversalServerAdmins**组中，并且您打算使用进行持久聊天服务器文件存储 （以便该拓扑生成器可以配置所需的 Dacl），文件存储在具有完全控制权限 （读取、 写入和修改） 或与帐户同等的权利。</span><span class="sxs-lookup"><span data-stu-id="10225-113">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install Skype for Business Server, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="10225-114">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="10225-114">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="10225-115">在控制台树中，导航到**持久聊天池**节点并展开它要选择 Skype 业务服务器池，或者用鼠标右键单击节点并选择**新持续聊天池**。</span><span class="sxs-lookup"><span data-stu-id="10225-115">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Skype for Business Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="10225-116">必须定义该池的完全合格的域名称 (FQDN)，并指示该池是否单服务器池或池多服务器部署。</span><span class="sxs-lookup"><span data-stu-id="10225-116">You must define the pool's fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="10225-117">您可选择“**多计算机池**”或“**单计算机池**”。</span><span class="sxs-lookup"><span data-stu-id="10225-117">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="10225-118">如果您打算持续聊天服务器池中有多个前端服务器，则选择前者。</span><span class="sxs-lookup"><span data-stu-id="10225-118">Choose the former if you are planning to have more than one Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="10225-119">现在或稍后做出此选择，因为在创建单计算机池之后，将无法向其添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="10225-119">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="10225-120">如果您选择了多个计算机池，输入单个前端服务器构成该池的名称。</span><span class="sxs-lookup"><span data-stu-id="10225-120">If you choose a multiple computer pool, enter the names of the individual Front End Servers that comprise the pool.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="10225-121">如果正在标准版服务器上安装了永久性的聊天服务器角色，FQDN 需要标准版服务器的 FQDN 匹配。</span><span class="sxs-lookup"><span data-stu-id="10225-121">If the Persistent Chat Server role is being installed on a Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span> 
  
4. <span data-ttu-id="10225-122">定义一个简单的**显示名称**为持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="10225-122">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="10225-123">显示名称可以使用自定义客户端，特别是当有多个持久性聊天服务器池来区分房间。</span><span class="sxs-lookup"><span data-stu-id="10225-123">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools to differentiate rooms.</span></span>
    
5. <span data-ttu-id="10225-124">定义持久聊天服务器用于与 Skype 业务服务器前端服务器进行通信的端口。</span><span class="sxs-lookup"><span data-stu-id="10225-124">Define the port used by the Persistent Chat Server to communicate with Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="10225-125">默认端口为 5041。</span><span class="sxs-lookup"><span data-stu-id="10225-125">The default port is 5041.</span></span>
    
6. <span data-ttu-id="10225-126">如果您的组织需要合规性支持，请选中“**启用合规性**”复选框。</span><span class="sxs-lookup"><span data-stu-id="10225-126">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="10225-127">如果选择，为持久聊天服务器前端服务器的同一计算机上安装持久聊天服务器的符合性服务。</span><span class="sxs-lookup"><span data-stu-id="10225-127">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="10225-128">提示您选择 SQL Server 后端服务器以后持续聊天服务器的符合性。</span><span class="sxs-lookup"><span data-stu-id="10225-128">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>
    
7. <span data-ttu-id="10225-129">指定站点关系持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="10225-129">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="10225-130">选择**作为默认此池用于网站\<站点名\>**复选框或**使用该池为所有站点的默认值**作为当前站点或所有站点的默认池指定本持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="10225-130">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="10225-131">当 Skype 业务客户端用于创建和管理文件室时，与用户的站点相关联的默认池使用文件室的创建和管理经验，以便它可以将文件室的创建和管理操作路由到该池。</span><span class="sxs-lookup"><span data-stu-id="10225-131">When the Skype for Business client is used to create and manage rooms, the default pool associated with the user's site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="10225-132">此设置仅当您具有多个持久性聊天服务器池部署，并且想要使用持久聊天服务器的文件室创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="10225-132">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="10225-133">您可以自定义使用持久聊天服务器软件开发工具包 (SDK) 的文件室的创建和管理功能。</span><span class="sxs-lookup"><span data-stu-id="10225-133">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span> 
  
8. <span data-ttu-id="10225-134">通过执行以下任一操作来定义**SQL 存储持久聊天服务器后端 （聊天室内容的存储位置）** ：</span><span class="sxs-lookup"><span data-stu-id="10225-134">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
   - <span data-ttu-id="10225-135">若要使用现有的 SQL Server 存储，在下拉列表中，单击要使用的 SQL Server 存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="10225-135">To use an existing SQL Server store, in the drop-down list, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="10225-136">若要指定新的 SQL Server 数据库，单击**新建**，在**定义新建 SQL 存储**，请执行以下：</span><span class="sxs-lookup"><span data-stu-id="10225-136">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
   - <span data-ttu-id="10225-137">在**SQL Server FQDN**，指定您要在其创建新的 SQL Server 数据库的 SQL Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="10225-137">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
   - <span data-ttu-id="10225-138">选择“**默认实例**”以使用默认实例，或指定其他实例，选择“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="10225-138">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="10225-139">有关如何配置用于灾难恢复的 SQL Server 备份数据库的详细信息，请参阅[配置高可用性和业务服务器 2015年的 Skype 的持久聊天服务器的灾难恢复](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="10225-139">For details about how to configure SQL Server backup databases for disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
9. <span data-ttu-id="10225-140">如果您启用了法规遵从性，定义的 SQL Server 法规遵从性存储。</span><span class="sxs-lookup"><span data-stu-id="10225-140">Define the SQL Server compliance store if you enabled Compliance.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="10225-141">有关如何配置 SQL Server 镜像持久聊天服务器数据库和持久聊天服务器的法规遵从性数据库高可用性的详细信息，请参阅[配置高可用性和灾难恢复在 Skype 的持久聊天服务器为业务服务器 2015年](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="10225-141">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
10. <span data-ttu-id="10225-142">定义文件存储。</span><span class="sxs-lookup"><span data-stu-id="10225-142">Define the file store.</span></span> <span data-ttu-id="10225-143">文件存储是一个文件夹，其中存储了已上载到文件存储库的所有文件的副本（例如，存储已发布到聊天室的文件附件）。</span><span class="sxs-lookup"><span data-stu-id="10225-143">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="10225-144">对于多服务器持续聊天服务器拓扑中，它必须是通用命名约定 (UNC) 路径;并且，对于单服务器持续聊天服务器拓扑，它可以是本地文件路径。</span><span class="sxs-lookup"><span data-stu-id="10225-144">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="10225-145">若要使用现有文件存储，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="10225-145">To use an existing file store, perform the following steps:</span></span>
    
    - <span data-ttu-id="10225-146">在“**文件服务器 FQDN**”中，指定要在其上创建新的文件存储的计算机的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="10225-146">In **File Server FQDN**, specify the FQDN of the machine on which you want to create the new file store.</span></span>
    
    - <span data-ttu-id="10225-147">在“**文件共享**”中，指定要使用的文件存储。</span><span class="sxs-lookup"><span data-stu-id="10225-147">In **File Share**, specify the file store that you want to use.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="10225-148">之前创建的文件存储区中，但您必须在定义之前发布拓扑定义的位置创建文件存储区，您可以定义文件存储拓扑生成器中。</span><span class="sxs-lookup"><span data-stu-id="10225-148">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span> <span data-ttu-id="10225-149">如果文件存储不存在，则发布拓扑的尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="10225-149">If the file store doesn't already exist, attempts to publish the topology will fail.</span></span> 
  
11. <span data-ttu-id="10225-150">选择要用作该持久聊天服务器池下一跃点的前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="10225-150">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="10225-151">这是将能够持久聊天服务器请求路由到此池前端服务器池。</span><span class="sxs-lookup"><span data-stu-id="10225-151">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>
    
12. <span data-ttu-id="10225-152">若要保存配置，请单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="10225-152">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="10225-153">伴随着特定的池设置的拓扑生成器中出现持续聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="10225-153">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="10225-154">若要发布更新持久聊天服务器已添加到拓扑，请参阅发布更新拓扑。</span><span class="sxs-lookup"><span data-stu-id="10225-154">To publish your updated topology to which you've added Persistent Chat Server, see Publish the updated topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="10225-155">使用拓扑生成器已经打开，就可以继续到第 3 步在发布更新拓扑结构开始发布更新的拓扑。</span><span class="sxs-lookup"><span data-stu-id="10225-155">With Topology Builder already open, you can proceed to step 3 in Publish the updated topology to begin publishing your updated topology.</span></span> 
  
## <a name="publish-the-updated-topology"></a><span data-ttu-id="10225-156">发布更新的拓扑</span><span class="sxs-lookup"><span data-stu-id="10225-156">Publish the updated topology</span></span>
<span data-ttu-id="10225-157"><a name="BKMK_PublishTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="10225-157"></span></span>

<span data-ttu-id="10225-158">在更新之后您在拓扑生成器中的拓扑结构，必须将发布拓扑中央管理存储之前您可以配置和使用 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="10225-158">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Skype for Business Server.</span></span> <span data-ttu-id="10225-159">数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。</span><span class="sxs-lookup"><span data-stu-id="10225-159">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>
  
<span data-ttu-id="10225-160">在发布您的拓扑之前，持久聊天服务器安装数据库。</span><span class="sxs-lookup"><span data-stu-id="10225-160">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="10225-161">使用拓扑生成器来选择**操作**和**安装数据库**安装数据库。</span><span class="sxs-lookup"><span data-stu-id="10225-161">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>
  
1. <span data-ttu-id="10225-162">运行 Skype 业务服务器的计算机上或在其上 Skype 业务服务器管理工具都已安装，使用登录帐户，则**域管理员**组和**RTCUniversalServerAdmins**组的成员并具有完全控制权限 （读取、 写入和修改） 文件存储用于持久聊天服务器文件存储 （以便该拓扑生成器可以配置所需的自由访问控制列表 (Dacl)），或具有相当的用户的帐户权限。</span><span class="sxs-lookup"><span data-stu-id="10225-162">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>
    
2. <span data-ttu-id="10225-163">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="10225-163">Start Topology Builder.</span></span> <span data-ttu-id="10225-164">选择“**从本地文件打开拓扑**”（如果在本地保存它）。</span><span class="sxs-lookup"><span data-stu-id="10225-164">Select **Open Topology from a local file** if you saved it locally.</span></span>
    
3. <span data-ttu-id="10225-165">在控制台树中，**业务服务器 2015年的 Skype**，用鼠标右键单击，然后单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="10225-165">In the console tree, right-click **Skype for Business Server 2015**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="10225-166">在“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="10225-166">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="10225-167">在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="10225-167">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    

