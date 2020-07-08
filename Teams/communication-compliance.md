---
title: Microsoft 团队的通信合规性
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 了解有关通信合规性的信息，即 "预览体验成员" 解决方案集的一部分，从 Microsoft 团队的角度来看，这是 M365 通信合规性功能的一部分。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf97f4adc33b0855e986cf2baed54f69de91f4f0
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077688"
---
# <a name="communication-compliance-for-microsoft-teams"></a><span data-ttu-id="415f8-103">Microsoft 团队的通信合规性</span><span class="sxs-lookup"><span data-stu-id="415f8-103">Communication compliance for Microsoft Teams</span></span>

<span data-ttu-id="415f8-104">通信合规性是 Microsoft 365 中新的预览体验计划解决方案集的一部分，可帮助你对组织中的不当邮件检测、捕获和采取补救措施，从而减少通信风险。</span><span class="sxs-lookup"><span data-stu-id="415f8-104">Communication compliance is part of the new insider risk solution set in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="415f8-105">它有助于识别团队频道或1:1 和群组聊天中的攻击性语言和反骚扰。</span><span class="sxs-lookup"><span data-stu-id="415f8-105">It helps in identifying Offensive language and anti-harassment in Team Channels or 1:1 and Group chats.</span></span> <span data-ttu-id="415f8-106">您还可以设置策略以查看是否有任何敏感信息被共享为团队频道或1:1 和群组聊天的一部分。</span><span class="sxs-lookup"><span data-stu-id="415f8-106">You can also set policies to see if any Sensitive information is being shared as part of Team channels or 1:1 and Group chats.</span></span> <span data-ttu-id="415f8-107">有关不同类型的策略以及如何设置[M365 文章](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)的详细信息，请参阅 ""。</span><span class="sxs-lookup"><span data-stu-id="415f8-107">For more information on different types of policies and how to set up refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-teams"></a><span data-ttu-id="415f8-108">如何使用团队中的通信合规性</span><span class="sxs-lookup"><span data-stu-id="415f8-108">How to use communication compliance in Teams</span></span>

### <a name="identify-inappropriate-messages"></a><span data-ttu-id="415f8-109">标识不适当的邮件</span><span class="sxs-lookup"><span data-stu-id="415f8-109">Identify inappropriate messages</span></span>

<span data-ttu-id="415f8-110">如果要标识在 Microsoft 团队中发送的任何消息（1:1、群组聊天或频道对话）包含冒犯性的语言或反骚扰，则可以启用策略来标识此邮件，并且审阅者可以查看邮件并执行必要的步骤，如发送培训资料或升级到适当的机构。</span><span class="sxs-lookup"><span data-stu-id="415f8-110">If you want to identify any messages that are sent in Microsoft Teams (1:1, Group Chats or Channel conversations) contain Offensive Language or anti-harassment, you can enable policies to identify this and the reviewer can look into the messages and take necessary steps like sending training material or escalate to the right authorities.</span></span>

### <a name="identify-sensitive-or-regulatory-information"></a><span data-ttu-id="415f8-111">标识敏感或法规信息</span><span class="sxs-lookup"><span data-stu-id="415f8-111">Identify sensitive or Regulatory information</span></span>

<span data-ttu-id="415f8-112">如果要扫描 Microsoft 团队中发送的邮件（1:1、群组聊天或频道对话）以了解敏感信息或法规类型，可以选择支持预定义的敏感或法规类型的策略。</span><span class="sxs-lookup"><span data-stu-id="415f8-112">If you want to scan messages sent in Microsoft Teams (1:1, Group Chats or Channel conversations) for sensitive information or regulatory types, you can choose policies that support predefined sensitive or regulatory types.</span></span>

> [!NOTE]
> <span data-ttu-id="415f8-113">通信合规性不支持专用通道。</span><span class="sxs-lookup"><span data-stu-id="415f8-113">Private channels are not supported by communication compliance.</span></span>

### <a name="custom-policy"></a><span data-ttu-id="415f8-114">自定义策略</span><span class="sxs-lookup"><span data-stu-id="415f8-114">Custom Policy</span></span>

<span data-ttu-id="415f8-115">使用此模板配置特定通信通道、单个检测条件以及你的组织中要监视和查看的内容量。</span><span class="sxs-lookup"><span data-stu-id="415f8-115">Use this template to configure specific communication channels, individual detection conditions, and the amount of content to monitor and review in your organization.</span></span>

### <a name="custom-trainable-classifier"></a><span data-ttu-id="415f8-116">自定义 Trainable 分类器</span><span class="sxs-lookup"><span data-stu-id="415f8-116">Custom Trainable classifier</span></span>

<span data-ttu-id="415f8-117">当一个框中的某个分类器不能满足您的需要时，请使用 trainable 分类器。</span><span class="sxs-lookup"><span data-stu-id="415f8-117">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="415f8-118">Microsoft 365 分类器是一种工具，可通过提供示例来训练以识别各种类型的内容。</span><span class="sxs-lookup"><span data-stu-id="415f8-118">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="415f8-119">培训分类器首先需要为其提供人工挑选的示例，并正确匹配该类别。</span><span class="sxs-lookup"><span data-stu-id="415f8-119">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="415f8-120">然后，在处理这些示例之后，你可以通过给它混合使用正和负样本来测试预测。</span><span class="sxs-lookup"><span data-stu-id="415f8-120">Then, after it has processed those samples, you test the predictions by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="415f8-121">有关详细信息，请参阅[M365 文章](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier)了解有关本主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="415f8-121">To Lean more about this refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) for more on this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="415f8-122">通信合规性现在支持 Exchange 混合部署。</span><span class="sxs-lookup"><span data-stu-id="415f8-122">Communication compliance now supports Exchange hybrid deployments.</span></span>

<span data-ttu-id="415f8-123">通信合规性支持与策略匹配的任何消息的对话历史记录。</span><span class="sxs-lookup"><span data-stu-id="415f8-123">Communication compliance supports conversation history for any messages that match the polices.</span></span> <span data-ttu-id="415f8-124">这提供了调查管理员的上下文。</span><span class="sxs-lookup"><span data-stu-id="415f8-124">This provides context to the investigating admin.</span></span>

:::image type="content" source="media/communication-compliance-1.png" alt-text="用于在 Microsoft 团队中进行通信合规性的屏幕。":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a><span data-ttu-id="415f8-126">可在团队中应用通信策略的位置</span><span class="sxs-lookup"><span data-stu-id="415f8-126">Where communication policies can be applied in Teams</span></span>

<span data-ttu-id="415f8-127">可以为在以下级别的团队中发送的邮件设置通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="415f8-127">Communication compliance policies can be setup for messages sent in Teams at the following levels:</span></span>

- <span data-ttu-id="415f8-128">用户级别：管理员可以在单个用户级别设置策略，或将策略应用到租户上的所有用户。</span><span class="sxs-lookup"><span data-stu-id="415f8-128">User level : An admin can set up policies at an individual user level or apply it to all the users on the tenant.</span></span> <span data-ttu-id="415f8-129">这仅涵盖用户在1:1 或群组聊天中发送的消息。</span><span class="sxs-lookup"><span data-stu-id="415f8-129">This will only covers messages that a user sent in 1:1 or Group chats.</span></span>
- <span data-ttu-id="415f8-130">团队级别：管理员还可以设置团队的策略。</span><span class="sxs-lookup"><span data-stu-id="415f8-130">Team Level: An admin can also set up policies on a team.</span></span> <span data-ttu-id="415f8-131">这将涵盖该团队频道中发送的所有消息（不支持专用信道消息）。</span><span class="sxs-lookup"><span data-stu-id="415f8-131">This covers all the messages sent in the channel in that team (Private channel messages are not supported).</span></span>
