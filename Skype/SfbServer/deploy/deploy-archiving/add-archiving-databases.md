---
title: 业务服务器添加到现有部署中 Skype 的存档数据库
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 摘要： 阅读本主题可了解如何向您 Skype 业务服务器部署添加存档数据库。
ms.openlocfilehash: 083b6329cdf27331ba861b96a74f94e2ae5aa912
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229458"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a><span data-ttu-id="cd709-103">业务服务器添加到现有部署中 Skype 的存档数据库</span><span class="sxs-lookup"><span data-stu-id="cd709-103">Add archiving databases to an existing deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="cd709-104">**摘要：** 阅读本主题可了解如何将存档数据库添加到您 Skype 业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="cd709-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="cd709-105">必须先在拓扑中纳入存档，然后才能配置您的部署以支持存档。</span><span class="sxs-lookup"><span data-stu-id="cd709-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="cd709-106">本主题中的信息介绍如何使用拓扑生成器以：</span><span class="sxs-lookup"><span data-stu-id="cd709-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="cd709-107">向拓扑添加存档数据库。</span><span class="sxs-lookup"><span data-stu-id="cd709-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="cd709-108">发布更新的拓扑以向您 Skype 业务服务器部署添加存档数据库。</span><span class="sxs-lookup"><span data-stu-id="cd709-108">Publish the updated topology to add the archiving database to your Skype for Business Server deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cd709-109">如果您想要使用 Microsoft Exchange 集成来部署中存储存档数据和 Exchange 服务器上的所有用户的文件，不指定**存档 SQL Server 存储**或**使用 SQL Server 存储镜像**的信息。</span><span class="sxs-lookup"><span data-stu-id="cd709-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="cd709-110">向拓扑添加存档数据库</span><span class="sxs-lookup"><span data-stu-id="cd709-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="cd709-111">业务服务器运行 Skype 的计算机上或在其上 Skype 的安装了 Business Server 管理工具，使用登录本地 Users 组 （或具有同等用户权限的帐户） 的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="cd709-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="cd709-112">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="cd709-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="cd709-113">在控制台树中，导航到您要在其中部署存档的前端池，然后单击要在其中部署存档的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="cd709-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="cd709-114">在“**操作**”菜单上，单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="cd709-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="cd709-115">在“**编辑属性**”对话框中，单击“**常规**”。</span><span class="sxs-lookup"><span data-stu-id="cd709-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="cd709-116">向下滚动到“**存档**”。</span><span class="sxs-lookup"><span data-stu-id="cd709-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="cd709-117">选中“**存档**”复选框。</span><span class="sxs-lookup"><span data-stu-id="cd709-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="cd709-118">下**存档 SQL Server 存储，请**执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="cd709-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="cd709-119">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="cd709-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="cd709-120">如果您的所有用户都驻留在 Microsoft Exchange Server 2013 或上方，您可以存档 Skype 业务通信的所有用户在 Exchange。</span><span class="sxs-lookup"><span data-stu-id="cd709-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="cd709-121">在这种情况下，您无需配置 SQL Server 存档存储。</span><span class="sxs-lookup"><span data-stu-id="cd709-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="cd709-122">若要指定新的 SQL Server 存储，请单击**新建**，然后在**定义新的 SQL Server 存储**对话框中，执行以下：</span><span class="sxs-lookup"><span data-stu-id="cd709-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="cd709-123">在**SQL Server FQDN**中，指定要在其创建新的 SQL Server 存储的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cd709-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="cd709-124">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="cd709-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="cd709-125">如果指定的 SQL Server 实例处于镜像关系中，选择**此 SQL 实例处于镜像关系中**复选框，然后，在**镜像端口号**框中，指定的端口号。</span><span class="sxs-lookup"><span data-stu-id="cd709-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="cd709-126">如果您想要使用 SQL Server 存储镜像，选择**启用 SQL Server 存储镜像**，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cd709-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="cd709-127">若要将现有 SQL Server 存储用于镜像，请在**存档 SQL Server 存储镜像**下拉列表框中，单击您想要用于镜像的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="cd709-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="cd709-128">若要指定新的 SQL Server 存储用于镜像，请单击**新建**，然后在**定义新的 SQL Server 存储**对话框中，执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="cd709-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
     <span data-ttu-id="cd709-129">a.</span><span class="sxs-lookup"><span data-stu-id="cd709-129">a.</span></span> <span data-ttu-id="cd709-130">在**SQL Server FQDN**中，指定要在其创建新的 SQL Server 存储的 SQL Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cd709-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
     <span data-ttu-id="cd709-131">b.</span><span class="sxs-lookup"><span data-stu-id="cd709-131">b.</span></span> <span data-ttu-id="cd709-132">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="cd709-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
     <span data-ttu-id="cd709-133">c.</span><span class="sxs-lookup"><span data-stu-id="cd709-133">c.</span></span> <span data-ttu-id="cd709-134">如果指定的 SQL Server 实例处于镜像关系中，选择**此 SQL 实例处于镜像关系中**复选框，然后，在**镜像端口号**框中，指定的端口号。</span><span class="sxs-lookup"><span data-stu-id="cd709-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="cd709-135">如果您启用 SQL Server 镜像，并且想要包括 SQL Server 镜像见证 （的第三个单独 SQL Server 实例的可以检测到主 SQL Server 实例和镜像实例的运行状况），选择**使用 SQL Server 镜像见证启用自动故障转移**复选框，，然后执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="cd709-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
     <span data-ttu-id="cd709-136">a.</span><span class="sxs-lookup"><span data-stu-id="cd709-136">a.</span></span> <span data-ttu-id="cd709-137">在**SQL Server FQDN**中，指定要在其创建新的 SQL Server 镜像见证的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="cd709-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
     <span data-ttu-id="cd709-138">b.</span><span class="sxs-lookup"><span data-stu-id="cd709-138">b.</span></span> <span data-ttu-id="cd709-139">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。</span><span class="sxs-lookup"><span data-stu-id="cd709-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
     <span data-ttu-id="cd709-140">c.</span><span class="sxs-lookup"><span data-stu-id="cd709-140">c.</span></span> <span data-ttu-id="cd709-141">如果指定的 SQL Server 实例处于镜像关系中，选择**此 SQL 实例处于镜像关系中**复选框，然后，在**镜像端口号**框中，指定的端口号。</span><span class="sxs-lookup"><span data-stu-id="cd709-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="cd709-142">若要保存配置，请单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="cd709-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="cd709-143">发布更新的拓扑以将存档数据库添加到部署</span><span class="sxs-lookup"><span data-stu-id="cd709-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="cd709-144">业务服务器运行 Skype 的计算机上或在其上 Skype 的安装了 Business Server 管理工具，使用登录本地 Users 组 （或具有同等用户权限的帐户） 的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="cd709-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cd709-145">您可以使用本地用户组的成员的帐户定义拓扑，但要发布拓扑，需要将服务器添加到拓扑，必须使用**Domain Admins**组和**RTCUniversalServer 的成员的帐户Admins**组，并使用的业务服务器文件存储的 Skype （以便拓扑生成器可以配置所需的随机访问控制列表 (Dacl)，或一个文件共享上具有完全控制权限 （读取、 写入和修改）具有同等权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="cd709-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="cd709-146">打开您在上一节使用拓扑生成器中创建的拓扑。</span><span class="sxs-lookup"><span data-stu-id="cd709-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="cd709-147">在控制台树中，右键单击**Skype 业务服务器**，，然后单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="cd709-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="cd709-148">在“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cd709-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="cd709-149">在“**创建数据库**”页上，确认已经选择了数据库，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cd709-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="cd709-150">如果没有创建数据库所需的相应权限，则可以取消数据库的选择，并且具有相应权限的人可以创建数据库。</span><span class="sxs-lookup"><span data-stu-id="cd709-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="cd709-151">可以使用拓扑生成器安装 > 仅专用 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="cd709-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="cd709-152">与其他服务器组件并置的 SQL Server 上的数据库必须通过在该计算机上运行本地安装程序进行安装。</span><span class="sxs-lookup"><span data-stu-id="cd709-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="cd709-153">在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="cd709-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cd709-154">发布拓扑后，必须配置存档选项和策略，然后才能存档任何内容。</span><span class="sxs-lookup"><span data-stu-id="cd709-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="cd709-155">有关详细信息，请参阅[配置存档选项 Skype 业务服务器](configure-archiving-options.md)和[配置存档策略的 Skype 业务服务器](configure-archiving-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cd709-155">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server](configure-archiving-policies.md).</span></span> 
  

