---
title: 位置策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: 位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: a7528ea173d03714a8dc20c474d4e1f3d74a5bc2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245081"
---
# <a name="location-policy"></a><span data-ttu-id="ec47b-103">位置策略</span><span class="sxs-lookup"><span data-stu-id="ec47b-103">Location Policy</span></span>

<span data-ttu-id="ec47b-104">位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="ec47b-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="ec47b-105">位置策略包括全局策略以及可选的一个或多个站点和用户策略：</span><span class="sxs-lookup"><span data-stu-id="ec47b-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="ec47b-106">**全局策略：** 默认情况下创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="ec47b-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="ec47b-107">可以编辑全局策略，但无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="ec47b-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="ec47b-108">如果您尝试删除全局策略，则所有设置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="ec47b-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="ec47b-109">**的网站策略 （可选）：** 您可以创建一个或多个站点位置策略，其中每个适用于特定站点。</span><span class="sxs-lookup"><span data-stu-id="ec47b-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="ec47b-110">站点策略会覆盖全局策略。</span><span class="sxs-lookup"><span data-stu-id="ec47b-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="ec47b-111">**用户策略 （可选）：** 您可以创建一个或多个用户位置策略，其中每个适用于特定用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="ec47b-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="ec47b-112">用户策略会覆盖全局策略和站点策略。</span><span class="sxs-lookup"><span data-stu-id="ec47b-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="ec47b-113">也可以向网络站点（即子网组）分配位置策略。</span><span class="sxs-lookup"><span data-stu-id="ec47b-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="ec47b-114">分配给网络站点的位置策略优先于所有其他用户策略。</span><span class="sxs-lookup"><span data-stu-id="ec47b-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="ec47b-115">有关使用 cmdlet 将位置策略分配给网络站点的详细信息，请参阅[Add 与网络站点中的业务服务器 Skype 位置策略](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)。</span><span class="sxs-lookup"><span data-stu-id="ec47b-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="ec47b-116">有关使用业务 Server Control Panel 的 Skype 与网络站点分配位置策略的详细信息，请参阅[配置网络站点](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ec47b-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="ec47b-117">“**位置策略**”页显示一个为组织定义的所有位置策略的列表。</span><span class="sxs-lookup"><span data-stu-id="ec47b-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ec47b-118">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="ec47b-118">Tasks you can perform</span></span>

<span data-ttu-id="ec47b-119">您可以在“**位置策略**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="ec47b-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="ec47b-120">创建新的站点位置策略或用户位置策略</span><span class="sxs-lookup"><span data-stu-id="ec47b-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="ec47b-121">更改全局策略或现有站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="ec47b-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="ec47b-122">删除站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="ec47b-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ec47b-123">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="ec47b-123">UI Reference</span></span>

<span data-ttu-id="ec47b-124">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="ec47b-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="ec47b-125">**新**开始一个新的站点位置策略或用户位置策略。</span><span class="sxs-lookup"><span data-stu-id="ec47b-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="ec47b-126">**编辑**打开所选的位置策略以进行编辑，在列表中，选择所有位置策略或删除所选的站点策略或用户策略。</span><span class="sxs-lookup"><span data-stu-id="ec47b-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec47b-127">对于全局策略，“**删除**”会将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="ec47b-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="ec47b-128">**刷新**刷新位置策略的列表。</span><span class="sxs-lookup"><span data-stu-id="ec47b-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="ec47b-129">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="ec47b-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="ec47b-130">**名称**标识位置策略。</span><span class="sxs-lookup"><span data-stu-id="ec47b-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="ec47b-131">**范围**标识位置策略的范围： 全局、 站点或用户。</span><span class="sxs-lookup"><span data-stu-id="ec47b-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="ec47b-132">**E9-1-1**检查是否分配了此位置策略的用户启用了 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="ec47b-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="ec47b-133">**位置**指定会提示用户输入位置信息，以及他们的客户端将 Skype 将在新位置，业务服务器注册时是否如果他们无需输入位置信息消除提示符处，他们会看到免责声明。</span><span class="sxs-lookup"><span data-stu-id="ec47b-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="ec47b-134">**PSTN 用法**指定用于确定用于将来自客户端使用此配置文件的紧急呼叫路由的语音路由的公用电话交换网 (pstn) 用法。</span><span class="sxs-lookup"><span data-stu-id="ec47b-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="ec47b-135">**E9-1-1 号**指定要获得紧急服务时所拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="ec47b-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="ec47b-136">**E9-1-1 掩码**指定将用户拨打可转换成紧急拨打号码的号码。</span><span class="sxs-lookup"><span data-stu-id="ec47b-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="ec47b-137">有关企业语音紧急服务特性和功能的详细信息，请参阅规划文档中[概述的 E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="ec47b-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ec47b-138">有关使用位置策略的详细信息，请参阅操作文档中的[配置位置策略](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ec47b-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


