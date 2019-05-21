---
title: 部署试点 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主题重点介绍部署 Skype for Business Server 2019 Edge 服务器之前应注意的配置设置。 Skype for business Server 2019 的部署和配置过程非常类似于 Skype for business Server 2015。 本部分仅重点介绍您在试验池部署中应考虑的要点。 有关详细步骤, 请参阅部署文档中的 Skype for business Server 2019 中的部署外部用户访问 (介绍部署过程), 还提供外部用户访问的配置信息。
ms.openlocfilehash: f692eb5ad4a24b47a8bab7a56be218eab04af7dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280915"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="5ccf6-106">部署试点 Edge Server</span><span class="sxs-lookup"><span data-stu-id="5ccf6-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="5ccf6-107">本主题重点介绍部署 Skype for Business Server 2019 Edge 服务器之前应注意的配置设置。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="5ccf6-108">Skype for business Server 2019 的部署和配置过程非常类似于 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="5ccf6-109">本部分仅重点介绍您在试验池部署中应考虑的要点。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="5ccf6-110">通过 "**定义新的边缘池**" 向导导航时, 请查看以下步骤中所示的关键配置设置。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="5ccf6-111">请注意, 仅显示 "**定义新边缘池**" 向导的几个页面。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="5ccf6-112">定义边缘池</span><span class="sxs-lookup"><span data-stu-id="5ccf6-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="5ccf6-113">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="5ccf6-114">导航到 Skype for business 服务器2019节点。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="5ccf6-115">右键单击 "**边缘池**", 然后单击 "**新建边缘池**"。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![定义 "新建边缘池" 对话框](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="5ccf6-117">边缘池可以是**多台计算机池**或**单个计算机池**。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![定义 "边缘池 FQDN" 对话框](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="5ccf6-119">在 "**选择功能**" 页面上, 不要启用联盟或 XMPP 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="5ccf6-120">联合身份验证和 XMPP 联合身份验证当前通过旧版 Edge 服务器路由。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="5ccf6-121">将在迁移的后续阶段配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="5ccf6-122">继续完成以下向导页:**外部 fqdn**、**定义内部 Ip 地址**以及**定义外部 IP 地址**。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="5ccf6-123">在 "**定义下一个跃点服务器**" 页面上, 选择旧版 Edge 池的下一跃点的 Director。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     !["定义下一跃点" 对话框](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="5ccf6-125">此时, 在 "**关联前端或中介池**" 页面上, 不要将池与此边界池关联。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="5ccf6-126">外部媒体流量当前通过旧版 Edge 服务器路由。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="5ccf6-127">将在迁移的后续阶段配置此设置。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-127">This setting will be configured in a later phase of migration.</span></span> 
    
     !["关联前端池" 对话框](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="5ccf6-129">单击 "**完成**", 然后**发布**拓扑。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="5ccf6-130">按照部署文档中的步骤在新边缘服务器上安装文件、配置证书并启动服务。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="5ccf6-131">请务必遵循部署文档的主题中的指南。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="5ccf6-132">本部分仅提供了有关安装这些服务器角色时的配置设置指南。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="5ccf6-133">现在, 你应该与 Skype for business Server 2019 Edge 服务器部署并行部署旧式 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="5ccf6-134">验证两个部署是否正常运行, 服务是否已启动, 并且你可以在迁移到下一阶段之前管理每个部署。</span><span class="sxs-lookup"><span data-stu-id="5ccf6-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

