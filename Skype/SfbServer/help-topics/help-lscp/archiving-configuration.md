---
title: 存档配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 使用存档配置来控制您的业务服务器部署，包括启用和禁用以下选项的 Skype 的存档选项：
ms.openlocfilehash: ac03dd94a83a755c06e88b2abce27bde9625453a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887137"
---
# <a name="archiving-configuration"></a><span data-ttu-id="d5000-103">存档配置</span><span class="sxs-lookup"><span data-stu-id="d5000-103">Archiving Configuration</span></span>
 
<span data-ttu-id="d5000-104">使用存档配置来控制您的业务服务器部署，包括启用和禁用以下选项的 Skype 的存档选项：</span><span class="sxs-lookup"><span data-stu-id="d5000-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="d5000-105">存档失败时阻止即时消息 (IM) 或会议会话</span><span class="sxs-lookup"><span data-stu-id="d5000-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="d5000-106">与 Exchange 2013 存储，为用户的集成驻留在 Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="d5000-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="d5000-107">清除存档数据</span><span class="sxs-lookup"><span data-stu-id="d5000-107">Purging of archived data</span></span>
    
<span data-ttu-id="d5000-108">存档配置包括全局配置以及可选的一个或多个站点和池存档配置：</span><span class="sxs-lookup"><span data-stu-id="d5000-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="d5000-109">**全局配置**默认情况下，所有 Skype 业务服务器部署中创建全局配置。</span><span class="sxs-lookup"><span data-stu-id="d5000-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="d5000-110">您可以编辑全局配置，但无法删除此存档配置。</span><span class="sxs-lookup"><span data-stu-id="d5000-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="d5000-111">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="d5000-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="d5000-112">**网站配置 （可选）** 您可以指定一个或多个站点存档配置，其中每个您可以配置为特定站点的存档选项的控件。</span><span class="sxs-lookup"><span data-stu-id="d5000-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="d5000-113">站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="d5000-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="d5000-114">可以编辑或删除站点配置。</span><span class="sxs-lookup"><span data-stu-id="d5000-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="d5000-115">**池配置 （可选）** 您可以指定一个或多个池存档配置，控制特定池的存档选项。</span><span class="sxs-lookup"><span data-stu-id="d5000-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="d5000-116">池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。</span><span class="sxs-lookup"><span data-stu-id="d5000-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="d5000-117">可以编辑或删除池配置。</span><span class="sxs-lookup"><span data-stu-id="d5000-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d5000-118">存档配置适用于用户的企业服务器驻留在 Skype 和，如果您使用 Exchange 存储存档数据，Microsoft Exchange 中向用户驻留在 Exchange 2013 但略有不同的用户驻留在 Exchange 2013 上实现。</span><span class="sxs-lookup"><span data-stu-id="d5000-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="d5000-119">将在下节中介绍这些差异。</span><span class="sxs-lookup"><span data-stu-id="d5000-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="d5000-p105">“**存档配置**”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档配置启用的存档选项。在“**存档配置**”页上，您有以下选项：</span><span class="sxs-lookup"><span data-stu-id="d5000-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="d5000-123">**新**您可以添加一个或多个以下可选存档配置。</span><span class="sxs-lookup"><span data-stu-id="d5000-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="d5000-124">站点配置</span><span class="sxs-lookup"><span data-stu-id="d5000-124">Site configuration</span></span>
    
  - <span data-ttu-id="d5000-125">池配置</span><span class="sxs-lookup"><span data-stu-id="d5000-125">Pool configuration</span></span>
    
- <span data-ttu-id="d5000-126">**编辑**您可以更改的任何页面上列出在存档配置的选项。</span><span class="sxs-lookup"><span data-stu-id="d5000-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="d5000-127">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d5000-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="d5000-128">**显示详细信息**此选项可打开一个对话框，您可以在其中更改所选的存档配置的存档选项。</span><span class="sxs-lookup"><span data-stu-id="d5000-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="d5000-129">您仅可以显示一次一个的存档配置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d5000-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="d5000-130">**选择全部**此选项可选择列表中所有存档配置。</span><span class="sxs-lookup"><span data-stu-id="d5000-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="d5000-131">**删除**此选项可删除所有选定的存档配置。</span><span class="sxs-lookup"><span data-stu-id="d5000-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="d5000-132">**操作**您可以使用此选项可快速启用或禁用存档 IM 会话或 web 会议会话中列出在页上，而不是编辑配置任何配置。</span><span class="sxs-lookup"><span data-stu-id="d5000-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="d5000-133">可在**操作**下的选项取决于当前在存档配置中指定哪些选项。</span><span class="sxs-lookup"><span data-stu-id="d5000-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="d5000-134">所有选项都都可用，除当前选项生效的存档配置。</span><span class="sxs-lookup"><span data-stu-id="d5000-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="d5000-135">选项包括：</span><span class="sxs-lookup"><span data-stu-id="d5000-135">Options include the following:</span></span>
    
  - <span data-ttu-id="d5000-136">**存档 IM 会话**</span><span class="sxs-lookup"><span data-stu-id="d5000-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="d5000-137">**存档 IM 和 Web 会议会话**</span><span class="sxs-lookup"><span data-stu-id="d5000-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="d5000-138">**禁用存档**</span><span class="sxs-lookup"><span data-stu-id="d5000-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="d5000-139">**刷新**您可以刷新**存档配置**页以验证所有存档配置的选项状态。</span><span class="sxs-lookup"><span data-stu-id="d5000-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="d5000-140">有关的存档功能和功能，包括 Exchange 集成的详细信息，请参阅[规划存档中的业务服务器 2015 Skype](../../plan-your-deployment/archiving/archiving.md)、[业务服务器 2015年的 Skype 存档的部署](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档中的 Skype业务服务器 2015年](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="d5000-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

