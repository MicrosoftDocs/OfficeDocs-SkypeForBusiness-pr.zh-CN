---
title: 部署 Lync Server 2013 试验池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fb3c5062cc1f817d3de7b869f57600178ad454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="07acc-102">部署 Lync Server 2013 试验池</span><span class="sxs-lookup"><span data-stu-id="07acc-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07acc-103">_**主题上次修改时间:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="07acc-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="07acc-104">迁移到 Lync Server 2013 所需的第一步是部署试验池。</span><span class="sxs-lookup"><span data-stu-id="07acc-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="07acc-105">在 "试点" 池中, 你可以通过 Lync server 2010 部署来测试 Lync Server 2013 的共存。</span><span class="sxs-lookup"><span data-stu-id="07acc-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="07acc-106">共存是指在将所有用户和池移到 Lync Server 2013 之前一直持续的临时状态。</span><span class="sxs-lookup"><span data-stu-id="07acc-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="07acc-107">部署试验池时, 请使用 "定义新的前端池" 向导。</span><span class="sxs-lookup"><span data-stu-id="07acc-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="07acc-108">你应该在 lync Server 2010 池中的 Lync Server 2013 试验池中部署相同的功能和工作负荷。</span><span class="sxs-lookup"><span data-stu-id="07acc-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="07acc-109">如果你已部署用于存档或监视 Lync Server 2010 环境的存档服务器、监视服务器或 System Center Operations Manager, 并且希望在整个迁移过程中继续存档或监视, 你还需要部署这些您的试点环境中的功能。</span><span class="sxs-lookup"><span data-stu-id="07acc-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="07acc-110">你部署的用于存档或监视 Lync Server 2010 环境的版本将不会在 Lync Server 2013 环境中捕获数据。</span><span class="sxs-lookup"><span data-stu-id="07acc-110">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07acc-111">以下过程讨论了在整个试点池部署过程中应考虑的功能和设置。</span><span class="sxs-lookup"><span data-stu-id="07acc-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="07acc-112">本部分仅重点介绍您在试验池部署中应考虑的要点。</span><span class="sxs-lookup"><span data-stu-id="07acc-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="07acc-113">有关详细步骤, 请参阅<A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A>部署指南。</span><span class="sxs-lookup"><span data-stu-id="07acc-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="07acc-114">**部署 Lync Server 2013 试验池**</span><span class="sxs-lookup"><span data-stu-id="07acc-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="07acc-115">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="07acc-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="07acc-116">展开树, 直到到达**Lync Server 2013** **企业版前端池**。</span><span class="sxs-lookup"><span data-stu-id="07acc-116">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="07acc-117">右键单击 "**企业版前端池**", 然后选择 "**新建前端池**"。</span><span class="sxs-lookup"><span data-stu-id="07acc-117">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="07acc-118">![拓扑生成器服务器池选择子菜单](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "拓扑生成器服务器池选择子菜单")</span><span class="sxs-lookup"><span data-stu-id="07acc-118">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="07acc-119">输入池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="07acc-119">Enter the pool FQDN.</span></span> <span data-ttu-id="07acc-120">定义试验池时, 可以选择部署企业版前端池或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="07acc-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="07acc-121">Lync Server 2013 不要求引导池功能与您的旧版池中部署的功能相匹配。</span><span class="sxs-lookup"><span data-stu-id="07acc-121">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="07acc-122">为试点池定义的池或服务器完全限定的域名 (FQDN) 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="07acc-122">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="07acc-123">它不能与当前部署的 Lync Server 2010 池或当前部署的任何其他服务器的名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="07acc-123">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="07acc-124">![定义新的前端池向导 FQDN 页面](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "定义新的前端池向导 FQDN 页面")</span><span class="sxs-lookup"><span data-stu-id="07acc-124">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="07acc-125">在 "**选择功能**" 页面上, 选中您希望在此前端池上的功能所对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="07acc-125">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="07acc-126">例如, 如果您仅部署即时消息 (IM) 和状态功能, 则可以选择 "会议" 复选框以允许多方 IM, 但不会选择 "拨入 (PSTN) 会议"、"企业语音" 或 "呼叫许可控制" 复选框,因为它们代表语音、视频和协作式会议功能。</span><span class="sxs-lookup"><span data-stu-id="07acc-126">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="07acc-127">有关选择功能的其他信息, 请参阅部署文档中的[Lync server 2013 中的 "定义和配置前端池" 或 "标准版服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)"。</span><span class="sxs-lookup"><span data-stu-id="07acc-127">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="07acc-128">![前端池选择功能页面](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端池选择功能页面")</span><span class="sxs-lookup"><span data-stu-id="07acc-128">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="07acc-129">在 "**选择 collocated 服务器角色**" 页面上, 建议在 Lync server 2013 中 Collocate 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="07acc-129">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="07acc-130">将旧版拓扑与 Lync Server 2013 合并时, 我们需要首先 collocate Lync Server 2010 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="07acc-130">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="07acc-131">合并拓扑并配置 Lync Server 2013 中介服务器之后, 你可以决定在部署中将中介服务器角色移动到 Lync Server 2013 时是否保留 collocated 中介服务器或将其更改为独立服务器工艺.</span><span class="sxs-lookup"><span data-stu-id="07acc-131">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="07acc-132">![前端池选择 "collocated 服务器角色" 页面](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端池选择 \"collocated 服务器角色\" 页面")</span><span class="sxs-lookup"><span data-stu-id="07acc-132">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="07acc-133">在试验池部署期间, 在 "**关联服务器角色与此前端池**" 页面上, 不要选择 "**启用要由此前端池的媒体组件使用的边缘池**" 选项。</span><span class="sxs-lookup"><span data-stu-id="07acc-133">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="07acc-134">这是你将在迁移的后续阶段启用并联机的功能。</span><span class="sxs-lookup"><span data-stu-id="07acc-134">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="07acc-135">立即清除此设置。</span><span class="sxs-lookup"><span data-stu-id="07acc-135">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="07acc-136">![将服务器角色与前端池页面关联](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "将服务器角色与前端池页面关联")</span><span class="sxs-lookup"><span data-stu-id="07acc-136">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="07acc-137">在 "**选择 Office Web Apps 服务器**" 页面上, 单击 "**新建**", 然后指定应用程序服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="07acc-137">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="07acc-138">![定义新的 Office Web Apps 服务器 FQDN 属性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定义新的 Office Web Apps 服务器 FQDN 属性")</span><span class="sxs-lookup"><span data-stu-id="07acc-138">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="07acc-139">在 "**定义存档 Sql server 存储**" 页面上, 定义 "Lync server 存档和监视的 sql server 存储" 页面时, 选择之前为 lync server 2013 创建的 sql server 实例。</span><span class="sxs-lookup"><span data-stu-id="07acc-139">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="07acc-140">![定义 "存档 SQL Server 存储" 页面](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "定义 \"存档 SQL Server 存储\" 页面")</span><span class="sxs-lookup"><span data-stu-id="07acc-140">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="07acc-141">若要发布拓扑, 请右键单击 " **Lync 服务器**" 节点, 然后单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="07acc-141">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="07acc-142">![显示已配置拓扑的拓扑生成器](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "显示已配置拓扑的拓扑生成器")</span><span class="sxs-lookup"><span data-stu-id="07acc-142">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="07acc-143">发布过程完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="07acc-143">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="07acc-144">若要安装配置存储的本地副本并启动所需的服务, 请参阅部署文档中的[Lync Server 2013 设置前端服务器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="07acc-144">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

