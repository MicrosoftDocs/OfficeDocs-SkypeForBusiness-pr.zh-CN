---
title: 会议策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: 会议策略定义的特性和功能，用户可以 （也称为会议） 会议期间。
ms.openlocfilehash: e1fea90ed978602c45abf7b71035506b0c039058
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencing-policy"></a><span data-ttu-id="f298d-103">会议策略</span><span class="sxs-lookup"><span data-stu-id="f298d-103">Conferencing Policy</span></span>
 
<span data-ttu-id="f298d-104">会议策略定义的特性和功能，用户可以 （也称为会议） 会议期间。</span><span class="sxs-lookup"><span data-stu-id="f298d-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>
  
<span data-ttu-id="f298d-105">会议策略包括全球政策和一个或多个站点和用户策略 （可选）：</span><span class="sxs-lookup"><span data-stu-id="f298d-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="f298d-106">**全球政策：**默认情况下创建全球政策。</span><span class="sxs-lookup"><span data-stu-id="f298d-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="f298d-107">可以编辑全局策略，但无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="f298d-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="f298d-108">如果您尝试删除全局策略，则所有设置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="f298d-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="f298d-109">**网站策略 （可选）：**您可以创建一个或多个网站会议策略，其中每个适用的特定网站。</span><span class="sxs-lookup"><span data-stu-id="f298d-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="f298d-110">站点策略会覆盖全局策略。</span><span class="sxs-lookup"><span data-stu-id="f298d-110">Site policies override the global policy.</span></span>
    
- <span data-ttu-id="f298d-111">**用户策略 （可选）：**您可以创建一个或多个用户会议策略，其中每个适用于特定用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="f298d-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="f298d-112">用户策略会覆盖全局策略和站点策略。</span><span class="sxs-lookup"><span data-stu-id="f298d-112">User policies override the global policy and site policies.</span></span>
    
<span data-ttu-id="f298d-113">**会议策略**页显示为您的组织定义的所有会议策略的列表。</span><span class="sxs-lookup"><span data-stu-id="f298d-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="f298d-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="f298d-114">Tasks you can perform</span></span>

<span data-ttu-id="f298d-115">您可以在“**位置策略**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="f298d-115">You can perform the following tasks from the **Location Policy** page:</span></span>
  
- <span data-ttu-id="f298d-116">创建新的网站会议策略或用户会议策略</span><span class="sxs-lookup"><span data-stu-id="f298d-116">Create a new site conferencing policy or user conferencing policy</span></span>
    
- <span data-ttu-id="f298d-117">更改全局策略或现有站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="f298d-117">Change the global policy or an existing site policy or user policy</span></span>
    
- <span data-ttu-id="f298d-118">删除站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="f298d-118">Delete a site policy or user policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="f298d-119">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="f298d-119">UI Reference</span></span>

<span data-ttu-id="f298d-120">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="f298d-120">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="f298d-121">**新**启动一个新网站会议策略或用户会议策略。</span><span class="sxs-lookup"><span data-stu-id="f298d-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>
    
- <span data-ttu-id="f298d-122">**编辑**打开所选的会议策略对其进行编辑，在列表中，选择所有会议策略或删除选定的站点策略或用户策略。</span><span class="sxs-lookup"><span data-stu-id="f298d-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f298d-123">对于全局策略，“**删除**”会将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="f298d-123">For the global policy, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="f298d-124">**刷新**刷新列表中的策略会议。</span><span class="sxs-lookup"><span data-stu-id="f298d-124">**Refresh** Refreshes the list of conferencing policies.</span></span>
    
<span data-ttu-id="f298d-125">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="f298d-125">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="f298d-126">**名称**标识会议策略。</span><span class="sxs-lookup"><span data-stu-id="f298d-126">**Name** Identifies the conferencing policy.</span></span>
    
- <span data-ttu-id="f298d-127">**作用域**确定会议策略的作用域： 全局站点或用户。</span><span class="sxs-lookup"><span data-stu-id="f298d-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>
    
- <span data-ttu-id="f298d-128">**数据协作**已检查是否会议策略指定在会议允许数据协作。</span><span class="sxs-lookup"><span data-stu-id="f298d-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>
    
- <span data-ttu-id="f298d-129">**应用程序共享**已检查会议策略是否指定应用程序共享，允许在会议。</span><span class="sxs-lookup"><span data-stu-id="f298d-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>
    
- <span data-ttu-id="f298d-130">**音频**已检查是否会议策略指定了音频会议中允许。</span><span class="sxs-lookup"><span data-stu-id="f298d-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>
    
- <span data-ttu-id="f298d-131">**视频**已检查是否会议策略指定了允许该视频会议。</span><span class="sxs-lookup"><span data-stu-id="f298d-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>
    
- <span data-ttu-id="f298d-132">**PSTN**已检查会议策略是否指定允许 PSTN 拨入会议。</span><span class="sxs-lookup"><span data-stu-id="f298d-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>
    
- <span data-ttu-id="f298d-133">**记录**已检查是否会议策略指定在会议允许录制。</span><span class="sxs-lookup"><span data-stu-id="f298d-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>
    
<span data-ttu-id="f298d-134">有关会议的特性和功能的详细信息，请参阅规划文档中[概述的会议](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f298d-134">For details about conferencing features and capabilities, see [Overview of Conferencing](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="f298d-135">有关使用会议策略的详细信息，请参阅操作文档中的[策略会议](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f298d-135">For details about working with conferencing policies, see [Conferencing Policies](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>
  

