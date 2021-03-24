---
title: 位置策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: 4a5cf1ab5ec17681adef9b03cab06bed04285628
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099698"
---
# <a name="location-policy"></a><span data-ttu-id="0d512-103">位置策略</span><span class="sxs-lookup"><span data-stu-id="0d512-103">Location Policy</span></span>

<span data-ttu-id="0d512-104">位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="0d512-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="0d512-105">位置策略包括全局策略以及可选的一个或多个站点和用户策略：</span><span class="sxs-lookup"><span data-stu-id="0d512-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="0d512-106">**全局策略：** 默认情况下，将创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="0d512-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="0d512-107">可以编辑全局策略，但无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="0d512-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="0d512-108">如果您尝试删除全局策略，则所有设置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="0d512-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="0d512-109">**站点策略 (可选) ：** 可以创建一个或多个站点位置策略，每个策略都适用于特定网站。</span><span class="sxs-lookup"><span data-stu-id="0d512-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="0d512-110">站点策略会覆盖全局策略。</span><span class="sxs-lookup"><span data-stu-id="0d512-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="0d512-111">**用户策略 (可选) ：** 可以创建一个或多个用户位置策略，每个策略都适用于特定用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="0d512-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="0d512-112">用户策略会覆盖全局策略和站点策略。</span><span class="sxs-lookup"><span data-stu-id="0d512-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="0d512-113">也可以向网络站点（即子网组）分配位置策略。</span><span class="sxs-lookup"><span data-stu-id="0d512-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="0d512-114">分配给网络站点的位置策略优先于所有其他用户策略。</span><span class="sxs-lookup"><span data-stu-id="0d512-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="0d512-115">有关使用 cmdlet 向网络站点分配位置策略的详细信息，请参阅[Add a location policy to a network site in Skype for Business Server 2015。](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)</span><span class="sxs-lookup"><span data-stu-id="0d512-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="0d512-116">有关使用 Skype for Business Server 控制面板向网络站点分配位置策略的详细信息，请参阅 [配置网络站点](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites)。</span><span class="sxs-lookup"><span data-stu-id="0d512-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites).</span></span>

<span data-ttu-id="0d512-117">“位置策略”页显示一个为组织定义的所有位置策略的列表。</span><span class="sxs-lookup"><span data-stu-id="0d512-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="0d512-118">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="0d512-118">Tasks you can perform</span></span>

<span data-ttu-id="0d512-119">您可以在“位置策略”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0d512-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="0d512-120">创建新的站点位置策略或用户位置策略</span><span class="sxs-lookup"><span data-stu-id="0d512-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="0d512-121">更改全局策略或现有站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="0d512-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="0d512-122">删除站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="0d512-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0d512-123">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="0d512-123">UI Reference</span></span>

<span data-ttu-id="0d512-124">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="0d512-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="0d512-125">**新建** 启动新的站点位置策略或用户位置策略。</span><span class="sxs-lookup"><span data-stu-id="0d512-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="0d512-126">**编辑** 打开所选位置策略进行编辑，选择列表中的所有位置策略，或删除所选站点策略或用户策略。</span><span class="sxs-lookup"><span data-stu-id="0d512-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d512-127">对于全局策略，“删除”会将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="0d512-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="0d512-128">**刷新** 刷新位置策略的列表。</span><span class="sxs-lookup"><span data-stu-id="0d512-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="0d512-129">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="0d512-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0d512-130">**名称** 标识位置策略。</span><span class="sxs-lookup"><span data-stu-id="0d512-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="0d512-131">**范围** 标识位置策略的范围：全局、站点或用户。</span><span class="sxs-lookup"><span data-stu-id="0d512-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="0d512-132">**E9-1-1** 选中分配了此位置策略的用户是否已启用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="0d512-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="0d512-133">**位置** 指定当用户的客户端在 Skype for Business Server 的新位置注册时是否提示用户输入位置信息，以及当用户在未输入位置信息的情况下消除提示时是否看到免责声明。</span><span class="sxs-lookup"><span data-stu-id="0d512-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="0d512-134">**PSTN 用法** 指定公用电话交换网 (PSTN) 用法，用于确定使用此配置文件路由来自客户端的紧急呼叫的语音路由。</span><span class="sxs-lookup"><span data-stu-id="0d512-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="0d512-135">**E9-1-1 号码** 指定为获得紧急服务而拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="0d512-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="0d512-136">**E9-1-1 掩码** 指定用户拨打的、然后转换为紧急拨号号码的号码。</span><span class="sxs-lookup"><span data-stu-id="0d512-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="0d512-137">有关紧急企业语音功能的详细信息，请参阅规划文档中的[Overview of E9-1-1。](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1)</span><span class="sxs-lookup"><span data-stu-id="0d512-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) in the Planning documentation.</span></span> <span data-ttu-id="0d512-138">有关使用位置策略的详细信息，请参阅操作文档中的[Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information)。</span><span class="sxs-lookup"><span data-stu-id="0d512-138">For details about working with location policies, see [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) in the Operations documentation.</span></span>