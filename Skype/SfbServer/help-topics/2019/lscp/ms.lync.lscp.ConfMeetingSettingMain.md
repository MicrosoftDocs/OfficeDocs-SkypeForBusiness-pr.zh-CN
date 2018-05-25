---
title: 会议配置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: 会议配置设置中定义的会议 (还 calledmeetings) 用户可以创建和控制如何 （或是否） 匿名用户和电话拨入式会议用户可以参加这些会议的类型。 这些设置仅适用于安排的会议。 它们不适用于通过单击客户端中的立即开会选项创建的临时会议。
ms.openlocfilehash: 1318f2eee75809e736ce04af01eb2f2563b86f0f
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="meeting-configuration"></a><span data-ttu-id="e3fb3-105">会议配置</span><span class="sxs-lookup"><span data-stu-id="e3fb3-105">Meeting Configuration</span></span>
 
<span data-ttu-id="e3fb3-p102">会议配置设置定义用户可创建的会议类型，以及控制匿名用户和电话拨入式会议用户如何（或是否）可以加入这些会议。这些设置只适用于预定的会议，不适用于通过单击客户端中的“现在开会”选项创建的临时会议。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span> 
  
<span data-ttu-id="e3fb3-109">在全局级、站点级或池级上应用会议配置：</span><span class="sxs-lookup"><span data-stu-id="e3fb3-109">Meeting configurations apply on the global, site, or pool level:</span></span>
  
- <span data-ttu-id="e3fb3-110">**全局会议配置：** 默认情况下创建全局会议配置。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="e3fb3-111">可以编辑全局会议配置，但无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="e3fb3-112">如果您尝试删除全局会议配置，则所有设置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="e3fb3-113">**站点会议配置 （可选）：** 您可以创建一个或多个站点会议配置，其中每个适用于特定站点。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="e3fb3-114">站点配置会覆盖全局配置。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-114">Site configurations override the global configuration.</span></span>
    
- <span data-ttu-id="e3fb3-115">**池会议配置 （可选）：** 您可以创建一个或多个池会议配置，其中每个应用于一个特定的池。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="e3fb3-116">池配置会覆盖全局配置和站点配置。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-116">Pool configurations override the global configuration and site configurations.</span></span>
    
<span data-ttu-id="e3fb3-117">“**会议配置**”页显示一个为组织定义的所有会议配置的列表。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="e3fb3-118">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="e3fb3-118">Tasks you can perform</span></span>

<span data-ttu-id="e3fb3-119">您可以在“**会议配置**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e3fb3-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>
  
- <span data-ttu-id="e3fb3-120">创建新的站点会议配置或池会议配置</span><span class="sxs-lookup"><span data-stu-id="e3fb3-120">Create a new site meeting configuration or pool meeting configuration</span></span>
    
- <span data-ttu-id="e3fb3-121">更改全局配置或者现有站点配置或池配置</span><span class="sxs-lookup"><span data-stu-id="e3fb3-121">Change the global configuration or an existing site configuration or pool configuration</span></span>
    
- <span data-ttu-id="e3fb3-122">删除站点配置或池配置</span><span class="sxs-lookup"><span data-stu-id="e3fb3-122">Delete a site configuration or pool configuration</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="e3fb3-123">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="e3fb3-123">UI Reference</span></span>

<span data-ttu-id="e3fb3-124">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-124">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="e3fb3-125">**新**开始一个新的站点会议配置或池会议配置。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>
    
- <span data-ttu-id="e3fb3-126">**编辑**打开所选的会议配置以进行编辑，在列表中，选择所有会议配置或删除所选的站点配置或池配置。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3fb3-127">对于全局会议配置，“**删除**”会将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="e3fb3-128">**刷新**刷新会议配置的列表。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-128">**Refresh** Refreshes the list of meeting configurations.</span></span>
    
<span data-ttu-id="e3fb3-129">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-129">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="e3fb3-130">**名称**标识会议配置。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-130">**Name** Identifies the meeting configuration.</span></span>
    
- <span data-ttu-id="e3fb3-131">**范围**标识会议配置的范围： 全局、 站点或池。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>
    
<span data-ttu-id="e3fb3-132">有关使用会议配置的详细信息，请参阅[创建或修改会议配置设置集合](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)操作文档中。</span><span class="sxs-lookup"><span data-stu-id="e3fb3-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>
  

