---
title: Skype for Business Server 控制面板的首次运行清单
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: 欢迎使用 Skype for Business Server 控制面板，这是用于管理 Skype for Business Server 的基于 Web 的用户界面。 可以使用控制面板执行以前版本中使用 Microsoft 管理控制台执行的管理任务类型。
ms.openlocfilehash: 3e8fee53c37079c46862e05f246d984c621b57ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100438"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a><span data-ttu-id="80f6b-104">Skype for Business Server 控制面板的首次运行清单</span><span class="sxs-lookup"><span data-stu-id="80f6b-104">First Run Checklist for Skype for Business Server Control Panel</span></span>

<span data-ttu-id="80f6b-105">欢迎使用 Skype for Business Server 控制面板，这是用于管理 Skype for Business Server 的基于 Web 的用户界面。</span><span class="sxs-lookup"><span data-stu-id="80f6b-105">Welcome to the Skype for Business Server Control Panel, the web-based user interface for administration and management of Skype for Business Server.</span></span> <span data-ttu-id="80f6b-106">可以使用控制面板执行以前版本中使用 Microsoft 管理控制台执行的管理任务类型。</span><span class="sxs-lookup"><span data-stu-id="80f6b-106">You can use the control panel to perform the types of administrative tasks that were performed for by using the Microsoft Management Console in previous releases.</span></span>

<span data-ttu-id="80f6b-107">部署 Skype for Business Server 后，我们强烈建议你执行许多重要任务。</span><span class="sxs-lookup"><span data-stu-id="80f6b-107">There are a number of important tasks that we strongly recommend you perform after you have deployed Skype for Business Server.</span></span> <span data-ttu-id="80f6b-108">其中某些任务是初始配置步骤，您可能已在部署过程中执行过，而另一些任务是对您在部署过程中配置的设置或默认设置的细化或修改。</span><span class="sxs-lookup"><span data-stu-id="80f6b-108">Some of these tasks are initial configuration steps that you may have already performed during deployment, while others are refinements or modifications to settings that you configured during deployment or default settings.</span></span> <span data-ttu-id="80f6b-109">本主题中介绍的其他任务可验证您在部署过程中所做的配置。</span><span class="sxs-lookup"><span data-stu-id="80f6b-109">Other tasks described in this topic validate the configurations you made during the deployment process.</span></span>

> [!NOTE]
> <span data-ttu-id="80f6b-110">在执行下表中的任务之前，请确保使用正确的用户权限和角色登录，如基于角色的访问控制主题的"角色和作用域"[部分所述。](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)</span><span class="sxs-lookup"><span data-stu-id="80f6b-110">Before performing the tasks in the following table, ensure that you log on using the correct user rights, permissions, and role as described in the "Roles and Scope" section of the [Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) topic.</span></span>

## <a name="first-run-checklist"></a><span data-ttu-id="80f6b-111">首次运行检查表</span><span class="sxs-lookup"><span data-stu-id="80f6b-111">First Run Checklist</span></span>

<span data-ttu-id="80f6b-112">强烈建议您查看本主题中提及的任务，然后执行适当的过程以在组织中进行部署。</span><span class="sxs-lookup"><span data-stu-id="80f6b-112">We strongly recommend that you review the tasks referred to in this topic, and then perform the appropriate procedures for deployment in your organization.</span></span>

|<span data-ttu-id="80f6b-113">**任务**</span><span class="sxs-lookup"><span data-stu-id="80f6b-113">**Task**</span></span>|<span data-ttu-id="80f6b-114">**控制面板组**</span><span class="sxs-lookup"><span data-stu-id="80f6b-114">**Control Panel group**</span></span>|<span data-ttu-id="80f6b-115">**文档**</span><span class="sxs-lookup"><span data-stu-id="80f6b-115">**Documentation**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80f6b-116">验证在拓扑中安装的服务是否按预期运行。</span><span class="sxs-lookup"><span data-stu-id="80f6b-116">Verify the services that you installed in your topology are running as expected.</span></span>  <br/> |<span data-ttu-id="80f6b-117">**拓扑**</span><span class="sxs-lookup"><span data-stu-id="80f6b-117">**Topology**</span></span> <br/> |[<span data-ttu-id="80f6b-118">查看有关服务的详细信息</span><span class="sxs-lookup"><span data-stu-id="80f6b-118">View Details About a Service</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|<span data-ttu-id="80f6b-119">为用户启用 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="80f6b-119">Enable users for Skype for Business Server.</span></span> <span data-ttu-id="80f6b-120">或者，如果从早期版本迁移，将用户移动到 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="80f6b-120">Optionally and, if migrating from a previous release, move users to Skype for Business Server.</span></span>  <br/> |<span data-ttu-id="80f6b-121">**用户**</span><span class="sxs-lookup"><span data-stu-id="80f6b-121">**Users**</span></span> <br/> |[<span data-ttu-id="80f6b-122">管理用户</span><span class="sxs-lookup"><span data-stu-id="80f6b-122">Managing Users</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|<span data-ttu-id="80f6b-123">如果已部署或要部署企业语音，请配置 SIP 中继连接以启用与公用电话交换网 (PSTN) 的连接。</span><span class="sxs-lookup"><span data-stu-id="80f6b-123">If you deployed or want to deploy Enterprise Voice, configure a SIP trunk connection to enable connectivity to the public switched telephone network (PSTN).</span></span>  <br/> |<span data-ttu-id="80f6b-124">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="80f6b-124">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="80f6b-125">配置中继和转换规则</span><span class="sxs-lookup"><span data-stu-id="80f6b-125">Configuring Trunks and Translation Rules</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|<span data-ttu-id="80f6b-126">如果已部署企业语音，请验证企业语音路由设置。</span><span class="sxs-lookup"><span data-stu-id="80f6b-126">If you deployed Enterprise Voice, verify Enterprise Voice routing settings.</span></span>  <br/> |<span data-ttu-id="80f6b-127">**语音路由**</span><span class="sxs-lookup"><span data-stu-id="80f6b-127">**Voice Routing**</span></span> <br/> |[<span data-ttu-id="80f6b-128">测试语音路由</span><span class="sxs-lookup"><span data-stu-id="80f6b-128">Test Voice Routing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|<span data-ttu-id="80f6b-129">如果已部署存档服务器，请验证存档策略和设置是否满足组织的合规性要求。</span><span class="sxs-lookup"><span data-stu-id="80f6b-129">If you deployed Archiving Server, verify that archiving policies and settings meet the compliance needs of your organization.</span></span>  <br/> |<span data-ttu-id="80f6b-130">**监控和存档**</span><span class="sxs-lookup"><span data-stu-id="80f6b-130">**Monitoring and Archiving**</span></span> <br/> |[<span data-ttu-id="80f6b-131">管理存档</span><span class="sxs-lookup"><span data-stu-id="80f6b-131">Managing Archiving</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|<span data-ttu-id="80f6b-132">如果已部署监控服务器，请查看监控服务器报告以查看使用情况和诊断信息。</span><span class="sxs-lookup"><span data-stu-id="80f6b-132">If you deployed Monitoring Server, view Monitoring Server reports to view usage and diagnostic information.</span></span>  <br/> |<span data-ttu-id="80f6b-133">**主页**</span><span class="sxs-lookup"><span data-stu-id="80f6b-133">**Home**</span></span> <br/> |[<span data-ttu-id="80f6b-134">在 Skype for Business Server 中管理运行状况和监控</span><span class="sxs-lookup"><span data-stu-id="80f6b-134">Manage health and monitoring in Skype for Business Server</span></span>](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |