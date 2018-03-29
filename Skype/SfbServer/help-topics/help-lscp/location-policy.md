---
title: 位置策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: fa1ca0907d3316066e2ca6e1fcf8a1d09a9c315a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy"></a><span data-ttu-id="81b07-103">位置策略</span><span class="sxs-lookup"><span data-stu-id="81b07-103">Location Policy</span></span>
 
<span data-ttu-id="81b07-104">位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="81b07-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span> 
  
<span data-ttu-id="81b07-105">位置策略包括全局策略以及可选的一个或多个站点和用户策略：</span><span class="sxs-lookup"><span data-stu-id="81b07-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="81b07-106">**全球政策：**默认情况下创建全球政策。</span><span class="sxs-lookup"><span data-stu-id="81b07-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="81b07-107">可以编辑全局策略，但无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="81b07-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="81b07-108">如果您尝试删除全局策略，则所有设置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="81b07-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="81b07-109">**网站策略 （可选）：**您可以创建一个或多个站点的位置策略，其中每个适用的特定网站。</span><span class="sxs-lookup"><span data-stu-id="81b07-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="81b07-110">站点策略会覆盖全局策略。</span><span class="sxs-lookup"><span data-stu-id="81b07-110">Site policies override the global policy.</span></span>
    
- <span data-ttu-id="81b07-111">**用户策略 （可选）：**您可以创建一个或多个用户的位置策略，其中每个适用于特定用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="81b07-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="81b07-112">用户策略会覆盖全局策略和站点策略。</span><span class="sxs-lookup"><span data-stu-id="81b07-112">User policies override the global policy and site policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="81b07-113">也可以向网络站点（即子网组）分配位置策略。</span><span class="sxs-lookup"><span data-stu-id="81b07-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="81b07-114">分配给网络站点的位置策略优先于所有其他用户策略。</span><span class="sxs-lookup"><span data-stu-id="81b07-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="81b07-115">有关使用 cmdlet 分配到网络站点的位置策略的详细信息，请参阅[添加到业务服务器 2015年的 Skype 的网络站点的位置策略](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="81b07-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="81b07-116">有关使用 Skype 业务服务器控件面板将位置策略指派给网络站点的详细信息，请参阅[配置网络站点](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="81b07-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span> 
  
<span data-ttu-id="81b07-117">“**位置策略**”页显示一个为组织定义的所有位置策略的列表。</span><span class="sxs-lookup"><span data-stu-id="81b07-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="81b07-118">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="81b07-118">Tasks you can perform</span></span>

<span data-ttu-id="81b07-119">您可以在“**位置策略**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="81b07-119">You can perform the following tasks from the **Location Policy** page:</span></span>
  
- <span data-ttu-id="81b07-120">创建新的站点位置策略或用户位置策略</span><span class="sxs-lookup"><span data-stu-id="81b07-120">Create a new site location policy or user location policy</span></span>
    
- <span data-ttu-id="81b07-121">更改全局策略或现有站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="81b07-121">Change the global policy or an existing site policy or user policy</span></span>
    
- <span data-ttu-id="81b07-122">删除站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="81b07-122">Delete a site policy or user policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="81b07-123">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="81b07-123">UI Reference</span></span>

<span data-ttu-id="81b07-124">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="81b07-124">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="81b07-125">**新**启动一个新网站的位置策略或用户的位置策略。</span><span class="sxs-lookup"><span data-stu-id="81b07-125">**New** Starts a new site location policy or user location policy.</span></span>
    
- <span data-ttu-id="81b07-126">**编辑**打开所选的位置策略对其进行编辑，在列表中，选择所有位置策略或删除选定的站点策略或用户策略。</span><span class="sxs-lookup"><span data-stu-id="81b07-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="81b07-127">对于全局策略，“**删除**”会将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="81b07-127">For the global policy, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="81b07-128">**刷新**刷新列表中的位置策略。</span><span class="sxs-lookup"><span data-stu-id="81b07-128">**Refresh** Refreshes the list of location policies.</span></span>
    
<span data-ttu-id="81b07-129">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="81b07-129">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="81b07-130">**名称**标识的位置策略。</span><span class="sxs-lookup"><span data-stu-id="81b07-130">**Name** Identifies the location policy.</span></span>
    
- <span data-ttu-id="81b07-131">**作用域**标识位置策略的作用域： 全局站点或用户。</span><span class="sxs-lookup"><span data-stu-id="81b07-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>
    
- <span data-ttu-id="81b07-132">**E9-1-1**已检查如果分配了此位置策略为用户启用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="81b07-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>
    
- <span data-ttu-id="81b07-133">**位置**指定将提示用户输入位置信息，和当他们的客户端使用 Skype 注册业务服务器在一个新的位置，是否他们看到免责声明，如果它们消除而无需输入位置信息的提示。</span><span class="sxs-lookup"><span data-stu-id="81b07-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>
    
- <span data-ttu-id="81b07-134">**PSTN 使用情况**指定公用交换的电话网络 (PSTN) 用法，用来确定语音路由用于路由使用此配置文件从客户端的紧急电话。</span><span class="sxs-lookup"><span data-stu-id="81b07-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>
    
- <span data-ttu-id="81b07-135">**E9-1-1 号**指定拨号连接紧急服务的数量。</span><span class="sxs-lookup"><span data-stu-id="81b07-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>
    
- <span data-ttu-id="81b07-136">**E9-1-1 掩码**指定用户拨，然后转换成紧急拨数字的号码。</span><span class="sxs-lookup"><span data-stu-id="81b07-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>
    
<span data-ttu-id="81b07-137">企业语音紧急服务的特性和功能的详细信息，请参阅规划文档中[概述的 E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="81b07-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="81b07-138">有关使用位置策略的详细信息，请参阅操作文档中的[配置位置策略](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="81b07-138">For details about working with location policies, see [Configuring Location Policy](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>
  

