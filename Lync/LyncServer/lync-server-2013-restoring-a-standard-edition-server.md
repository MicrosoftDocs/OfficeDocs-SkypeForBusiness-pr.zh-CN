---
title: Lync Server 2013：还原 Standard Edition server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bffde0a5b6047aeb2eabe38ee10c6b313ff1f01
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="e14f1-102">在 Lync Server 2013 中还原 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="e14f1-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e14f1-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e14f1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e14f1-104">如果未承载中央管理存储的 Standard Edition 服务器出现故障，请按照本节中的过程操作。</span><span class="sxs-lookup"><span data-stu-id="e14f1-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="e14f1-105">如果中央管理存储失败，请参阅[在 Lync server 2013 中还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="e14f1-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e14f1-106">我们建议您先获取系统的图像副本，然后再开始还原。</span><span class="sxs-lookup"><span data-stu-id="e14f1-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="e14f1-107">您可以将此图像用作回滚点，以防还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="e14f1-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="e14f1-108">您可能需要在安装操作系统和 SQL Server 之后制作映像副本，然后再还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="e14f1-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="e14f1-109">还原 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="e14f1-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="e14f1-110">从具有与故障计算机相同的完全限定域名（FQDN）的干净或新服务器开始，安装操作系统，然后还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="e14f1-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e14f1-111">按照您组织的服务器部署过程来执行该步骤。</span><span class="sxs-lookup"><span data-stu-id="e14f1-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="e14f1-112">从作为 RTCUniversalServerAdmins 组成员和本地 Administrators 组成员的用户帐户，登录到要还原的服务器。</span><span class="sxs-lookup"><span data-stu-id="e14f1-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="e14f1-113">通过将相应的文件存储从 $Backup 复制到服务器上的文件存储位置并共享该文件夹来还原文件存储。</span><span class="sxs-lookup"><span data-stu-id="e14f1-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e14f1-114">已还原文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。</span><span class="sxs-lookup"><span data-stu-id="e14f1-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="e14f1-115">运行拓扑生成器：</span><span class="sxs-lookup"><span data-stu-id="e14f1-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="e14f1-116">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="e14f1-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="e14f1-117">单击“从现有部署下载拓扑”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e14f1-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="e14f1-p103">选择拓扑，然后单击“保存”\*\*\*\*。单击“是”\*\*\*\* 确认您的选择。</span><span class="sxs-lookup"><span data-stu-id="e14f1-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="e14f1-120">浏览到 Lync Server 安装文件夹或媒体，然后启动安装程序\\\\Amd64\\Setup.exe 处的 lync server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="e14f1-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="e14f1-121">使用 Lync Server 部署向导执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e14f1-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="e14f1-122">运行“步骤 1: 安装本地配置存储”\*\*\*\* 以安装本地配置文件。</span><span class="sxs-lookup"><span data-stu-id="e14f1-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="e14f1-123">运行**步骤2：安装或删除 Lync Server 组件**以安装 lync server 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e14f1-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="e14f1-124">运行“步骤 3: 请求、安装或分配证书”\*\*\*\* 以分配证书。</span><span class="sxs-lookup"><span data-stu-id="e14f1-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="e14f1-125">运行“步骤 4: 启动服务”\*\*\*\* 以在服务器上启动服务。</span><span class="sxs-lookup"><span data-stu-id="e14f1-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="e14f1-126">有关运行部署向导的详细信息，请参阅适用于您要还原的服务器角色的部署文档。</span><span class="sxs-lookup"><span data-stu-id="e14f1-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="e14f1-127">执行以下操作以还原用户数据：</span><span class="sxs-lookup"><span data-stu-id="e14f1-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="e14f1-128">将 ExportedUserData 从 $Backup\\复制到本地目录。</span><span class="sxs-lookup"><span data-stu-id="e14f1-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="e14f1-129">在还原用户数据之前，必须停止 Lync 服务。</span><span class="sxs-lookup"><span data-stu-id="e14f1-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="e14f1-130">为此，请键入：</span><span class="sxs-lookup"><span data-stu-id="e14f1-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="e14f1-131">若要还原用户数据，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="e14f1-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="e14f1-132">例如：</span><span class="sxs-lookup"><span data-stu-id="e14f1-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="e14f1-133">通过键入以下命令重新启动 Lync 服务：</span><span class="sxs-lookup"><span data-stu-id="e14f1-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="e14f1-134">如果您在此 Standard Edition 服务器上部署了响应组，请还原响应组配置数据。</span><span class="sxs-lookup"><span data-stu-id="e14f1-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="e14f1-135">有关详细信息，请参阅[在 Lync Server 2013 中还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="e14f1-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="e14f1-136">如果已在此 Standard Edition 服务器上部署持久聊天，请还原持久聊天数据库（mgc）。</span><span class="sxs-lookup"><span data-stu-id="e14f1-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="e14f1-137">如果您使用 SQL Server 备份来备份持久聊天数据库，请使用 SQL Server 还原过程将其还原。</span><span class="sxs-lookup"><span data-stu-id="e14f1-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="e14f1-138">如果使用 Export-cspersistentchatdata cmdlet 对其进行备份，请使用 Export-cspersistentchatdata 将其还原。</span><span class="sxs-lookup"><span data-stu-id="e14f1-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

