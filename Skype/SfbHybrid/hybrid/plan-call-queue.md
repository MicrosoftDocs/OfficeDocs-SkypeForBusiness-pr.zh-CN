---
title: 规划云呼叫队列
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 将云自动助理与 Skype for Business Server 2019 一同使用概述。
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918738"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="55158-103">规划云呼叫队列</span><span class="sxs-lookup"><span data-stu-id="55158-103">Plan Cloud call queues</span></span>

<span data-ttu-id="55158-104">云呼叫队列是一项服务，该服务接受客户呼叫、播放问候消息，然后在搜索预先配置的代理列表以应答这些呼叫时，将这些呼叫发送到等待队列中。</span><span class="sxs-lookup"><span data-stu-id="55158-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="55158-105">可以在启用邮件的通讯组列表或安全组中定义代理集。</span><span class="sxs-lookup"><span data-stu-id="55158-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="55158-106">您的组织可以有一个或多个呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="55158-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="55158-107">呼叫队列通常与自动助理结合使用。</span><span class="sxs-lookup"><span data-stu-id="55158-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="55158-108">此外，云呼叫队列可以提供：</span><span class="sxs-lookup"><span data-stu-id="55158-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="55158-109">音乐呼叫者等待等待时显示</span><span class="sxs-lookup"><span data-stu-id="55158-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="55158-110">呼叫队列最大大小、超时和呼叫处理选项的自定义设置</span><span class="sxs-lookup"><span data-stu-id="55158-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="55158-111">每个呼叫队列分配有一个资源 **帐户 (请参阅** 在 Skype for Business Server 2019 系统上配置资源帐户 [) ，](configure-onprem-ra.md) 这些帐户将直接链接到 Microsoft Teams 管理中心中的呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="55158-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="55158-112">请参阅 ["创建云呼叫队列](/MicrosoftTeams/create-a-phone-system-call-queue) "，了解有关什么是呼叫队列以及呼叫队列存在哪些选项和功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="55158-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="55158-113">可以将多个电话号码分配给呼叫队列，但它们必须是 Microsoft 服务号码、直接路由号码或混合号码。</span><span class="sxs-lookup"><span data-stu-id="55158-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="55158-114">要求</span><span class="sxs-lookup"><span data-stu-id="55158-114">Requirements</span></span>

<span data-ttu-id="55158-115">以下要求假定你已在支持的拓扑中部署了 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="55158-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="55158-116">你的要求取决于你的方案：</span><span class="sxs-lookup"><span data-stu-id="55158-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="55158-117">有关云呼叫队列的新配置，请按照配置资源帐户中 [概述的步骤操作](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="55158-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="55158-118">你将需要联机或在 Skype for Business Server 2019 中创建资源帐户，并且可能还需要将电话号码与呼叫队列关联。</span><span class="sxs-lookup"><span data-stu-id="55158-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="55158-119">除了上述要求之外，还必须将以下要求配置为连接到 Microsoft 云呼叫队列服务：</span><span class="sxs-lookup"><span data-stu-id="55158-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="55158-120">混合连接。</span><span class="sxs-lookup"><span data-stu-id="55158-120">Hybrid connectivity.</span></span> <span data-ttu-id="55158-121">如果你已部署 Skype for Business Server，并且希望为本地用户启用云呼叫队列，则必须确保在本地环境和联机环境之间设置了混合连接。</span><span class="sxs-lookup"><span data-stu-id="55158-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="55158-122">这有时称为拆分域配置。</span><span class="sxs-lookup"><span data-stu-id="55158-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="55158-123">有关详细信息，请参阅[Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="55158-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="55158-124">如果你将电话号码分配给资源帐户，你现在可以使用免费电话系统虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="55158-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="55158-125">这将为组织级别的电话号码提供电话系统功能，并允许创建自动助理和呼叫队列功能。</span><span class="sxs-lookup"><span data-stu-id="55158-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="55158-126">为每个呼叫队列 [创建](configure-onprem-ra.md) 本地资源帐户，并分配许可证和电话号码（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="55158-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="55158-127">当你拥有一个满足你需求的稳固结构和一个可有效地指导客户的脚本时，请继续  [配置资源帐户](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="55158-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="55158-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55158-128">See Also</span></span>

[<span data-ttu-id="55158-129">配置资源帐户</span><span class="sxs-lookup"><span data-stu-id="55158-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="55158-130">允许使用电话用户界面录制自定义提示语</span><span class="sxs-lookup"><span data-stu-id="55158-130">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="55158-131">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="55158-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="55158-132">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="55158-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="55158-133">规划 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="55158-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="55158-134">配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="55158-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="55158-135">在 Microsoft Teams 中管理资源帐户</span><span class="sxs-lookup"><span data-stu-id="55158-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
