---
title: 'Lync Server 2013: 更改存档数据库选项'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a98c2efc0dc956a6b8c33f2fcf065f629e5e57d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="fedb4-102">在 Lync Server 2013 中更改存档数据库选项</span><span class="sxs-lookup"><span data-stu-id="fedb4-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fedb4-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fedb4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fedb4-104">如果使用 SQL Server 存储部署存档以便为任何用户存档存储, 则可以更改以下数据库存储:</span><span class="sxs-lookup"><span data-stu-id="fedb4-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="fedb4-105">将不同的 SQL Server 数据库用于存档存储。</span><span class="sxs-lookup"><span data-stu-id="fedb4-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="fedb4-106">这包括用于 SQL Server 镜像的主存档数据库和任何数据库。</span><span class="sxs-lookup"><span data-stu-id="fedb4-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="fedb4-107">切换到 Microsoft Exchange 集成以在 Exchange 2013 服务器上存储存档数据和文件。</span><span class="sxs-lookup"><span data-stu-id="fedb4-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="fedb4-108">如果你的所有用户都托管在 Exchange 2013 服务器上, 并且你希望为部署中的所有用户使用 Microsoft Exchange 存储, 则应从拓扑中删除 SQL Server 应用商店数据库。</span><span class="sxs-lookup"><span data-stu-id="fedb4-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="fedb4-109">若要执行上述任一更改, 必须运行拓扑生成器, 进行更改, 然后再次发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="fedb4-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="fedb4-110">可以使用拓扑生成器执行此操作。</span><span class="sxs-lookup"><span data-stu-id="fedb4-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="fedb4-111">不要指定**存档 Sql server 存储**或**启用 sql server 存储镜像**信息, 除非您没有在 Exchange 2013 服务器上托管的 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="fedb4-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="fedb4-112">更改存档数据库选项</span><span class="sxs-lookup"><span data-stu-id="fedb4-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="fedb4-113">在运行 Lync Server 2013 的计算机上, 或安装了 Lync Server 管理工具的计算机上, 使用属于本地 Users 组的成员 (或具有等效用户权限的帐户) 登录。</span><span class="sxs-lookup"><span data-stu-id="fedb4-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fedb4-114">你可以通过使用属于本地用户组的成员的帐户定义拓扑, 但要发布将组件添加到拓扑所需的拓扑, 你必须使用<STRONG>域管理员</STRONG>组和 RTCUniversalSer 的成员帐户。 <STRONG>verAdmins</STRONG>组, 具有对 Lync Server 2013 文件存储使用的文件共享的完全控制权限 (即读取、写入和修改), 以便拓扑生成器可以配置所需的随机访问控制列表 (Dacl) 或具有等效权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="fedb4-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="fedb4-115">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="fedb4-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="fedb4-116">在控制台树中，导航到您在其中部署了存档的前端池，然后单击要在其中更改数据库选项的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="fedb4-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="fedb4-117">在“**操作**”菜单上，单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="fedb4-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="fedb4-118">在“**编辑属性**”对话框中，单击“**常规**”。</span><span class="sxs-lookup"><span data-stu-id="fedb4-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="fedb4-119">向下滚动到“**存档**”。</span><span class="sxs-lookup"><span data-stu-id="fedb4-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="fedb4-120">在“**存档**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fedb4-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="fedb4-121">若要切换到其他现有 SQL Server 存储，请在“**存档 SQL Server 存储**”下的下拉列表框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fedb4-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="fedb4-122">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="fedb4-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="fedb4-123">若要指定新的 SQL Server 存储，请单击“**新建**”，然后在“**定义新的 SQL Server 存储**”对话框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fedb4-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="fedb4-124">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="fedb4-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="fedb4-125">若要指定新的 SQL Server 应用商店, 请单击 "**新建**", 然后在 "**定义新的 SQL server 存储**" 对话框中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="fedb4-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="fedb4-126">在**SQL SERVER FQDN**中, 指定要在其上创建新的 SQL Server 应用商店的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fedb4-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="fedb4-127">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="fedb4-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="fedb4-128">如果指定的 SQL Server 实例位于镜像关系中, 请选中 "**此 sql 实例处于镜像关系中**" 复选框, 然后在 "**镜像端口号**" 中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="fedb4-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="fedb4-129">若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“**启用 SQL Server 存储镜像**”，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fedb4-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="fedb4-130">若要使用现有的 SQL Server 应用商店进行镜像, 请在 "**存档 Sql server 存储镜像**" 下拉列表框中, 单击要用于镜像的 SQL server 应用商店的名称。</span><span class="sxs-lookup"><span data-stu-id="fedb4-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="fedb4-131">若要为镜像指定新的 SQL Server 存储, 请单击 "**新建**", 然后在 "**定义新的 SQL server 存储**" 对话框中, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="fedb4-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="fedb4-132">在**SQL SERVER FQDN**中, 指定要在其上创建新的 sql server 应用商店的 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fedb4-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="fedb4-133">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="fedb4-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="fedb4-134">如果指定的 SQL Server 实例位于镜像关系中, 请选中 "**此 sql 实例处于镜像关系中**" 复选框, 然后在 "**镜像端口号**" 中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="fedb4-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="fedb4-135">如果启用 SQL Server 镜像, 并且想要添加或更改 SQL Server 镜像见证 (第三个单独的 SQL Server 实例, 它可以检测主 SQL Server 服务器和镜像实例的运行状况), 请选择 "**使用 SQL server 镜像见证""启用自动故障转移**" 复选框, 然后执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="fedb4-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="fedb4-136">在**SQL SERVER FQDN**中, 指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fedb4-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="fedb4-137">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。</span><span class="sxs-lookup"><span data-stu-id="fedb4-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="fedb4-138">如果指定的 SQL Server 实例位于镜像关系中, 请选中 "**此 sql 实例处于镜像关系中**" 复选框, 然后在 "**镜像端口号**" 中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="fedb4-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="fedb4-139">若要切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 2013 服务器上 (如果你的部署中的所有用户都托管在 Exchange 2013 服务器上), 请删除存档数据库的所有信息。</span><span class="sxs-lookup"><span data-stu-id="fedb4-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fedb4-140">如果你的任何 Lync 用户均未托管在 Exchange 2013 服务器上, 请不要删除 SQL Server 存储信息。</span><span class="sxs-lookup"><span data-stu-id="fedb4-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="fedb4-141">若要保存配置，请单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="fedb4-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fedb4-142">在发布新拓扑之前, 在拓扑生成器中所做的更改不会生效。</span><span class="sxs-lookup"><span data-stu-id="fedb4-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="fedb4-143">有关详细信息, 请参阅<A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">发布更新后的拓扑以在 Lync Server 2013</A>中的部署文档中添加存档数据库。</span><span class="sxs-lookup"><span data-stu-id="fedb4-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

