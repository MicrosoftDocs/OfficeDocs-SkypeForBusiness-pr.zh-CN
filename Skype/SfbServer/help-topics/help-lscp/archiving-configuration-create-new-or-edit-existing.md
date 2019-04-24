---
title: 存档配置创建新的或编辑现有的
ms.reviewer: ''
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
ms.openlocfilehash: 2167b0ccc65a9bfc6ae731add156fa0b0925eaf2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234843"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a><span data-ttu-id="d8c0f-104">存档配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="d8c0f-104">Archiving Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="d8c0f-p102">使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：</span><span class="sxs-lookup"><span data-stu-id="d8c0f-p102">You use Archiving configurations to control archiving options for your deployment. Archiving configurations include the global configuration, and, optionally, one or more site and pool configurations:</span></span>
  
- <span data-ttu-id="d8c0f-107">**全局配置**默认情况下创建的全局配置。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-107">**Global configuration** The global configuration is created by default.</span></span> <span data-ttu-id="d8c0f-108">您可以编辑全局配置，但无法删除此存档配置。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-108">You can edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="d8c0f-109">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="d8c0f-110">**网站配置 （可选）** 您可以指定一个或多个站点存档配置，其中每个您可以配置为特定站点的存档选项的控件。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-110">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="d8c0f-111">站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-111">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="d8c0f-112">可以编辑或删除站点配置。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-112">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="d8c0f-113">**池配置 （可选）** 您可以指定一个或多个池存档配置，来控制特定池的存档选项。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-113">**Pool configuration (optional)** You can specify one or more pool Archiving configurations, to control archiving options for a specific pool.</span></span> <span data-ttu-id="d8c0f-114">池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-114">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="d8c0f-115">可以编辑或删除池配置。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-115">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d8c0f-116">存档配置适用于用户的企业服务器驻留在 Skype 上，如果您启用 Microsoft Exchange 集成选项以使用 Exchange 2013 存储存档数据在 Microsoft Exchange、 用户驻留在 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-116">Archiving configurations apply to users homed on Skype for Business Server, and, if you enable the Microsoft Exchange integration option to use Exchange 2013 to store archiving data in Microsoft Exchange, to users homed on Exchange 2013.</span></span> <span data-ttu-id="d8c0f-117">但是，某些选项实现略有不同的用户驻留在 Exchange 2013 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-117">However, some options are implemented slightly differently for users homed on Exchange 2013, as described in the next section.</span></span> 
  
<span data-ttu-id="d8c0f-118">若要配置新的或现有的存档配置的设置，请指定以下选项：</span><span class="sxs-lookup"><span data-stu-id="d8c0f-118">To configure the settings for a new or existing Archiving configuration, specify the following options:</span></span>
- <span data-ttu-id="d8c0f-119">**名称**每个存档配置需要的名称。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-119">**Name** Each Archiving configuration requires a name.</span></span> <span data-ttu-id="d8c0f-120">名称取决于要添加或编辑的配置的类型：</span><span class="sxs-lookup"><span data-stu-id="d8c0f-120">The name is determined by the type of configuration you are adding or editing:</span></span>
    
  - <span data-ttu-id="d8c0f-121">**全局配置**默认名称为 Global。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-121">**Global configuration** The default name is Global.</span></span> <span data-ttu-id="d8c0f-122">例如，Contoso 北美机构。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-122">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="d8c0f-123">**网站配置**该列表包含在部署中可用的站点。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-123">**Site configuration** The list contains the available sites in your deployment.</span></span> <span data-ttu-id="d8c0f-124">单击某个站点即可将其选中。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-124">Click a single site to select it.</span></span> <span data-ttu-id="d8c0f-125">例如，Redmond 数据中心。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-125">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="d8c0f-126">**池配置**指定合适的名称，可以是一个特定的前端池或 Standard Edition Server 部署中的名称。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-126">**Pool configuration** Specify an appropriate name, which can be the name of a specific Front End pool or Standard Edition Server in your deployment.</span></span> <span data-ttu-id="d8c0f-127">例如，市场营销部门。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-127">For example, Marketing Division.</span></span>
    
- <span data-ttu-id="d8c0f-128">**说明**这是可选的。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-128">**Description** This is optional.</span></span> <span data-ttu-id="d8c0f-129">使用它来提供其他详细信息，例如使用配置的范围。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-129">Use it to provide additional details, such as the scope or use of the configuration.</span></span> <span data-ttu-id="d8c0f-130">例如，法律部门的其他网站与协调一致。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-130">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="d8c0f-131">**存档设置**选项包括：</span><span class="sxs-lookup"><span data-stu-id="d8c0f-131">**Archiving setting** Options include the following:</span></span>
    
  - <span data-ttu-id="d8c0f-132">**存档 IM 会话**</span><span class="sxs-lookup"><span data-stu-id="d8c0f-132">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="d8c0f-133">**存档 IM 和 Web 会议会话**</span><span class="sxs-lookup"><span data-stu-id="d8c0f-133">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="d8c0f-134">**禁用存档**</span><span class="sxs-lookup"><span data-stu-id="d8c0f-134">**Disable archiving**</span></span>
    
- <span data-ttu-id="d8c0f-135">**阻止即时消息 (IM) 或 web 会议会话存档失败时**故障包括以下方面：</span><span class="sxs-lookup"><span data-stu-id="d8c0f-135">**Block instant messaging (IM) or web conferencing sessions if archiving fails** Failures include the following:</span></span>
    
  - <span data-ttu-id="d8c0f-136">**IM**失败可能是完整数据库备份或问题的存储服务。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-136">**IM** A failure could be a full database or problem with the storage service.</span></span> <span data-ttu-id="d8c0f-137">在此情况下，将阻止为存档启用的用户使用 IM。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-137">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
  - <span data-ttu-id="d8c0f-138">**会议**失败可能是不可用的文件共享或存储服务有问题。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-138">**Conferencing** A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="d8c0f-139">在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-139">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="d8c0f-140">IM 和会议都能在修复故障后自动恢复。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-140">Both IM and conferencing automatically recover after the failures are corrected.</span></span>
    
- <span data-ttu-id="d8c0f-141">**Microsoft Exchange 集成**如果有用户驻留在 Exchange 2013，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-141">**Microsoft Exchange integration** Select this option if you have users who are homed on Exchange 2013.</span></span> <span data-ttu-id="d8c0f-142">使用此选项，Exchange 2013 用于存储数据的用户，如果其邮箱已被置于就地保留。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-142">With this option, Exchange 2013 is used to store data for those users, if their mailboxes have been placed on In-Place Hold.</span></span> <span data-ttu-id="d8c0f-143">如果您的所有用户都驻留在 Exchange 2013 中，您不需要单独的 SQL Server 数据库来存储存档数据设置。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-143">If all your users are homed on Exchange 2013, you do not need to set up separate SQL Server databases for storage of archiving data.</span></span>
    
- <span data-ttu-id="d8c0f-144">**启用清除存档数据功能**选择此选项可启用清除功能并指定清除选项，包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="d8c0f-144">**Enable purging of archiving data** Select this option to enable purging and specify purging options, which include the following:</span></span>
    
  - <span data-ttu-id="d8c0f-145">在您指定的特定天数之后清除</span><span class="sxs-lookup"><span data-stu-id="d8c0f-145">Purging after a specific number of days that you specify.</span></span>
    
  - <span data-ttu-id="d8c0f-146">之后的存档数据清除已导出 （如果启用 Microsoft Exchange 集成，其中包括已上载到 Exchange 的数据）。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-146">Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d8c0f-147">如果您启用 Microsoft Exchange 集成，请清除用户驻留在 Exchange 2013 和 exchange 控制其邮箱置于就地保留。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-147">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes placed on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="d8c0f-148">对于会议文件，存储在 Lync Server 文件共享中是唯一的例外。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-148">The only exception is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="d8c0f-149">如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-149">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span> 
  
<span data-ttu-id="d8c0f-150">有关的存档功能和功能，包括 Exchange 集成的详细信息，请参阅[规划存档中的业务服务器 2015 Skype](../../plan-your-deployment/archiving/archiving.md)、[业务服务器 2015年的 Skype 存档的部署](../../deploy/deploy-archiving/deploy-archiving.md)，和[管理存档中的 Skype业务服务器 2015年](../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c0f-150">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

