---
title: Skype for Business Server 2019 中的新增功能 |功能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：这些功能是 Skype for Business Server 2019 中的新增功能。
ms.openlocfilehash: f20abfa7d48717052c8ee0144e143a21b168286d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812582"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="45a2c-103">Skype for Business Server 2019 中的功能</span><span class="sxs-lookup"><span data-stu-id="45a2c-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="45a2c-104">**摘要：** 阅读本主题，了解 Skype for Business Server 2019 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="45a2c-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="45a2c-105">Skype for Business Server 2019 中的新功能包括：</span><span class="sxs-lookup"><span data-stu-id="45a2c-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="45a2c-106">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="45a2c-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="45a2c-107">呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="45a2c-107">Call Data Connector</span></span>
- <span data-ttu-id="45a2c-108">并列迁移</span><span class="sxs-lookup"><span data-stu-id="45a2c-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="45a2c-109">统一消息服务：云语音邮件</span><span class="sxs-lookup"><span data-stu-id="45a2c-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="45a2c-110">将 Skype for Business 2019 与 Exchange 2013 或 Exchange 2016 集成后，Exchange UM 在 Skype for Business Server 2019 中仍可用。</span><span class="sxs-lookup"><span data-stu-id="45a2c-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="45a2c-111">由于 Exchange 2019 中支持的变化，Exchange UM 集成的重要性正在减少，以支持云语音邮件和云自动助理功能。</span><span class="sxs-lookup"><span data-stu-id="45a2c-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="45a2c-112">云语音邮件使所有 Skype for Business 2019 用户&#x2014;无论他们位于本地还是联机&#x2014;，都有权访问 Microsoft 云中的同一语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="45a2c-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="45a2c-113">云语音邮件为本地用户和在线用户提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="45a2c-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="45a2c-114">使用 Skype for Business Online、Teams 或 Outlook 客户端访问 Exchange 邮箱中的语音邮件</span><span class="sxs-lookup"><span data-stu-id="45a2c-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="45a2c-115">能够使用基于 Web 的门户管理其语音邮件选项</span><span class="sxs-lookup"><span data-stu-id="45a2c-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="45a2c-116">有关详细信息 [，请参阅规划云语音邮件](../sfbhybrid/hybrid/plan-cloud-voicemail.md) 服务和 [Skype for Business Server Exchange Server迁移](../sfbhybrid/hybrid/plan-um-migration.md) 。</span><span class="sxs-lookup"><span data-stu-id="45a2c-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="45a2c-117">呼叫监控：呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="45a2c-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="45a2c-118">呼叫数据连接器大大简化了混合环境中呼叫监控，因为不再需要使用不同的内部部署和联机工具集来监视所有用户的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="45a2c-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="45a2c-119">无论是本地用户还是联机用户，都可以选择联机查看整个组织的通话质量。</span><span class="sxs-lookup"><span data-stu-id="45a2c-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="45a2c-120">使用呼叫数据连接器，可以使用单个工具集执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="45a2c-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="45a2c-121">监视 Microsoft Teams、Skype for Business Online 和 Skype for Business Server 中的用户体验。</span><span class="sxs-lookup"><span data-stu-id="45a2c-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="45a2c-122">查看并排查整个网络问题</span><span class="sxs-lookup"><span data-stu-id="45a2c-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="45a2c-123">为呼叫分析分配支持人员角色和管理员角色，以便技术支持工作人员可以查看其职责区域并排除其故障。</span><span class="sxs-lookup"><span data-stu-id="45a2c-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="45a2c-124">有关详细信息 [，请参阅"规划呼叫数据](../sfbhybrid/hybrid/plan-call-data-connector.md) 连接器"。</span><span class="sxs-lookup"><span data-stu-id="45a2c-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="45a2c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45a2c-125">See also</span></span>

[<span data-ttu-id="45a2c-126">Skype for Business Server 2019 弃用内容</span><span class="sxs-lookup"><span data-stu-id="45a2c-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
