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
ms.openlocfilehash: 3e52b10f0a7a8dd3ac67f7a2c15b9d1e082186ab
ms.sourcegitcommit: dba7984f899f8921b462a56d158fa0a1cc2c2a8b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929288"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="c0527-103">将 Microsoft Teams 用户或团队置于法定保留状态</span><span class="sxs-lookup"><span data-stu-id="c0527-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="c0527-104">当存在合理的诉讼预期时，组织需要保留以电子方式 (ESI) 的信息，Teams与案例相关的聊天消息。</span><span class="sxs-lookup"><span data-stu-id="c0527-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="c0527-105">组织可能需要保留与特定主题或特定个人相关的所有消息。</span><span class="sxs-lookup"><span data-stu-id="c0527-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="c0527-106">本文将介绍在 Microsoft Teams (中解决 M365 空间的保留实施问题，请查看管理电子数据展示事例[：](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)将内容位置放在保留) 。</span><span class="sxs-lookup"><span data-stu-id="c0527-106">This article will cover legal hold in Microsoft Teams (To address hold implementation across the M365 space, please review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).).</span></span>

> [!NOTE]
> <span data-ttu-id="c0527-107">2020 年 2 月，我们对专用通道启用了法定保留或案例保留 (专用频道聊天存储在用户邮箱中，普通频道聊天存储在团队的组邮箱) 。</span><span class="sxs-lookup"><span data-stu-id="c0527-107">In February 2020, we enabled legal hold or case hold on private channels (private channel chats are stored in user mailboxes, normal channel chats are stored in a Team's group mailbox).</span></span> <span data-ttu-id="c0527-108">如果用户邮箱已有法定保留，则保留策略现在将自动应用于存储在该邮箱中的专用频道邮件。</span><span class="sxs-lookup"><span data-stu-id="c0527-108">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="c0527-109">管理员无需执行进一步的操作来启用此功能。</span><span class="sxs-lookup"><span data-stu-id="c0527-109">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="c0527-110">还支持对在专用通道中共享的文件进行法定保留。</span><span class="sxs-lookup"><span data-stu-id="c0527-110">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="c0527-111">在Microsoft Teams内，整个团队或选定用户都可以被置于保留状态或法定保留状态。</span><span class="sxs-lookup"><span data-stu-id="c0527-111">Within Microsoft Teams, an entire team or select users can be put on hold or legal hold.</span></span> <span data-ttu-id="c0527-112">这样做将确保所有团队中交换的消息 (包括专用频道) 或这些人员交换的消息都由组织的合规性经理或管理员Teams发现。</span><span class="sxs-lookup"><span data-stu-id="c0527-112">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization’s compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="c0527-113">将用户置于保留状态并不会自动将组置于保留状态，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="c0527-113">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>
> <span data-ttu-id="c0527-114">活动源中发送的通知不能置于法定保留状态。</span><span class="sxs-lookup"><span data-stu-id="c0527-114">Notifications sent in activity feed cannot be put under legal hold.</span></span>

<span data-ttu-id="c0527-115">将用户或团队置于法定保留状态：</span><span class="sxs-lookup"><span data-stu-id="c0527-115">To put a user or a team on legal hold:</span></span>

1. <span data-ttu-id="c0527-116">导航到 [安全&中心](https://go.microsoft.com/fwlink/?linkid=854628)。</span><span class="sxs-lookup"><span data-stu-id="c0527-116">Navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="c0527-117">在你创建新案例时，系统会为你提供用于将邮箱或网站置于保留状态的选项。</span><span class="sxs-lookup"><span data-stu-id="c0527-117">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="c0527-118">转到电子数据展示或Advanced eDiscovery单击"创建案例"创建案例。</span><span class="sxs-lookup"><span data-stu-id="c0527-118">Go to eDiscovery or Advanced eDiscovery and create a case by clicking "Create a case".</span></span> <span data-ttu-id="c0527-119">创建案例后，打开它。</span><span class="sxs-lookup"><span data-stu-id="c0527-119">Once the case is created, open it.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c0527-120">![Microsoft Teams"电子数据展示"选项卡，显示"创建案例"按钮。](media/LegalHold1.png)</span><span class="sxs-lookup"><span data-stu-id="c0527-120">![Microsoft Teams eDiscovery tab is selected, showing the Create a case button.](media/LegalHold1.png)</span></span>

3. <span data-ttu-id="c0527-121">从顶部菜单中转到"保留"部分，然后单击"+ 创建"以创建保留。</span><span class="sxs-lookup"><span data-stu-id="c0527-121">Go to the "Holds" section from the top menu and click "+ Create" to create a hold.</span></span> <span data-ttu-id="c0527-122">保留用户或团队会保存这些用户或消息交换的所有消息。</span><span class="sxs-lookup"><span data-stu-id="c0527-122">Putting a user or a team on hold saves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="c0527-123">在你创建新案例时，系统会为你提供用于将邮箱或网站置于保留状态的选项。</span><span class="sxs-lookup"><span data-stu-id="c0527-123">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c0527-124">![显示选中了"保留"选项卡和下方的"创建"按钮的图像。](media/LegalHold2.png)</span><span class="sxs-lookup"><span data-stu-id="c0527-124">![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)</span></span>

   1. <span data-ttu-id="c0527-125">**将保留名称为**。</span><span class="sxs-lookup"><span data-stu-id="c0527-125">**Name your hold**.</span></span> <span data-ttu-id="c0527-126">选择要创建的保留的描述性唯一名称。</span><span class="sxs-lookup"><span data-stu-id="c0527-126">Select a descriptive and unique name for the hold you are going to create.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="c0527-127">![此屏幕截图显示"命名保留"选项卡，可在其中输入要创建的保留的名称和说明。](media/LegalHold3.png)</span><span class="sxs-lookup"><span data-stu-id="c0527-127">![This screenshot shows the Name your hold tab, where you can enter in a name and description for the hold you are creating.](media/LegalHold3.png)</span></span>

    2. <span data-ttu-id="c0527-128">**选择位置**。</span><span class="sxs-lookup"><span data-stu-id="c0527-128">**Choose location**.</span></span> <span data-ttu-id="c0527-129">选择要将保留应用于用户还是整个团队， (目前不能应用于单个频道) 。</span><span class="sxs-lookup"><span data-stu-id="c0527-129">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="c0527-130">注意：如果用户保持状态，其所有消息将被保留，包括他们在 1：1 聊天、1：多聊天或群组聊天中发送的任何消息，或者频道对话 (包括私人频道) 。</span><span class="sxs-lookup"><span data-stu-id="c0527-130">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
  
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="c0527-131">![在这里，我们提供了"创建新保留"的"选择位置"部分，您可以在其中决定要应用到的 M365 选项Microsoft Teams选项（包括 Microsoft Teams）。](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="c0527-131">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    3. <span data-ttu-id="c0527-132">**创建查询**。</span><span class="sxs-lookup"><span data-stu-id="c0527-132">**Create Query**.</span></span> <span data-ttu-id="c0527-133">如果希望保留策略中具有更精细的粒度，可以自定义保留。</span><span class="sxs-lookup"><span data-stu-id="c0527-133">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="c0527-134">例如，您可以指定要查找的关键字，或者可以添加更多条件，需要满足这些条件才能使保留生效。</span><span class="sxs-lookup"><span data-stu-id="c0527-134">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    4. <span data-ttu-id="c0527-135">**在将设置** 发布到组织之前，请查看设置。</span><span class="sxs-lookup"><span data-stu-id="c0527-135">**Review your settings** before publishing it to your organization.</span></span>

<span data-ttu-id="c0527-136">设置法定保留后，可以按照电子数据展示一文Teams[保留的内容](eDiscovery-investigation.md)。</span><span class="sxs-lookup"><span data-stu-id="c0527-136">After the legal hold has been set, you can discover all the content retained by any hold policy following the [Teams eDiscovery](eDiscovery-investigation.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0527-137">将用户或组置于保留状态时，将保留所有邮件副本。</span><span class="sxs-lookup"><span data-stu-id="c0527-137">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="c0527-138">例如，如果用户在频道中发布消息，然后修改了消息，在保留方案中，消息的两个副本将保留。</span><span class="sxs-lookup"><span data-stu-id="c0527-138">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="c0527-139">如果不就地保留法定保留，则仅保留最新邮件。</span><span class="sxs-lookup"><span data-stu-id="c0527-139">Without the legal hold in-place, only the latest message is retained.</span></span>

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a><span data-ttu-id="c0527-140">要保留法定保留的内容位置，以保留Teams内容</span><span class="sxs-lookup"><span data-stu-id="c0527-140">Content locations to place on legal hold to preserve Teams content</span></span>

<span data-ttu-id="c0527-141">作为有用的指南，可以使用下表来了解哪些内容位置 (例如邮箱或网站) ，以保留不同类型的 Teams 内容。</span><span class="sxs-lookup"><span data-stu-id="c0527-141">As a helpful guide, you can use the following table to understand what content location (such as a mailbox or site) to place on legal hold to preserve different types of Teams content.</span></span>

|<span data-ttu-id="c0527-142">使用场景</span><span class="sxs-lookup"><span data-stu-id="c0527-142">Scenario</span></span>  |<span data-ttu-id="c0527-143">内容位置</span><span class="sxs-lookup"><span data-stu-id="c0527-143">Content location</span></span>  |
|---------|---------|
|<span data-ttu-id="c0527-144">Teams 1：1 (聊天、1：N 群组聊天和私人频道对话等用户聊天) </span><span class="sxs-lookup"><span data-stu-id="c0527-144">Teams chats for a user (for example, 1:1 chats, 1:N group chats, and private channel conversations)</span></span>     |<span data-ttu-id="c0527-145">用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="c0527-145">User mailbox.</span></span>         |
|<span data-ttu-id="c0527-146">Teams频道聊天 (专用频道除外) </span><span class="sxs-lookup"><span data-stu-id="c0527-146">Teams channel chats (excluding private channels)</span></span>    |<span data-ttu-id="c0527-147">用于团队的组邮箱。</span><span class="sxs-lookup"><span data-stu-id="c0527-147">Group mailbox used for the team.</span></span>         |
|<span data-ttu-id="c0527-148">Teams文件内容 (，例如 Wiki 内容和文件) </span><span class="sxs-lookup"><span data-stu-id="c0527-148">Teams file content (for example, Wiki content and files)</span></span>     |<span data-ttu-id="c0527-149">SharePoint团队使用的网站。</span><span class="sxs-lookup"><span data-stu-id="c0527-149">SharePoint site used by the team.</span></span>         |
|<span data-ttu-id="c0527-150">Teams专用频道文件</span><span class="sxs-lookup"><span data-stu-id="c0527-150">Teams private channel files</span></span>     |<span data-ttu-id="c0527-151">专用SharePoint专用频道的专用站点。</span><span class="sxs-lookup"><span data-stu-id="c0527-151">Dedicated SharePoint site for private channels.</span></span>     |
|<span data-ttu-id="c0527-152">用户的私人内容</span><span class="sxs-lookup"><span data-stu-id="c0527-152">User's private content</span></span>     |<span data-ttu-id="c0527-153">用户的帐户OneDrive for Business帐户。</span><span class="sxs-lookup"><span data-stu-id="c0527-153">The user's OneDrive for Business account.</span></span>         |
|<span data-ttu-id="c0527-154">聊天中的卡片内容</span><span class="sxs-lookup"><span data-stu-id="c0527-154">Card content in chats</span></span>|<span data-ttu-id="c0527-155">用于 1：1 聊天、1：N 群组聊天以及私人频道对话或群组邮箱的用户邮箱，用于频道消息中的卡片内容。</span><span class="sxs-lookup"><span data-stu-id="c0527-155">User mailbox for 1:1 chats, 1:N group chats, and private channel conversations or group mailbox for card content in channel messages.</span></span> <span data-ttu-id="c0527-156">有关详细信息，请参阅创建电子数据展示保留中的"保留卡内容 ["部分](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)。</span><span class="sxs-lookup"><span data-stu-id="c0527-156">For more information, see the "Preserve card content" section in [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).</span></span>
||||

> [!NOTE]
> <span data-ttu-id="c0527-157">若要在专用通道中保留通信，需要将用户邮箱 ( 专用通道用户) 置于保留状态，使用电子数据展示工具进行搜索时，应在该用户的邮箱中搜索。</span><span class="sxs-lookup"><span data-stu-id="c0527-157">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="c0527-158">如前面所述，私人频道聊天存储在用户邮箱中，而不是存储在团队的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="c0527-158">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="c0527-159">若要进一步阅读本主题，了解Teams区域，Microsoft 365电子数据展示事例[：保留内容位置](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)。</span><span class="sxs-lookup"><span data-stu-id="c0527-159">If you want to read further on this topic for non-Teams areas in Microsoft 365, you should review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>
