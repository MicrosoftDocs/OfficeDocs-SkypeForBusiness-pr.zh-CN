---
title: 确认旧环境
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署以共存的业务服务器 2019 Skype 之前, 需要确认已配置并启动旧式服务。 务必来确定关键服务和在旧环境中，在部署业务服务器 2019年试点池 Skype 之前存在的功能。 在之前部署 Microsoft Skype 业务服务器 2019 XMPP 与旧的 XMPP 部署以共存，您需要验证旧版 XMPP 服务已配置并启动，并确认旧的 XMPP 配置的联盟的伙伴支持。
ms.openlocfilehash: 0f9812efe966d72eba1eeead9d74780f2ba16661
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235112"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="dbf44-105">确认旧环境</span><span class="sxs-lookup"><span data-stu-id="dbf44-105">Verify the legacy environment</span></span>

<span data-ttu-id="dbf44-106">部署以共存的业务服务器 2019 Skype 之前, 需要确认已配置并启动旧式服务。</span><span class="sxs-lookup"><span data-stu-id="dbf44-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="dbf44-107">务必来确定关键服务和部署业务服务器 2019年试点池 Skype 之前旧环境中存在的功能。</span><span class="sxs-lookup"><span data-stu-id="dbf44-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="dbf44-108">在之前部署 Microsoft Skype 业务服务器 2019 XMPP 与旧的 XMPP 部署以共存，您需要验证已将旧的 XMPP 服务配置并启动，并确定该联盟伙伴的旧的 XMPP配置为支持。</span><span class="sxs-lookup"><span data-stu-id="dbf44-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="dbf44-109">验证旧版部署涉及以下：</span><span class="sxs-lookup"><span data-stu-id="dbf44-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="dbf44-110">验证已启动旧的服务</span><span class="sxs-lookup"><span data-stu-id="dbf44-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="dbf44-111">查看拓扑和用户</span><span class="sxs-lookup"><span data-stu-id="dbf44-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="dbf44-112">验证联盟和边缘服务器设置</span><span class="sxs-lookup"><span data-stu-id="dbf44-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="dbf44-113">确认 XMPP 服务和联盟的伙伴</span><span class="sxs-lookup"><span data-stu-id="dbf44-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="dbf44-114">确认旧服务已启动</span><span class="sxs-lookup"><span data-stu-id="dbf44-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="dbf44-115">从旧前端服务器，导航到管理工具 \ 服务小程序。</span><span class="sxs-lookup"><span data-stu-id="dbf44-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="dbf44-116">确认以下服务都在前端服务器上运行：</span><span class="sxs-lookup"><span data-stu-id="dbf44-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![前端服务器上运行的服务列表](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="dbf44-118">为业务 Server Control Panel 查看 Skype 中的将旧拓扑</span><span class="sxs-lookup"><span data-stu-id="dbf44-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dbf44-119">使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="dbf44-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="dbf44-120">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="dbf44-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="dbf44-121">选择**拓扑**。</span><span class="sxs-lookup"><span data-stu-id="dbf44-121">Select **Topology**.</span></span> <span data-ttu-id="dbf44-122">确认列出旧部署中的各个服务器。</span><span class="sxs-lookup"><span data-stu-id="dbf44-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![控件控制面板拓扑页](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="dbf44-124">查看旧用户中的业务 Server Control Panel Skype</span><span class="sxs-lookup"><span data-stu-id="dbf44-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dbf44-125">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="dbf44-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="dbf44-126">选择**用户**，然后单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="dbf44-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="dbf44-127">确认**注册器池**列指向旧池列出的每个用户。</span><span class="sxs-lookup"><span data-stu-id="dbf44-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![列出用户控制面板](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="dbf44-129">确认旧的边缘服务器和联合身份验证设置</span><span class="sxs-lookup"><span data-stu-id="dbf44-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="dbf44-130">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="dbf44-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="dbf44-131">选择**从现有部署下载拓扑**。</span><span class="sxs-lookup"><span data-stu-id="dbf44-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="dbf44-132">选择文件名并保存具有默认.tbxml 文件类型的拓扑。</span><span class="sxs-lookup"><span data-stu-id="dbf44-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="dbf44-133">展开以显示部署中的各个服务器角色的旧式安装节点。</span><span class="sxs-lookup"><span data-stu-id="dbf44-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="dbf44-134">选择网站节点并验证设置了**站点联盟路由分配**值。</span><span class="sxs-lookup"><span data-stu-id="dbf44-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![拓扑生成器，站点联盟路由](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="dbf44-136">选择 Standard Edition Server 或 Enterprise Edition 前端池。</span><span class="sxs-lookup"><span data-stu-id="dbf44-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="dbf44-137">确定是否已下方**关联**的媒体配置边缘池。</span><span class="sxs-lookup"><span data-stu-id="dbf44-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![显示服务器和池的拓扑生成器](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="dbf44-139">选择边缘池，并确定是否下一个跃点池配置**下一个跃点选择**下方。</span><span class="sxs-lookup"><span data-stu-id="dbf44-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![拓扑生成器下, 一个跃点选择](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="dbf44-141">验证旧版 XMPP 联盟的伙伴配置</span><span class="sxs-lookup"><span data-stu-id="dbf44-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="dbf44-142">从旧版 XMPP 服务器中，导航到管理工具 \ 服务小程序。</span><span class="sxs-lookup"><span data-stu-id="dbf44-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="dbf44-143">确认 Office Communications Server XMPP 网关服务已启动。</span><span class="sxs-lookup"><span data-stu-id="dbf44-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office Communications Server XMPP 网关服务](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

