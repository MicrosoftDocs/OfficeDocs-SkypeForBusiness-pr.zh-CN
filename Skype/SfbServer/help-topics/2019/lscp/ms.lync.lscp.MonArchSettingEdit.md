---
title: 存档配置新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：
ms.openlocfilehash: 68d5de88fc56441989e8ffc9ceabfd3236179d1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291976"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a><span data-ttu-id="8a01f-104">存档配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="8a01f-104">Archiving Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="8a01f-p102">使用存档配置可控制用于部署的存档选项。存档配置包括全局配置以及可选的一个或多个站点和池配置：</span><span class="sxs-lookup"><span data-stu-id="8a01f-p102">You use Archiving configurations to control archiving options for your deployment. Archiving configurations include the global configuration, and, optionally, one or more site and pool configurations:</span></span>
  
- <span data-ttu-id="8a01f-107">**全局配置**默认情况下会创建全局配置。</span><span class="sxs-lookup"><span data-stu-id="8a01f-107">**Global configuration** The global configuration is created by default.</span></span> <span data-ttu-id="8a01f-108">您可以编辑全局配置，但无法删除此存档配置。</span><span class="sxs-lookup"><span data-stu-id="8a01f-108">You can edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="8a01f-109">如果您尝试将其删除，则所有选项将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="8a01f-109">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="8a01f-110">**网站配置 (可选)** 你可以指定一个或多个网站存档配置, 每个配置都可以配置用于控制特定网站的存档选项。</span><span class="sxs-lookup"><span data-stu-id="8a01f-110">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="8a01f-111">站点配置会覆盖全局配置，但仅限于在存档站点配置中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="8a01f-111">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="8a01f-112">可以编辑或删除站点配置。</span><span class="sxs-lookup"><span data-stu-id="8a01f-112">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="8a01f-113">**池配置 (可选)** 你可以指定一个或多个池存档配置, 以控制特定池的存档选项。</span><span class="sxs-lookup"><span data-stu-id="8a01f-113">**Pool configuration (optional)** You can specify one or more pool Archiving configurations, to control archiving options for a specific pool.</span></span> <span data-ttu-id="8a01f-114">池配置会覆盖全局配置和站点配置，但仅限于在存档池配置中指定的池。</span><span class="sxs-lookup"><span data-stu-id="8a01f-114">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="8a01f-115">可以编辑或删除池配置。</span><span class="sxs-lookup"><span data-stu-id="8a01f-115">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8a01f-116">存档配置适用于驻留在 Skype for business Server 上的用户, 如果你启用了 Microsoft Exchange 集成选项以使用 Exchange 将存档数据存储在 Microsoft Exchange 中, 则用户驻留在 Exchange 上。</span><span class="sxs-lookup"><span data-stu-id="8a01f-116">Archiving configurations apply to users homed on Skype for Business Server, and, if you enable the Microsoft Exchange integration option to use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange.</span></span> <span data-ttu-id="8a01f-117">但是, 对于驻留在 Exchange 上的用户而言, 某些选项的实现方式稍有不同, 如下一节所述。</span><span class="sxs-lookup"><span data-stu-id="8a01f-117">However, some options are implemented slightly differently for users homed on Exchange, as described in the next section.</span></span> 
  
<span data-ttu-id="8a01f-118">若要配置新的或现有的存档配置的设置，请指定以下选项：</span><span class="sxs-lookup"><span data-stu-id="8a01f-118">To configure the settings for a new or existing Archiving configuration, specify the following options:</span></span>
- <span data-ttu-id="8a01f-119">**名称**每个存档配置都需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="8a01f-119">**Name** Each Archiving configuration requires a name.</span></span> <span data-ttu-id="8a01f-120">该名称由你添加或编辑的配置类型确定:</span><span class="sxs-lookup"><span data-stu-id="8a01f-120">The name is determined by the type of configuration you are adding or editing:</span></span>
    
  - <span data-ttu-id="8a01f-121">**全局配置**默认名称为全局名称。</span><span class="sxs-lookup"><span data-stu-id="8a01f-121">**Global configuration** The default name is Global.</span></span> <span data-ttu-id="8a01f-122">例如，Contoso 北美机构。</span><span class="sxs-lookup"><span data-stu-id="8a01f-122">For example, Contoso North American Organization.</span></span>
    
  - <span data-ttu-id="8a01f-123">**网站配置**列表包含部署中的可用网站。</span><span class="sxs-lookup"><span data-stu-id="8a01f-123">**Site configuration** The list contains the available sites in your deployment.</span></span> <span data-ttu-id="8a01f-124">单击某个站点即可将其选中。</span><span class="sxs-lookup"><span data-stu-id="8a01f-124">Click a single site to select it.</span></span> <span data-ttu-id="8a01f-125">例如，Redmond 数据中心。</span><span class="sxs-lookup"><span data-stu-id="8a01f-125">For example, Redmond Data Center.</span></span>
    
  - <span data-ttu-id="8a01f-126">**池配置**指定一个合适的名称, 该名称可以是部署中特定前端池或标准版服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="8a01f-126">**Pool configuration** Specify an appropriate name, which can be the name of a specific Front End pool or Standard Edition Server in your deployment.</span></span> <span data-ttu-id="8a01f-127">例如，市场营销部门。</span><span class="sxs-lookup"><span data-stu-id="8a01f-127">For example, Marketing Division.</span></span>
    
- <span data-ttu-id="8a01f-128">**说明**这是可选操作。</span><span class="sxs-lookup"><span data-stu-id="8a01f-128">**Description** This is optional.</span></span> <span data-ttu-id="8a01f-129">使用它提供其他详细信息, 如配置的范围或使用。</span><span class="sxs-lookup"><span data-stu-id="8a01f-129">Use it to provide additional details, such as the scope or use of the configuration.</span></span> <span data-ttu-id="8a01f-130">例如, 与其他网站的法律部门协调。</span><span class="sxs-lookup"><span data-stu-id="8a01f-130">For example, Coordinate with Legal Departments of Other Sites.</span></span>
    
- <span data-ttu-id="8a01f-131">**存档设置**选项包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="8a01f-131">**Archiving setting** Options include the following:</span></span>
    
  - <span data-ttu-id="8a01f-132">**存档 IM 会话**</span><span class="sxs-lookup"><span data-stu-id="8a01f-132">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="8a01f-133">**存档 IM 和 Web 会议会话**</span><span class="sxs-lookup"><span data-stu-id="8a01f-133">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="8a01f-134">**禁用存档**</span><span class="sxs-lookup"><span data-stu-id="8a01f-134">**Disable archiving**</span></span>
    
- <span data-ttu-id="8a01f-135">**如果存档失败, 阻止即时消息 (IM) 或 web 会议会话**失败包括以下几项:</span><span class="sxs-lookup"><span data-stu-id="8a01f-135">**Block instant messaging (IM) or web conferencing sessions if archiving fails** Failures include the following:</span></span>
    
  - <span data-ttu-id="8a01f-136">**IM**故障可能是整个数据库或存储服务有问题。</span><span class="sxs-lookup"><span data-stu-id="8a01f-136">**IM** A failure could be a full database or problem with the storage service.</span></span> <span data-ttu-id="8a01f-137">在此情况下，将阻止为存档启用的用户使用 IM。</span><span class="sxs-lookup"><span data-stu-id="8a01f-137">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
  - <span data-ttu-id="8a01f-138">**会议**故障可能是不可用的文件共享或存储服务有问题。</span><span class="sxs-lookup"><span data-stu-id="8a01f-138">**Conferencing** A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="8a01f-139">在此情况下，池中托管的所有活动会议在发生故障时将切换到限制模式，并且不能激活新会议。</span><span class="sxs-lookup"><span data-stu-id="8a01f-139">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="8a01f-140">IM 和会议都能在修复故障后自动恢复。</span><span class="sxs-lookup"><span data-stu-id="8a01f-140">Both IM and conferencing automatically recover after the failures are corrected.</span></span>
    
- <span data-ttu-id="8a01f-141">**Microsoft Exchange 集成**如果你有托管在 Exchange 上的用户, 请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="8a01f-141">**Microsoft Exchange integration** Select this option if you have users who are homed on Exchange.</span></span> <span data-ttu-id="8a01f-142">使用此选项, 如果用户的邮箱已放在原地保留中, 则使用 Exchange 存储这些用户的数据。</span><span class="sxs-lookup"><span data-stu-id="8a01f-142">With this option, Exchange is used to store data for those users, if their mailboxes have been placed on In-Place Hold.</span></span> <span data-ttu-id="8a01f-143">如果你的所有用户都托管在 Exchange 上, 则无需设置单独的 SQL Server 数据库来存储存档数据。</span><span class="sxs-lookup"><span data-stu-id="8a01f-143">If all your users are homed on Exchange, you do not need to set up separate SQL Server databases for storage of archiving data.</span></span>
    
- <span data-ttu-id="8a01f-144">**启用清除存档数据**选择此选项可启用清除并指定清除选项, 包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="8a01f-144">**Enable purging of archiving data** Select this option to enable purging and specify purging options, which include the following:</span></span>
    
  - <span data-ttu-id="8a01f-145">在您指定的特定天数之后清除</span><span class="sxs-lookup"><span data-stu-id="8a01f-145">Purging after a specific number of days that you specify.</span></span>
    
  - <span data-ttu-id="8a01f-146">在导出存档数据 (包括已上载到 Exchange 的数据, 如果启用 Microsoft Exchange 集成) 后清除。</span><span class="sxs-lookup"><span data-stu-id="8a01f-146">Purging after the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8a01f-147">如果启用 Microsoft Exchange 集成, 请清除托管在 Exchange 上的用户, 并将其邮箱置于就地保留状态由 Exchange 控制。</span><span class="sxs-lookup"><span data-stu-id="8a01f-147">If you enable Microsoft Exchange integration, purging for users homed on Exchange and with their mailboxes placed on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="8a01f-148">唯一的例外是存储在 Lync Server 文件共享上的会议文件。</span><span class="sxs-lookup"><span data-stu-id="8a01f-148">The only exception is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="8a01f-149">如果您选择在已导出存档数据后清除数据，或在指定的最长天数（如果您指定了最长保留天数）后清除数据，则仅在导出文件（上载到 Exchange）后才从文件共享中清除这些文件。</span><span class="sxs-lookup"><span data-stu-id="8a01f-149">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span> 
  
<span data-ttu-id="8a01f-150">有关存档功能和功能 (包括 Exchange 集成) 的详细信息, 请参阅[在 skype For Business 服务器中规划存档](../../../plan-your-deployment/archiving/archiving.md)、[部署 Skype for business 服务器存档](../../../deploy/deploy-archiving/deploy-archiving.md)和[管理 skype for business 中的存档服务器](../../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="8a01f-150">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

