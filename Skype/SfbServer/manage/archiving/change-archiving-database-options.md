---
title: 在 Skype for Business 服务器中更改存档数据库选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 摘要：了解如何更改 Skype for business 服务器的存档数据库选项。
ms.openlocfilehash: c489117894eca69141ac07860c45aa07eb5916ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818974"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a><span data-ttu-id="9a51d-103">在 Skype for Business 服务器中更改存档数据库选项</span><span class="sxs-lookup"><span data-stu-id="9a51d-103">Change Archiving database options in Skype for Business Server</span></span>

<span data-ttu-id="9a51d-104">**摘要：** 了解如何更改 Skype for business 服务器的存档数据库选项。</span><span class="sxs-lookup"><span data-stu-id="9a51d-104">**Summary:** Learn how to change archiving database options for Skype for Business Server.</span></span>
  
<span data-ttu-id="9a51d-105">如果使用 SQL Server 存储部署存档以便为任何用户存档存储，则可以更改以下数据库存储：</span><span class="sxs-lookup"><span data-stu-id="9a51d-105">If you deploy archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>
  
- <span data-ttu-id="9a51d-106">将不同的 SQL Server 数据库用于存档存储。</span><span class="sxs-lookup"><span data-stu-id="9a51d-106">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="9a51d-107">这包括用于 SQL Server 镜像的主存档数据库和任何数据库。</span><span class="sxs-lookup"><span data-stu-id="9a51d-107">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>
    
- <span data-ttu-id="9a51d-108">切换到 Microsoft Exchange 集成以存储 Exchange 服务器上的存档数据和文件。</span><span class="sxs-lookup"><span data-stu-id="9a51d-108">Switch to Microsoft Exchange integration to store archiving data and files on Exchange servers.</span></span> <span data-ttu-id="9a51d-109">如果你的所有用户都托管在 Exchange 服务器上，并且你希望为部署中的所有用户使用 Microsoft Exchange 存储，则应从拓扑中删除 SQL Server 应用商店数据库。</span><span class="sxs-lookup"><span data-stu-id="9a51d-109">If all your users are homed on your Exchange servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span> 
    
<span data-ttu-id="9a51d-110">若要执行上述任一更改，必须运行拓扑生成器，进行更改，然后再次发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="9a51d-110">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="9a51d-111">不要指定**存档 Sql server 存储**或**启用 sql server 应用商店镜像**信息，除非您有未托管在 Exchange 服务器上的 Skype for business 用户。</span><span class="sxs-lookup"><span data-stu-id="9a51d-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Skype for Business users who are not homed on Exchange servers.</span></span>
  
## <a name="change-archiving-database-options"></a><span data-ttu-id="9a51d-112">更改存档数据库选项</span><span class="sxs-lookup"><span data-stu-id="9a51d-112">Change Archiving database options</span></span>

1. <span data-ttu-id="9a51d-113">在运行 Skype for Business 服务器或安装了 Skype for business 服务器管理工具的计算机上，使用属于本地 Users 组的成员的帐户（或具有等效用户权限的帐户）登录。</span><span class="sxs-lookup"><span data-stu-id="9a51d-113">On a computer that is running Skype for Business Server, or on which the Skype for Business Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9a51d-114">你可以通过使用属于本地用户组的成员的帐户定义拓扑，但要发布拓扑（这是将组件添加到拓扑所必需的）你必须使用属于**域管理员**组和**RTCUniversalServerAdmins**组成员的帐户，并且具有对 Skype for business Server 文件存储所使用的文件共享的完全控制权限（即读取、写入和修改），以便拓扑生成器可以配置所需的随机访问控制列表（Dacl）或具有等效权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="9a51d-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Skype for Business Server file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="9a51d-115">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="9a51d-115">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="9a51d-116">在控制台树中，导航到您在其中部署了存档的前端池，然后单击要在其中更改数据库选项的前端池的名称。</span><span class="sxs-lookup"><span data-stu-id="9a51d-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>
    
4. <span data-ttu-id="9a51d-117">在“**操作**”菜单上，单击“**编辑属性**”。</span><span class="sxs-lookup"><span data-stu-id="9a51d-117">In the **Action** menu, click **Edit Properties**.</span></span> 
    
5. <span data-ttu-id="9a51d-118">在“**编辑属性**”对话框中，单击“**常规**”。</span><span class="sxs-lookup"><span data-stu-id="9a51d-118">In the **Edit Properties** dialog box, click **General**.</span></span>
    
6. <span data-ttu-id="9a51d-119">向下滚动到“**存档**”。</span><span class="sxs-lookup"><span data-stu-id="9a51d-119">Scroll down to **Archiving**.</span></span>
    
7. <span data-ttu-id="9a51d-120">在“**存档**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9a51d-120">In **Archiving**, do the following:</span></span>
    
   - <span data-ttu-id="9a51d-121">若要切换到其他现有 SQL Server 存储，请在“**存档 SQL Server 存储**”下的下拉列表框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9a51d-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
    
   - <span data-ttu-id="9a51d-122">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="9a51d-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="9a51d-123">若要指定新的 SQL Server 存储，请单击“**新建**”，然后在“**定义新的 SQL Server 存储**”对话框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9a51d-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
    
     - <span data-ttu-id="9a51d-124">若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。</span><span class="sxs-lookup"><span data-stu-id="9a51d-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
    
     - <span data-ttu-id="9a51d-125">若要指定新的 SQL Server 应用商店，请单击 "**新建**"，然后在 "**定义新的 SQL server 存储**" 对话框中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9a51d-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
    
       - <span data-ttu-id="9a51d-126">在**SQL SERVER FQDN**中，指定要在其上创建新的 SQL Server 应用商店的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9a51d-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
    
       - <span data-ttu-id="9a51d-127">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="9a51d-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
    
       - <span data-ttu-id="9a51d-128">如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="9a51d-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="9a51d-129">若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“**启用 SQL Server 存储镜像**”，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9a51d-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
    
     - <span data-ttu-id="9a51d-130">若要使用现有的 SQL Server 应用商店进行镜像，请在 "**存档 Sql server 存储镜像**" 下拉列表框中，单击要用于镜像的 SQL server 应用商店的名称。</span><span class="sxs-lookup"><span data-stu-id="9a51d-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
     - <span data-ttu-id="9a51d-131">若要为镜像指定新的 SQL Server 存储，请单击 "**新建**"，然后在 "**定义新的 SQL server 存储**" 对话框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="9a51d-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
    
       <span data-ttu-id="9a51d-132">a.</span><span class="sxs-lookup"><span data-stu-id="9a51d-132">a.</span></span> <span data-ttu-id="9a51d-133">在**SQL SERVER FQDN**中，指定要在其上创建新的 sql server 应用商店的 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9a51d-133">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
    
       <span data-ttu-id="9a51d-134">b.</span><span class="sxs-lookup"><span data-stu-id="9a51d-134">b.</span></span> <span data-ttu-id="9a51d-135">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要使用的实例。</span><span class="sxs-lookup"><span data-stu-id="9a51d-135">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
    
       <span data-ttu-id="9a51d-136">c.</span><span class="sxs-lookup"><span data-stu-id="9a51d-136">c.</span></span> <span data-ttu-id="9a51d-137">如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="9a51d-137">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="9a51d-138">如果启用 SQL Server 镜像并希望添加或更改 SQL Server 镜像见证（第三个单独的 SQL Server 实例，它可以检测主 SQL Server 服务器和镜像实例的运行状况），请选中 "**使用 SQL Server 镜像见证服务器启用自动故障转移**" 复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="9a51d-138">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
    
      <span data-ttu-id="9a51d-139">a.</span><span class="sxs-lookup"><span data-stu-id="9a51d-139">a.</span></span> <span data-ttu-id="9a51d-140">在**SQL SERVER FQDN**中，指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9a51d-140">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
    
      <span data-ttu-id="9a51d-141">b.</span><span class="sxs-lookup"><span data-stu-id="9a51d-141">b.</span></span> <span data-ttu-id="9a51d-142">单击“**默认实例**”以使用默认的实例，或者，若要指定其他实例，请单击“**命名实例**”，然后指定要用于镜像见证的实例。</span><span class="sxs-lookup"><span data-stu-id="9a51d-142">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
    
      <span data-ttu-id="9a51d-143">c.</span><span class="sxs-lookup"><span data-stu-id="9a51d-143">c.</span></span> <span data-ttu-id="9a51d-144">如果指定的 SQL Server 实例位于镜像关系中，请选中 "**此 sql 实例处于镜像关系中**" 复选框，然后在 "**镜像端口号**" 中指定端口号。</span><span class="sxs-lookup"><span data-stu-id="9a51d-144">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
   - <span data-ttu-id="9a51d-145">若要切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 服务器上（如果部署中的所有用户都托管在 Exchange 服务器上），请删除存档数据库的所有信息。</span><span class="sxs-lookup"><span data-stu-id="9a51d-145">To switch to Microsoft Exchange integration to store archiving data and files on Exchange servers (if all users in your deployment are homed on your Exchange servers), delete all information for Archiving databases.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="9a51d-146">如果您有未驻留在 Exchange 服务器上的任何 Skype for Business 用户，请不要删除 SQL Server 存储信息。</span><span class="sxs-lookup"><span data-stu-id="9a51d-146">If you have any Skype for Business users who are not homed on Exchange servers, do not delete the SQL Server store information.</span></span> 
  
8. <span data-ttu-id="9a51d-147">若要保存配置，请单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9a51d-147">To save the configuration, click **OK**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9a51d-148">在发布新拓扑之前，在拓扑生成器中所做的更改不会生效。</span><span class="sxs-lookup"><span data-stu-id="9a51d-148">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="9a51d-149">有关详细信息，请参阅[将存档数据库添加到 Skype for Business 服务器中的现有部署](../../deploy/deploy-archiving/add-archiving-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="9a51d-149">For details, see [Add archiving databases to an existing deployment in Skype for Business Server](../../deploy/deploy-archiving/add-archiving-databases.md).</span></span> 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a><span data-ttu-id="9a51d-150">使用 Windows PowerShell 更改存档数据库的位置</span><span class="sxs-lookup"><span data-stu-id="9a51d-150">Change the location of the Archiving database by using Windows PowerShell</span></span>

<span data-ttu-id="9a51d-151">在大多数情况下，您无需更改存档数据库的位置，在您安装存档服务器时将指定该位置。</span><span class="sxs-lookup"><span data-stu-id="9a51d-151">In most cases, you will not need to change the location of the Archiving database, which is specified when you install Archiving Server.</span></span> <span data-ttu-id="9a51d-152">但是，如果出现硬件故障或其他问题，您可以使用 **Set-CsArchivingServer** cmdlet 将存档服务器指向新的数据库。</span><span class="sxs-lookup"><span data-stu-id="9a51d-152">However, if a hardware failure or other problem should occur, you can point Archiving Server to a new database by using the **Set-CsArchivingServer** cmdlet.</span></span>
  
<span data-ttu-id="9a51d-153">以下示例更改了 ArchivingServer：001.contoso.com 存档服务器的存档数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="9a51d-153">The following example changes the location of the Archiving database for the ArchivingServer:atl-cs-001.contoso.com Archiving Server.</span></span> <span data-ttu-id="9a51d-154">在此示例中，新数据库位于 ArchivingDatabase:atl-sql-001.contoso.com中：</span><span class="sxs-lookup"><span data-stu-id="9a51d-154">In this example, the new database is located at ArchivingDatabase:atl-sql-001.contoso.com:</span></span>
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


