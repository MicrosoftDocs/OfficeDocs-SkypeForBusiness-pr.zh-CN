---
title: 规划云呼叫队列
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 使用与 Skype for business Server 2019 的云自动助理的概述。
ms.openlocfilehash: bcb1f14ed9dfc3471b146a318a97700c362f115c
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160467"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="205eb-103">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="205eb-103">Plan Cloud call queues</span></span>

<span data-ttu-id="205eb-104">云呼叫队列是一项服务, 它可以接受客户呼叫、播放问候语邮件, 然后将这些呼叫放在等待队列中, 同时搜索预先配置的代理列表以应答这些呼叫。</span><span class="sxs-lookup"><span data-stu-id="205eb-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="205eb-105">您可以在启用邮件的通讯组列表或安全组中定义一组代理。</span><span class="sxs-lookup"><span data-stu-id="205eb-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="205eb-106">您的组织可以有一个或多个呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="205eb-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="205eb-107">呼叫队列通常与自动助理结合使用。</span><span class="sxs-lookup"><span data-stu-id="205eb-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="205eb-108">此外, 云呼叫队列可以提供:</span><span class="sxs-lookup"><span data-stu-id="205eb-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="205eb-109">呼叫者等待保留时的音乐</span><span class="sxs-lookup"><span data-stu-id="205eb-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="205eb-110">呼叫队列的自定义设置最大大小、超时和呼叫处理选项</span><span class="sxs-lookup"><span data-stu-id="205eb-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="205eb-111">将在 Skype for Business Server 2019 系统上为每个呼叫队列分配一个**资源帐户**(请参阅[配置资源帐户](configure-onprem-ra.md)), 该帐户将直接链接到 Microsoft 团队管理中心中的呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="205eb-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="205eb-112">请参阅[创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue), 了解有关呼叫队列的内容以及呼叫队列中存在哪些选项和功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="205eb-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="205eb-113">可以将多个电话号码分配给呼叫队列, 但这些号码必须是 Microsoft 服务号码或混合号码。</span><span class="sxs-lookup"><span data-stu-id="205eb-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="205eb-114">要求</span><span class="sxs-lookup"><span data-stu-id="205eb-114">Requirements</span></span>

<span data-ttu-id="205eb-115">以下要求假定您已在受支持的拓扑中部署了 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="205eb-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="205eb-116">您的要求取决于您的方案:</span><span class="sxs-lookup"><span data-stu-id="205eb-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="205eb-117">对于云呼叫队列的新配置, 请执行[配置资源帐户](configure-onprem-ra.md)中所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="205eb-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="205eb-118">你将需要联机或在 Skype for Business Server 2019 中创建资源帐户, 并且你可能还需要将电话号码与呼叫队列相关联。</span><span class="sxs-lookup"><span data-stu-id="205eb-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="205eb-119">除了上述要求之外, 还必须配置以下要求以连接到 Microsoft 云呼叫队列服务:</span><span class="sxs-lookup"><span data-stu-id="205eb-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="205eb-120">混合连接性。</span><span class="sxs-lookup"><span data-stu-id="205eb-120">Hybrid connectivity.</span></span> <span data-ttu-id="205eb-121">如果已部署 Skype for Business Server, 并且要为本地用户启用云呼叫队列, 则必须确保在本地和联机环境之间设置混合连接。</span><span class="sxs-lookup"><span data-stu-id="205eb-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="205eb-122">这有时称为拆分域配置。</span><span class="sxs-lookup"><span data-stu-id="205eb-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="205eb-123">有关详细信息, 请参阅[规划 skype For Business server 和 office 365 之间的混合连接](plan-hybrid-connectivity.md)和[配置 Skype for Business server 和 office 365 之间的混合连接](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="205eb-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="205eb-124">如果要将电话号码分配给资源帐户, 现在可以使用免费电话系统虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="205eb-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="205eb-125">这样可以在组织级别为电话号码提供电话系统功能, 并允许您创建自动助理和呼叫队列功能。</span><span class="sxs-lookup"><span data-stu-id="205eb-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="205eb-126">为每个呼叫队列创建本地[资源帐户](configure-onprem-ra.md), 并根据需要分配许可证和电话号码。</span><span class="sxs-lookup"><span data-stu-id="205eb-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="205eb-127">其他规划资源</span><span class="sxs-lookup"><span data-stu-id="205eb-127">Additional planning resources</span></span>

<span data-ttu-id="205eb-128">标题为 "[小型企业" 的教程示例-设置自动助理, 以](/microsoftteams/tutorial-org-aa)收集有关用户需求的信息、规划自动助理和用户的结构 (以及可能的呼叫队列)、编写菜单提示以及在联机管理中心实施计划。</span><span class="sxs-lookup"><span data-stu-id="205eb-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="205eb-129">查看教程并使用练习。 t 创建计划。</span><span class="sxs-lookup"><span data-stu-id="205eb-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="205eb-130">如果您具有满足需求的实体结构和指导客户有效的脚本, 请继续[配置资源帐户](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="205eb-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="205eb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="205eb-131">See Also</span></span>

[<span data-ttu-id="205eb-132">配置资源帐户</span><span class="sxs-lookup"><span data-stu-id="205eb-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="205eb-133">允许使用电话用户界面录制自定义提示语</span><span class="sxs-lookup"><span data-stu-id="205eb-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="205eb-134">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="205eb-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="205eb-135">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="205eb-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="205eb-136">规划 Skype for Business Server 和 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="205eb-136">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="205eb-137">配置 Skype for Business Server 和 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="205eb-137">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="205eb-138">在 Microsoft 团队中管理资源帐户</span><span class="sxs-lookup"><span data-stu-id="205eb-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
