---
title: Lync Server 2013：更改存档数据库选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f06b1327b1f0718015de0a877963ad7eb04cc03c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502709"
---
# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="8685c-102">在 Lync Server 2013 中更改存档数据库选项</span><span class="sxs-lookup"><span data-stu-id="8685c-102">Changing Archiving database options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8685c-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8685c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8685c-104">如果使用 SQL Server 存储部署存档以存档任何用户的存储，则可以进行以下数据库存储更改：</span><span class="sxs-lookup"><span data-stu-id="8685c-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="8685c-105">使用不同的 SQL Server 数据库存档存储。</span><span class="sxs-lookup"><span data-stu-id="8685c-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="8685c-106">这包括主存档数据库和用于 SQL Server 镜像的任何数据库。</span><span class="sxs-lookup"><span data-stu-id="8685c-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="8685c-107">切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 2013 服务器上。</span><span class="sxs-lookup"><span data-stu-id="8685c-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="8685c-108">如果你的所有用户都驻留在 Exchange 2013 服务器上，并且想要对部署中的所有用户使用 Microsoft Exchange 存储，则应从拓扑中删除 SQL Server 存储数据库。</span><span class="sxs-lookup"><span data-stu-id="8685c-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="8685c-109">若要进行上述任一更改，必须运行拓扑生成器，进行更改，然后再次发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="8685c-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="8685c-110">您可以使用拓扑生成器执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8685c-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="8685c-111">不要指定 **存档 Sql server 存储** 或 **启用 sql server 存储镜像** 信息，除非您没有在 Exchange 2013 服务器上托管的 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="8685c-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="8685c-112">更改存档数据库选项</span><span class="sxs-lookup"><span data-stu-id="8685c-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="8685c-113">在运行 Lync Server 2013 的计算机上，或安装了 Lync Server 管理工具的计算机上，使用属于本地用户组成员的帐户登录 (或者) 具有同等用户权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="8685c-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8685c-114">您可以通过使用属于本地用户组成员的帐户来定义拓扑，但若要发布将组件添加到拓扑所需的拓扑，必须使用属于 <STRONG>Domain Admins</STRONG> 组和 <STRONG>RTCUniversalServerAdmins</STRONG> 组成员的帐户。并且具有 "完全控制" 权限 (即读取、写入和修改要用于 Lync Server 2013 文件存储的文件共享上的) ，因此拓扑生成器可以配置所需的任意自由访问控制列表 (dacl) 或具有等效权限的帐户。 (</span><span class="sxs-lookup"><span data-stu-id="8685c-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="8685c-115">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="8685c-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="8685c-116">在控制台树中，导航到您在其中部署了存档的前端池，然后单击要在其中更改数据库选项的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="8685c-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="8685c-117">在“操作”\*\*\*\* 菜单上，单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8685c-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="8685c-118">在“编辑属性”\*\*\*\* 对话框中，单击“常规”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8685c-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="8685c-119">向下滚动到“存档”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8685c-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="8685c-120">在“存档”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8685c-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="8685c-121">若要切换到其他现有 SQL Server 存储，请在“存档 SQL Server 存储”\*\*\*\* 下的下拉列表框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8685c-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="8685c-122">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="8685c-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="8685c-123">若要指定新的 SQL Server 存储，请单击“新建”\*\*\*\*，然后在“定义新的 SQL Server 存储”\*\*\*\* 对话框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8685c-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="8685c-124">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="8685c-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="8685c-125">若要指定新的 SQL Server 存储，请单击 " **新建**"，然后在 " **定义新的 SQL server 存储** " 对话框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8685c-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="8685c-126">在 " **SQL SERVER FQDN**" 中，指定要在其上创建新 SQL Server 存储的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8685c-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="8685c-127">单击“默认实例”\*\*\*\* 以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”\*\*\*\*，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="8685c-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="8685c-128">如果指定的 SQL Server 实例位于镜像关系中，请选中 " **此 sql 实例处于镜像关系中** " 复选框，然后在 " **镜像端口号**" 中，指定端口号。</span><span class="sxs-lookup"><span data-stu-id="8685c-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="8685c-129">若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“启用 SQL Server 存储镜像”\*\*\*\*，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8685c-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="8685c-130">若要将现有的 SQL Server 存储用于镜像，请在 " **存档 Sql server 存储镜像** " 下拉列表框中，单击要用于镜像的 SQL server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="8685c-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="8685c-131">若要指定新的 SQL Server 存储进行镜像，请单击 " **新建**"，然后在 " **定义新的 sql server 存储** " 对话框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8685c-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="8685c-132">在 " **SQL SERVER FQDN**" 中，指定要在其上创建新 sql server 存储的 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8685c-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="8685c-133">单击“默认实例”\*\*\*\* 以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”\*\*\*\*，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="8685c-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="8685c-134">如果指定的 SQL Server 实例位于镜像关系中，请选中 " **此 sql 实例处于镜像关系中** " 复选框，然后在 " **镜像端口号**" 中，指定端口号。</span><span class="sxs-lookup"><span data-stu-id="8685c-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="8685c-135">如果启用 SQL Server 镜像，并且想要添加或更改 SQL Server 镜像见证 (第三个单独的 SQL Server 实例（可检测主 SQL Server 服务器和镜像实例的运行状况）) ，请选中 " **使用 SQL Server 镜像见证启用自动故障转移** " 复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8685c-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="8685c-136">在 " **SQL SERVER FQDN**" 中，指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8685c-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="8685c-137">单击“默认实例”\*\*\*\* 以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”\*\*\*\*，然后指定要用于镜像见证的实例。</span><span class="sxs-lookup"><span data-stu-id="8685c-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="8685c-138">如果指定的 SQL Server 实例位于镜像关系中，请选中 " **此 sql 实例处于镜像关系中** " 复选框，然后在 " **镜像端口号**" 中，指定端口号。</span><span class="sxs-lookup"><span data-stu-id="8685c-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="8685c-139">若要切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 2013 服务器上 (如果部署中的所有用户都托管在 Exchange 2013 服务器) 上，则删除存档数据库的所有信息。</span><span class="sxs-lookup"><span data-stu-id="8685c-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8685c-140">如果您有任何 Lync 用户未驻留在 Exchange 2013 服务器上，请不要删除 SQL Server 存储信息。</span><span class="sxs-lookup"><span data-stu-id="8685c-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="8685c-141">若要保存配置，请单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8685c-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8685c-142">您在拓扑生成器中所做的更改在您发布新的拓扑之前不会生效。</span><span class="sxs-lookup"><span data-stu-id="8685c-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="8685c-143">有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">发布更新后的拓扑以在 Lync Server 2013 中添加存档数据库</A> 。</span><span class="sxs-lookup"><span data-stu-id="8685c-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

