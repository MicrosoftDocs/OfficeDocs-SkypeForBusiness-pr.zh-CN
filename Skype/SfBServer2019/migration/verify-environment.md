---
title: 验证旧环境
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
description: 在将 Skype for Business Server 2019 部署到共存状态之前，您需要验证是否已配置并启动旧版服务。 在部署 Skype for Business Server 2019 试点池之前，请务必确定旧环境中存在的关键服务和功能。 在使用旧版 XMPP 部署在共存状态中部署 Microsoft Skype for Business Server 2019 XMPP 之前，您需要验证是否已配置并启动旧的 XMPP 服务，并确定旧版 XMPP 配置支持的联盟伙伴。
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751674"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="f5eec-105">验证旧环境</span><span class="sxs-lookup"><span data-stu-id="f5eec-105">Verify the legacy environment</span></span>

<span data-ttu-id="f5eec-106">在将 Skype for Business Server 2019 部署到共存状态之前，您需要验证是否已配置并启动旧版服务。</span><span class="sxs-lookup"><span data-stu-id="f5eec-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="f5eec-107">在部署 Skype for business Server 2019 试点池之前，请务必确定旧环境中存在的关键服务和功能。</span><span class="sxs-lookup"><span data-stu-id="f5eec-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="f5eec-108">在将 Microsoft Skype for Business Server 2019 XMPP 部署到旧版 XMPP 部署的共存状态之前，您需要验证是否已配置并启动旧的 XMPP 服务，并确定旧版 XMPP 配置支持的联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="f5eec-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="f5eec-109">验证您的旧部署需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f5eec-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="f5eec-110">验证是否已启动旧版服务</span><span class="sxs-lookup"><span data-stu-id="f5eec-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="f5eec-111">查看拓扑和用户</span><span class="sxs-lookup"><span data-stu-id="f5eec-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="f5eec-112">验证联盟和边缘服务器设置</span><span class="sxs-lookup"><span data-stu-id="f5eec-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="f5eec-113">验证 XMPP 服务和联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="f5eec-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="f5eec-114">验证是否已启动旧版服务</span><span class="sxs-lookup"><span data-stu-id="f5eec-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="f5eec-115">在旧版前端服务器中，导航到 "管理" Tools\Services 小程序。</span><span class="sxs-lookup"><span data-stu-id="f5eec-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="f5eec-116">确认以下服务正在前端服务器上运行：</span><span class="sxs-lookup"><span data-stu-id="f5eec-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![前端服务器上运行的服务的列表](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="f5eec-118">查看 Skype for Business Server 控制面板中的旧版拓扑</span><span class="sxs-lookup"><span data-stu-id="f5eec-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f5eec-119">使用具有 RTCUniversalServerAdmins 组成员身份或者 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="f5eec-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="f5eec-120">打开 "Skype for Business Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f5eec-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f5eec-121">选择“拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5eec-121">Select **Topology**.</span></span> <span data-ttu-id="f5eec-122">验证是否列出了旧版部署中的各个服务器。</span><span class="sxs-lookup"><span data-stu-id="f5eec-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     !["控制面板拓扑" 页面](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="f5eec-124">查看 Skype for Business Server 控制面板中的旧版用户</span><span class="sxs-lookup"><span data-stu-id="f5eec-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f5eec-125">打开 "Skype for Business Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f5eec-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="f5eec-126">选择 "**用户**"，然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="f5eec-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="f5eec-127">验证 "**注册器池**" 列是否指向列出的每个用户的旧版池。</span><span class="sxs-lookup"><span data-stu-id="f5eec-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![控制面板列出用户](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="f5eec-129">验证旧版边缘和联盟设置</span><span class="sxs-lookup"><span data-stu-id="f5eec-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="f5eec-130">启动拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="f5eec-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="f5eec-131">选择“从现有部署下载拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f5eec-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="f5eec-132">选择一个文件名，并使用默认的 tbxml 文件类型保存该拓扑。</span><span class="sxs-lookup"><span data-stu-id="f5eec-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="f5eec-133">展开 "旧版安装" 节点，以显示部署中的各种服务器角色。</span><span class="sxs-lookup"><span data-stu-id="f5eec-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="f5eec-134">选择 "站点" 节点并验证是否设置了 "**站点联盟路由分配**" 值。</span><span class="sxs-lookup"><span data-stu-id="f5eec-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![拓扑生成器、站点联合路由](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="f5eec-136">选择 Standard Edition Server 或 Enterprise Edition 前端池。</span><span class="sxs-lookup"><span data-stu-id="f5eec-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="f5eec-137">确定是否已为低于资源的**关联**配置了边缘池。</span><span class="sxs-lookup"><span data-stu-id="f5eec-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![显示服务器和池的拓扑生成器](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="f5eec-139">选择边缘池并确定下一个跃点池是否在**下一个跃点选择**下配置。</span><span class="sxs-lookup"><span data-stu-id="f5eec-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![拓扑生成器，下一个跃点选择](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="f5eec-141">验证旧版 XMPP 联盟伙伴配置</span><span class="sxs-lookup"><span data-stu-id="f5eec-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="f5eec-142">从旧的 XMPP 服务器导航到“管理工具\服务”小程序。</span><span class="sxs-lookup"><span data-stu-id="f5eec-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="f5eec-143">确认已启动 Office Communications Server XMPP 网关服务。</span><span class="sxs-lookup"><span data-stu-id="f5eec-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office 通信服务器 XMPP 网关服务](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

