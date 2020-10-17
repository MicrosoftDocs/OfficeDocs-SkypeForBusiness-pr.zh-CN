---
title: 部署 Lync Server 2013 试点池
description: 部署 Lync Server 2013 试点池。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a599cee1719f773ebbf3cf5a71405aa9b7259261
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550788"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="33887-103">部署 Lync Server 2013 试点池</span><span class="sxs-lookup"><span data-stu-id="33887-103">Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33887-104">_**上次修改的主题：** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="33887-104">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="33887-105">迁移到 Lync Server 2013 所需的第一步是部署试点池。</span><span class="sxs-lookup"><span data-stu-id="33887-105">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="33887-106">试点池是您在 Lync server 2010 部署中测试 Lync Server 2013 共存的地方。</span><span class="sxs-lookup"><span data-stu-id="33887-106">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="33887-107">共存是在将所有用户和池移到 Lync Server 2013 之前一直持续的临时状态。</span><span class="sxs-lookup"><span data-stu-id="33887-107">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="33887-108">部署试点池时，应使用“定义新前端池”向导。</span><span class="sxs-lookup"><span data-stu-id="33887-108">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="33887-109">您应在 lync Server 2010 池中部署 Lync Server 2013 引导池中的相同功能和工作负载。</span><span class="sxs-lookup"><span data-stu-id="33887-109">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="33887-110">如果您部署了存档服务器、监视服务器或 System Center Operations Manager 以存档或监视 Lync Server 2010 环境，并且您希望在整个迁移过程中继续进行存档或监控，则还需要在您的试点环境中部署这些功能。</span><span class="sxs-lookup"><span data-stu-id="33887-110">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="33887-111">您部署的用于存档或监视 Lync Server 2010 环境的版本将不会在 Lync Server 2013 环境中捕获数据。</span><span class="sxs-lookup"><span data-stu-id="33887-111">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33887-112">随后的过程讨论应被视为试点池总体部署过程一部分的功能和设置。</span><span class="sxs-lookup"><span data-stu-id="33887-112">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="33887-113">本节只着重介绍在部署试点池的过程中应考虑的关键点。</span><span class="sxs-lookup"><span data-stu-id="33887-113">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="33887-114">有关详细步骤，请参阅 <A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A> 部署指南。</span><span class="sxs-lookup"><span data-stu-id="33887-114">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="33887-115">**部署 Lync Server 2013 引导池**</span><span class="sxs-lookup"><span data-stu-id="33887-115">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="33887-116">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="33887-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="33887-117">展开树，直至您进入 **Lync Server 2013** **Enterprise Edition 前端池**。</span><span class="sxs-lookup"><span data-stu-id="33887-117">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="33887-118">右键单击 " **Enterprise Edition 前端池**"，然后选择 " **新建前端池**"。</span><span class="sxs-lookup"><span data-stu-id="33887-118">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="33887-119">![拓扑生成器服务器池选择子菜单](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "拓扑生成器服务器池选择子菜单")</span><span class="sxs-lookup"><span data-stu-id="33887-119">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="33887-120">输入池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="33887-120">Enter the pool FQDN.</span></span> <span data-ttu-id="33887-121">在定义试点池时，可以选择部署企业版前端池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="33887-121">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="33887-122">Lync Server 2013 不要求您的引导池功能与您的旧版池中部署的功能相匹配。</span><span class="sxs-lookup"><span data-stu-id="33887-122">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="33887-123">您为试点定义的池或服务器的完全限定域名 (FQDN) 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="33887-123">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="33887-124">它无法匹配当前部署的 Lync Server 2010 池的名称，或当前部署的任何其他服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="33887-124">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="33887-125">![定义新的前端池向导 FQDN 页](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "定义新的前端池向导 FQDN 页")</span><span class="sxs-lookup"><span data-stu-id="33887-125">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="33887-126">在“选择功能”\*\*\*\* 页上，选中希望此前端池具有的功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="33887-126">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="33887-127">例如，如果您仅部署即时消息 (IM) 和状态功能，可以选中“会议”复选框以允许多方 IM，但不能选中“电话拨入式(PSTN)会议”、“企业语音”或“呼叫允许控制”复选框，因为它们代表语音、视频和协作会议功能。</span><span class="sxs-lookup"><span data-stu-id="33887-127">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="33887-128">有关选择功能的其他信息，请参阅部署文档中的在 [Lync server 2013 中定义和配置前端池或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="33887-128">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="33887-129">![前端池选择功能页](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端池选择功能页")</span><span class="sxs-lookup"><span data-stu-id="33887-129">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="33887-130">在 " **选择并置服务器角色** " 页上，我们建议您在 Lync server 2013 中并置中介服务器。</span><span class="sxs-lookup"><span data-stu-id="33887-130">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="33887-131">将旧版拓扑与 Lync Server 2013 合并时，我们需要您首先并置 Lync Server 2010 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="33887-131">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="33887-132">在合并拓扑并配置 Lync Server 2013 中介服务器之后，您可以决定是否保留并置中介服务器，或在部署过程中稍后将中介服务器角色移动到 Lync Server 2013 时，将其更改为独立服务器。</span><span class="sxs-lookup"><span data-stu-id="33887-132">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="33887-133">![前端池选择 "并置服务器角色" 页](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端池选择 "并置服务器角色" 页")</span><span class="sxs-lookup"><span data-stu-id="33887-133">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="33887-p108">在部署试点池过程中，不要选择“将服务器角色与此前端池关联”\*\*\*\* 页上的“启用此前端池的媒体组件要使用的边缘池”\*\*\*\* 选项。这是您将启用并使其在后面的迁移阶段进入联机状态的功能。目前请清除此设置。</span><span class="sxs-lookup"><span data-stu-id="33887-p108">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="33887-137">![将服务器角色与前端池页面关联](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "将服务器角色与前端池页面关联")</span><span class="sxs-lookup"><span data-stu-id="33887-137">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="33887-138">在“选择 Office Web Apps 服务器”\*\*\*\* 页上，单击“新建”\*\*\*\* 并指定应用程序服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="33887-138">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="33887-139">![定义新的 Office Web Apps Server FQDN 属性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定义新的 Office Web Apps Server FQDN 属性")</span><span class="sxs-lookup"><span data-stu-id="33887-139">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="33887-140">在 " **定义存档 Sql server 存储** " 页上，定义 Lync server 存档和监视的 sql server 存储区时，请选择之前为 lync server 2013 创建的 sql server 实例。</span><span class="sxs-lookup"><span data-stu-id="33887-140">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="33887-141">![定义 "存档 SQL Server 存储" 页](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "定义 "存档 SQL Server 存储" 页")</span><span class="sxs-lookup"><span data-stu-id="33887-141">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="33887-142">若要发布拓扑，请右键单击 " **Lync Server** " 节点，然后单击 " **发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="33887-142">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="33887-143">![显示已配置拓扑的拓扑生成器](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "显示已配置拓扑的拓扑生成器")</span><span class="sxs-lookup"><span data-stu-id="33887-143">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="33887-144">发布过程完成后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="33887-144">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="33887-145">若要安装配置存储的本地副本并启动所需的服务，请参阅部署文档中的为 [Lync Server 2013 设置前端服务器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 。</span><span class="sxs-lookup"><span data-stu-id="33887-145">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

