---
title: Lync Server 2013：还原企业版后端服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 429bf681e157beece170b9fe10e64fa8dea749ef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="7c3f7-102">在 Lync Server 2013 中还原企业版后端服务器</span><span class="sxs-lookup"><span data-stu-id="7c3f7-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c3f7-103">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="7c3f7-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="7c3f7-104">在以下两种情况下，请使用本主题中介绍的过程：</span><span class="sxs-lookup"><span data-stu-id="7c3f7-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="7c3f7-105">镜像企业版后端服务器的主数据库和镜像数据库都将失败。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="7c3f7-106">未镜像的企业版后端服务器失败。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="7c3f7-107">如果您有一个镜像的企业版后端，并且只有镜像或主数据库出现故障，请参阅在 lync server [2013-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)用于还原主数据库，并[在 Lync server 2013 中还原镜像的企业版后端服务器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)（用于还原镜像的镜像）中的镜像企业版后端服务器。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="7c3f7-108">如果中央管理存储失败，请参阅[在 Lync server 2013 中还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="7c3f7-109">如果不是后端服务器的企业版成员服务器出现故障，请参阅[在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7c3f7-110">我们建议您先获取系统的图像副本，然后再开始还原。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="7c3f7-111">您可以将此图像用作回滚点，以防还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="7c3f7-112">您可能需要在安装操作系统和 SQL Server 后拍摄图像副本，并还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="7c3f7-113">还原 Enterprise Edition 后端服务器</span><span class="sxs-lookup"><span data-stu-id="7c3f7-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="7c3f7-114">从具有与故障计算机相同的完全限定域名（FQDN）的干净或新服务器开始，安装操作系统，然后还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c3f7-115">按照您组织的服务器部署过程来执行该步骤。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="7c3f7-116">从作为 RTCUniversalServerAdmins 组成员的用户帐户，登录到要还原的服务器。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="7c3f7-117">安装 SQL Server 2012 或 SQL Server 2008 R2，并保持实例名称与失败前相同。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c3f7-p103">根据您的部署，后端服务器可能包含多个并置或独立数据库。按照先前部署服务器时使用的过程来安装 SQL Server，包括 SQL Server 权限和登录名。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-p103">Depending on your deployment, the Back End Server might include multiple collocated or separate databases. Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="7c3f7-120">安装 SQL Server 后，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7c3f7-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="7c3f7-121">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="7c3f7-122">单击“从现有部署下载拓扑”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="7c3f7-p104">选择拓扑，然后单击“保存”\*\*\*\*。单击“是”\*\*\*\* 确认您的选择。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-p104">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="7c3f7-125">右键单击 " **Lync Server 2013** " 节点，然后单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="7c3f7-126">按照“发布拓扑”\*\*\*\* 向导操作。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="7c3f7-127">在 "**创建数据库**" 页上，选择要重新创建的数据库。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7c3f7-128">只有独立数据库会显示在“创建数据库”<STRONG></STRONG>页上。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="7c3f7-129">如果要还原已镜像的后端，请继续遵循向导的其余部分，直到出现提示**创建镜像数据库**。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="7c3f7-130">选择要安装的数据库，并完成此过程。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="7c3f7-131">按照向导的其余部分操作，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="7c3f7-132">除了运行拓扑生成器之外，您还可以使用<STRONG>CsDatabase</STRONG> cmdlet 来创建每个数据库，并使用<STRONG>CsMirrorDatabase</STRONG> cmdlet 来配置镜像。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="7c3f7-133">有关详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="7c3f7-134">执行以下操作以还原用户数据：</span><span class="sxs-lookup"><span data-stu-id="7c3f7-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="7c3f7-135">将 ExportedUserData 从 $Backup\\复制到本地目录。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="7c3f7-136">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="7c3f7-137">在还原用户数据之前，必须停止 Lync 服务。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="7c3f7-138">为此，请键入：</span><span class="sxs-lookup"><span data-stu-id="7c3f7-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="7c3f7-139">若要还原用户数据，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="7c3f7-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="7c3f7-140">例如：</span><span class="sxs-lookup"><span data-stu-id="7c3f7-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="7c3f7-141">通过键入以下命令重新启动 Lync 服务：</span><span class="sxs-lookup"><span data-stu-id="7c3f7-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="7c3f7-142">如果您在此池上部署了响应组，请还原响应组配置数据。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="7c3f7-143">有关详细信息，请参阅[在 Lync Server 2013 中还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="7c3f7-144">如果要还原的后端服务器包含存档或监控数据库，请使用 SQL Server 工具（如 SQL Server Management Studio）还原存档或监控数据。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="7c3f7-145">有关详细信息，请参阅[在 Lync Server 2013 中还原监视或存档数据](lync-server-2013-restoring-monitoring-or-archiving-data.md)。</span><span class="sxs-lookup"><span data-stu-id="7c3f7-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

