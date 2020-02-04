---
title: 还原镜像的企业版后端服务器-镜像
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84a7c5a2aa12c1599d16ec563d10e8f5147df400
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="53873-102">在 Lync Server 2013 中还原镜像的企业版后端服务器-镜像</span><span class="sxs-lookup"><span data-stu-id="53873-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53873-103">_**主题上次修改时间：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="53873-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="53873-104">如果在镜像配置中有企业版后端服务器且只有镜像失败，请按照本部分中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="53873-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="53873-105">如果主数据库和镜像均失败，请参阅[在 Lync Server 2013 中还原企业版后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。</span><span class="sxs-lookup"><span data-stu-id="53873-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="53873-106">如果只有主服务器出现故障，请参阅[在 Lync server 2013 中还原镜像的企业版后端服务器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)。</span><span class="sxs-lookup"><span data-stu-id="53873-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="53873-107">如果托管中央管理存储的数据库失败，请参阅[在 Lync server 2013 中还原托管中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="53873-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="53873-108">如果不是后端服务器的企业版成员服务器出现故障，请参阅[在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="53873-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="53873-109">我们建议你先拍摄系统的映像副本，然后再开始还原。</span><span class="sxs-lookup"><span data-stu-id="53873-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="53873-110">你可以将此映像用作回退点，以防在还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="53873-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="53873-111">您可能希望在安装操作系统和 SQL Server 后获取图像副本，并还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="53873-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="53873-112">还原企业版后端服务器镜像数据库</span><span class="sxs-lookup"><span data-stu-id="53873-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="53873-113">从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="53873-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="53873-114">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="53873-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="53873-115">卸载镜像。</span><span class="sxs-lookup"><span data-stu-id="53873-115">Uninstall mirroring.</span></span> <span data-ttu-id="53873-116">首先，键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="53873-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="53873-117">例如：</span><span class="sxs-lookup"><span data-stu-id="53873-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="53873-118">对此服务器上的所有数据库类型执行此操作。</span><span class="sxs-lookup"><span data-stu-id="53873-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="53873-119">创建具有与失败计算机相同的完全限定的域名（FQDN）（DB1.contoso.com）的干净或新服务器，安装操作系统，然后还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="53873-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="53873-120">此服务器将作为新镜像运行。</span><span class="sxs-lookup"><span data-stu-id="53873-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="53873-121">从 RTCUniversalServerAdmins 组成员的用户帐户登录到新服务器。</span><span class="sxs-lookup"><span data-stu-id="53873-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="53873-122">安装 SQL Server 2012 或 SQL Server 2008 R2，使实例名称与失败之前保持相同。</span><span class="sxs-lookup"><span data-stu-id="53873-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="53873-123">从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="53873-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="53873-124">使用拓扑生成器安装镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="53873-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="53873-125">执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="53873-125">Perform the following:</span></span>
    
      - <span data-ttu-id="53873-126">启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="53873-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="53873-127">右键单击 "Lync Server 2013" 节点，单击 "**拓扑结构**"，然后单击 "**安装数据库**"。</span><span class="sxs-lookup"><span data-stu-id="53873-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="53873-128">按照**安装数据库**向导操作。</span><span class="sxs-lookup"><span data-stu-id="53873-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="53873-129">在 "**创建数据库**" 页面上，选择要重新创建的数据库。</span><span class="sxs-lookup"><span data-stu-id="53873-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="53873-130">按照向导中的步骤操作，直到出现 "**创建镜像" 数据库**的提示。</span><span class="sxs-lookup"><span data-stu-id="53873-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="53873-131">选择要安装的数据库并完成此过程。</span><span class="sxs-lookup"><span data-stu-id="53873-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="53873-132">你可以使用<STRONG>CsMirrorDatabase</STRONG> cmdlet 配置镜像，而不是运行拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="53873-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="53873-133">有关详细信息，请参阅 Lync Server Management Shell 文档。</span><span class="sxs-lookup"><span data-stu-id="53873-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

