---
title: 未分配电话号码
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
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: 4b736aef028421bca6c4945095f9d293d18f3550
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826882"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="8cb71-104">未分配电话号码</span><span class="sxs-lookup"><span data-stu-id="8cb71-104">Unassigned Phone Number</span></span>

<span data-ttu-id="8cb71-p102">未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。</span><span class="sxs-lookup"><span data-stu-id="8cb71-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="8cb71-p103">配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码定制所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码并将其分配给提供新号码的通知。</span><span class="sxs-lookup"><span data-stu-id="8cb71-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cb71-113">在配置未分配号码表之前，必须已定义一个或多个通知，或已设置 Exchange UM 自动助理。</span><span class="sxs-lookup"><span data-stu-id="8cb71-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="8cb71-114">“未分配号码”页将显示一个为组织定义的未分配号码范围的列表。</span><span class="sxs-lookup"><span data-stu-id="8cb71-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="8cb71-115">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="8cb71-115">Tasks you can perform</span></span>

<span data-ttu-id="8cb71-116">您可以在“未分配号码”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8cb71-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="8cb71-117">创建新的未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="8cb71-117">Create a new unassigned number range</span></span>

- <span data-ttu-id="8cb71-118">更改现有未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="8cb71-118">Change an existing unassigned number range</span></span>

- <span data-ttu-id="8cb71-119">删除未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="8cb71-119">Delete an unassigned number range</span></span>

- <span data-ttu-id="8cb71-120">更改未分配号码范围的顺序，以便确定对匹配未分配号码的传入呼叫首先应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="8cb71-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8cb71-121">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="8cb71-121">UI Reference</span></span>

<span data-ttu-id="8cb71-122">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="8cb71-122">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="8cb71-123">**新建** 启动新的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="8cb71-123">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="8cb71-124">**编辑** 打开选定的未分配号码范围进行编辑，选择列表中所有未分配号码范围，或删除所选的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="8cb71-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="8cb71-125">**上移** 将所选未分配号码范围向上移动，以便 Skype for Business Server 能够更早地找到该号码范围，并应用指定操作，然后再应用为列表中其他范围指定的操作。</span><span class="sxs-lookup"><span data-stu-id="8cb71-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8cb71-126">Skype for Business Server 从上到下搜索未分配号码表，并使用与未分配号码匹配的第一个范围。</span><span class="sxs-lookup"><span data-stu-id="8cb71-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="8cb71-127">例如，如果有一个范围指定了最后一种操作，请确保将该范围置于列表底部。</span><span class="sxs-lookup"><span data-stu-id="8cb71-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="8cb71-128">**下移** 在列表中将选定的未分配号码范围向下移动。</span><span class="sxs-lookup"><span data-stu-id="8cb71-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="8cb71-129">**全部提交** 保存对未分配号码范围进行的所有更改。</span><span class="sxs-lookup"><span data-stu-id="8cb71-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8cb71-130">该命令可保存您在“新建未分配号码”页和“编辑未分配号码”页上所做的全部更改。</span><span class="sxs-lookup"><span data-stu-id="8cb71-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="8cb71-131">**刷新** 刷新未分配号码范围的列表。</span><span class="sxs-lookup"><span data-stu-id="8cb71-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="8cb71-132">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="8cb71-132">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="8cb71-133">**名称** 标识未分配号码范围的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="8cb71-133">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="8cb71-134">**状态** 显示哪些号码范围已保存到数据库，哪些未保存到数据库中。</span><span class="sxs-lookup"><span data-stu-id="8cb71-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="8cb71-135">**开始范围** 未分配号码范围的开始号码。</span><span class="sxs-lookup"><span data-stu-id="8cb71-135">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="8cb71-136">**结束范围** 未分配号码范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="8cb71-136">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="8cb71-137">**目标** 承载通知应用程序的应用程序服务的服务 ID，它将处理对此未分配号码范围的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="8cb71-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="8cb71-138">**公告** 将为此未分配号码范围播放的公告。</span><span class="sxs-lookup"><span data-stu-id="8cb71-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="8cb71-139">有关通知特性和功能的详细信息，请参阅规划文档中[的 Plan for the Announcement application in Skype for Business 2015。](../../plan-your-deployment/enterprise-voice-solution/announcement.md)</span><span class="sxs-lookup"><span data-stu-id="8cb71-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="8cb71-140">有关使用未分配号码范围的详细信息，请参阅操作文档中的[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8cb71-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


