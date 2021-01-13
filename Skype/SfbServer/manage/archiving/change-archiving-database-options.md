---
title: 更改 Skype for Business Server 中的存档数据库选项
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 摘要：了解如何更改 Skype for Business Server 的存档数据库选项。
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817692"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="3632c-103">更改 Skype for Business Server 中的存档数据库选项</span><span class="sxs-lookup"><span data-stu-id="3632c-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="3632c-104">**摘要：** 了解如何更改 Skype for Business Server 的存档数据库选项。</span><span class="sxs-lookup"><span data-stu-id="3632c-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="3632c-105">如果使用存档存储SQL Server任何用户的存档存储部署存档，您可以进行以下数据库存储更改：</span><span class="sxs-lookup"><span data-stu-id="3632c-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="3632c-106">使用不同的数据库SQL Server存档存储。</span><span class="sxs-lookup"><span data-stu-id="3632c-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="3632c-107">这包括主存档数据库和用于镜像SQL Server数据库。</span><span class="sxs-lookup"><span data-stu-id="3632c-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="3632c-108">切换到 Microsoft Exchange 集成以在 Exchange 服务器上存储存档数据和文件。</span><span class="sxs-lookup"><span data-stu-id="3632c-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="3632c-109">如果您的所有用户都位于 Exchange 服务器上，并且您希望对部署中的所有用户使用 Microsoft Exchange 存储，则应该从拓扑中删除 SQL Server 存储数据库。</span><span class="sxs-lookup"><span data-stu-id="3632c-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="3632c-110">若要进行上述任一更改，必须运行拓扑生成器，进行更改，然后再次发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="3632c-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="3632c-111">不要指定存档 **SQL Server或** 启用SQL Server存储 **镜像** 信息，除非你的 Skype for Business 用户未位于 Exchange 服务器上。</span><span class="sxs-lookup"><span data-stu-id="3632c-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="3632c-112">更改存档数据库选项</span><span class="sxs-lookup"><span data-stu-id="3632c-112">Change Archiving database options</span></span>

1. <span data-ttu-id="3632c-113">在运行 Skype for Business Server 或安装了 Skype for Business Server 管理工具的计算机上，使用本地用户组 (或具有同等用户权限的帐户登录) 。</span><span class="sxs-lookup"><span data-stu-id="3632c-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3632c-114">可以使用作为本地 Users 组的成员的帐户定义拓扑，但若要发布拓扑（向拓扑中添加组件是必需的）必须使用 Domain **Admins** 组和 **RTCUniversalServerAdmins** 组的成员帐户， 并且具有对要用于 Skype for Business Server 文件存储 (的文件共享的完全控制权限 (即读取、写入和修改) ，以便拓扑生成器可以配置所需的任意访问控制列表 (DACLS) 或具有同等权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="3632c-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="3632c-115">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="3632c-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="3632c-116">在控制台树中，导航到您在其中部署了存档的前端池，然后单击要在其中更改数据库选项的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="3632c-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="3632c-117">在“操作”菜单上，单击“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="3632c-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="3632c-118">在“编辑属性”对话框中，单击“常规”。</span><span class="sxs-lookup"><span data-stu-id="3632c-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="3632c-119">向下滚动到“存档”。</span><span class="sxs-lookup"><span data-stu-id="3632c-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="3632c-120">在“存档”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3632c-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="3632c-121">若要切换到其他现有 SQL Server 存储，请在“存档 SQL Server 存储”下的下拉列表框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3632c-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="3632c-122">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="3632c-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="3632c-123">若要指定新的 SQL Server 存储，请单击“新建”，然后在“定义新的 SQL Server 存储”对话框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3632c-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="3632c-124">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="3632c-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="3632c-125">若要指定新的SQL Server，请单击"新建 **"，然后在**"定义新的 SQL Server 应用商店"对话框中，执行以下操作： </span><span class="sxs-lookup"><span data-stu-id="3632c-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="3632c-126">在 **SQL Server FQDN** 中，指定要创建新数据库存储的服务器的 FQDN SQL Server FQDN。</span><span class="sxs-lookup"><span data-stu-id="3632c-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="3632c-127">单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="3632c-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="3632c-128">如果指定的 SQL Server 实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在镜像端口号中指定端口号。 </span><span class="sxs-lookup"><span data-stu-id="3632c-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3632c-129">若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“启用 SQL Server 存储镜像”，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3632c-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="3632c-130">若要将现有 SQL Server 存储用于镜像，请在"存档 **SQL Server** 存储镜像"下拉列表框中，单击要用于镜像的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="3632c-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="3632c-131">若要指定新的SQL Server存储进行镜像，请单击"新建"，然后在"定义新的 SQL Server **应用商店**"对话框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3632c-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="3632c-132">a.</span><span class="sxs-lookup"><span data-stu-id="3632c-132">a.</span></span> <span data-ttu-id="3632c-133">在 **SQL Server FQDN** 中，指定要SQL Server新存储的 SQL Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3632c-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="3632c-134">b.</span><span class="sxs-lookup"><span data-stu-id="3632c-134">b.</span></span> <span data-ttu-id="3632c-135">单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="3632c-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="3632c-136">c.</span><span class="sxs-lookup"><span data-stu-id="3632c-136">c.</span></span> <span data-ttu-id="3632c-137">如果指定的 SQL Server 实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在镜像端口号中指定端口号。 </span><span class="sxs-lookup"><span data-stu-id="3632c-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3632c-138">如果启用 SQL Server 镜像，并且想要添加或更改 SQL Server 镜像见证 (第三个可检测主 SQL Server 服务器和镜像实例) 运行状况的单独 SQL Server 实例，请选中"使用 **SQL Server** 镜像见证启用自动故障转移"复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3632c-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="3632c-139">a.</span><span class="sxs-lookup"><span data-stu-id="3632c-139">a.</span></span> <span data-ttu-id="3632c-140">在 **SQL Server FQDN** 中，指定要创建新的镜像见证SQL Server服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3632c-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="3632c-141">b.</span><span class="sxs-lookup"><span data-stu-id="3632c-141">b.</span></span> <span data-ttu-id="3632c-142">单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要用于镜像见证的实例。</span><span class="sxs-lookup"><span data-stu-id="3632c-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="3632c-143">c.</span><span class="sxs-lookup"><span data-stu-id="3632c-143">c.</span></span> <span data-ttu-id="3632c-144">如果指定的 SQL Server 实例位于镜像关系中，请选中"此 **SQL** 实例位于镜像关系中"复选框，然后在镜像端口号中指定端口号。 </span><span class="sxs-lookup"><span data-stu-id="3632c-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="3632c-145">若要切换到 Microsoft Exchange 集成以在 Exchange 服务器上存储存档数据和文件 (如果部署中的所有用户都位于 Exchange 服务器上) ，请删除存档数据库的所有信息。</span><span class="sxs-lookup"><span data-stu-id="3632c-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="3632c-146">如果有未在 Exchange 服务器上存储的任何 Skype for Business 用户，请不要删除SQL Server存储信息。</span><span class="sxs-lookup"><span data-stu-id="3632c-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="3632c-147">若要保存配置，请单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="3632c-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3632c-148">在发布新拓扑之前，在拓扑生成器中所做的更改不会生效。</span><span class="sxs-lookup"><span data-stu-id="3632c-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="3632c-149">有关详细信息，请参阅在 Skype for Business Server 中 [向现有部署添加存档数据库](../../deploy/deploy-archiving/add-archiving-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="3632c-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="3632c-150">使用"存档"选项更改存档数据库Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3632c-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="3632c-151">在大多数情况下，不需要更改存档数据库的位置，该位置是在安装存档服务器时指定的。</span><span class="sxs-lookup"><span data-stu-id="3632c-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="3632c-152">但是，如果发生硬件故障或其他问题，您可以使用 **Set-CsArchivingServer** cmdlet 将存档服务器指向新数据库。</span><span class="sxs-lookup"><span data-stu-id="3632c-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="3632c-153">以下示例更改 ArchivingServer：atl-cs-001.contoso.com存档服务器的存档数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="3632c-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="3632c-154">本示例中，新数据库位于 ArchivingDatabase：atl-sql-001.contoso.com：</span><span class="sxs-lookup"><span data-stu-id="3632c-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


