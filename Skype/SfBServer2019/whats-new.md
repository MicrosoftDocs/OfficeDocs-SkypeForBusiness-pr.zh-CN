---
title: Skype for Business Server 2019 中的新增功能 |功能
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：这些功能是 Skype for Business Server 2019 中的新增功能。
ms.openlocfilehash: 6db5ea6589a56f696f233854372fc95d6064fed7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799412"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="cfe03-103">Skype for Business Server 2019 中的内容</span><span class="sxs-lookup"><span data-stu-id="cfe03-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="cfe03-104">**摘要：** 阅读本主题，了解 Skype for Business Server 2019 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="cfe03-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="cfe03-105">Skype for Business Server 2019 中的新增功能包括以下几项：</span><span class="sxs-lookup"><span data-stu-id="cfe03-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="cfe03-106">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="cfe03-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="cfe03-107">呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="cfe03-107">Call Data Connector</span></span>
- <span data-ttu-id="cfe03-108">并行迁移</span><span class="sxs-lookup"><span data-stu-id="cfe03-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="cfe03-109">统一消息服务：云语音邮件</span><span class="sxs-lookup"><span data-stu-id="cfe03-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="cfe03-110">将 Skype for business 2019 与 Exchange 2013 或 Exchange 2016 集成时，exchange UM 将在 Skype for business Server 2019 中保持可用。</span><span class="sxs-lookup"><span data-stu-id="cfe03-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="cfe03-111">由于 Exchange 2019 中的支持的更改，Exchange UM 集成已被取消重点，取而代之的是云语音邮件和云自动助理功能。</span><span class="sxs-lookup"><span data-stu-id="cfe03-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="cfe03-112">云语音邮件支持所有 Skype for Business 2019 用户&#x2014;他们是托管在本地还是联机&#x2014;才能访问 Microsoft 云中的同一语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="cfe03-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="cfe03-113">云语音邮件为你的本地用户和联机用户提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="cfe03-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="cfe03-114">通过使用 Skype for Business Online、团队或 Outlook 客户端访问其 Exchange 邮箱中的语音邮件</span><span class="sxs-lookup"><span data-stu-id="cfe03-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="cfe03-115">能够使用基于 web 的门户管理其语音邮件选项</span><span class="sxs-lookup"><span data-stu-id="cfe03-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="cfe03-116">有关详细信息，请参阅[规划云语音邮件服务](../sfbhybrid/hybrid/plan-cloud-voicemail.md)和[规划 Skype for Business 服务器和 Exchange Server 迁移](../sfbhybrid/hybrid/plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="cfe03-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="cfe03-117">呼叫监视：呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="cfe03-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="cfe03-118">呼叫数据连接器极大地简化了混合环境中的呼叫监视，因为不再需要使用不同的本地和联机工具集来监视所有用户的通话质量。</span><span class="sxs-lookup"><span data-stu-id="cfe03-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="cfe03-119">无论您的用户是在本地还是在网上托管，您都可以选择查看整个组织的通话质量。</span><span class="sxs-lookup"><span data-stu-id="cfe03-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="cfe03-120">使用 "调用数据" 连接器，您可以使用单个工具集执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="cfe03-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="cfe03-121">跨 Microsoft 团队、Skype for business Online 和 Skype for business 服务器监控你的用户体验。</span><span class="sxs-lookup"><span data-stu-id="cfe03-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="cfe03-122">查看和解决网络上的问题</span><span class="sxs-lookup"><span data-stu-id="cfe03-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="cfe03-123">为 "呼叫分析" 分配帮助台和管理员角色，以便让帮助台工作人员能够查看和解决他们的责任领域。</span><span class="sxs-lookup"><span data-stu-id="cfe03-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="cfe03-124">有关详细信息，请参阅[计划通话数据连接器](../sfbhybrid/hybrid/plan-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="cfe03-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="cfe03-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfe03-125">See also</span></span>

[<span data-ttu-id="cfe03-126">Skype for Business Server 2019 中的弃用内容</span><span class="sxs-lookup"><span data-stu-id="cfe03-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
