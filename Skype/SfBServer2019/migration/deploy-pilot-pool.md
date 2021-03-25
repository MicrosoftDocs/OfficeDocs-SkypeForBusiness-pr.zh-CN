---
title: 部署试点池
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 迁移到 Skype for Business Server 2019 所需的第一步之一是部署试点池。 试点池是测试 Skype for Business Server 2019 与旧部署共存的地方。 共存是一种临时状态，一直持续到将所有用户和池移动到 Skype for Business Server 2019。
ms.openlocfilehash: a8d9a1bbe5f629a91721ebe530e6a192e3e65b62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113288"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="ddebe-105">部署 Skype for Business Server 2019 试点池</span><span class="sxs-lookup"><span data-stu-id="ddebe-105">Deploy Skype for Business Server 2019 pilot pool</span></span>

<span data-ttu-id="ddebe-106">迁移到 Skype for Business Server 2019 所需的第一步之一是部署试点池。</span><span class="sxs-lookup"><span data-stu-id="ddebe-106">One of the first steps required for migration to Skype for Business Server 2019 is to deploy a pilot pool.</span></span> <span data-ttu-id="ddebe-107">试点池是测试 Skype for Business Server 2019 与旧部署共存的地方。</span><span class="sxs-lookup"><span data-stu-id="ddebe-107">The pilot pool is where you test coexistence of Skype for Business Server 2019 with your legacy deployment.</span></span> <span data-ttu-id="ddebe-108">共存是一种临时状态，一直持续到将所有用户和池移动到 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="ddebe-108">Coexistence is a temporary state that lasts until you have moved all users and pools to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="ddebe-109">部署试点池时，应使用“定义新前端池”向导。</span><span class="sxs-lookup"><span data-stu-id="ddebe-109">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="ddebe-110">应在 Skype for Business Server 2019 试点池中部署与旧版池中相同的功能和工作负载。</span><span class="sxs-lookup"><span data-stu-id="ddebe-110">You should deploy the same features and workloads in your Skype for Business Server 2019 pilot pool that you have in your legacy pool.</span></span> <span data-ttu-id="ddebe-111">如果已部署存档服务器、监控服务器或 System Center Operations Manager 以存档或监视旧环境，并且您希望在整个迁移过程中继续存档或监控，则还需要在试点环境中部署这些功能。</span><span class="sxs-lookup"><span data-stu-id="ddebe-111">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your legacy environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="ddebe-112">你部署用于存档或监视旧环境的版本不会捕获 Skype for Business Server 2019 环境中的数据。</span><span class="sxs-lookup"><span data-stu-id="ddebe-112">The version you deployed to archive or monitor your legacy environment will not capture data in your Skype for Business Server 2019 environment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ddebe-113">随后的过程讨论应被视为试点池总体部署过程一部分的功能和设置。</span><span class="sxs-lookup"><span data-stu-id="ddebe-113">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="ddebe-114">本节只着重介绍在部署试点池的过程中应考虑的关键点。</span><span class="sxs-lookup"><span data-stu-id="ddebe-114">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="ddebe-115">部署 Skype for Business Server 2019 试点池</span><span class="sxs-lookup"><span data-stu-id="ddebe-115">To deploy a Skype for Business Server 2019 pilot pool</span></span>

1. <span data-ttu-id="ddebe-116">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="ddebe-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="ddebe-117">展开树，直到到达 **Skype for Business Server 2019**  >  **Enterprise Edition 前端池**。</span><span class="sxs-lookup"><span data-stu-id="ddebe-117">Expand the tree until you reach **Skype for Business Server 2019** > **Enterprise Edition Front End pools**.</span></span>
    
3. <span data-ttu-id="ddebe-118">右键单击 **"Enterprise Edition 前端池"，** 然后选择 **"新建前端池"。**</span><span class="sxs-lookup"><span data-stu-id="ddebe-118">Right-click **Enterprise Edition Front End pools** and select **New Front End Pool**.</span></span>
  
4. <span data-ttu-id="ddebe-119">输入 FQDN 中的池完全限定 (域名) 。</span><span class="sxs-lookup"><span data-stu-id="ddebe-119">Enter the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="ddebe-120">定义试点池时，可以选择部署 Enterprise Edition 前端池或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="ddebe-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="ddebe-121">Skype for Business Server 2019 不要求试点池功能与旧池中部署的功能相匹配。</span><span class="sxs-lookup"><span data-stu-id="ddebe-121">Skype for Business Server 2019 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ddebe-122">为试点池定义的池或服务器 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ddebe-122">The pool or server FQDN that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="ddebe-123">它不能匹配当前部署的旧池或当前部署任何其他服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ddebe-123">It cannot match the name of the currently deployed legacy pool or any other servers currently deployed.</span></span> 
  
5. <span data-ttu-id="ddebe-124">在“选择功能”页上，选中希望此前端池具有的功能的复选框。</span><span class="sxs-lookup"><span data-stu-id="ddebe-124">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="ddebe-125">例如，如果您仅部署即时消息 (IM) 和状态功能，则应该选中"会议"复选框以允许多方 IM，但不选中"电话拨入式 (PSTN) 会议、企业语音 或呼叫允许控制"复选框，因为它们代表语音、视频和协作会议功能。</span><span class="sxs-lookup"><span data-stu-id="ddebe-125">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but you would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. <span data-ttu-id="ddebe-126">在" **选择并并的服务器** 角色"页上，我们建议您选择在 Skype for Business Server 2019 中并并中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ddebe-126">On the **Select collocated server roles** page, we recommend that you choose to collocate the Mediation Server in Skype for Business Server 2019.</span></span> <span data-ttu-id="ddebe-127">在将旧拓扑与 Skype for Business Server 2019 合并时，我们要求您首先并并旧中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ddebe-127">When merging a legacy topology with Skype for Business Server 2019, we require that you first collocate the legacy Mediation Server.</span></span> <span data-ttu-id="ddebe-128">合并拓扑并配置 Skype for Business Server 2019 中介服务器后，可以在部署过程中稍后将中介服务器角色移动到 Skype for Business Server 2019 时决定是保留并并的中介服务器，还是将其更改为独立服务器。</span><span class="sxs-lookup"><span data-stu-id="ddebe-128">After merging the topologies and configuring the Skype for Business Server 2019 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Skype for Business Server 2019 later in the deployment process.</span></span> 
   
7. <span data-ttu-id="ddebe-129">在"**将服务器角色与此** 前端池关联"页上的"试点池部署期间，不要选择"启用此前端池的媒体组件使用的边缘 **池"** 选项。</span><span class="sxs-lookup"><span data-stu-id="ddebe-129">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, *do not* choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="ddebe-130">这是您将启用并使其在后面的迁移阶段进入联机状态的功能。</span><span class="sxs-lookup"><span data-stu-id="ddebe-130">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="ddebe-131">目前请清除此设置。</span><span class="sxs-lookup"><span data-stu-id="ddebe-131">Keep this setting cleared for now.</span></span> 
  
8. <span data-ttu-id="ddebe-132">在“选择 Office Web Apps 服务器”页上，单击“新建”并指定应用程序服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ddebe-132">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
  
9. <span data-ttu-id="ddebe-133">在"定义存档 **SQL Server** 存储"页上，为 Skype for Business Server 存档和监控定义 SQL Server 存储时，选择之前为 Skype for Business Server 2019 创建的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="ddebe-133">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Skype for Business Server Archiving and Monitoring, select the SQL Server instance created earlier for Skype for Business Server 2019.</span></span> 
  
10. <span data-ttu-id="ddebe-134">要发布拓扑，请右键单击 **"Skype for Business Server"** 节点，然后单击"**发布拓扑"。**</span><span class="sxs-lookup"><span data-stu-id="ddebe-134">To publish your topology, right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
  
11. <span data-ttu-id="ddebe-135">发布过程完成后，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="ddebe-135">When the publish process has completed, click **Finish**.</span></span>

12. <span data-ttu-id="ddebe-136">在移动到下一部分"验证试点池与旧池共存"之前，你需要安装我们刚刚在已发布拓扑中定义的 Skype for Business Server 新前端试点池，请按照此处列出的步骤在拓扑中的服务器上安装 [Skype for Business Server](../../SfbServer/deploy/install/install-skype-for-business-server.md)</span><span class="sxs-lookup"><span data-stu-id="ddebe-136">Before moving to the next section called "Verify pilot pool coexistence with legacy pool" you need to install the Skype for Business Server new Front End pilot pool we just defined in the published topology, follow the procedures outlined here [Install Skype for Business Server on servers in the topology](../../SfbServer/deploy/install/install-skype-for-business-server.md)</span></span>

13. <span data-ttu-id="ddebe-137">完成上一步后，移至下一部分以验证试点池与旧池的共存。</span><span class="sxs-lookup"><span data-stu-id="ddebe-137">Once previous step is complete, move to the next section to Verify pilot pool coexistence with legacy pool.</span></span>
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
