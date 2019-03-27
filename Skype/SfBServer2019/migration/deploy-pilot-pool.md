---
title: 部署试点池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 一个迁移到 Skype 的业务服务器 2019年所需的第一个步骤是部署试点池。 试点池是与旧部署测试业务服务器 2019 Skype 的共存的位置。 共存一直持续到移动所有用户和池到 Skype 的业务服务器 2019年的临时状态。
ms.openlocfilehash: e0ac949b0cc7a52e1da5edd9f150e5f59717c08f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890653"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="ac33a-105">为业务服务器 2019年试点池部署 Skype</span><span class="sxs-lookup"><span data-stu-id="ac33a-105">Deploy Skype for Business Server 2019 pilot pool</span></span>

<span data-ttu-id="ac33a-106">一个迁移到 Skype 的业务服务器 2019年所需的第一个步骤是部署试点池。</span><span class="sxs-lookup"><span data-stu-id="ac33a-106">One of the first steps required for migration to Skype for Business Server 2019 is to deploy a pilot pool.</span></span> <span data-ttu-id="ac33a-107">试点池是与旧部署测试业务服务器 2019 Skype 的共存的位置。</span><span class="sxs-lookup"><span data-stu-id="ac33a-107">The pilot pool is where you test coexistence of Skype for Business Server 2019 with your legacy deployment.</span></span> <span data-ttu-id="ac33a-108">共存一直持续到移动所有用户和池到 Skype 的业务服务器 2019年的临时状态。</span><span class="sxs-lookup"><span data-stu-id="ac33a-108">Coexistence is a temporary state that lasts until you have moved all users and pools to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="ac33a-109">部署试点池时，您可以使用定义新前端池向导。</span><span class="sxs-lookup"><span data-stu-id="ac33a-109">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="ac33a-110">您应在您的业务服务器 2019年试点池已在旧池中的 Skype 部署相同的功能和工作负荷。</span><span class="sxs-lookup"><span data-stu-id="ac33a-110">You should deploy the same features and workloads in your Skype for Business Server 2019 pilot pool that you have in your legacy pool.</span></span> <span data-ttu-id="ac33a-111">如果您部署存档服务器、 监控服务器或 System Center Operations Manager 存档或监控旧环境，并且想要继续存档或监控在迁移过程，您需要同时部署中的这些功能您试验环境。</span><span class="sxs-lookup"><span data-stu-id="ac33a-111">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your legacy environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="ac33a-112">部署存档或监控您的旧版本环境不会捕获您 Skype 业务服务器 2019年环境中的数据。</span><span class="sxs-lookup"><span data-stu-id="ac33a-112">The version you deployed to archive or monitor your legacy environment will not capture data in your Skype for Business Server 2019 environment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ac33a-113">功能和设置应考虑您的总体试点池部署过程的一部分，讨论了下面的过程。</span><span class="sxs-lookup"><span data-stu-id="ac33a-113">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="ac33a-114">本节仅突出显示试点池中部署的一部分应考虑的要点。</span><span class="sxs-lookup"><span data-stu-id="ac33a-114">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="ac33a-115">若要部署的业务服务器 2019年试点池 Skype</span><span class="sxs-lookup"><span data-stu-id="ac33a-115">To deploy a Skype for Business Server 2019 pilot pool</span></span>

1. <span data-ttu-id="ac33a-116">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="ac33a-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="ac33a-117">展开树，直到到达**业务服务器 2019年的 Skype** > **Enterprise Edition 前端池**。</span><span class="sxs-lookup"><span data-stu-id="ac33a-117">Expand the tree until you reach **Skype for Business Server 2019** > **Enterprise Edition Front End pools**.</span></span>
    
3. <span data-ttu-id="ac33a-118">右键单击**Enterprise Edition 前端池**，然后选择**新前端池**。</span><span class="sxs-lookup"><span data-stu-id="ac33a-118">Right-click **Enterprise Edition Front End pools** and select **New Front End Pool**.</span></span>
  
4. <span data-ttu-id="ac33a-119">输入池完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ac33a-119">Enter the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="ac33a-120">定义您的试点池时，您可以选择部署 Enterprise Edition 前端池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="ac33a-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="ac33a-121">Skype 的业务服务器 2019年不需要试点池功能匹配内容已在旧池中部署。</span><span class="sxs-lookup"><span data-stu-id="ac33a-121">Skype for Business Server 2019 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ac33a-122">池或服务器为试点池定义的 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ac33a-122">The pool or server FQDN that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="ac33a-123">它不能匹配当前部署的旧池或当前部署的任何其他服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ac33a-123">It cannot match the name of the currently deployed legacy pool or any other servers currently deployed.</span></span> 
  
5. <span data-ttu-id="ac33a-124">在**选择功能**页上，选择您希望此前端池上的功能对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="ac33a-124">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="ac33a-125">如果您正在部署仅即时消息 (IM) 和状态功能，例如，应选择会议复选框，以允许多方 IM，但不是应选择的电话拨入式 (PSTN) 会议，企业语音或 Call Admission Control 检查框中，因为它们代表语音、 视频和协作会议功能。</span><span class="sxs-lookup"><span data-stu-id="ac33a-125">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but you would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. <span data-ttu-id="ac33a-126">在**选择并置的服务器角色**页中，我们建议您选择要将 Skype 中的中介服务器并置的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="ac33a-126">On the **Select collocated server roles** page, we recommend that you choose to collocate the Mediation Server in Skype for Business Server 2019.</span></span> <span data-ttu-id="ac33a-127">合并时旧拓扑与 Skype 的业务服务器 2019年，我们需要您首先并置旧中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ac33a-127">When merging a legacy topology with Skype for Business Server 2019, we require that you first collocate the legacy Mediation Server.</span></span> <span data-ttu-id="ac33a-128">合并拓扑并配置后 Skype 业务 Server 2019 中介服务器，可以决定是否保留并置的中介服务器，或将其更改为独立服务器时将中介服务器角色到 Skype 移动业务服务器2019 更高版本中的部署过程。</span><span class="sxs-lookup"><span data-stu-id="ac33a-128">After merging the topologies and configuring the Skype for Business Server 2019 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Skype for Business Server 2019 later in the deployment process.</span></span> 
   
7. <span data-ttu-id="ac33a-129">在**关联服务器角色与此前端池**页上试点池部署期间*不*选择**启用此前端池的媒体组件使用的边缘池**选项。</span><span class="sxs-lookup"><span data-stu-id="ac33a-129">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, *do not* choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="ac33a-130">这是迁移的一项功能将启用，还可以联机在更高版本阶段。</span><span class="sxs-lookup"><span data-stu-id="ac33a-130">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="ac33a-131">保留此设置清除现在。</span><span class="sxs-lookup"><span data-stu-id="ac33a-131">Keep this setting cleared for now.</span></span> 
  
8. <span data-ttu-id="ac33a-132">在**选择 Office Web Apps 服务器**页上，单击**新建**，并指定应用程序服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ac33a-132">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
  
9. <span data-ttu-id="ac33a-133">在**定义存档 SQL Server 存储**页上时定义的两个 Skype 业务 Server 存档和监控的 SQL Server 存储，选择为 Skype 前面创建的业务服务器 2019年的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="ac33a-133">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Skype for Business Server Archiving and Monitoring, select the SQL Server instance created earlier for Skype for Business Server 2019.</span></span> 
  
10. <span data-ttu-id="ac33a-134">若要发布拓扑，右键单击**Skype 业务服务器**节点，然后单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="ac33a-134">To publish your topology, right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
  
11. <span data-ttu-id="ac33a-135">完成发布过程后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="ac33a-135">When the publish process has completed, click **Finish**.</span></span>
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

