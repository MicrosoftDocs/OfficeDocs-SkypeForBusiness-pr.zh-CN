---
title: Skype for Business Server 中的新增功能
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要： 这些功能是新的业务服务器 2019 Skype 中。
ms.openlocfilehash: 411ca0705fa06d0b5720656cec2fcb3cbda50eeb
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696154"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="5df08-103">什么是 Business server 2019 Skype 中</span><span class="sxs-lookup"><span data-stu-id="5df08-103">What's in Skype for Business Server 2019</span></span> 

<span data-ttu-id="5df08-104">**摘要：** 阅读本主题可了解业务服务器 2019 Skype 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="5df08-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="5df08-105">中的业务服务器 2019 Skype 的新功能包括：</span><span class="sxs-lookup"><span data-stu-id="5df08-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="5df08-106">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="5df08-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="5df08-107">调用数据连接器</span><span class="sxs-lookup"><span data-stu-id="5df08-107">Call Data Connector</span></span>
- <span data-ttu-id="5df08-108">并行迁移</span><span class="sxs-lookup"><span data-stu-id="5df08-108">Side-by-side migration</span></span>
- <span data-ttu-id="5df08-109">向工作组的迁移</span><span class="sxs-lookup"><span data-stu-id="5df08-109">Migration to Teams</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="5df08-110">统一消息服务： 云语音邮件</span><span class="sxs-lookup"><span data-stu-id="5df08-110">Unified messaging services: Cloud Voicemail</span></span> 

<span data-ttu-id="5df08-111">Exchange UM 仍可在 Skype 的业务服务器 2019年与 Exchange 2013 或 Exchange 2016 集成 for Business 2019 Skype 时。</span><span class="sxs-lookup"><span data-stu-id="5df08-111">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="5df08-112">由于 Exchange 2019 中支持的变化，Exchange UM 集成正在注销 emphasised 支持云语音邮件和云自动助理功能。</span><span class="sxs-lookup"><span data-stu-id="5df08-112">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="5df08-113">云语音邮件使您的业务 2019年用户 #x 2014年; 它们驻留在本地或联机 & #x 2014; Microsoft 云具有相同的语音邮件服务的访问权限的所有 Skype。</span><span class="sxs-lookup"><span data-stu-id="5df08-113">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="5df08-114">云语音邮件的本地和联机用户提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="5df08-114">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="5df08-115">使用适用于业务联机、 团队或 Outlook 客户端 Skype 其 Exchange 邮箱中的语音邮件访问</span><span class="sxs-lookup"><span data-stu-id="5df08-115">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span> 
- <span data-ttu-id="5df08-116">能够使用基于 web 的门户管理其语音邮件选项</span><span class="sxs-lookup"><span data-stu-id="5df08-116">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="5df08-117">有关详细信息，请参阅[规划云语音邮件服务](hybrid/plan-cloud-voicemail.md)和[Plan for Business Server 和 Exchange Server 迁移的 Skype](hybrid/plan-um-migration.md) 。</span><span class="sxs-lookup"><span data-stu-id="5df08-117">See [Plan Cloud Voicemail service](hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="5df08-118">监控呼叫： 调用数据连接器</span><span class="sxs-lookup"><span data-stu-id="5df08-118">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="5df08-119">调用数据连接器可大大简化呼叫监视混合环境中，因为您不再需要不同的内部部署和联机工具集用于监视所有您用户的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="5df08-119">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="5df08-120">驻留在本地或联机用户是否，您可以选择要查看为整个组织的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="5df08-120">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="5df08-121">与调用数据连接器，您可以使用一个工具集执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5df08-121">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="5df08-122">跨 Microsoft 团队、 业务 online Skype 和 Skype 业务 server 监视您的用户体验。</span><span class="sxs-lookup"><span data-stu-id="5df08-122">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="5df08-123">查看和解决问题跨网络</span><span class="sxs-lookup"><span data-stu-id="5df08-123">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="5df08-124">为呼叫 Analytics 分配支持人员和管理员角色，以便可以为帮助台工作者可以查看和解决其责任范围提供强大功能。</span><span class="sxs-lookup"><span data-stu-id="5df08-124">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="5df08-125">有关详细信息，请参阅[规划呼叫数据连接器](hybrid/plan-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="5df08-125">See [Plan Call Data Connector](hybrid/plan-call-data-connector.md) for more information.</span></span>
  


## <a name="installation-and-upgrade-side-by-side-migration"></a><span data-ttu-id="5df08-126">安装和升级:-并行迁移</span><span class="sxs-lookup"><span data-stu-id="5df08-126">Installation and Upgrade: Side-by-side migration</span></span>

<span data-ttu-id="5df08-127">在-并行迁移中，您部署的业务服务器 2019年一起运行的是以前版本 (业务服务器 2015年或 Lync Server 2013 的 Skype) 的相应服务器运行 Skype 的新服务器，然后转接到新服务器的操作。</span><span class="sxs-lookup"><span data-stu-id="5df08-127">In a side-by-side migration, you deploy a new server running Skype for Business Server 2019 alongside a corresponding server that is running a previous version (Skype for Business Server 2015 or Lync Server 2013), and then transfer operations to the new server.</span></span> <span data-ttu-id="5df08-128">如果需要回滚到以前的版本，您只需要只要将操作切换回原始服务器。</span><span class="sxs-lookup"><span data-stu-id="5df08-128">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> 

<span data-ttu-id="5df08-129">完整详细信息，请参阅[Migration to Business Server 2019 的 Skype](migration/migration-to-skype-for-business-server-2019.md)。</span><span class="sxs-lookup"><span data-stu-id="5df08-129">For complete details, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md).</span></span>

### <a name="see-also"></a><span data-ttu-id="5df08-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5df08-130">See also</span></span>

[<span data-ttu-id="5df08-131">什么被弃用从 Skype 业务服务器 2019</span><span class="sxs-lookup"><span data-stu-id="5df08-131">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)