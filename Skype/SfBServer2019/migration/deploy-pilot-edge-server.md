---
title: 部署试点边缘服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主题重点介绍您应了解业务 Server 2019 边缘服务器部署您 Skype 之前的配置设置。 业务服务器 2019年的 Skype 的部署和配置过程就如同 Skype 的业务服务器 2015年。 本节仅突出显示试点池中部署的一部分应考虑的要点。 有关详细步骤，请参阅 Skype 中的部署外部用户访问业务服务器 2019年中 for 部署文档，其中介绍的部署过程，并还提供了针对外部用户访问的配置信息。
ms.openlocfilehash: 3ae1508c56ac3240cfb9904415090ff1bdf18677
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029858"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="fcc4e-106">部署试点边缘服务器</span><span class="sxs-lookup"><span data-stu-id="fcc4e-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="fcc4e-107">本主题重点介绍应业务 Server 2019 边缘服务器部署您 Skype 之前了解您的配置设置。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="fcc4e-108">业务服务器 2019年的 Skype 的部署和配置过程就如同 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="fcc4e-109">本节仅突出显示试点池中部署的一部分应考虑的要点。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="fcc4e-110">导航至**定义新边缘池**向导时，查看以下步骤中所示的密钥配置设置。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="fcc4e-111">请注意，只有少数页面的**定义新边缘池**向导所示。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="fcc4e-112">定义边缘池</span><span class="sxs-lookup"><span data-stu-id="fcc4e-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="fcc4e-113">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="fcc4e-114">导航到业务服务器 2019年节点 Skype。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="fcc4e-115">右键单击**边缘池**，然后单击**新建边缘池**。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![定义新建边缘池对话框](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="fcc4e-117">边缘池可以是**多计算机池**或**单计算机池**。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![定义边缘池 FQDN 对话框](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="fcc4e-119">在**选择功能**页上不要启用联盟或 XMPP 联盟。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="fcc4e-120">联盟和 XMPP 联盟同时当前路由通过旧边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="fcc4e-121">将在迁移的更高版本阶段中配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="fcc4e-122">继续完成以下向导页：**外部 Fqdn**、**定义内部 IP 地址**，和**定义外部 IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="fcc4e-123">在**定义下一个跃点服务器**页中，选择旧的边缘池的下一个跃点的控制器。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![定义下一跃点对话框](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="fcc4e-125">在**关联前端或中介池**页上没有相关联池与此边缘池这一次。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="fcc4e-126">当前路由通过旧边缘服务器外部媒体流量。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="fcc4e-127">此设置将在更高版本阶段的迁移配置。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![关联前端池对话框](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="fcc4e-129">单击**完成**，然后**发布**拓扑。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="fcc4e-130">按照部署文档中新的边缘服务器上安装文件，配置证书并启动服务中的步骤。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="fcc4e-131">它是非常重要您按照部署文档中的主题中的准则。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="fcc4e-132">本节只安装这些服务器角色时上配置设置提供的一些指导。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="fcc4e-133">现在，您应具有与业务 Server 2019 边缘服务器部署 Skype 并行部署了旧边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="fcc4e-134">确认同时部署都正常运行，服务已启动，您可以管理每个部署之前将移动到下一个阶段。</span><span class="sxs-lookup"><span data-stu-id="fcc4e-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

