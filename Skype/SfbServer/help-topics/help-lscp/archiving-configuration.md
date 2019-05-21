---
title: 存档配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: '使用存档配置控制 Skype for Business Server 部署的存档选项, 包括启用和禁用以下选项:'
ms.openlocfilehash: 8f3ed4289d68359cb8eb0d4cb0bfc3a303c53dd3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299846"
---
# <a name="archiving-configuration"></a><span data-ttu-id="f6a69-103">存档配置</span><span class="sxs-lookup"><span data-stu-id="f6a69-103">Archiving Configuration</span></span>
 
<span data-ttu-id="f6a69-104">使用存档配置控制 Skype for Business Server 部署的存档选项, 包括启用和禁用以下选项:</span><span class="sxs-lookup"><span data-stu-id="f6a69-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="f6a69-105">存档失败时阻止即时消息 (IM) 或会议会话</span><span class="sxs-lookup"><span data-stu-id="f6a69-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="f6a69-106">与托管于 Exchange 2013 的用户的 Exchange 2013 存储集成</span><span class="sxs-lookup"><span data-stu-id="f6a69-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="f6a69-107">清除存档数据</span><span class="sxs-lookup"><span data-stu-id="f6a69-107">Purging of archived data</span></span>
    
<span data-ttu-id="f6a69-108">存档配置包括全局配置以及可选的一个或多个站点和池存档配置：</span><span class="sxs-lookup"><span data-stu-id="f6a69-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="f6a69-109">**全局配置**默认情况下, 全局配置在所有 Skype for Business 服务器部署中创建。</span><span class="sxs-lookup"><span data-stu-id="f6a69-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="f6a69-110">您可以编辑全局配置，但无法删除此存档配置。</span><span class="sxs-lookup"><span data-stu-id="f6a69-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="f6a69-111">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="f6a69-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="f6a69-112">**网站配置 (可选)** 你可以指定一个或多个网站存档配置, 每个配置都可以配置用于控制特定网站的存档选项。</span><span class="sxs-lookup"><span data-stu-id="f6a69-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="f6a69-113">站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="f6a69-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="f6a69-114">可以编辑或删除站点配置。</span><span class="sxs-lookup"><span data-stu-id="f6a69-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="f6a69-115">**池配置 (可选)** 你可以指定一个或多个池存档配置, 以控制特定池的存档选项。</span><span class="sxs-lookup"><span data-stu-id="f6a69-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="f6a69-116">池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。</span><span class="sxs-lookup"><span data-stu-id="f6a69-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="f6a69-117">可以编辑或删除池配置。</span><span class="sxs-lookup"><span data-stu-id="f6a69-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f6a69-118">存档配置适用于驻留在 Skype for business Server 上的用户, 并且, 如果你使用 Exchange 将存档数据存储在 Microsoft Exchange 中, 而托管在 exchange 2013 上的用户的执行方式稍有不同, 而托管在 Exchange 2013 上的用户会稍有不同。</span><span class="sxs-lookup"><span data-stu-id="f6a69-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="f6a69-119">将在下节中介绍这些差异。</span><span class="sxs-lookup"><span data-stu-id="f6a69-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="f6a69-p105">“**存档配置**”页将列出为部署配置的每个存档策略。该页还将显示策略名称、范围（全局、站点或用户）以及为每个存档配置启用的存档选项。在“**存档配置**”页上，您有以下选项：</span><span class="sxs-lookup"><span data-stu-id="f6a69-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="f6a69-123">**新**你可以添加以下每个可选存档配置中的一个或多个配置。</span><span class="sxs-lookup"><span data-stu-id="f6a69-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="f6a69-124">站点配置</span><span class="sxs-lookup"><span data-stu-id="f6a69-124">Site configuration</span></span>
    
  - <span data-ttu-id="f6a69-125">池配置</span><span class="sxs-lookup"><span data-stu-id="f6a69-125">Pool configuration</span></span>
    
- <span data-ttu-id="f6a69-126">**编辑**你可以更改页面上列出的任何存档配置的选项。</span><span class="sxs-lookup"><span data-stu-id="f6a69-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="f6a69-127">使用此选项, 您可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f6a69-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="f6a69-128">**显示详细信息**此选项将打开一个对话框, 您可以在其中更改所选存档配置的存档选项。</span><span class="sxs-lookup"><span data-stu-id="f6a69-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="f6a69-129">一次只能显示一个存档配置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6a69-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="f6a69-130">**全选**此选项选择列表中的所有存档配置。</span><span class="sxs-lookup"><span data-stu-id="f6a69-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="f6a69-131">**Delete**此选项将删除所有选定的存档配置。</span><span class="sxs-lookup"><span data-stu-id="f6a69-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="f6a69-132">**操作**你可以使用此选项快速启用或禁用页面上列出的任何配置中的 IM 会话或 web 会议会话的存档, 而不是编辑配置。</span><span class="sxs-lookup"><span data-stu-id="f6a69-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="f6a69-133">"**操作**" 下的可用选项取决于存档配置中当前指定的选项。</span><span class="sxs-lookup"><span data-stu-id="f6a69-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="f6a69-134">除了当前对存档配置有效的选项之外, 所有选项均可用。</span><span class="sxs-lookup"><span data-stu-id="f6a69-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="f6a69-135">选项包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="f6a69-135">Options include the following:</span></span>
    
  - <span data-ttu-id="f6a69-136">**存档 IM 会话**</span><span class="sxs-lookup"><span data-stu-id="f6a69-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="f6a69-137">**存档 IM 和 Web 会议会话**</span><span class="sxs-lookup"><span data-stu-id="f6a69-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="f6a69-138">**禁用存档**</span><span class="sxs-lookup"><span data-stu-id="f6a69-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="f6a69-139">**刷新**你可以刷新 "**存档配置**" 页, 以验证所有存档配置的选项的状态。</span><span class="sxs-lookup"><span data-stu-id="f6a69-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="f6a69-140">有关存档功能和功能 (包括 Exchange 集成) 的详细信息, 请参阅[在 skype for Business server 2015 中计划存档](../../plan-your-deployment/archiving/archiving.md)、[部署 Skype for business server 2015 存档](../../deploy/deploy-archiving/deploy-archiving.md)和[管理 skype for business 中的存档Business Server 2015](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="f6a69-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

