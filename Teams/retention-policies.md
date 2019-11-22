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
ms.openlocfilehash: 6779e9b0fa236b1c239f9e6aa56d97e9437fb422
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793518"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="01d99-103">Microsoft Teams 中的保留策略</span><span class="sxs-lookup"><span data-stu-id="01d99-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="01d99-104">默认情况下，团队对话保持不变并永久保留。</span><span class="sxs-lookup"><span data-stu-id="01d99-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="01d99-105">随着保留策略的推出，管理员可以在安全 & 合规性中心中配置保留策略（保留和删除），以便团队聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="01d99-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="01d99-106">这有助于组织在特定时间段内保留数据以实现合规性（即保留策略）或删除数据（即删除策略）（如果在特定时间段后被视为负债）。</span><span class="sxs-lookup"><span data-stu-id="01d99-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="01d99-107">团队保留策略可确保在你删除数据时，团队服务上的所有永久数据存储位置都将删除该数据。</span><span class="sxs-lookup"><span data-stu-id="01d99-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span>

> [!NOTE]
> <span data-ttu-id="01d99-108">我们尚不支持保留专用频道消息的配置。</span><span class="sxs-lookup"><span data-stu-id="01d99-108">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="01d99-109">支持在专用频道中共享的文件的保留。</span><span class="sxs-lookup"><span data-stu-id="01d99-109">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="01d99-110">若要管理团队保留策略，请在 "**信息管理** > **保留**" 下的 Office 365 安全 & 合规中心中使用设置和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="01d99-110">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Information governance** > **Retention**.</span></span>

<span data-ttu-id="01d99-111">团队保留策略支持：</span><span class="sxs-lookup"><span data-stu-id="01d99-111">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="01d99-112">保留：保留指定工期的工作组数据，然后不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="01d99-112">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="01d99-113">保留并删除：将团队数据保留指定工期，然后删除</span><span class="sxs-lookup"><span data-stu-id="01d99-113">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="01d99-114">删除：在指定工期后删除团队数据</span><span class="sxs-lookup"><span data-stu-id="01d99-114">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="01d99-115">团队保留策略尚不支持：</span><span class="sxs-lookup"><span data-stu-id="01d99-115">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="01d99-116">高级保留策略不适用于团队聊天和团队频道消息位置</span><span class="sxs-lookup"><span data-stu-id="01d99-116">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="01d99-117">持续时间少于30天</span><span class="sxs-lookup"><span data-stu-id="01d99-117">Duration of fewer than 30 days</span></span>

<span data-ttu-id="01d99-118">管理员可以为团队私人聊天（1:1 或1：许多聊天）和团队频道消息设置单独的保留策略。</span><span class="sxs-lookup"><span data-stu-id="01d99-118">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="01d99-119">在许多情况下，组织将专用聊天数据视为比频道消息更多的责任，这通常是更多与项目相关的对话。</span><span class="sxs-lookup"><span data-stu-id="01d99-119">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="01d99-120">在安全 & 合规性中心（**信息管理** > **保留**）中设置这些策略。</span><span class="sxs-lookup"><span data-stu-id="01d99-120">Set up these policies in the Security & Compliance Center, **Information governance** > **Retention**.</span></span> <span data-ttu-id="01d99-121">打开**团队频道消息**和**团队聊天**，然后定义这些位置的保留策略（也显示在下图中）。</span><span class="sxs-lookup"><span data-stu-id="01d99-121">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="01d99-122">当您打开**团队频道消息**时，您可以指定将应用此策略的团队。</span><span class="sxs-lookup"><span data-stu-id="01d99-122">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="01d99-123">例如，对于团队 X、Y 和 Z，管理员可以将删除策略设置为1年（通过单独选择这些团队），并向团队的其余成员应用3年删除策略。</span><span class="sxs-lookup"><span data-stu-id="01d99-123">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="01d99-124">你可以通过选择特定用户并应用唯一的保留策略来为**团队聊天**执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="01d99-124">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="01d99-126">团队频道消息位置和团队聊天位置仅解决存储在 Exchange Online 邮箱（用户和组邮箱）中的团队对话。</span><span class="sxs-lookup"><span data-stu-id="01d99-126">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="01d99-127">将从所有相关存储位置（即邮箱、基底和聊天服务）中删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="01d99-127">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="01d99-128">若要管理团队文件（存储在 OneDrive for Business 和 SharePoint 中）的保留策略，请使用其保留策略。</span><span class="sxs-lookup"><span data-stu-id="01d99-128">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="01d99-129">根据设计，团队文件的删除策略是通过 SharePoint Online 和 OneDrive for Business 位置配置的。</span><span class="sxs-lookup"><span data-stu-id="01d99-129">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="01d99-130">因此，策略可能会删除团队聊天或频道消息中引用的文件，然后再删除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="01d99-130">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="01d99-131">在这种情况下，文件仍将显示在 "团队" 消息中，但如果你单击该文件，你将收到 "找不到文件" 错误（如果有人手动删除 SharePoint Online 或 OneDrive for business 中的文件，也可能会发生此错误）。</span><span class="sxs-lookup"><span data-stu-id="01d99-131">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="01d99-132">有关配置 Office 365 的保留策略的详细信息，请阅读[保留策略概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="01d99-132">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
