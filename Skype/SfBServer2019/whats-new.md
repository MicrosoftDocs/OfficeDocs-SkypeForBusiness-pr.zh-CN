---
title: Skype for Business Server 2019 中的新增功能 |提供
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：这些功能是 Skype for Business Server 2019 中的新功能。
ms.openlocfilehash: 86a8ce580a8aafcfb487a4b0cf839cd001dace8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129395"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="fac3e-103">Skype for Business Server 2019 中的内容</span><span class="sxs-lookup"><span data-stu-id="fac3e-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="fac3e-104">**摘要：** 阅读本主题，了解 Skype for Business Server 2019 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="fac3e-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="fac3e-105">Skype for Business Server 2019 中的新功能包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="fac3e-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="fac3e-106">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="fac3e-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="fac3e-107">呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="fac3e-107">Call Data Connector</span></span>
- <span data-ttu-id="fac3e-108">并列迁移</span><span class="sxs-lookup"><span data-stu-id="fac3e-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="fac3e-109">统一消息服务：云语音邮件</span><span class="sxs-lookup"><span data-stu-id="fac3e-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="fac3e-110">将 Skype for Business 2019 与 Exchange 2013 或 Exchange 2016 集成时，Exchange UM 在 Skype for business Server 2019 中仍可用。</span><span class="sxs-lookup"><span data-stu-id="fac3e-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="fac3e-111">由于 Exchange 2019 中支持的更改，Exchange UM 集成在取代云语音邮件和云自动助理功能方面进行了强调。</span><span class="sxs-lookup"><span data-stu-id="fac3e-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="fac3e-112">云语音邮件支持所有 Skype for Business 2019 用户&#x2014;他们是否驻留在本地或联机&#x2014;中，以便能够访问 Microsoft 云中的同一语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="fac3e-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="fac3e-113">云语音邮件为您的内部部署用户和联机用户提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="fac3e-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="fac3e-114">使用 Skype for Business Online、团队或 Outlook 客户端访问其 Exchange 邮箱中的语音邮件</span><span class="sxs-lookup"><span data-stu-id="fac3e-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="fac3e-115">能够使用基于 web 的门户管理其语音邮件选项</span><span class="sxs-lookup"><span data-stu-id="fac3e-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="fac3e-116">有关详细信息，请参阅[规划云语音邮件服务](../sfbhybrid/hybrid/plan-cloud-voicemail.md)并[规划 Skype for Business Server 和 Exchange Server 迁移](../sfbhybrid/hybrid/plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="fac3e-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="fac3e-117">呼叫监控：呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="fac3e-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="fac3e-118">呼叫数据连接器极大地简化了混合环境中的呼叫监视，因为您不再需要使用不同的内部部署和联机工具来监视所有用户的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="fac3e-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="fac3e-119">无论您的用户是驻留在本地还是联机，您都可以选择查看整个组织的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="fac3e-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="fac3e-120">使用 "呼叫数据连接器"，您可以使用单个工具集执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="fac3e-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="fac3e-121">在 Microsoft 团队、Skype for Business Online 和 Skype for Business Server 中监视你的用户体验。</span><span class="sxs-lookup"><span data-stu-id="fac3e-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="fac3e-122">查看整个网络中的问题并进行故障排除</span><span class="sxs-lookup"><span data-stu-id="fac3e-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="fac3e-123">为呼叫分析分配帮助台和管理员角色，以便让帮助台工作人员能够查看和解决他们的责任领域。</span><span class="sxs-lookup"><span data-stu-id="fac3e-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="fac3e-124">有关详细信息，请参阅[Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) 。</span><span class="sxs-lookup"><span data-stu-id="fac3e-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="fac3e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fac3e-125">See also</span></span>

[<span data-ttu-id="fac3e-126">Skype for Business Server 2019 中弃用的内容</span><span class="sxs-lookup"><span data-stu-id="fac3e-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
