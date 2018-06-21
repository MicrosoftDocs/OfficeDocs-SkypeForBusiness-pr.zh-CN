---
title: Skype for Business Server 控制面板的首次运行检查表
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: 欢迎使用 Skype 业务 Server Control Panel，管理和 Skype 管理业务服务器的基于 web 的用户界面。 您可以使用控制面板执行以前版本中使用 Microsoft 管理控制台执行的各种管理任务。
ms.openlocfilehash: 78c9943145e0dd12feb5b73e165610fef19bf396
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19978081"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a><span data-ttu-id="15697-104">Skype for Business Server 控制面板的首次运行检查表</span><span class="sxs-lookup"><span data-stu-id="15697-104">First Run Checklist for Skype for Business Server Control Panel</span></span>
 
<span data-ttu-id="15697-105">欢迎使用 Skype 业务 Server Control Panel，管理和 Skype 管理业务服务器的基于 web 的用户界面。</span><span class="sxs-lookup"><span data-stu-id="15697-105">Welcome to the Skype for Business Server Control Panel, the web-based user interface for administration and management of Skype for Business Server.</span></span> <span data-ttu-id="15697-106">您可以使用控制面板执行以前版本中使用 Microsoft 管理控制台执行的各种管理任务。</span><span class="sxs-lookup"><span data-stu-id="15697-106">You can use the control panel to perform the types of administrative tasks that were performed for by using the Microsoft Management Console in previous releases.</span></span>
  
<span data-ttu-id="15697-107">有多种我们强烈建议您执行的业务服务器部署 Skype 之后的重要任务。</span><span class="sxs-lookup"><span data-stu-id="15697-107">There are a number of important tasks that we strongly recommend you perform after you have deployed Skype for Business Server.</span></span> <span data-ttu-id="15697-108">其中某些任务是初始配置步骤，您可能已在部署过程中执行过，而另一些任务是对您在部署过程中配置的设置或默认设置的细化或修改。</span><span class="sxs-lookup"><span data-stu-id="15697-108">Some of these tasks are initial configuration steps that you may have already performed during deployment, while others are refinements or modifications to settings that you configured during deployment or default settings.</span></span> <span data-ttu-id="15697-109">本主题中介绍的其他任务可验证您在部署过程中所做的配置。</span><span class="sxs-lookup"><span data-stu-id="15697-109">Other tasks described in this topic validate the configurations you made during the deployment process.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15697-110">下表中执行的任务之前, 确保您登录使用正确的用户权限、 权限和角色的[基于角色的访问控制](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)主题的"角色和作用域"部分中所述。</span><span class="sxs-lookup"><span data-stu-id="15697-110">Before performing the tasks in the following table, ensure that you log on using the correct user rights, permissions, and role as described in the "Roles and Scope" section of the [Role-Based Access Control](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) topic.</span></span>
  
## <a name="first-run-checklist"></a><span data-ttu-id="15697-111">首次运行检查表</span><span class="sxs-lookup"><span data-stu-id="15697-111">First Run Checklist</span></span>

<span data-ttu-id="15697-112">我们强烈建议您查看本主题中提及的任务，然后在组织中的 Lync Server 部署执行的相应过程。</span><span class="sxs-lookup"><span data-stu-id="15697-112">We strongly recommend that you review the tasks referred to in this topic, and then perform the appropriate procedures for the Lync Server deployment in your organization.</span></span>
  
|<span data-ttu-id="15697-113">**任务**</span><span class="sxs-lookup"><span data-stu-id="15697-113">**Task**</span></span>|<span data-ttu-id="15697-114">**控件面板组**</span><span class="sxs-lookup"><span data-stu-id="15697-114">**Control Panel group**</span></span>|<span data-ttu-id="15697-115">**文档**</span><span class="sxs-lookup"><span data-stu-id="15697-115">**Documentation**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15697-116">验证在拓扑中安装的服务是否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="15697-116">Verify the services that you installed in your topology are running as expected.</span></span>  <br/> |<span data-ttu-id="15697-117">**拓扑**</span><span class="sxs-lookup"><span data-stu-id="15697-117">**Topology**</span></span> <br/> |[<span data-ttu-id="15697-118">查看有关服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="15697-118">View Details About a Service</span></span>](http://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|<span data-ttu-id="15697-119">Skype 为用户启用企业服务器。</span><span class="sxs-lookup"><span data-stu-id="15697-119">Enable users for Skype for Business Server.</span></span> <span data-ttu-id="15697-120">（可选)，如果从早期版本迁移，将用户移至 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="15697-120">Optionally and, if migrating from a previous release, move users to Skype for Business Server.</span></span>  <br/> |<span data-ttu-id="15697-121">**用户**</span><span class="sxs-lookup"><span data-stu-id="15697-121">**Users**</span></span> <br/> |[<span data-ttu-id="15697-122">管理用户</span><span class="sxs-lookup"><span data-stu-id="15697-122">Managing Users</span></span>](http://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|<span data-ttu-id="15697-123">如果已部署或要部署企业语音，请配置 SIP 中继连接以启用与公用电话交换网 (PSTN) 的连接。</span><span class="sxs-lookup"><span data-stu-id="15697-123">If you deployed or want to deploy Enterprise Voice, configure a SIP trunk connection to enable connectivity to the public switched telephone network (PSTN).</span></span>  <br/> |<span data-ttu-id="15697-124">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="15697-124">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="15697-125">配置中继和转换规则</span><span class="sxs-lookup"><span data-stu-id="15697-125">Configuring Trunks and Translation Rules</span></span>](http://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|<span data-ttu-id="15697-126">如果已部署企业语音，请验证企业语音路由设置。</span><span class="sxs-lookup"><span data-stu-id="15697-126">If you deployed Enterprise Voice, verify Enterprise Voice routing settings.</span></span>  <br/> |<span data-ttu-id="15697-127">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="15697-127">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="15697-128">测试语音路由</span><span class="sxs-lookup"><span data-stu-id="15697-128">Test Voice Routing</span></span>](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|<span data-ttu-id="15697-129">如果已部署存档服务器，请验证存档策略和设置是否满足组织的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="15697-129">If you deployed Archiving Server, verify that archiving policies and settings meet the compliance needs of your organization.</span></span>  <br/> |<span data-ttu-id="15697-130">**监控和存档**</span><span class="sxs-lookup"><span data-stu-id="15697-130">**Monitoring and Archiving**</span></span> <br/> |[<span data-ttu-id="15697-131">管理存档</span><span class="sxs-lookup"><span data-stu-id="15697-131">Managing Archiving</span></span>](http://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|<span data-ttu-id="15697-132">如果已部署监控服务器，请查看监控服务器报告以查看使用情况和诊断信息。</span><span class="sxs-lookup"><span data-stu-id="15697-132">If you deployed Monitoring Server, view Monitoring Server reports to view usage and diagnostic information.</span></span>  <br/> |<span data-ttu-id="15697-133">**主页**</span><span class="sxs-lookup"><span data-stu-id="15697-133">**Home**</span></span> <br/> |[<span data-ttu-id="15697-134">管理运行状况和监控业务服务器 2015 Skype 中</span><span class="sxs-lookup"><span data-stu-id="15697-134">Manage health and monitoring in Skype for Business Server 2015</span></span>](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |
   

