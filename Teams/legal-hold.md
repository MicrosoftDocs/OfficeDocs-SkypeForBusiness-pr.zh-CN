---
title: 将 Microsoft Teams 用户或团队置于法定保留状态
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何使用安全性和合规性中心将 Microsoft Teams 用户或团队置于法定保留状态，以及了解根据数据要求哪些内容需要法定保留。
appliesto:
- Microsoft Teams
ms.openlocfilehash: d11ae740f051d4da2a5e930193797c08451cbe7c
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121352"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="f10eb-103">将 Microsoft Teams 用户或团队置于法定保留状态</span><span class="sxs-lookup"><span data-stu-id="f10eb-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="f10eb-104">如果有合理的诉讼预期，组织需要保留电子存储的信息（ESI），包括与案例相关的团队聊天消息。</span><span class="sxs-lookup"><span data-stu-id="f10eb-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="f10eb-105">组织可能需要保留与特定主题或特定人员相关的所有消息。</span><span class="sxs-lookup"><span data-stu-id="f10eb-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="f10eb-106">本文将介绍 Microsoft 团队中的法律封存（若要解决跨 M365 空间的保留实施，请参阅[管理电子数据展示事例：保留内容位置](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)。）。</span><span class="sxs-lookup"><span data-stu-id="f10eb-106">This article will cover legal hold in Microsoft Teams (To address hold implementation across the M365 space, please review [Manage eDiscovery cases: Place content locations on hold](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).).</span></span>

> [!NOTE]
> <span data-ttu-id="f10eb-107">在2020年2月，我们已为专用频道（专用频道聊天存储在用户邮箱中，普通频道聊天存储在该团队的组邮箱中）启用了法律封存或案例保留。</span><span class="sxs-lookup"><span data-stu-id="f10eb-107">In Feb 2020, we turned on legal hold or case hold on private channels (private channel chats are stored in user mailboxes, normal channel chats are stored in that Teams’ group mailboxes).</span></span> <span data-ttu-id="f10eb-108">如果用户邮箱已有合法保留，则保留策略现在将自动应用到存储在该邮箱中的专用通道邮件。</span><span class="sxs-lookup"><span data-stu-id="f10eb-108">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="f10eb-109">管理员无需执行任何操作即可打开此功能。</span><span class="sxs-lookup"><span data-stu-id="f10eb-109">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="f10eb-110">在专用频道中共享的文件的法定保留也受支持。</span><span class="sxs-lookup"><span data-stu-id="f10eb-110">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="f10eb-111">在 Microsoft 团队中，整个团队或选择用户可进行保留或法律封存。</span><span class="sxs-lookup"><span data-stu-id="f10eb-111">Within Microsoft Teams, an entire team or select users can be put on hold or legal hold.</span></span> <span data-ttu-id="f10eb-112">执行此操作将确保组织的合规性管理者或团队管理员可以发现在这些团队（包括专用信道）或由这些人员交换的消息中交换的所有消息。</span><span class="sxs-lookup"><span data-stu-id="f10eb-112">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization’s compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="f10eb-113">将用户置于保留状态并不会自动将组置于保留状态，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f10eb-113">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

<span data-ttu-id="f10eb-114">将用户或团队置于法律封存状态：</span><span class="sxs-lookup"><span data-stu-id="f10eb-114">To put a user or a team on Legal Hold:</span></span>

1. <span data-ttu-id="f10eb-115">导航到[安全 & 合规中心](https://go.microsoft.com/fwlink/?linkid=854628)。</span><span class="sxs-lookup"><span data-stu-id="f10eb-115">Navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="f10eb-116">在你创建新案例时，系统会为你提供用于将邮箱或网站置于保留状态的选项。</span><span class="sxs-lookup"><span data-stu-id="f10eb-116">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>
1. <span data-ttu-id="f10eb-117">转到电子数据展示或高级电子数据展示，并通过单击 "创建事例" 来创建案例。</span><span class="sxs-lookup"><span data-stu-id="f10eb-117">Go to eDiscovery or Advanced eDiscovery and create a case by clicking “+ Create a case”.</span></span> <span data-ttu-id="f10eb-118">一旦创建了事例，请将其打开。</span><span class="sxs-lookup"><span data-stu-id="f10eb-118">Once the case is created, open it.</span></span>
<span data-ttu-id="f10eb-119">!["Microsoft 团队电子数据展示" 选项卡已选中，显示 "创建事例" 按钮。](media/LegalHold1.png)</span><span class="sxs-lookup"><span data-stu-id="f10eb-119">![Microsoft Teams eDiscovery tab is selected, showing the Create a case button.](media/LegalHold1.png)</span></span>
1. <span data-ttu-id="f10eb-120">转到顶部菜单中的 "保留" 部分，然后单击 "+ 创建" 以创建将用户或团队置于保持状态时保存由这些用户或邮件交换的所有邮件保存由这些用户或邮件交换的所有邮件当您创建新事例时，将显示将邮箱或网站置于保持状态的选项。</span><span class="sxs-lookup"><span data-stu-id="f10eb-120">Go to “Holds” section from the top menu and click on “+ Create” to create a hold Putting a user or a team on hold saves all the messages exchanged by those users or messages When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>
<span data-ttu-id="f10eb-121">![显示选定的 "保留" 选项卡和 "创建" 按钮下方的图像。](media/LegalHold2.png)</span><span class="sxs-lookup"><span data-stu-id="f10eb-121">![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)</span></span>
    1. <span data-ttu-id="f10eb-122">为**您的保留命名**。</span><span class="sxs-lookup"><span data-stu-id="f10eb-122">**Name your hold**.</span></span> <span data-ttu-id="f10eb-123">为要创建的保留选择一个描述性且唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="f10eb-123">Select a descriptive and unique name for the hold you are going to create.</span></span>
<span data-ttu-id="f10eb-124">![此屏幕截图显示 "为你的保留" 选项卡的名称，你可以在其中输入你正在创建的保留的名称和说明。](media/LegalHold3.png)</span><span class="sxs-lookup"><span data-stu-id="f10eb-124">![This screenshot shows the Name your hold tab, where you can enter in a name and description for the hold you are creating.](media/LegalHold3.png)</span></span>
    1. <span data-ttu-id="f10eb-125">**选择 "位置**"。</span><span class="sxs-lookup"><span data-stu-id="f10eb-125">**Choose location**.</span></span> <span data-ttu-id="f10eb-126">选择是希望保留应用于用户还是整个团队（现在无法在单个频道上应用保留）。</span><span class="sxs-lookup"><span data-stu-id="f10eb-126">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="f10eb-127">注意：如果用户处于暂停状态，则其所有邮件都将处于暂停状态，包括在1:1 聊天中发送的任何内容、1：许多或群组聊天，或者频道对话（包括专用频道）。</span><span class="sxs-lookup"><span data-stu-id="f10eb-127">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
    <span data-ttu-id="f10eb-128">![在这里，我们有 "创建新保留" 的 "选择位置" 部分，您可以在其中做出决定要应用到的 M365 选项，包括 Microsoft 团队。](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="f10eb-128">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>
    1. <span data-ttu-id="f10eb-129">**创建查询**。</span><span class="sxs-lookup"><span data-stu-id="f10eb-129">**Create Query**.</span></span> <span data-ttu-id="f10eb-130">如果在保留策略中需要更多粒度，则可以自定义保留。</span><span class="sxs-lookup"><span data-stu-id="f10eb-130">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="f10eb-131">例如，你可以指定要查找的关键字，也可以添加更多条件，使保留生效。</span><span class="sxs-lookup"><span data-stu-id="f10eb-131">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    1. <span data-ttu-id="f10eb-132">请先**查看您的设置**，然后再将其发布到您的组织。</span><span class="sxs-lookup"><span data-stu-id="f10eb-132">**Review your settings** before publishing it to your organization.</span></span>

<span data-ttu-id="f10eb-133">设置法律封存后，您可以通过关注[团队 eDiscovery](eDiscovery-investigation.md)文章的任何保留政策来发现所有内容。</span><span class="sxs-lookup"><span data-stu-id="f10eb-133">Once the legal hold has been set, you can discover all the content retained by any hold policy following the [Teams eDiscovery](eDiscovery-investigation.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f10eb-134">当用户或组处于保留状态时，将保留所有邮件副本。</span><span class="sxs-lookup"><span data-stu-id="f10eb-134">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="f10eb-135">例如，如果用户在频道中发布了一封邮件，然后修改了该邮件，则在保留方案中，将保留该邮件的两个副本。</span><span class="sxs-lookup"><span data-stu-id="f10eb-135">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="f10eb-136">如果不保留法律保留，则仅保留最新消息。</span><span class="sxs-lookup"><span data-stu-id="f10eb-136">Without the legal hold in-place, only the latest message is retained.</span></span>

<span data-ttu-id="f10eb-137">作为一个有用的指南，您可以使用下表了解基于数据需求需要对法律封存施加哪些内容：</span><span class="sxs-lookup"><span data-stu-id="f10eb-137">As a helpful guide, you can use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="f10eb-138">应用场景</span><span class="sxs-lookup"><span data-stu-id="f10eb-138">Scenario</span></span>  |<span data-ttu-id="f10eb-139">置于保留状态的内容</span><span class="sxs-lookup"><span data-stu-id="f10eb-139">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="f10eb-140">**Microsoft 团队通过用户（在1:1 聊天上，1：多个或群组聊天、专用频道对话等）聊天内容**</span><span class="sxs-lookup"><span data-stu-id="f10eb-140">**Microsoft Teams chat content by a user (on 1:1 chats, 1:many or group chats, private channel conversations, etc.)**</span></span>     |<span data-ttu-id="f10eb-141">用户邮箱</span><span class="sxs-lookup"><span data-stu-id="f10eb-141">User mailbox</span></span>         |
|<span data-ttu-id="f10eb-142">**Microsoft 团队频道聊天（不包括专用频道）**</span><span class="sxs-lookup"><span data-stu-id="f10eb-142">**Microsoft Teams Channel chats (excluding private channels)**</span></span>    |<span data-ttu-id="f10eb-143">用于团队的组邮箱</span><span class="sxs-lookup"><span data-stu-id="f10eb-143">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="f10eb-144">**Microsoft 团队内容（如 Wiki、文件）**</span><span class="sxs-lookup"><span data-stu-id="f10eb-144">**Microsoft Teams content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="f10eb-145">团队使用的 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="f10eb-145">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="f10eb-146">**Microsoft 团队专用频道文件**</span><span class="sxs-lookup"><span data-stu-id="f10eb-146">**Microsoft Teams Private Channel files**</span></span>     |<span data-ttu-id="f10eb-147">专用的专用通道 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="f10eb-147">Dedicated Private Channel SharePoint Site</span></span>     |
|<span data-ttu-id="f10eb-148">**用户的私人内容**</span><span class="sxs-lookup"><span data-stu-id="f10eb-148">**User's private content**</span></span>     |<span data-ttu-id="f10eb-149">用户的 OneDrive for Business 网站</span><span class="sxs-lookup"><span data-stu-id="f10eb-149">OneDrive for Business site of the user</span></span>         |

> [!NOTE]
> <span data-ttu-id="f10eb-150">若要在专用通道中保留通信，你需要将用户邮箱（专用通道用户）置于保留状态，使用电子数据展示工具进行搜索时，应在该用户的邮箱中进行搜索。</span><span class="sxs-lookup"><span data-stu-id="f10eb-150">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="f10eb-151">正如之前所述，专用通道聊天存储在用户邮箱中，而不是在团队的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="f10eb-151">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="f10eb-152">如果想要阅读有关 M365 中非团队区域的本主题的详细内容，请参阅[管理电子数据展示事例：保留内容位置](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)。</span><span class="sxs-lookup"><span data-stu-id="f10eb-152">If you want to read further on this topic for non-Teams areas in M365, you should review [Manage eDiscovery cases: Place content locations on hold](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>
