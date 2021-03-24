---
title: 会议配置
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
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: 会议配置设置定义会议类型 (也称为会议) 用户可以创建的会议类型，并控制 (或) 匿名用户和电话拨入式会议用户是否可以加入这些会议。 这些设置仅适用于安排的会议。 它们不适用于通过单击客户端中的"现在开会"选项创建临时会议。
ms.openlocfilehash: e53297aaae7707f8cc0ae4821a97afb78e0382e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099658"
---
# <a name="meeting-configuration"></a><span data-ttu-id="71027-105">会议配置</span><span class="sxs-lookup"><span data-stu-id="71027-105">Meeting Configuration</span></span>

<span data-ttu-id="71027-106">会议配置设置定义会议类型 (也称为"会议") 用户可以创建的会议类型，并控制 (或) 匿名用户和电话拨入式会议用户是否可以加入这些会议。</span><span class="sxs-lookup"><span data-stu-id="71027-106">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences.</span></span> <span data-ttu-id="71027-107">这些设置仅适用于安排的会议。</span><span class="sxs-lookup"><span data-stu-id="71027-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="71027-108">它们不适用于通过单击客户端中的"现在开会"选项创建临时会议。</span><span class="sxs-lookup"><span data-stu-id="71027-108">They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="71027-109">在全局级、站点级或池级上应用会议配置：</span><span class="sxs-lookup"><span data-stu-id="71027-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="71027-110">**全局会议配置：** 默认情况下，将创建全局会议配置。</span><span class="sxs-lookup"><span data-stu-id="71027-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="71027-111">可以编辑全局会议配置，但无法将其删除。</span><span class="sxs-lookup"><span data-stu-id="71027-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="71027-112">如果您尝试删除全局会议配置，则所有设置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="71027-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="71027-113">**站点会议配置 (可选) ：** 可以创建一个或多个站点会议配置，其中每个配置都适用于特定站点。</span><span class="sxs-lookup"><span data-stu-id="71027-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="71027-114">站点配置会覆盖全局配置。</span><span class="sxs-lookup"><span data-stu-id="71027-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="71027-115">**池会议配置 (可选) ：** 可以创建一个或多个池会议配置，每个配置都适用于特定池。</span><span class="sxs-lookup"><span data-stu-id="71027-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="71027-116">池配置会覆盖全局配置和站点配置。</span><span class="sxs-lookup"><span data-stu-id="71027-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="71027-117">“会议配置”页显示一个为组织定义的所有会议配置的列表。</span><span class="sxs-lookup"><span data-stu-id="71027-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="71027-118">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="71027-118">Tasks you can perform</span></span>

<span data-ttu-id="71027-119">您可以在“会议配置”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="71027-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="71027-120">创建新的站点会议配置或池会议配置</span><span class="sxs-lookup"><span data-stu-id="71027-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="71027-121">更改全局配置或者现有站点配置或池配置</span><span class="sxs-lookup"><span data-stu-id="71027-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="71027-122">删除站点配置或池配置</span><span class="sxs-lookup"><span data-stu-id="71027-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="71027-123">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="71027-123">UI Reference</span></span>

<span data-ttu-id="71027-124">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="71027-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="71027-125">**新建** 启动新的站点会议配置或池会议配置。</span><span class="sxs-lookup"><span data-stu-id="71027-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="71027-126">**编辑** 打开所选会议配置以对其进行编辑，选择列表中的所有会议配置，或删除所选的站点配置或池配置。</span><span class="sxs-lookup"><span data-stu-id="71027-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71027-127">对于全局会议配置，“删除”会将设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="71027-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="71027-128">**刷新** 刷新会议配置列表。</span><span class="sxs-lookup"><span data-stu-id="71027-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="71027-129">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="71027-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="71027-130">**名称** 标识会议配置。</span><span class="sxs-lookup"><span data-stu-id="71027-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="71027-131">**范围** 标识会议配置的范围：全局、站点或池。</span><span class="sxs-lookup"><span data-stu-id="71027-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="71027-132">有关使用会议配置的详细信息，请参阅操作文档中的[Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings)。</span><span class="sxs-lookup"><span data-stu-id="71027-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span>