---
title: 与 Microsoft Teams 通信符合性
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 从内部风险解决方案集（内部风险解决方案的一部分）Microsoft Teams通信符合性 (这是 M365 通信合规性功能的一) 。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf032669edc7255571e2501774ac0d0ee0df47d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121530"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="4d048-103">与 Microsoft Teams 通信符合性</span><span class="sxs-lookup"><span data-stu-id="4d048-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="4d048-104">通信合规性是一种内部风险解决方案，Microsoft 365帮助检测、捕获和操作组织中不适当的邮件，从而最大程度地降低通信风险。</span><span class="sxs-lookup"><span data-stu-id="4d048-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="4d048-105">对于Microsoft Teams，通信符合性可帮助识别以下类型的不适当内容[](/microsoft-365/compliance/communication-compliance-feature-reference)Teams频道或 1：1 和群组聊天中：</span><span class="sxs-lookup"><span data-stu-id="4d048-105">For Microsoft Teams, communication compliance helps identify the [following types](/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="4d048-106">冒犯性、亵渎和攻击性语言</span><span class="sxs-lookup"><span data-stu-id="4d048-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="4d048-107">成人、不性与成人图像</span><span class="sxs-lookup"><span data-stu-id="4d048-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="4d048-108">共享敏感信息</span><span class="sxs-lookup"><span data-stu-id="4d048-108">Sharing of sensitive information</span></span>

<span data-ttu-id="4d048-109">有关通信符合性以及如何为组织配置策略的信息，请参阅通信符合性[Microsoft 365。](/microsoft-365/compliance/communication-compliance)</span><span class="sxs-lookup"><span data-stu-id="4d048-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="4d048-110">如何在 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d048-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="4d048-111">通信合规性Microsoft Teams紧密集成，有助于将组织中通信风险降至最低。</span><span class="sxs-lookup"><span data-stu-id="4d048-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="4d048-112">配置第一个通信符合性策略后，可以主动管理Microsoft Teams警报中自动标记的不适宜的邮件和内容。</span><span class="sxs-lookup"><span data-stu-id="4d048-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="4d048-113">入门</span><span class="sxs-lookup"><span data-stu-id="4d048-113">Getting started</span></span>

<span data-ttu-id="4d048-114">Microsoft Teams通信符合性入门，首先规划和创建预定义或自定义策略，[](/microsoft-365/compliance/communication-compliance-plan)以识别 Teams 通道或 1：1 和组中不适宜的用户活动。</span><span class="sxs-lookup"><span data-stu-id="4d048-114">Getting started with communication compliance in Microsoft Teams begins with [planning](/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="4d048-115">请记住，需要在配置过程中配置一些权限[](/microsoft-365/compliance/communication-compliance-configure)和基本先决条件。</span><span class="sxs-lookup"><span data-stu-id="4d048-115">Keep in mind that you'll need to [configure](/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="4d048-116">Teams管理员可以在下列级别配置通信符合性策略：</span><span class="sxs-lookup"><span data-stu-id="4d048-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="4d048-117">**用户级别**：此级别的策略适用于单个Teams用户，也可以应用于Teams用户。</span><span class="sxs-lookup"><span data-stu-id="4d048-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="4d048-118">这些策略涵盖这些用户可以在 1：1 或群组聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="4d048-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="4d048-119">用户的聊天通信会在用户作为成员的所有Microsoft Teams自动进行监视。</span><span class="sxs-lookup"><span data-stu-id="4d048-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="4d048-120">**Teams级别**：此级别的策略适用于 Microsoft 团队频道。</span><span class="sxs-lookup"><span data-stu-id="4d048-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="4d048-121">这些策略仅涵盖在 Teams 中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="4d048-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="4d048-122">在邮件中处理不适当的Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d048-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="4d048-123">配置策略并收到针对这些邮件Microsoft Teams通信符合性警报后，组织中的符合性评审者可以针对这些邮件采取措施。</span><span class="sxs-lookup"><span data-stu-id="4d048-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="4d048-124">审阅者可以通过查看通信符合性警报和删除邮件视图中的标记邮件来帮助保护Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4d048-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![删除邮件Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="4d048-126">已删除的消息和内容将被替换为通知，供查看者说明邮件或内容已删除以及适用于删除的策略。</span><span class="sxs-lookup"><span data-stu-id="4d048-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="4d048-127">已删除邮件或内容的发送者也会收到删除状态通知，并针对与删除相关的上下文提供原始邮件内容。</span><span class="sxs-lookup"><span data-stu-id="4d048-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="4d048-128">发送方还可以查看应用于邮件删除的特定策略条件。</span><span class="sxs-lookup"><span data-stu-id="4d048-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="4d048-129">发送方看到的策略提示示例：</span><span class="sxs-lookup"><span data-stu-id="4d048-129">Example of policy tip seen by sender:</span></span>

![发件人的策略提示](./media/communication-compliance-warning-1.png)

<span data-ttu-id="4d048-131">发件人看到的策略条件通知示例：</span><span class="sxs-lookup"><span data-stu-id="4d048-131">Example of policy condition notification seen by the sender:</span></span>

![发件人的策略条件信息](./media/communication-compliance-warning-2.png)

<span data-ttu-id="4d048-133">收件人看到的策略提示示例：</span><span class="sxs-lookup"><span data-stu-id="4d048-133">Example of policy tip seen by recipient:</span></span>

![收件人的策略提示](./media/communication-compliance-warning-3.png)