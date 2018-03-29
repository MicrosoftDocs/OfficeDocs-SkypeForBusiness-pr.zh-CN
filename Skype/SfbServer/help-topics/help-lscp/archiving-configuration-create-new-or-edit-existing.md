---
title: 创建新模板或编辑现有的存档配置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：
ms.openlocfilehash: 49227ded326c893d42852796e9c783a2dc4096cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a><span data-ttu-id="0dce5-104">存档配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="0dce5-104">Archiving Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="0dce5-p102">使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：</span><span class="sxs-lookup"><span data-stu-id="0dce5-p102">You use Archiving configurations to control archiving options for your deployment. Archiving configurations include the global configuration, and, optionally, one or more site and pool configurations:</span></span>
  
- <span data-ttu-id="0dce5-107">**全局配置**默认情况下创建全局配置。</span><span class="sxs-lookup"><span data-stu-id="0dce5-107">**Global configuration** The global configuration is created by default.</span></span> <span data-ttu-id="0dce5-108">您可以编辑全局配置，但无法删除此存档配置。</span><span class="sxs-lookup"><span data-stu-id="0dce5-108">You can edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="0dce5-109">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="0dce5-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="0dce5-110">**站点配置 （可选）**您可以指定一个或多个站点存档配置，您可以配置归档选项针对特定的网站控制每个。</span><span class="sxs-lookup"><span data-stu-id="0dce5-110">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="0dce5-111">站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="0dce5-111">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="0dce5-112">可以编辑或删除站点配置。</span><span class="sxs-lookup"><span data-stu-id="0dce5-112">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="0dce5-113">**池配置 （可选）**您可以指定一个或多个池存档配置，控制归档选项为一个特定的池。</span><span class="sxs-lookup"><span data-stu-id="0dce5-113">**Pool configuration (optional)** You can specify one or more pool Archiving configurations, to control archiving options for a specific pool.</span></span> <span data-ttu-id="0dce5-114">池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。</span><span class="sxs-lookup"><span data-stu-id="0dce5-114">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="0dce5-115">可以编辑或删除池配置。</span><span class="sxs-lookup"><span data-stu-id="0dce5-115">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0dce5-116">存档的配置将应用于用户业务服务器驻留在 Skype 上，如果启用 Microsoft Exchange 集成选项，使用 Exchange 2013 存档数据存储在 Microsoft Exchange 用户驻留在 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="0dce5-116">Archiving configurations apply to users homed on Skype for Business Server, and, if you enable the Microsoft Exchange integration option to use Exchange 2013 to store archiving data in Microsoft Exchange, to users homed on Exchange 2013.</span></span> <span data-ttu-id="0dce5-117">但是，某些选项将实现略有不同的用户驻留在 Exchange 2013 下一节中所述。</span><span class="sxs-lookup"><span data-stu-id="0dce5-117">However, some options are implemented slightly differently for users homed on Exchange 2013, as described in the next section.</span></span> 
  
<span data-ttu-id="0dce5-118">若要配置新的或现有的存档配置的设置，请指定以下选项：</span><span class="sxs-lookup"><span data-stu-id="0dce5-118">To configure the settings for a new or existing Archiving configuration, specify the following options:</span></span>
- <span data-ttu-id="0dce5-119">**名称**每个存档配置需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="0dce5-119">**Name** Each Archiving configuration requires a name.</span></span> <span data-ttu-id="0dce5-120">名称取决于您在添加或编辑的配置的类型：</span><span class="sxs-lookup"><span data-stu-id="0dce5-120">The name is determined by the type of configuration you are adding or editing:</span></span>
    
  - <span data-ttu-id="0dce5-121">**全局配置**默认名称是全局。</span><span class="sxs-lookup"><span data-stu-id="0dce5-121">**Global configuration** The default name is Global.</span></span> <span data-ttu-id="0dce5-122">例如，Contoso 北美机构。</span><span class="sxs-lookup"><span data-stu-id="0dce5-122">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="0dce5-123">**站点配置**该列表包含在部署中的可用站点。</span><span class="sxs-lookup"><span data-stu-id="0dce5-123">**Site configuration** The list contains the available sites in your deployment.</span></span> <span data-ttu-id="0dce5-124">单击某个站点将其选中。</span><span class="sxs-lookup"><span data-stu-id="0dce5-124">Click a single site to select it.</span></span> <span data-ttu-id="0dce5-125">例如，Redmond 数据中心。</span><span class="sxs-lookup"><span data-stu-id="0dce5-125">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="0dce5-126">**池配置**指定适当的名称，它可以是一个特定的前端池或标准版服务器部署中的名称。</span><span class="sxs-lookup"><span data-stu-id="0dce5-126">**Pool configuration** Specify an appropriate name, which can be the name of a specific Front End pool or Standard Edition Server in your deployment.</span></span> <span data-ttu-id="0dce5-127">例如，市场营销部门。</span><span class="sxs-lookup"><span data-stu-id="0dce5-127">For example, Marketing Division.</span></span>
    
- <span data-ttu-id="0dce5-128">**说明**这是可选的。</span><span class="sxs-lookup"><span data-stu-id="0dce5-128">**Description** This is optional.</span></span> <span data-ttu-id="0dce5-129">使用它来提供更多详细信息，如使用配置的范围。</span><span class="sxs-lookup"><span data-stu-id="0dce5-129">Use it to provide additional details, such as the scope or use of the configuration.</span></span> <span data-ttu-id="0dce5-130">例如，协调与其他站点的法律部门。</span><span class="sxs-lookup"><span data-stu-id="0dce5-130">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="0dce5-131">**存档设置**选项如下所示：</span><span class="sxs-lookup"><span data-stu-id="0dce5-131">**Archiving setting** Options include the following:</span></span>
    
  - <span data-ttu-id="0dce5-132">**存档 IM 会话**</span><span class="sxs-lookup"><span data-stu-id="0dce5-132">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="0dce5-133">**存档 IM 和 Web 会议会话**</span><span class="sxs-lookup"><span data-stu-id="0dce5-133">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="0dce5-134">**禁用存档**</span><span class="sxs-lookup"><span data-stu-id="0dce5-134">**Disable archiving**</span></span>
    
- <span data-ttu-id="0dce5-135">**阻止即时消息 (IM) 或 web 会议会话如果存档失败则**以下故障：</span><span class="sxs-lookup"><span data-stu-id="0dce5-135">**Block instant messaging (IM) or web conferencing sessions if archiving fails** Failures include the following:</span></span>
    
  - <span data-ttu-id="0dce5-136">**即时消息**故障可能是一个完整的数据库或存储服务问题。</span><span class="sxs-lookup"><span data-stu-id="0dce5-136">**IM** A failure could be a full database or problem with the storage service.</span></span> <span data-ttu-id="0dce5-137">在此情况下，将阻止为存档启用的用户使用 IM。</span><span class="sxs-lookup"><span data-stu-id="0dce5-137">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
  - <span data-ttu-id="0dce5-138">**会议**故障可能是不可用的文件共享或存储服务有问题。</span><span class="sxs-lookup"><span data-stu-id="0dce5-138">**Conferencing** A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="0dce5-139">在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。</span><span class="sxs-lookup"><span data-stu-id="0dce5-139">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="0dce5-140">IM 和会议都能在修复故障后自动恢复。</span><span class="sxs-lookup"><span data-stu-id="0dce5-140">Both IM and conferencing automatically recover after the failures are corrected.</span></span>
    
- <span data-ttu-id="0dce5-141">**Microsoft Exchange 集成**如果必须驻留在 Exchange 2013 的用户，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="0dce5-141">**Microsoft Exchange integration** Select this option if you have users who are homed on Exchange 2013.</span></span> <span data-ttu-id="0dce5-142">使用此选项，Exchange 2013 用于存储数据的用户，如果他们的邮箱已经置于适当地存放。</span><span class="sxs-lookup"><span data-stu-id="0dce5-142">With this option, Exchange 2013 is used to store data for those users, if their mailboxes have been placed on In-Place Hold.</span></span> <span data-ttu-id="0dce5-143">如果您的所有用户都驻留在 Exchange 2013，您不需要设置单独的 SQL Server 数据库，用于存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="0dce5-143">If all your users are homed on Exchange 2013, you do not need to set up separate SQL Server databases for storage of archiving data.</span></span>
    
- <span data-ttu-id="0dce5-144">**启用存档数据的清除**选择此选项可启用清除，并指定清除选项，包括下列：</span><span class="sxs-lookup"><span data-stu-id="0dce5-144">**Enable purging of archiving data** Select this option to enable purging and specify purging options, which include the following:</span></span>
    
  - <span data-ttu-id="0dce5-145">在您指定的特定天数之后清除</span><span class="sxs-lookup"><span data-stu-id="0dce5-145">Purging after a specific number of days that you specify.</span></span>
    
  - <span data-ttu-id="0dce5-146">清除存档数据后已导出 （如果启用 Microsoft Exchange 集成，其中包括已上载到交换的数据）。</span><span class="sxs-lookup"><span data-stu-id="0dce5-146">Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0dce5-147">如果您启用 Microsoft Exchange 集成，清除用户驻留在 Exchange 2013，并通过交换控制放置适当地存放在其邮箱。</span><span class="sxs-lookup"><span data-stu-id="0dce5-147">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes placed on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="0dce5-148">唯一的例外是存储 Lync Server 文件共享上的会议文件。</span><span class="sxs-lookup"><span data-stu-id="0dce5-148">The only exception is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="0dce5-149">如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。</span><span class="sxs-lookup"><span data-stu-id="0dce5-149">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span> 
  
<span data-ttu-id="0dce5-150">有关存档功能和功能，其中包括交换集成详细信息请参阅[存档业务服务器 2015年的 Skype 的规划](../../plan-your-deployment/archiving/archiving.md)、[部署存档业务服务器 2015年的 Skype](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档的 Skype 的商业服务器 2015年](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="0dce5-150">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

