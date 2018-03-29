---
title: 在 Skype for Business Server 2015 中将存档数据库添加到现有部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 摘要： 阅读本主题，了解如何添加到您的业务服务器 2015年部署 Skype 的存档数据库。
ms.openlocfilehash: 09185eed2a8bd0cc9b2a03fc6361abeadbd01829
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server-2015"></a><span data-ttu-id="af349-103">在 Skype for Business Server 2015 中将存档数据库添加到现有部署</span><span class="sxs-lookup"><span data-stu-id="af349-103">Add archiving databases to an existing deployment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="af349-104">**摘要：**阅读本主题，了解如何添加到您的业务服务器 2015年部署 Skype 的存档数据库。</span><span class="sxs-lookup"><span data-stu-id="af349-104">**Summary:** Read this topic to learn how to add archiving databases to your Skype for Business Server 2015 deployment.</span></span>
  
<span data-ttu-id="af349-105">必须先在拓扑中纳入存档，然后才能配置您的部署以支持存档。</span><span class="sxs-lookup"><span data-stu-id="af349-105">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="af349-106">本主题中的信息介绍如何使用到拓扑生成器：</span><span class="sxs-lookup"><span data-stu-id="af349-106">The information in this topic explains how to use Topology Builder to:</span></span>
  
- <span data-ttu-id="af349-107">向拓扑添加存档数据库。</span><span class="sxs-lookup"><span data-stu-id="af349-107">Add an archiving database to your topology.</span></span>
    
- <span data-ttu-id="af349-108">发布更新拓扑结构中，将添加到您的业务服务器 2015年部署 Skype 存档数据库。</span><span class="sxs-lookup"><span data-stu-id="af349-108">Publish the updated topology to add the archiving database to your Skype for Business Server 2015 deployment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="af349-109">如果您想要使用 Microsoft Exchange 集成在您的部署中存储存档数据和所有用户的 Exchange 服务器上的文件，则不需要指定**存档的 SQL Server 存储**或**使用 SQL Server 存储镜像**信息。</span><span class="sxs-lookup"><span data-stu-id="af349-109">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange servers for all your users in your deployment, do not specify **Archiving SQL Server store** or **Use SQL Server Store mirroring** information.</span></span>
  
### <a name="add-an-archiving-database-to-your-topology"></a><span data-ttu-id="af349-110">向拓扑添加存档数据库</span><span class="sxs-lookup"><span data-stu-id="af349-110">Add an archiving database to your topology</span></span>

1. <span data-ttu-id="af349-111">运行 Skype 业务服务器的计算机上或在其上 Skype 的安装业务服务器管理工具，使用登录的帐户是本地用户组 （或具有相当的用户权限的帐户） 的成员。</span><span class="sxs-lookup"><span data-stu-id="af349-111">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
2. <span data-ttu-id="af349-112">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="af349-112">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="af349-113">在控制台树中，导航到您要在其中部署存档的前端池，然后单击要在其中部署存档的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="af349-113">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy archiving.</span></span>
    
4. <span data-ttu-id="af349-114">在“**操作**”菜单上，单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="af349-114">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="af349-115">在“**编辑属性**”对话框中，单击“**常规**”。</span><span class="sxs-lookup"><span data-stu-id="af349-115">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="af349-116">向下滚动到“**存档**”。</span><span class="sxs-lookup"><span data-stu-id="af349-116">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="af349-117">选中“**存档**”复选框。</span><span class="sxs-lookup"><span data-stu-id="af349-117">Select the **Archiving** check box.</span></span>
    
8. <span data-ttu-id="af349-118">**存档的 SQL Server 存储区**下, 执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="af349-118">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
   - <span data-ttu-id="af349-119">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="af349-119">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="af349-120">如果 Microsoft Exchange Server 2013年或以上托管您的所有用户，您可以存档 Skype 业务交流所有用户在 Exchange。</span><span class="sxs-lookup"><span data-stu-id="af349-120">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Skype for Business communications for all your users in Exchange.</span></span> <span data-ttu-id="af349-121">在这种情况下，您不需要配置 SQL Server 存档存储。</span><span class="sxs-lookup"><span data-stu-id="af349-121">In this case, you don't need to configure SQL Server Archiving store.</span></span>
    
   - <span data-ttu-id="af349-122">若要指定新的 SQL Server 存储，单击**新建**，然后在**定义新建 SQL Server 存储**对话框中，执行下列：</span><span class="sxs-lookup"><span data-stu-id="af349-122">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
   - <span data-ttu-id="af349-123">在**SQL Server FQDN**，指定您要在其创建新的 SQL Server 存储的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="af349-123">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
   - <span data-ttu-id="af349-124">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="af349-124">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
   - <span data-ttu-id="af349-125">如果指定的 SQL Server 实例处于镜像关系，选择**此 SQL 实例处于镜像关系**复选框，然后在**镜像端口编号**，指定的端口号。</span><span class="sxs-lookup"><span data-stu-id="af349-125">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
9. <span data-ttu-id="af349-126">如果您想要使用 SQL Server 存储镜像，选择**启用 SQL Server 存储镜像**，然后请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="af349-126">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
   - <span data-ttu-id="af349-127">要用于现有的 SQL Server 存储镜像中**存档的 SQL Server 存储镜像**下拉列表框中，单击想要使用镜像的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="af349-127">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
   - <span data-ttu-id="af349-128">若要指定新的 SQL Server 存储镜像，单击**新建**，然后在**定义新建 SQL Server 存储**对话框中，执行以下任一项：</span><span class="sxs-lookup"><span data-stu-id="af349-128">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
    <span data-ttu-id="af349-129">a.</span><span class="sxs-lookup"><span data-stu-id="af349-129">a.</span></span> <span data-ttu-id="af349-130">在**SQL Server FQDN**，指定您要在其创建新的 SQL Server 存储 SQL Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="af349-130">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
    <span data-ttu-id="af349-131">b.</span><span class="sxs-lookup"><span data-stu-id="af349-131">b.</span></span> <span data-ttu-id="af349-132">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="af349-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
    <span data-ttu-id="af349-133">c.</span><span class="sxs-lookup"><span data-stu-id="af349-133">c.</span></span> <span data-ttu-id="af349-134">如果指定的 SQL Server 实例处于镜像关系，选择**此 SQL 实例处于镜像关系**复选框，然后在**镜像端口编号**，指定的端口号。</span><span class="sxs-lookup"><span data-stu-id="af349-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="af349-135">如果启用 SQL Server 镜像并希望包含镜像见证 （的第三个独立 SQL Server 实例可以检测到主 SQL Server 实例和镜像实例的运行状况） 的 SQL Server 时，选择以启用自动**使用 SQL Server 镜像见证故障切换**复选框，然后再执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="af349-135">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
    <span data-ttu-id="af349-136">a.</span><span class="sxs-lookup"><span data-stu-id="af349-136">a.</span></span> <span data-ttu-id="af349-137">在**SQL Server FQDN**，指定您要在其创建镜像见证新的 SQL Server 的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="af349-137">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
    <span data-ttu-id="af349-138">b.</span><span class="sxs-lookup"><span data-stu-id="af349-138">b.</span></span> <span data-ttu-id="af349-139">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。</span><span class="sxs-lookup"><span data-stu-id="af349-139">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
    <span data-ttu-id="af349-140">c.</span><span class="sxs-lookup"><span data-stu-id="af349-140">c.</span></span> <span data-ttu-id="af349-141">如果指定的 SQL Server 实例处于镜像关系，选择**此 SQL 实例处于镜像关系**复选框，然后在**镜像端口编号**，指定的端口号。</span><span class="sxs-lookup"><span data-stu-id="af349-141">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
10. <span data-ttu-id="af349-142">若要保存配置，请单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="af349-142">To save the configuration, click **OK**.</span></span>
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a><span data-ttu-id="af349-143">发布更新的拓扑以将存档数据库添加到部署</span><span class="sxs-lookup"><span data-stu-id="af349-143">Publish the updated topology to add an archiving database to your deployment</span></span>

1. <span data-ttu-id="af349-144">运行 Skype 业务服务器的计算机上或在其上 Skype 的安装业务服务器管理工具，使用登录的帐户是本地用户组 （或具有相当的用户权限的帐户） 的成员。</span><span class="sxs-lookup"><span data-stu-id="af349-144">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="af349-145">您可以通过使用本地用户组的成员帐户定义拓扑，但若要发布一个拓扑结构，需要将服务器添加到拓扑结构中，则必须使用的帐户是**域管理员**组和**RTCUniversalServer 的成员管理员**组中，并且使用的业务服务器文件存储的 Skype （这样拓扑生成器可以配置所需的自由访问控制列表 (Dacl)，或一个文件共享具有完全控制权限 （读取、 写入和修改）具有同等权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="af349-145">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file share that you are using for the Skype for Business Server file store (so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="af349-146">打开您在上一节使用拓扑生成器中创建的拓扑。</span><span class="sxs-lookup"><span data-stu-id="af349-146">Open the topology you created in the previous section using Topology Builder.</span></span>
    
3. <span data-ttu-id="af349-147">在控制台树中， **Skype 业务服务器**，右键单击，然后单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="af349-147">In the console tree, right-click **Skype for Business Server**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="af349-148">在“**发布拓扑**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="af349-148">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="af349-149">在“**创建数据库**”页上，确认已经选择了数据库，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="af349-149">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="af349-150">如果没有创建数据库所需的相应权限，则可以取消数据库的选择，并且具有相应权限的人可以创建数据库。</span><span class="sxs-lookup"><span data-stu-id="af349-150">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="af349-151">> 可以通过使用拓扑生成器安装只有在专用的 SQL 服务器上的数据库。</span><span class="sxs-lookup"><span data-stu-id="af349-151">> Only databases on dedicated SQL Servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="af349-152">与其他服务器组件并置的 SQL Server 上的数据库必须通过在该计算机上运行本地安装程序进行安装。</span><span class="sxs-lookup"><span data-stu-id="af349-152">Databases on SQL Servers that are collocated with other server components must be installed by running local setup on that computer.</span></span> 
  
6. <span data-ttu-id="af349-153">在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="af349-153">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="af349-154">发布拓扑后，必须配置存档选项和策略，然后才能存档任何内容。</span><span class="sxs-lookup"><span data-stu-id="af349-154">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="af349-155">有关详细信息，请参阅[配置归档业务服务器 2015年的 Skype 的选项](configure-archiving-options.md)和[配置归档业务服务器 2015年的 Skype 的策略](configure-archiving-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="af349-155">For details, see [Configure archiving options for Skype for Business Server 2015](configure-archiving-options.md) and [Configure archiving policies for Skype for Business Server 2015](configure-archiving-policies.md).</span></span> 
  

