---
title: 规划云语音邮件服务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 本文介绍优点、 规划注意事项以及用于实现 Microsoft 云语音邮件服务的要求。 有关配置云语音邮件的信息，请参阅配置云语音邮件。
ms.openlocfilehash: e307ddcb5159e51ebe26e6a5bee10f9b2ee716e9
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2018
ms.locfileid: "25030621"
---
# <a name="plan-cloud-voicemail-service"></a><span data-ttu-id="b1e91-104">规划云语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="b1e91-104">Plan Cloud Voicemail service</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="b1e91-105">概述</span><span class="sxs-lookup"><span data-stu-id="b1e91-105">Overview</span></span> 

<span data-ttu-id="b1e91-106">本文介绍优点、 规划注意事项以及用于实现 Microsoft 云语音邮件服务的要求。</span><span class="sxs-lookup"><span data-stu-id="b1e91-106">This article describes benefits, planning considerations, and requirements for implementing the Microsoft Cloud Voicemail service.</span></span> <span data-ttu-id="b1e91-107">有关配置云语音邮件的信息，请参阅[配置云语音邮件服务](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e91-107">For information on configuring Cloud Voicemail, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="b1e91-108">云语音邮件将取代的 Exchange 统一消息 (UM) 中提供语音消息通讯功能的 Skype 的业务 2019年语音用户拥有在 Exchange Server 2019 或 Exchange Online 邮箱。</span><span class="sxs-lookup"><span data-stu-id="b1e91-108">Cloud Voicemail takes the place of Exchange Unified Messaging (UM) in providing voice messaging functionality for Skype for Business 2019 voice users who have mailboxes on Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="b1e91-109">云语音邮件的本地和联机用户提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="b1e91-109">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="b1e91-110">语音邮件应答和处理功能提供增强的语音转录</span><span class="sxs-lookup"><span data-stu-id="b1e91-110">Voicemail answering and deposit functionality with enhanced speech transcription</span></span>

- <span data-ttu-id="b1e91-111">使用 Skype 业务联机或 Outlook 客户端的用户的 Exchange 邮箱中的语音邮件访问</span><span class="sxs-lookup"><span data-stu-id="b1e91-111">Access to voicemail in the user's Exchange mailbox by using the Skype for Business Online or Outlook clients</span></span> 

- <span data-ttu-id="b1e91-112">能够使用基于 web 的 Office 365 门户管理语音邮件选项</span><span class="sxs-lookup"><span data-stu-id="b1e91-112">The ability to use the Office 365 web-based portal to manage voicemail options</span></span>

- <span data-ttu-id="b1e91-113">对 Exchange 邮箱在本地或云中的支持</span><span class="sxs-lookup"><span data-stu-id="b1e91-113">Support for Exchange mailboxes on premises or in the cloud</span></span>

- <span data-ttu-id="b1e91-114">利用从 Exchange Online 统一消息的现有用户问候语</span><span class="sxs-lookup"><span data-stu-id="b1e91-114">Leveraging of existing user greetings from Exchange Online Unified Messaging</span></span>

<span data-ttu-id="b1e91-115">有关功能比较的详细信息，请参阅[Plan for Business Server 和 Exchange Server 迁移的 Skype](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e91-115">For more information about feature comparison, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span> 

<span data-ttu-id="b1e91-116">业务服务器 2019年的 Skype 继续使用 Exchange UM 用户为邮箱位于早期版本的 Exchange Server 2013 (2016年）。</span><span class="sxs-lookup"><span data-stu-id="b1e91-116">Skype for Business Server 2019 continues to use Exchange UM for users whose mailboxes are on previous versions of Exchange Server (2013, 2016).</span></span>  <span data-ttu-id="b1e91-117">了解基于 Exchange Server 和 Skype 业务服务器将使用语音邮件解决方案版本是规划迁移到任一 Skype 业务服务器 2019年或 Exchange Server 2019 的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="b1e91-117">Understanding which voicemail solution will be used based on the Exchange Server and Skype for Business Server version is an important part of planning for migration to either Skype for Business Server 2019 or Exchange Server 2019.</span></span> <span data-ttu-id="b1e91-118">有关迁移和互操作性的详细信息，请参阅[Plan for Business Server 和 Exchange Server 迁移的 Skype](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e91-118">For more information about migration and interoperability, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span> 

<span data-ttu-id="b1e91-119">与云语音邮件，因为是大大简化管理任务：</span><span class="sxs-lookup"><span data-stu-id="b1e91-119">With Cloud Voicemail, your administration tasks are greatly simplified because:</span></span>

- <span data-ttu-id="b1e91-120">没有需要配置 Exchange UM 角色。</span><span class="sxs-lookup"><span data-stu-id="b1e91-120">There is no need to configure the Exchange UM role.</span></span>
- <span data-ttu-id="b1e91-121">云语音邮件的安装任务更加简单。</span><span class="sxs-lookup"><span data-stu-id="b1e91-121">The setup tasks for Cloud Voicemail are simpler.</span></span>
- <span data-ttu-id="b1e91-122">直接在云中，了传递到语音邮件功能的更新，以便您的用户始终在累积更新 （累积） 有权访问的最新功能和更新较少的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="b1e91-122">Updates to voicemail functionality are delivered directly in the cloud, so your users always have access to the latest features and updates with less dependency on Cumulative Updates (CUs).</span></span>
- <span data-ttu-id="b1e91-123">您具有一组相同的内部部署和联机 Exchange 邮箱的控件。</span><span class="sxs-lookup"><span data-stu-id="b1e91-123">You have the same set of controls for both on-premises and online Exchange mailboxes.</span></span> <span data-ttu-id="b1e91-124">有关这些控件的详细信息，请参阅[设置电话系统的语音邮件](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="b1e91-124">For more information on these controls, see [Set up Phone System voicemail](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).</span></span>

<span data-ttu-id="b1e91-125">下图显示了在混合部署中的云语音邮件：</span><span class="sxs-lookup"><span data-stu-id="b1e91-125">The following diagram shows Cloud Voicemail in a hybrid deployment:</span></span>


![SfB 云语音邮件](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

<span data-ttu-id="b1e91-127">未应答的呼叫处理，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1e91-127">Unanswered calls are handled as follows:</span></span>  

1. <span data-ttu-id="b1e91-128">为用户驻留在 Skype 的本地业务 2019年，未应答的呼叫发送通过内部部署 Skype 业务服务器到 online 云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="b1e91-128">For users homed in Skype for Business 2019 on premises, unanswered calls are sent by the on-premises Skype for Business Server to the online Cloud Voicemail service.</span></span> 
2. <span data-ttu-id="b1e91-129">该服务处理语音邮件，包括转录。</span><span class="sxs-lookup"><span data-stu-id="b1e91-129">The service processes the voicemail, including transcription.</span></span>
3. <span data-ttu-id="b1e91-130">该服务然后放语音邮件的用户的 Exchange 邮箱中邮箱是否在本地或联机。</span><span class="sxs-lookup"><span data-stu-id="b1e91-130">The service then deposits the voicemail in the Exchange mailbox of the user, whether the mailbox is on-premises or online.</span></span>  
4. <span data-ttu-id="b1e91-131">用户可以从以下任意业务或 Outlook 客户端其 Skype 访问他们的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b1e91-131">Users can access their voicemail from either their Skype for Business or Outlook client.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1e91-132">要求</span><span class="sxs-lookup"><span data-stu-id="b1e91-132">Requirements</span></span>

<span data-ttu-id="b1e91-133">以下要求假定您已有 Skype 业务服务器部署中支持的拓扑。</span><span class="sxs-lookup"><span data-stu-id="b1e91-133">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="b1e91-134">您的要求取决于您的方案：</span><span class="sxs-lookup"><span data-stu-id="b1e91-134">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="b1e91-135">如果您已使用 Exchange UM online 您升级到业务 2019年的 Skype，您将需要修改托管语音邮件策略，请确认已正确设置宿主提供商。</span><span class="sxs-lookup"><span data-stu-id="b1e91-135">If you are already using Exchange UM online and you upgrade to Skype for Business 2019, you will need to modify your hosted voicemail policy and verify that your hosting providers are set correctly.</span></span> <span data-ttu-id="b1e91-136">有关详细信息，请参阅[配置云语音邮件服务](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e91-136">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="b1e91-137">如果您在本地，Exchange UM 使用或具有联机和本地 Exchange UM 使用的用户的组合，您将需要修改您的托管语音邮件策略和宿主提供商。</span><span class="sxs-lookup"><span data-stu-id="b1e91-137">If you are using Exchange UM on premises, or you have a mix of users using Exchange UM online and on premises, you will need modify both your hosted voicemail policy and hosting provider.</span></span>  <span data-ttu-id="b1e91-138">有关详细信息，请参阅[配置云语音邮件服务](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e91-138">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="b1e91-139">云语音邮件的新配置，请按照所述[配置语音邮件云服务](configure-cloud-voicemail.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="b1e91-139">For a new configuration of Cloud Voicemail, follow the steps outlined in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="b1e91-140">除了上述，要求如下要求必须配置为连接到 Microsoft 云语音邮件服务：</span><span class="sxs-lookup"><span data-stu-id="b1e91-140">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud Voicemail service:</span></span>

- <span data-ttu-id="b1e91-141">混合连接性。</span><span class="sxs-lookup"><span data-stu-id="b1e91-141">Hybrid connectivity.</span></span> <span data-ttu-id="b1e91-142">如果您已有 Skype 业务服务器部署，并且您希望为您的内部部署用户启用云语音邮件，您必须确保您有设置您的本地和联机环境之间的混合连接性。</span><span class="sxs-lookup"><span data-stu-id="b1e91-142">If you already have Skype for Business Server deployed, and you want to enable Cloud Voicemail for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="b1e91-143">此有时也称为拆分域配置。</span><span class="sxs-lookup"><span data-stu-id="b1e91-143">This is sometimes called a split domain configuration.</span></span> 

   <span data-ttu-id="b1e91-144">有关详细信息，请参阅[规划之间 Skype Business Server 和 Office 365 的混合连接性](plan-hybrid-connectivity.md)和[Skype Business Server 和 Office 365 之间配置混合连接性](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e91-144">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="b1e91-145">内部部署业务服务器，必须为用户启用了企业语音和 Skype 中承载语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b1e91-145">On-premises users must be enabled for Enterprise Voice and Hosted Voicemail in Skype for Business Server.</span></span>

- <span data-ttu-id="b1e91-146">外部 Exchange Web Services (EWS) URL 和自动发现，必须先设置或某些云语音邮件功能将受到限制。</span><span class="sxs-lookup"><span data-stu-id="b1e91-146">An External Exchange Web Services (EWS) URL and Autodiscover must be setup or some Cloud Voicemail features will be limited.</span></span>

-  <span data-ttu-id="b1e91-147">如果您具有内部部署仅部署-的只有 Exchange 和 Skype for Business 的本地服务器-但要充分利用云语音邮件，则需要 ON PREM 许可证。</span><span class="sxs-lookup"><span data-stu-id="b1e91-147">If you have an on-premises only deployment--that is, only Exchange and Skype for Business on-premises servers--but you want to take advantage of Cloud Voicemail, you need the ON-PREM license.</span></span> 

##<a name="migration-and-interoperability"></a><span data-ttu-id="b1e91-148">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="b1e91-148">Migration and interoperability</span></span>

<span data-ttu-id="b1e91-149">如果您打算部署的 Business Server 2019 和/或 Exchange Server 2019 Skype，您必须规划迁移仔细以确保能够持续的语音消息传递服务。</span><span class="sxs-lookup"><span data-stu-id="b1e91-149">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued service for voice messaging.</span></span> <span data-ttu-id="b1e91-150">注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="b1e91-150">Keep the following in mind:</span></span>

- <span data-ttu-id="b1e91-151">Exchange Server 2019 不再提供的 Exchange UM 功能</span><span class="sxs-lookup"><span data-stu-id="b1e91-151">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="b1e91-152">Skype 的业务服务器 2019年不再与 Exchange Online UM 集成</span><span class="sxs-lookup"><span data-stu-id="b1e91-152">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="b1e91-153">下表中列出版本互操作性和受支持的拓扑云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b1e91-153">Version interoperability and supported topologies for Cloud Voicemail are listed in the following table.</span></span> <span data-ttu-id="b1e91-154">对于预览版本，云语音邮件只适用于 Skype Business Server 和 Exchange Server 2019 或 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b1e91-154">For the preview release, Cloud Voicemail only works with Skype for Business Server and Exchange Server 2019 or Exchange Online.</span></span>


|                               | <span data-ttu-id="b1e91-155">Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1e91-155">Exchange Server 2013</span></span> | <span data-ttu-id="b1e91-156">Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="b1e91-156">Exchange Server 2016</span></span> | <span data-ttu-id="b1e91-157">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="b1e91-157">Exchange Server 2019</span></span> | <span data-ttu-id="b1e91-158">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1e91-158">Exchange Online</span></span>   |
|:---------------------------    |:---------------------|:---------------------|:------------------|:---------------------- |
| <span data-ttu-id="b1e91-159">Skype 业务服务器 2019</span><span class="sxs-lookup"><span data-stu-id="b1e91-159">Skype for Business Server 2019</span></span> | <span data-ttu-id="b1e91-160">Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="b1e91-160">Exchange Server UM</span></span> | <span data-ttu-id="b1e91-161">Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="b1e91-161">Exchange Server UM</span></span> | <span data-ttu-id="b1e91-162">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="b1e91-162">Cloud Voicemail</span></span> | <span data-ttu-id="b1e91-163">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="b1e91-163">Cloud Voicemail</span></span>
<span data-ttu-id="b1e91-164">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b1e91-164">Skype for Business Server 2015</span></span> | <span data-ttu-id="b1e91-165">Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="b1e91-165">Exchange Server UM</span></span> | <span data-ttu-id="b1e91-166">Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="b1e91-166">Exchange Server UM</span></span> |  | <span data-ttu-id="b1e91-167">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="b1e91-167">Cloud Voicemail</span></span> <br> <span data-ttu-id="b1e91-168">Exchange Online UM \*</span><span class="sxs-lookup"><span data-stu-id="b1e91-168">Exchange Online UM\*</span></span> |
<span data-ttu-id="b1e91-169">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1e91-169">Lync Server 2013</span></span> <br>  | <span data-ttu-id="b1e91-170">Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="b1e91-170">Exchange Server UM</span></span> | <span data-ttu-id="b1e91-171">Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="b1e91-171">Exchange Server UM</span></span> | | <span data-ttu-id="b1e91-172">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="b1e91-172">Cloud Voicemail</span></span> <br> <span data-ttu-id="b1e91-173">Exchange Online UM \*</span><span class="sxs-lookup"><span data-stu-id="b1e91-173">Exchange Online UM\*</span></span> |

<span data-ttu-id="b1e91-174">\*直到弃用。</span><span class="sxs-lookup"><span data-stu-id="b1e91-174">\* Until deprecated.</span></span>

<span data-ttu-id="b1e91-175">Microsoft 建议的以下的迁移路径：</span><span class="sxs-lookup"><span data-stu-id="b1e91-175">Microsoft recommends the following migration paths:</span></span>

-  <span data-ttu-id="b1e91-176">如果您要升级到 Skype 的业务服务器 2019年，您可以使用 Exchange UM 中 Exchange Server 2013 或 2016，但如果使用 Exchange Server 2019 必须升级到云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="b1e91-176">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud Voicemail if you are using Exchange Server 2019.</span></span>

- <span data-ttu-id="b1e91-177">如果您要升级到 Exchange Server 2019，并且您使用早期版本的 Exchange Server UM 的 Skype 进行业务服务器语音消息传递，Microsoft 建议您升级到 Skype 的业务服务器 2019年邮箱升级之前。</span><span class="sxs-lookup"><span data-stu-id="b1e91-177">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="b1e91-178">否则，语音消息功能都将丢失。</span><span class="sxs-lookup"><span data-stu-id="b1e91-178">Otherwise, voice messaging capabilities will be lost.</span></span> 


<span data-ttu-id="b1e91-179">有关规划迁移的详细信息，请参阅[Plan for Business Server 和 Exchange Server 迁移的 Skype](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="b1e91-179">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>
