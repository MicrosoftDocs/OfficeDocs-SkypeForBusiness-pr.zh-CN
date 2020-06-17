---
title: 部署试点边缘服务器
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
description: 本主题重点介绍在部署 Skype for Business Server 2019 边缘服务器之前应注意的配置设置。 Skype for business Server 2019 的部署和配置过程与 Skype for business Server 2015 非常相似。 本节仅重点介绍了应作为试点池部署的一部分考虑的关键点。 有关详细步骤，请参阅部署文档中的在 Skype for Business Server 2019 中部署外部用户访问，它介绍了部署过程，同时提供了外部用户访问的配置信息。
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752864"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="2f234-106">部署试点边缘服务器</span><span class="sxs-lookup"><span data-stu-id="2f234-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="2f234-107">本主题重点介绍了在部署 Skype for Business Server 2019 边缘服务器之前应注意的配置设置。</span><span class="sxs-lookup"><span data-stu-id="2f234-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="2f234-108">Skype for business Server 2019 的部署和配置过程与 Skype for business Server 2015 非常相似。</span><span class="sxs-lookup"><span data-stu-id="2f234-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="2f234-109">本节仅重点介绍了应作为试点池部署的一部分考虑的关键点。</span><span class="sxs-lookup"><span data-stu-id="2f234-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="2f234-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span><span class="sxs-lookup"><span data-stu-id="2f234-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="2f234-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span><span class="sxs-lookup"><span data-stu-id="2f234-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="2f234-112">定义边缘池</span><span class="sxs-lookup"><span data-stu-id="2f234-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="2f234-113">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="2f234-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="2f234-114">导航到 Skype for Business Server 2019 节点。</span><span class="sxs-lookup"><span data-stu-id="2f234-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="2f234-115">右键单击“边缘池”\*\*\*\*，然后单击“新建边缘池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2f234-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     !["定义新的边缘池" 对话框](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="2f234-117">边缘池可以是**多计算机池**，也可以是**单计算机池**。</span><span class="sxs-lookup"><span data-stu-id="2f234-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![定义 "边缘池 FQDN" 对话框](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="2f234-119">在“选择功能”\*\*\*\* 页上，不要启用联盟或 XMPP 联盟。</span><span class="sxs-lookup"><span data-stu-id="2f234-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="2f234-120">联盟和 XMPP 联盟当前通过旧版边缘服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="2f234-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="2f234-121">将在迁移的稍后阶段中配置这些功能。</span><span class="sxs-lookup"><span data-stu-id="2f234-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="2f234-122">继续完成以下向导页：**外部 fqdn**、**定义内部 Ip 地址**和**定义外部 ip 地址**。</span><span class="sxs-lookup"><span data-stu-id="2f234-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="2f234-123">在 "**定义下一个跃点服务器**" 页上，选择旧版边缘池的下一个跃点的控制器。</span><span class="sxs-lookup"><span data-stu-id="2f234-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     !["定义下一跃点" 对话框](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="2f234-125">在 "**关联前端或中介池**" 页上，此时不要将池与此边缘池相关联。</span><span class="sxs-lookup"><span data-stu-id="2f234-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="2f234-126">外部媒体流量当前通过旧版边缘服务器路由。</span><span class="sxs-lookup"><span data-stu-id="2f234-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="2f234-127">将在迁移的稍后阶段中配置此设置。</span><span class="sxs-lookup"><span data-stu-id="2f234-127">This setting will be configured in a later phase of migration.</span></span> 
    
     !["关联前端池" 对话框](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="2f234-129">单击 "**完成**"，然后**发布**拓扑。</span><span class="sxs-lookup"><span data-stu-id="2f234-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="2f234-130">按照部署文档中的步骤操作，在新的边缘服务器上安装文件、配置证书并启动服务。</span><span class="sxs-lookup"><span data-stu-id="2f234-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="2f234-131">请务必遵循部署文档中的主题中的准则。</span><span class="sxs-lookup"><span data-stu-id="2f234-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="2f234-132">本节仅提供了一些有关安装这些服务器角色时的配置设置的指南。</span><span class="sxs-lookup"><span data-stu-id="2f234-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="2f234-133">现在，您应该已与 Skype for business Server 2019 Edge 服务器部署并行部署了旧边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="2f234-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="2f234-134">在进入下一个阶段之前，确认这两个部署都正常运行，服务已启动，并且您可以管理每个部署。</span><span class="sxs-lookup"><span data-stu-id="2f234-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

