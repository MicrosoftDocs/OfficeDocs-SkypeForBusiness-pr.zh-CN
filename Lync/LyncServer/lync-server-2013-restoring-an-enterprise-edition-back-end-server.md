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
ms.openlocfilehash: 2bd57054505b3200f63bed8a60c47b400f7e7642
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="e2392-102">在 Lync Server 2013 中还原企业版后端服务器</span><span class="sxs-lookup"><span data-stu-id="e2392-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2392-103">_**主题上次修改时间：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="e2392-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="e2392-104">在以下两种情况下使用本主题中介绍的过程：</span><span class="sxs-lookup"><span data-stu-id="e2392-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="e2392-105">镜像企业版后端服务器的主数据库和镜像数据库均失败。</span><span class="sxs-lookup"><span data-stu-id="e2392-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="e2392-106">不进行镜像的企业版后端服务器失败。</span><span class="sxs-lookup"><span data-stu-id="e2392-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="e2392-107">如果你有一个镜像的企业版后端，并且只有镜像或主数据库失败，请参阅[在 Lync server 2013 中还原镜像的企业版后端服务器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)用于还原主数据库，以及[在 lync Server 2013 中还原镜像的企业版后端服务器-镜像](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)以还原镜像。</span><span class="sxs-lookup"><span data-stu-id="e2392-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="e2392-108">如果中央管理存储失败，请参阅[在 Lync server 2013 中还原托管中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="e2392-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="e2392-109">如果不是后端服务器的企业版成员服务器出现故障，请参阅[在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e2392-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e2392-110">我们建议你先拍摄系统的映像副本，然后再开始还原。</span><span class="sxs-lookup"><span data-stu-id="e2392-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="e2392-111">你可以将此映像用作回退点，以防在还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="e2392-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="e2392-112">您可能希望在安装操作系统和 SQL Server 后获取图像副本，并还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="e2392-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="e2392-113">还原企业版后端服务器</span><span class="sxs-lookup"><span data-stu-id="e2392-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="e2392-114">从具有与故障计算机相同的完全限定的域名（FQDN）的全新或新服务器开始，安装操作系统，然后还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="e2392-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2392-115">按照组织的服务器部署过程执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="e2392-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="e2392-116">从作为 RTCUniversalServerAdmins 组成员的用户帐户，登录到要还原的服务器。</span><span class="sxs-lookup"><span data-stu-id="e2392-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="e2392-117">安装 SQL Server 2012 或 SQL Server 2008 R2，使实例名称与失败之前保持相同。</span><span class="sxs-lookup"><span data-stu-id="e2392-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2392-118">根据你的部署，后端服务器可能包含多个 collocated 或单独的数据库。</span><span class="sxs-lookup"><span data-stu-id="e2392-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="e2392-119">按照相同的步骤安装最初用于部署服务器的 SQL Server，包括 SQL Server 权限和登录。</span><span class="sxs-lookup"><span data-stu-id="e2392-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="e2392-120">安装 SQL Server 后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2392-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="e2392-121">启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="e2392-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="e2392-122">单击 "**从现有部署下载拓扑**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e2392-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="e2392-123">选择拓扑，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="e2392-123">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="e2392-124">单击 **"是"** 以确认您的选择。</span><span class="sxs-lookup"><span data-stu-id="e2392-124">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="e2392-125">右键单击 " **Lync Server 2013** " 节点，然后单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="e2392-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="e2392-126">按照 "**发布拓扑**向导" 中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="e2392-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="e2392-127">在 "**创建数据库**" 页面上，选择要重新创建的数据库。</span><span class="sxs-lookup"><span data-stu-id="e2392-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e2392-128">"<STRONG>创建数据库</STRONG>" 页面上仅显示独立数据库。</span><span class="sxs-lookup"><span data-stu-id="e2392-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="e2392-129">如果要还原已镜像的后端，请继续按照向导的其余部分操作，直到出现 "提示**创建镜像数据库**"。</span><span class="sxs-lookup"><span data-stu-id="e2392-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="e2392-130">选择要安装的数据库，然后完成此过程。</span><span class="sxs-lookup"><span data-stu-id="e2392-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="e2392-131">按照向导的其余部分，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="e2392-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e2392-132">你可以使用<STRONG>CsDatabase</STRONG> cmdlet 创建每个数据库，使用<STRONG>CsMirrorDatabase</STRONG> cmdlet 来配置镜像，而不是运行拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="e2392-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="e2392-133">有关详细信息，请参阅 Lync Server Management Shell 文档。</span><span class="sxs-lookup"><span data-stu-id="e2392-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="e2392-134">通过执行下列操作还原用户数据：</span><span class="sxs-lookup"><span data-stu-id="e2392-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="e2392-135">将 ExportedUserData 从 $Backup\\复制到本地目录。</span><span class="sxs-lookup"><span data-stu-id="e2392-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="e2392-136">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="e2392-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="e2392-137">还原用户数据之前，必须停止 Lync 服务。</span><span class="sxs-lookup"><span data-stu-id="e2392-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="e2392-138">若要执行此操作，请键入：</span><span class="sxs-lookup"><span data-stu-id="e2392-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="e2392-139">若要还原用户数据，请在命令行键入：</span><span class="sxs-lookup"><span data-stu-id="e2392-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="e2392-140">例如：</span><span class="sxs-lookup"><span data-stu-id="e2392-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="e2392-141">通过键入以下内容重启 Lync 服务：</span><span class="sxs-lookup"><span data-stu-id="e2392-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="e2392-142">如果你在此池中部署了响应组，请还原响应组配置数据。</span><span class="sxs-lookup"><span data-stu-id="e2392-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="e2392-143">有关详细信息，请参阅[在 Lync Server 2013 中还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="e2392-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="e2392-144">如果要还原包含存档或监视数据库的后端服务器，请使用 SQL Server 工具（如 SQL Server Management Studio）还原存档或监视数据。</span><span class="sxs-lookup"><span data-stu-id="e2392-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="e2392-145">有关详细信息，请参阅[在 Lync Server 2013 中还原监视或存档数据](lync-server-2013-restoring-monitoring-or-archiving-data.md)。</span><span class="sxs-lookup"><span data-stu-id="e2392-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

