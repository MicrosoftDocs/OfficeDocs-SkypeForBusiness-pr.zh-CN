---
title: 会议策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
ROBOTS: NOINDEX, NOFOLLOW
description: 会议策略定义会议期间用户可以使用的各种功能。
ms.openlocfilehash: 23377ce4974be1139cf5ff3e7d090cb83d8f2504
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824862"
---
# <a name="conferencing-policy"></a><span data-ttu-id="be47e-103">会议策略</span><span class="sxs-lookup"><span data-stu-id="be47e-103">Conferencing Policy</span></span>

<span data-ttu-id="be47e-104">会议策略定义会议期间用户可以使用的各种功能。</span><span class="sxs-lookup"><span data-stu-id="be47e-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="be47e-105">会议策略包括全局策略以及可选的一个或多个站点和用户策略：</span><span class="sxs-lookup"><span data-stu-id="be47e-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="be47e-106">**全局策略：** 默认情况下，将创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="be47e-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="be47e-107">可以编辑全局策略，但无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="be47e-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="be47e-108">如果您尝试删除全局策略，则所有设置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="be47e-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="be47e-109">**网站策略 (可选) ：** 可以创建一个或多个站点会议策略，每个策略都适用于特定站点。</span><span class="sxs-lookup"><span data-stu-id="be47e-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="be47e-110">站点策略会覆盖全局策略。</span><span class="sxs-lookup"><span data-stu-id="be47e-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="be47e-111">**用户策略 (可选) ：** 可以创建一个或多个用户会议策略，每个策略都适用于特定用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="be47e-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="be47e-112">用户策略会覆盖全局策略和站点策略。</span><span class="sxs-lookup"><span data-stu-id="be47e-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="be47e-113">“会议策略”页将显示一个为组织定义的所有会议策略的列表。</span><span class="sxs-lookup"><span data-stu-id="be47e-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="be47e-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="be47e-114">Tasks you can perform</span></span>

<span data-ttu-id="be47e-115">您可以在“位置策略”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="be47e-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="be47e-116">创建新的站点会议策略或用户会议策略</span><span class="sxs-lookup"><span data-stu-id="be47e-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="be47e-117">更改全局策略或现有站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="be47e-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="be47e-118">删除站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="be47e-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="be47e-119">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="be47e-119">UI Reference</span></span>

<span data-ttu-id="be47e-120">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="be47e-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="be47e-121">**新建** 启动新的站点会议策略或用户会议策略。</span><span class="sxs-lookup"><span data-stu-id="be47e-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="be47e-122">**编辑** 打开所选会议策略进行编辑，选择列表中的所有会议策略，或删除所选的站点策略或用户策略。</span><span class="sxs-lookup"><span data-stu-id="be47e-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="be47e-123">对于全局策略，“删除”会将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="be47e-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="be47e-124">**刷新** 刷新会议策略列表。</span><span class="sxs-lookup"><span data-stu-id="be47e-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="be47e-125">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="be47e-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="be47e-126">**名称** 标识会议策略。</span><span class="sxs-lookup"><span data-stu-id="be47e-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="be47e-127">**范围** 标识会议策略的范围：全局、站点或用户。</span><span class="sxs-lookup"><span data-stu-id="be47e-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="be47e-128">**数据协作** 如果会议策略指定允许在会议中进行数据协作，则选中。</span><span class="sxs-lookup"><span data-stu-id="be47e-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="be47e-129">**应用程序共享** 如果会议策略指定允许在会议中共享应用程序，则选中。</span><span class="sxs-lookup"><span data-stu-id="be47e-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="be47e-130">**音频** 如果会议策略指定会议允许音频，则选中。</span><span class="sxs-lookup"><span data-stu-id="be47e-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="be47e-131">**视频** 如果会议策略指定会议允许视频，则选中。</span><span class="sxs-lookup"><span data-stu-id="be47e-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="be47e-132">**PSTN** 如果会议策略指定允许 PSTN 电话拨入式会议，则选中。</span><span class="sxs-lookup"><span data-stu-id="be47e-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="be47e-133">**录制** 如果会议策略指定允许在会议中录制，则选中。</span><span class="sxs-lookup"><span data-stu-id="be47e-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="be47e-134">有关会议特性和功能的详细信息，请参阅规划文档中的[Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="be47e-134">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="be47e-135">有关使用会议策略的详细信息，请参阅操作文档中的[Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)。</span><span class="sxs-lookup"><span data-stu-id="be47e-135">For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


