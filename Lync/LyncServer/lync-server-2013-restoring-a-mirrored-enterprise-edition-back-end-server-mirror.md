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
ms.openlocfilehash: 6e4bbb7d74c6bf660c69a15ff8250d95f04fed98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511579"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="e7ae4-102">在 Lync Server 2013-镜像中还原镜像的企业版后端服务器</span><span class="sxs-lookup"><span data-stu-id="e7ae4-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7ae4-103">_**上次修改的主题：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="e7ae4-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="e7ae4-104">如果在镜像配置中有企业版后端服务器且只有镜像失败，请按照本节中的过程操作。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="e7ae4-105">如果主数据库和镜像都失败，请参阅 [在 Lync Server 2013 中还原企业版后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="e7ae4-106">如果只有主服务器出现故障，请参阅 [在 Lync Server 2013 中还原镜像的企业版后端服务器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="e7ae4-107">如果承载中央管理存储的数据库失败，请参阅 [在 Lync server 2013 中还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="e7ae4-108">如果不是后端服务器的企业版成员服务器出现故障，请参阅 [在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="e7ae4-109">我们建议您先获取系统的图像副本，然后再开始还原。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="e7ae4-110">您可以将此图像用作回滚点，以防还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="e7ae4-111">您可能需要在安装操作系统和 SQL Server 后拍摄图像副本，并还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="e7ae4-112">还原企业版后端服务器镜像数据库</span><span class="sxs-lookup"><span data-stu-id="e7ae4-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="e7ae4-113">从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="e7ae4-114">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e7ae4-115">卸载镜像。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-115">Uninstall mirroring.</span></span> <span data-ttu-id="e7ae4-116">首先，键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e7ae4-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="e7ae4-117">例如：</span><span class="sxs-lookup"><span data-stu-id="e7ae4-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="e7ae4-118">对此服务器上的所有数据库类型执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="e7ae4-119">创建具有相同完全限定的域名 (FQDN)  (DB1.contoso.com) 作为故障计算机的全新或新服务器，安装操作系统，然后还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="e7ae4-120">此服务器将作为新镜像运行。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="e7ae4-121">从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到新服务器。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="e7ae4-122">安装 SQL Server 2012 或 SQL Server 2008 R2，并保持实例名称与失败前相同。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="e7ae4-123">从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="e7ae4-124">使用拓扑生成器安装镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="e7ae4-125">执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e7ae4-125">Perform the following:</span></span>
    
      - <span data-ttu-id="e7ae4-126">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="e7ae4-127">右键单击 "Lync Server 2013" 节点，单击 " **拓扑**"，然后单击 " **安装数据库**"。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="e7ae4-128">按照 " **安装数据库** " 向导操作。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="e7ae4-129">在 " **创建数据库** " 页上，选择要重新创建的数据库。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="e7ae4-130">按照向导操作，直到出现 " **创建镜像数据库** " 的提示。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="e7ae4-131">选择要安装的数据库并完成此过程。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="e7ae4-132">您可以使用 <STRONG>CsMirrorDatabase</STRONG> cmdlet 配置镜像，而无需运行拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="e7ae4-133">有关详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="e7ae4-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

