---
title: 会议策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
ROBOTS: NOINDEX, NOFOLLOW
description: 会议策略定义的特性和功能 （也称为会议） 会议期间用户可以使用。
ms.openlocfilehash: ac53ac12d61680a3cbbb54cd90020d9b91e39e14
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255470"
---
# <a name="conferencing-policy"></a><span data-ttu-id="1f469-103">会议策略</span><span class="sxs-lookup"><span data-stu-id="1f469-103">Conferencing Policy</span></span>

<span data-ttu-id="1f469-104">会议策略定义的特性和功能 （也称为会议） 会议期间用户可以使用。</span><span class="sxs-lookup"><span data-stu-id="1f469-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="1f469-105">会议策略包括全局策略和一个或多个站点和用户策略 （可选）：</span><span class="sxs-lookup"><span data-stu-id="1f469-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="1f469-106">**全局策略：** 默认情况下创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="1f469-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="1f469-107">可以编辑全局策略，但无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="1f469-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="1f469-108">如果您尝试删除全局策略，则所有设置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="1f469-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="1f469-109">**的网站策略 （可选）：** 您可以创建一个或多个站点会议策略，其中每个适用于特定站点。</span><span class="sxs-lookup"><span data-stu-id="1f469-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="1f469-110">站点策略会覆盖全局策略。</span><span class="sxs-lookup"><span data-stu-id="1f469-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="1f469-111">**用户策略 （可选）：** 您可以创建一个或多个用户会议策略，其中每个适用于特定用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="1f469-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="1f469-112">用户策略会覆盖全局策略和站点策略。</span><span class="sxs-lookup"><span data-stu-id="1f469-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="1f469-113">**会议策略**页上显示为组织定义的所有会议策略的列表。</span><span class="sxs-lookup"><span data-stu-id="1f469-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="1f469-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="1f469-114">Tasks you can perform</span></span>

<span data-ttu-id="1f469-115">您可以在“**位置策略**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="1f469-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="1f469-116">创建新的站点会议策略或用户会议策略</span><span class="sxs-lookup"><span data-stu-id="1f469-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="1f469-117">更改全局策略或现有站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="1f469-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="1f469-118">删除站点策略或用户策略</span><span class="sxs-lookup"><span data-stu-id="1f469-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1f469-119">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="1f469-119">UI Reference</span></span>

<span data-ttu-id="1f469-120">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="1f469-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="1f469-121">**新**开始一个新的站点会议策略或用户会议策略。</span><span class="sxs-lookup"><span data-stu-id="1f469-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="1f469-122">**编辑**打开所选的会议策略以进行编辑，在列表中，选择所有会议策略，或者删除所选的站点策略或用户策略。</span><span class="sxs-lookup"><span data-stu-id="1f469-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f469-123">对于全局策略，“**删除**”会将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="1f469-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="1f469-124">**刷新**刷新会议策略的列表。</span><span class="sxs-lookup"><span data-stu-id="1f469-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="1f469-125">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="1f469-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="1f469-126">**名称**标识会议策略。</span><span class="sxs-lookup"><span data-stu-id="1f469-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="1f469-127">**范围**标识会议策略的范围： 全局、 站点或用户。</span><span class="sxs-lookup"><span data-stu-id="1f469-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="1f469-128">**数据协作**如果会议策略指定在会议中允许数据协作，则检查。</span><span class="sxs-lookup"><span data-stu-id="1f469-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="1f469-129">**应用程序共享**检查是否会议策略指定在会议中允许应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="1f469-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="1f469-130">**音频**如果会议策略指定在会议中允许音频，则检查。</span><span class="sxs-lookup"><span data-stu-id="1f469-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="1f469-131">**视频**如果会议策略指定在会议中允许视频，则检查。</span><span class="sxs-lookup"><span data-stu-id="1f469-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="1f469-132">**PSTN**检查是否会议策略指定允许 PSTN 电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="1f469-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="1f469-133">**录制**检查是否会议策略指定在会议中允许录制。</span><span class="sxs-lookup"><span data-stu-id="1f469-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="1f469-134">有关会议特性和功能的详细信息，请参阅规划文档中[概述的会议](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1f469-134">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="1f469-135">有关使用会议策略的详细信息，请参阅操作文档中的[会议策略](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1f469-135">For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


