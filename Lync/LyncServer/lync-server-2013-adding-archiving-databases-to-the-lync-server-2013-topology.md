---
title: 'Lync Server 2013: 将存档数据库添加到 Lync Server 2013 拓扑'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe77c57050d6d6c70d5818405fd657d5a8fd3f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="bc281-102">将存档数据库添加到 Lync Server 2013 拓扑</span><span class="sxs-lookup"><span data-stu-id="bc281-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc281-103">_**主题上次修改时间:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="bc281-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="bc281-104">必须先在拓扑中纳入存档，然后才能配置您的部署以支持存档。</span><span class="sxs-lookup"><span data-stu-id="bc281-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="bc281-105">本主题中的信息介绍了如何使用拓扑生成器将存档添加到现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="bc281-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc281-106">如果你想要使用 Microsoft Exchange 集成在 Exchange 2013 服务器上为你的部署中的所有用户存储存档数据和文件, 请不要指定<STRONG>存档 SQL server 存储</STRONG>或<STRONG>使用 Sql Server 应用商店镜像</STRONG>信息。</span><span class="sxs-lookup"><span data-stu-id="bc281-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="bc281-107">将存档数据库支持添加到你的拓扑</span><span class="sxs-lookup"><span data-stu-id="bc281-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="bc281-108">在运行 Lync Server 2013 的计算机上, 或安装了 Lync Server 管理工具的计算机上, 使用属于本地 Users 组的成员 (或具有等效用户权限的帐户) 登录。</span><span class="sxs-lookup"><span data-stu-id="bc281-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bc281-109">你可以通过使用属于本地用户组的成员的帐户定义拓扑, 但要发布将服务器添加到拓扑所需的拓扑, 你必须使用<STRONG>域管理员</STRONG>组和 RTCUniversalServer 的成员帐户。 <STRONG>管理员</STRONG>组, 并且具有对 Lync Server 2013 文件存储所使用的文件共享的完全控制权限 (即读取、写入和修改), 以便拓扑生成器可以配置所需的随机访问控制列表 (dacl)或具有等效权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="bc281-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="bc281-110">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="bc281-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="bc281-111">在控制台树中, 导航到要在其中部署存档的前端池, 然后单击要在其中部署存档的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="bc281-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="bc281-112">在“**操作**”菜单上，单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="bc281-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="bc281-113">在“**编辑属性**”对话框中，单击“**常规**”。</span><span class="sxs-lookup"><span data-stu-id="bc281-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="bc281-114">向下滚动到“**存档**”。</span><span class="sxs-lookup"><span data-stu-id="bc281-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="bc281-115">选中“**存档**”复选框。</span><span class="sxs-lookup"><span data-stu-id="bc281-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="bc281-116">在 "**存档 SQL Server 应用商店" 下,** 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="bc281-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="bc281-117">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="bc281-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="bc281-118">如果你的所有用户都托管在 Microsoft Exchange Server 2013 或更高版本上, 你可以将 Lync 通信存档到 Exchange 中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="bc281-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="bc281-119">在这种情况下, 你无需配置 SQL Server 存档存储。</span><span class="sxs-lookup"><span data-stu-id="bc281-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="bc281-120">若要指定新的 SQL Server 应用商店, 请单击 "**新建**", 然后在 "**定义新的 SQL server 存储**" 对话框中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="bc281-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="bc281-121">在**SQL SERVER FQDN**中, 指定要在其上创建新的 SQL Server 应用商店的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bc281-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="bc281-122">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="bc281-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="bc281-123">如果指定的 SQL Server 实例位于镜像关系中, 请选中 "**此 sql 实例处于镜像关系中**" 复选框, 然后在 "**镜像端口号**" 中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="bc281-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="bc281-124">如果要使用 SQL Server 应用商店镜像, 请选择 "**启用 Sql Server 应用商店镜像**", 然后执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="bc281-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="bc281-125">若要使用现有的 SQL Server 应用商店进行镜像, 请在 "**存档 Sql server 存储镜像**" 下拉列表框中, 单击要用于镜像的 SQL server 应用商店的名称。</span><span class="sxs-lookup"><span data-stu-id="bc281-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="bc281-126">若要为镜像指定新的 SQL Server 存储, 请单击 "**新建**", 然后在 "**定义新的 SQL server 存储**" 对话框中, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="bc281-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="bc281-127">在**SQL SERVER FQDN**中, 指定要在其上创建新的 sql server 应用商店的 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bc281-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="bc281-128">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="bc281-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="bc281-129">如果指定的 SQL Server 实例位于镜像关系中, 请选中 "**此 sql 实例处于镜像关系中**" 复选框, 然后在 "**镜像端口号**" 中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="bc281-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="bc281-130">如果启用 SQL Server 镜像, 并且希望包括 SQL Server 镜像见证 (第三个单独的 SQL Server 实例, 它可以检测主 SQL Server 服务器和镜像实例的运行状况), 请选择 "**使用 SQL server 镜像见证" 启用"自动故障转移**" 复选框, 然后执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="bc281-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="bc281-131">在**SQL SERVER FQDN**中, 指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="bc281-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="bc281-132">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。</span><span class="sxs-lookup"><span data-stu-id="bc281-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="bc281-133">如果指定的 SQL Server 实例位于镜像关系中, 请选中 "**此 sql 实例处于镜像关系中**" 复选框, 然后在 "**镜像端口号**" 中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="bc281-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="bc281-134">若要保存配置，请单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bc281-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

