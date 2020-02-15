---
title: 还原镜像的企业版后端服务器-主要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b895a5071a3844e755fe453f92959f98ec0fbff5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="2241c-102">在 Lync Server 2013 中还原镜像的企业版后端服务器-主要</span><span class="sxs-lookup"><span data-stu-id="2241c-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2241c-103">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="2241c-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="2241c-104">如果在镜像配置中有一个企业版后端服务器，并且只有主数据库出现故障，请按照本节中的过程操作。</span><span class="sxs-lookup"><span data-stu-id="2241c-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="2241c-105">如果主数据库和镜像都失败，请参阅[在 Lync Server 2013 中还原企业版后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2241c-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="2241c-106">如果只有镜像失败，请参阅[在 Lync Server 2013-镜像中还原镜像的企业版后端服务器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)。</span><span class="sxs-lookup"><span data-stu-id="2241c-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="2241c-107">如果承载中央管理存储的数据库失败，请参阅[在 Lync server 2013 中还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="2241c-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="2241c-108">如果不是后端服务器的企业版成员服务器出现故障，请参阅[在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2241c-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="2241c-109">我们建议您先获取系统的图像副本，然后再开始还原。</span><span class="sxs-lookup"><span data-stu-id="2241c-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="2241c-110">您可以将此图像用作回滚点，以防还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="2241c-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="2241c-111">您可能需要在安装操作系统和 SQL Server 后拍摄图像副本，并还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="2241c-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="2241c-112">在本主题中，示例主数据库将具有 BE1.contoso.com 的完全限定域名（FQDN），并且镜像数据库将具有 FQDN "BE2.contoso.com"。</span><span class="sxs-lookup"><span data-stu-id="2241c-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="2241c-113">还原企业版后端服务器主数据库</span><span class="sxs-lookup"><span data-stu-id="2241c-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="2241c-114">从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2241c-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="2241c-115">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2241c-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2241c-116">强制所有已配置的数据库故障转移到镜像。</span><span class="sxs-lookup"><span data-stu-id="2241c-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="2241c-117">对于您在此服务器上配置的每个数据库类型，请键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2241c-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="2241c-118">例如：</span><span class="sxs-lookup"><span data-stu-id="2241c-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="2241c-119">如果已将后端数据库配置为使用具有见证的同步镜像，则故障转移是自动的。</span><span class="sxs-lookup"><span data-stu-id="2241c-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="2241c-120">完成故障转移后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2241c-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="2241c-121">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="2241c-122">在后端服务器上禁用镜像：右键单击 " **Enterprise Edition 前端池**" 下的 "池"，然后选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="2241c-123">在 "**常规**" 选项卡上的 "**关联**" 下，清除 "**启用 SQL Server 存储镜像**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="2241c-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="2241c-124">执行此操作以根据需要进行存档和监视。</span><span class="sxs-lookup"><span data-stu-id="2241c-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="2241c-125">单击" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="2241c-126">右键单击 "Lync Server 2013" 节点，单击 "**拓扑**"，然后单击 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="2241c-127">选择 "仍在运行后端（BE2.contoso.com）" 作为新的 SQL 存储。</span><span class="sxs-lookup"><span data-stu-id="2241c-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="2241c-128">为此，请右键单击 " **Enterprise Edition 前端池**" 下的 "池"，然后选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="2241c-129">在 "**常规**" 选项卡上的 "**关联**" 下，在 " **SQL Server 存储**" 字段中键入功能后端的 FQDN （在我们的示例中为 BE2.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="2241c-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="2241c-130">右键单击 "Lync Server 2013" 节点，单击 "**拓扑**"，然后单击 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="2241c-131">重新启动服务，以便每个服务器可以读取新的拓扑。</span><span class="sxs-lookup"><span data-stu-id="2241c-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="2241c-132">在 Lync Server 命令行管理程序中，在属于此池的每台前端服务器上运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2241c-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="2241c-133">卸载镜像。</span><span class="sxs-lookup"><span data-stu-id="2241c-133">Uninstall mirroring.</span></span> <span data-ttu-id="2241c-134">在 Lync Server 命令行管理程序中，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2241c-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="2241c-135">例如：</span><span class="sxs-lookup"><span data-stu-id="2241c-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="2241c-136">对此服务器上的所有数据库类型执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2241c-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="2241c-137">创建具有相同 FQDN （在此示例中为 DB1.contoso.com）的干净或新服务器作为故障计算机，安装操作系统，然后还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="2241c-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="2241c-138">此服务器将作为新镜像运行。</span><span class="sxs-lookup"><span data-stu-id="2241c-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="2241c-139">从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到新服务器。</span><span class="sxs-lookup"><span data-stu-id="2241c-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="2241c-140">安装 SQL Server 2012 或 SQL Server 2008 R2，并保持实例名称与失败前相同。</span><span class="sxs-lookup"><span data-stu-id="2241c-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="2241c-141">从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2241c-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="2241c-142">使用拓扑生成器安装镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="2241c-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="2241c-143">执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2241c-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="2241c-144">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="2241c-145">在后端服务器上启用镜像。</span><span class="sxs-lookup"><span data-stu-id="2241c-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="2241c-146">为此，请右键单击 " **Enterprise Edition 前端池**" 下的 "池"，然后选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="2241c-147">在 "**常规**" 选项卡上的 "**关联**" 下，选中 "**启用 SQL Server 存储镜像**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="2241c-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="2241c-148">如果需要，还可以执行存档和监控。</span><span class="sxs-lookup"><span data-stu-id="2241c-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="2241c-149">然后，在 "**镜像 SQL Server 存储**" 字段中，键入新服务器的 FQDN （n 本示例，BE1.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="2241c-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="2241c-150">单击" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="2241c-151">右键单击 "Lync Server 2013" 节点，单击 "**拓扑**"，然后单击 "**安装数据库**"。</span><span class="sxs-lookup"><span data-stu-id="2241c-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="2241c-152">按照 "**安装数据库**" 向导操作。</span><span class="sxs-lookup"><span data-stu-id="2241c-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="2241c-153">在 "**创建数据库**" 页上，选择要重新创建的数据库。</span><span class="sxs-lookup"><span data-stu-id="2241c-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="2241c-154">按照向导操作，直到出现提示，**创建镜像数据库**。</span><span class="sxs-lookup"><span data-stu-id="2241c-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="2241c-155">选择要安装的数据库，并完成此过程。</span><span class="sxs-lookup"><span data-stu-id="2241c-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

