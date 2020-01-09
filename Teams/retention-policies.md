---
title: Microsoft Teams 中的保留策略
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: 了解如何保留策略以及如何在团队中管理它们。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 73d8de57b7b47ced8217e0f7aca384f4b55b0468
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988977"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="a93bf-103">Microsoft Teams 中的保留策略</span><span class="sxs-lookup"><span data-stu-id="a93bf-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="a93bf-104">默认情况下，团队对话保持不变并永久保留。</span><span class="sxs-lookup"><span data-stu-id="a93bf-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="a93bf-105">随着保留策略的推出，管理员可以在安全 & 合规性中心中配置保留策略（保留和删除），以便团队聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="a93bf-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="a93bf-106">这有助于组织在特定时间段内保留数据以实现合规性（即保留策略）或删除数据（即删除策略）（如果在特定时间段后被视为负债）。</span><span class="sxs-lookup"><span data-stu-id="a93bf-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="a93bf-107">团队保留策略可确保在你删除数据时，团队服务上的所有永久数据存储位置都将删除该数据。</span><span class="sxs-lookup"><span data-stu-id="a93bf-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span>

> [!NOTE]
> <span data-ttu-id="a93bf-108">我们尚不支持保留专用频道消息的配置。</span><span class="sxs-lookup"><span data-stu-id="a93bf-108">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="a93bf-109">支持在专用频道中共享的文件的保留。</span><span class="sxs-lookup"><span data-stu-id="a93bf-109">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="a93bf-110">若要管理团队保留策略，请在 "**信息管理** > **保留**" 下的 Office 365 安全 & 合规中心中使用设置和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a93bf-110">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Information governance** > **Retention**.</span></span>

<span data-ttu-id="a93bf-111">团队保留策略支持：</span><span class="sxs-lookup"><span data-stu-id="a93bf-111">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="a93bf-112">保留：保留指定工期的工作组数据，然后不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="a93bf-112">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="a93bf-113">保留并删除：将团队数据保留指定工期，然后删除</span><span class="sxs-lookup"><span data-stu-id="a93bf-113">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="a93bf-114">删除：在指定工期后删除团队数据</span><span class="sxs-lookup"><span data-stu-id="a93bf-114">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="a93bf-115">团队保留策略尚不支持：</span><span class="sxs-lookup"><span data-stu-id="a93bf-115">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="a93bf-116">高级保留策略不适用于团队聊天和团队频道消息位置</span><span class="sxs-lookup"><span data-stu-id="a93bf-116">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>

<span data-ttu-id="a93bf-117">管理员可以为团队私人聊天（1:1 或1：许多聊天）和团队频道消息设置单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="a93bf-117">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="a93bf-118">在许多情况下，组织将专用聊天数据视为比频道消息更多的责任，这通常是更多与项目相关的对话。</span><span class="sxs-lookup"><span data-stu-id="a93bf-118">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="a93bf-119">在安全 & 合规性中心（**信息管理** > **保留**）中设置这些策略。</span><span class="sxs-lookup"><span data-stu-id="a93bf-119">Set up these policies in the Security & Compliance Center, **Information governance** > **Retention**.</span></span> <span data-ttu-id="a93bf-120">打开**团队频道消息**和**团队聊天**，然后定义这些位置的保留策略（也显示在下图中）。</span><span class="sxs-lookup"><span data-stu-id="a93bf-120">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="a93bf-121">当您打开**团队频道消息**时，您可以指定将应用此策略的团队。</span><span class="sxs-lookup"><span data-stu-id="a93bf-121">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="a93bf-122">例如，对于团队 X、Y 和 Z，管理员可以将删除策略设置为1年（通过单独选择这些团队），并向团队的其余成员应用3年删除策略。</span><span class="sxs-lookup"><span data-stu-id="a93bf-122">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="a93bf-123">你可以通过选择特定用户并应用唯一的保留策略来为**团队聊天**执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="a93bf-123">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="a93bf-125">团队频道消息位置和团队聊天位置仅解决存储在 Exchange Online 邮箱（用户和组邮箱）中的团队对话。</span><span class="sxs-lookup"><span data-stu-id="a93bf-125">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="a93bf-126">将从所有相关存储位置（即邮箱、基底和聊天服务）中删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="a93bf-126">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="a93bf-127">若要管理团队文件（存储在 OneDrive for Business 和 SharePoint 中）的保留策略，请使用其保留策略。</span><span class="sxs-lookup"><span data-stu-id="a93bf-127">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="a93bf-128">根据设计，团队文件的删除策略是通过 SharePoint Online 和 OneDrive for Business 位置配置的。</span><span class="sxs-lookup"><span data-stu-id="a93bf-128">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="a93bf-129">因此，策略可能会删除团队聊天或频道消息中引用的文件，然后再删除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="a93bf-129">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="a93bf-130">在这种情况下，文件仍将显示在 "团队" 消息中，但如果你单击该文件，你将收到 "找不到文件" 错误（如果有人手动删除 SharePoint Online 或 OneDrive for business 中的文件，也可能会发生此错误）。</span><span class="sxs-lookup"><span data-stu-id="a93bf-130">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="a93bf-131">有关配置 Office 365 的保留策略的详细信息，请阅读[保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="a93bf-131">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
