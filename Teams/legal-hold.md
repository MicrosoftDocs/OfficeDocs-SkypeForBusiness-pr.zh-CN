---
title: 将 Microsoft Teams 用户或团队置于法定保留状态
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 了解如何使用安全性和合规性中心将 Microsoft Teams 用户或团队置于法定保留状态，以及了解根据数据要求哪些内容需要法定保留。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25bd8e235be79ed805a854cbda2b4947f1c1269b
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968033"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="a32ee-103">将 Microsoft Teams 用户或团队置于法定保留状态</span><span class="sxs-lookup"><span data-stu-id="a32ee-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="a32ee-104">要将用户或团队置于法定保留状态，请导航到[安全性和合规性中心](https://go.microsoft.com/fwlink/?linkid=854628)。</span><span class="sxs-lookup"><span data-stu-id="a32ee-104">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="a32ee-105">在你创建新案例时，系统会为你提供用于将邮箱或网站置于保留状态的选项。</span><span class="sxs-lookup"><span data-stu-id="a32ee-105">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="a32ee-106">将用户置于保留状态并不会自动将组置于保留状态，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a32ee-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!NOTE]
> <span data-ttu-id="a32ee-107">我们尚不支持专用频道消息的法定保留配置。</span><span class="sxs-lookup"><span data-stu-id="a32ee-107">We don’t yet support configuration for legal hold of private channel messages.</span></span> <span data-ttu-id="a32ee-108">支持在专用频道中共享的文件的法定保留。</span><span class="sxs-lookup"><span data-stu-id="a32ee-108">Legal hold of files shared in private channels is supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a32ee-109">当用户或组处于保留状态时，将保留所有邮件副本。</span><span class="sxs-lookup"><span data-stu-id="a32ee-109">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="a32ee-110">示例：Clay 在某个频道中发布了一条消息，之后修改了该消息。</span><span class="sxs-lookup"><span data-stu-id="a32ee-110">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="a32ee-111">在保留应用场景中，会保留该消息的两个副本。</span><span class="sxs-lookup"><span data-stu-id="a32ee-111">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="a32ee-112">如果未处于法定保留状态，则只保留最新消息。</span><span class="sxs-lookup"><span data-stu-id="a32ee-112">Without Legal Hold, only the latest message is retained.</span></span>

<span data-ttu-id="a32ee-113">在下图中，有一个涉及 Clay 的调查。</span><span class="sxs-lookup"><span data-stu-id="a32ee-113">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="a32ee-114">Clay 是 Brokers-Dealers 团队的成员。</span><span class="sxs-lookup"><span data-stu-id="a32ee-114">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="a32ee-115">如果我们需要将 Clay 可能讨论了 Brokering 计划的所有地方置于法定保留状态，请确保将该团队的 SharePoint 网站以及 Clay 的 OneDrive for Business 网站添加到法定保留网站列表。</span><span class="sxs-lookup"><span data-stu-id="a32ee-115">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![“创建新保留”对话框屏幕截图。](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="a32ee-117">概括起来，使用下表了解根据数据要求需要将哪些内容置于法定保留状态：</span><span class="sxs-lookup"><span data-stu-id="a32ee-117">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="a32ee-118">应用场景</span><span class="sxs-lookup"><span data-stu-id="a32ee-118">Scenario</span></span>  |<span data-ttu-id="a32ee-119">置于保留状态的内容</span><span class="sxs-lookup"><span data-stu-id="a32ee-119">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="a32ee-120">**Microsoft Teams 私人聊天**</span><span class="sxs-lookup"><span data-stu-id="a32ee-120">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="a32ee-121">用户邮箱</span><span class="sxs-lookup"><span data-stu-id="a32ee-121">User mailbox</span></span>         |
|<span data-ttu-id="a32ee-122">**Microsoft Teams 频道聊天**</span><span class="sxs-lookup"><span data-stu-id="a32ee-122">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="a32ee-123">用于团队的组邮箱</span><span class="sxs-lookup"><span data-stu-id="a32ee-123">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="a32ee-124">**Microsoft Teams 内容（例如 Wiki、文件）**</span><span class="sxs-lookup"><span data-stu-id="a32ee-124">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="a32ee-125">团队使用的 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="a32ee-125">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="a32ee-126">**私密内容**</span><span class="sxs-lookup"><span data-stu-id="a32ee-126">**Private Content**</span></span>     |<span data-ttu-id="a32ee-127">用户的 OneDrive for Business 网站</span><span class="sxs-lookup"><span data-stu-id="a32ee-127">OneDrive for Business site of the user</span></span>         |
