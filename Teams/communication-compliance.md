---
title: 与 Microsoft 团队的通信合规性
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 了解有关通信合规性的知识合规性风险解决方案集的一部分，从 Microsoft 团队角度 (这是 M365 通信合规性功能的一部分) 。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328251"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="ebf3e-103">与 Microsoft 团队的通信合规性</span><span class="sxs-lookup"><span data-stu-id="ebf3e-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="ebf3e-104">通信合规性是 Microsoft 365 中的内幕风险解决方案，可帮助你检测、捕获和处理组织中不适当的邮件，从而帮助最大程度地减少通信风险。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="ebf3e-105">对于 Microsoft 团队，通信合规性有助于标识团队频道或1:1 和群组聊天中的 [以下类型](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) 的不当内容：</span><span class="sxs-lookup"><span data-stu-id="ebf3e-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="ebf3e-106">冒犯性、亵渎和 harassing 语言</span><span class="sxs-lookup"><span data-stu-id="ebf3e-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="ebf3e-107">成人、racy 和 gory 图像</span><span class="sxs-lookup"><span data-stu-id="ebf3e-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="ebf3e-108">敏感信息的共享</span><span class="sxs-lookup"><span data-stu-id="ebf3e-108">Sharing of sensitive information</span></span>

<span data-ttu-id="ebf3e-109">有关通信合规性以及如何为你的组织配置策略的详细信息，请参阅 [Microsoft 365 中的通信合规性](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="ebf3e-110">如何在 Microsoft 团队中使用通信合规性</span><span class="sxs-lookup"><span data-stu-id="ebf3e-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="ebf3e-111">通信合规性和 Microsoft 团队紧密集成，有助于最大程度地减少组织中的通信风险。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="ebf3e-112">配置您的第一个通信合规性策略后，您可以主动管理不合适的 Microsoft 团队邮件和自动标记为通知的内容。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="ebf3e-113">入门</span><span class="sxs-lookup"><span data-stu-id="ebf3e-113">Getting started</span></span>

<span data-ttu-id="ebf3e-114">Microsoft 团队中的通信合规性入门首先 [计划](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) 和创建预定义或自定义策略，以在团队频道或1:1 和组中标识不适当的用户活动。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="ebf3e-115">请记住，在配置过程中，你将需要 [配置](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) 某些权限和基本先决条件。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="ebf3e-116">团队管理员可以在以下级别配置通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="ebf3e-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="ebf3e-117">**用户级别**：此级别的策略适用于单个团队用户或应用于你组织中的所有团队用户。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="ebf3e-118">这些策略涵盖了这些用户可以在1:1 或群组聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="ebf3e-119">用户的聊天通信将在用户所属的所有 Microsoft 团队中自动监视。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="ebf3e-120">**团队级别**：此级别的策略适用于 Microsoft 团队频道。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="ebf3e-121">这些策略涵盖仅在团队频道中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="ebf3e-122">对 Microsoft 团队中不恰当的邮件执行操作</span><span class="sxs-lookup"><span data-stu-id="ebf3e-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="ebf3e-123">配置策略并收到 Microsoft 团队邮件的通信合规性警报后，您的组织中的合规性审阅者可以对这些消息执行操作。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="ebf3e-124">审阅者可以通过查看通信合规性警报和从 Microsoft 团队中删除已标记的邮件来帮助保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![删除团队中的邮件](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="ebf3e-126">删除的邮件和内容被替换为查看者通知，说明邮件或内容已删除，以及哪些策略适用于删除。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="ebf3e-127">已删除的消息的发件人也会收到删除状态的通知，并附带原始邮件内容与删除相关的上下文。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="ebf3e-128">发件人还可以查看适用于邮件删除的特定策略条件。</span><span class="sxs-lookup"><span data-stu-id="ebf3e-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="ebf3e-129">由发件人查看的策略提示的示例：</span><span class="sxs-lookup"><span data-stu-id="ebf3e-129">Example of policy tip seen by sender:</span></span>

![发件人的策略提示](./media/communication-compliance-warning-1.png)

<span data-ttu-id="ebf3e-131">发件人看到的策略条件通知的示例：</span><span class="sxs-lookup"><span data-stu-id="ebf3e-131">Example of policy condition notification seen by the sender:</span></span>

![发件人的策略条件信息](./media/communication-compliance-warning-2.png)

<span data-ttu-id="ebf3e-133">收件人显示的策略提示的示例：</span><span class="sxs-lookup"><span data-stu-id="ebf3e-133">Example of policy tip seen by recipient:</span></span>

![收件人的策略提示](./media/communication-compliance-warning-3.png)
