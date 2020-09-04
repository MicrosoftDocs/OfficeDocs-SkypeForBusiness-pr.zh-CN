---
title: 为本地用户规划云语音邮件服务 |PBX Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 本文介绍了实施 Microsoft 云语音邮件服务的好处、规划注意事项和要求。 有关配置云语音邮件的信息，请参阅配置云语音邮件。
ms.openlocfilehash: d95d3674eb9119be07e8b588ec3fe0e619fb5f1c
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359128"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="de64c-104">为本地用户规划云语音邮件服务</span><span class="sxs-lookup"><span data-stu-id="de64c-104">Plan Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="de64c-105">概述</span><span class="sxs-lookup"><span data-stu-id="de64c-105">Overview</span></span>

<span data-ttu-id="de64c-106">本文介绍了为您的本地用户实施 Microsoft 云语音邮件服务的好处、规划注意事项和要求。</span><span class="sxs-lookup"><span data-stu-id="de64c-106">This article describes benefits, planning considerations, and requirements for implementing the Microsoft Cloud Voicemail service for your on-premises users.</span></span> <span data-ttu-id="de64c-107">有关配置云语音邮件的信息，请参阅 [配置云语音邮件服务](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="de64c-107">For information on configuring Cloud Voicemail, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="de64c-108">云语音邮件取代 Exchange 统一消息 (UM) 为在 Exchange Server 2019 或 Exchange Online 上拥有邮箱的 Skype for Business 2019 语音用户提供语音邮件功能。</span><span class="sxs-lookup"><span data-stu-id="de64c-108">Cloud Voicemail takes the place of Exchange Unified Messaging (UM) in providing voice messaging functionality for Skype for Business 2019 voice users who have mailboxes on Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="de64c-109">云语音邮件为您的内部部署用户和联机用户提供以下好处：</span><span class="sxs-lookup"><span data-stu-id="de64c-109">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="de64c-110">通过增强的语音方式应答和放入功能的语音邮件</span><span class="sxs-lookup"><span data-stu-id="de64c-110">Voicemail answering and deposit functionality with enhanced speech transcription</span></span>

- <span data-ttu-id="de64c-111">使用 Skype for Business Online 或 Outlook 客户端访问用户的 Exchange 邮箱中的语音邮件</span><span class="sxs-lookup"><span data-stu-id="de64c-111">Access to voicemail in the user's Exchange mailbox by using the Skype for Business Online or Outlook clients</span></span>

- <span data-ttu-id="de64c-112">使用 Microsoft 365 管理中心管理语音邮件选项的功能</span><span class="sxs-lookup"><span data-stu-id="de64c-112">The ability to use the Microsoft 365 admin center to manage voicemail options</span></span>

- <span data-ttu-id="de64c-113">在本地或在云中支持 Exchange 邮箱</span><span class="sxs-lookup"><span data-stu-id="de64c-113">Support for Exchange mailboxes on premises or in the cloud</span></span>

- <span data-ttu-id="de64c-114">从 Exchange Online 统一消息中利用现有用户问候语</span><span class="sxs-lookup"><span data-stu-id="de64c-114">Leveraging of existing user greetings from Exchange Online Unified Messaging</span></span>

> [!Important]
> <span data-ttu-id="de64c-115">Skype for Business Online 将于2021年7月31日停用，此后用户将无法再通过 Skype for Business Online 客户端访问其 Exchange 邮箱中的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="de64c-115">Skype for Business Online will be retired on July 31, 2021 after which users will no longer be able to access voicemail in their Exchange mailbox through the Skype for Business Online client.</span></span>

<span data-ttu-id="de64c-116">有关功能比较的详细信息，请参阅 [Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="de64c-116">For more information about feature comparison, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="de64c-117">Skype for Business Server 2019 继续为其邮箱位于早期版本的 Exchange Server (2013，2016) 的用户使用 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="de64c-117">Skype for Business Server 2019 continues to use Exchange UM for users whose mailboxes are on previous versions of Exchange Server (2013, 2016).</span></span>  <span data-ttu-id="de64c-118">了解将根据 Exchange Server 和 Skype for Business Server 版本使用哪种语音邮件解决方案是规划迁移到 Skype for business Server 2019 或 Exchange Server 2019 的重要部分。</span><span class="sxs-lookup"><span data-stu-id="de64c-118">Understanding which voicemail solution will be used based on the Exchange Server and Skype for Business Server version is an important part of planning for migration to either Skype for Business Server 2019 or Exchange Server 2019.</span></span> <span data-ttu-id="de64c-119">有关迁移和互操作性的详细信息，请参阅 [Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="de64c-119">For more information about migration and interoperability, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="de64c-120">使用云语音邮件，您的管理任务大大简化，因为：</span><span class="sxs-lookup"><span data-stu-id="de64c-120">With Cloud Voicemail, your administration tasks are greatly simplified because:</span></span>

- <span data-ttu-id="de64c-121">无需配置 Exchange UM 角色。</span><span class="sxs-lookup"><span data-stu-id="de64c-121">There is no need to configure the Exchange UM role.</span></span>
- <span data-ttu-id="de64c-122">云语音邮件的设置任务更简单。</span><span class="sxs-lookup"><span data-stu-id="de64c-122">The setup tasks for Cloud Voicemail are simpler.</span></span>
- <span data-ttu-id="de64c-123">对语音邮件功能的更新是直接在云中传递的，因此，您的用户始终可以访问最新的功能和更新，而不依赖 (Cu) 的累积更新。</span><span class="sxs-lookup"><span data-stu-id="de64c-123">Updates to voicemail functionality are delivered directly in the cloud, so your users always have access to the latest features and updates with less dependency on Cumulative Updates (CUs).</span></span>
- <span data-ttu-id="de64c-124">对于内部部署和联机 Exchange 邮箱，都具有相同的控件集。</span><span class="sxs-lookup"><span data-stu-id="de64c-124">You have the same set of controls for both on-premises and online Exchange mailboxes.</span></span> <span data-ttu-id="de64c-125">有关这些控件的详细信息，请参阅 [设置电话系统语音邮件](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)。</span><span class="sxs-lookup"><span data-stu-id="de64c-125">For more information on these controls, see [Set up Phone System voicemail](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).</span></span>

<span data-ttu-id="de64c-126">下图显示了混合部署中的云语音邮件：</span><span class="sxs-lookup"><span data-stu-id="de64c-126">The following diagram shows Cloud Voicemail in a hybrid deployment:</span></span>

![SfB 云语音邮件](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

<span data-ttu-id="de64c-128">将按如下方式处理未应答的呼叫：</span><span class="sxs-lookup"><span data-stu-id="de64c-128">Unanswered calls are handled as follows:</span></span>  

1. <span data-ttu-id="de64c-129">对于驻留在本地 Skype for business 2019 中的用户，本地 Skype for Business Server 会将未应答的呼叫发送到联机云语音邮件服务。</span><span class="sxs-lookup"><span data-stu-id="de64c-129">For users homed in Skype for Business 2019 on premises, unanswered calls are sent by the on-premises Skype for Business Server to the online Cloud Voicemail service.</span></span>
2. <span data-ttu-id="de64c-130">该服务处理语音邮件，包括进行工作。</span><span class="sxs-lookup"><span data-stu-id="de64c-130">The service processes the voicemail, including transcription.</span></span>
3. <span data-ttu-id="de64c-131">然后，该服务将语音邮件存款到用户的 Exchange 邮箱中，无论邮箱是位于本地还是联机。</span><span class="sxs-lookup"><span data-stu-id="de64c-131">The service then deposits the voicemail in the Exchange mailbox of the user, whether the mailbox is on-premises or online.</span></span>  
4. <span data-ttu-id="de64c-132">用户可以从其 Skype for Business 或 Outlook 客户端访问其语音邮件。</span><span class="sxs-lookup"><span data-stu-id="de64c-132">Users can access their voicemail from either their Skype for Business or Outlook client.</span></span>

## <a name="requirements"></a><span data-ttu-id="de64c-133">Requirements</span><span class="sxs-lookup"><span data-stu-id="de64c-133">Requirements</span></span>

<span data-ttu-id="de64c-134">以下要求假定您已在受支持的拓扑中部署了 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="de64c-134">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="de64c-135">您的要求取决于您的方案：</span><span class="sxs-lookup"><span data-stu-id="de64c-135">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="de64c-136">如果你已在使用 Exchange UM online，并且升级到 Skype for Business 2019，则需要修改托管的语音邮件策略，并验证托管提供程序的设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="de64c-136">If you are already using Exchange UM online and you upgrade to Skype for Business 2019, you will need to modify your hosted voicemail policy and verify that your hosting providers are set correctly.</span></span> <span data-ttu-id="de64c-137">有关详细信息，请参阅 [配置云语音邮件服务](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="de64c-137">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="de64c-138">如果您在本地使用 Exchange UM，或者使用 Exchange UM online 和内部部署的用户混合，则需要修改托管的语音邮件策略和托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="de64c-138">If you are using Exchange UM on premises, or you have a mix of users using Exchange UM online and on premises, you will need modify both your hosted voicemail policy and hosting provider.</span></span>  <span data-ttu-id="de64c-139">有关详细信息，请参阅 [配置云语音邮件服务](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="de64c-139">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="de64c-140">对于云语音邮件的新配置，请按照 [配置云语音邮件服务](configure-cloud-voicemail.md)中所述的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="de64c-140">For a new configuration of Cloud Voicemail, follow the steps outlined in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="de64c-141">除了上述要求之外，还必须配置以下要求以连接到 Microsoft 云语音邮件服务：</span><span class="sxs-lookup"><span data-stu-id="de64c-141">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud Voicemail service:</span></span>

- <span data-ttu-id="de64c-142">混合连接性。</span><span class="sxs-lookup"><span data-stu-id="de64c-142">Hybrid connectivity.</span></span> <span data-ttu-id="de64c-143">如果已部署 Skype for Business Server，并且要为本地用户启用云语音邮件，则必须确保在本地和联机环境之间设置混合连接。</span><span class="sxs-lookup"><span data-stu-id="de64c-143">If you already have Skype for Business Server deployed, and you want to enable Cloud Voicemail for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="de64c-144">这有时称为拆分域配置。</span><span class="sxs-lookup"><span data-stu-id="de64c-144">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="de64c-145">有关详细信息，请参阅 [规划 skype For Business server 与 Microsoft 365 或 office 365 之间的混合连接](plan-hybrid-connectivity.md) 和 [配置 Skype for Business server 和 office 365 之间的混合连接](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="de64c-145">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="de64c-146">必须在 Skype for Business Server 中为企业语音和托管语音邮件启用本地用户。</span><span class="sxs-lookup"><span data-stu-id="de64c-146">On-premises users must be enabled for Enterprise Voice and Hosted Voicemail in Skype for Business Server.</span></span>

- <span data-ttu-id="de64c-147">必须设置 (EWS) URL 和自动发现的外部 Exchange Web 服务，否则一些云语音邮件功能将受到限制。</span><span class="sxs-lookup"><span data-stu-id="de64c-147">An External Exchange Web Services (EWS) URL and Autodiscover must be set up or some Cloud Voicemail features will be limited.</span></span>

- <span data-ttu-id="de64c-148">如果您有一个内部部署 Exchange 服务器，请使用为 [Exchange Server 邮箱用户设置云语音邮件](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)中的步骤设置云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="de64c-148">If you have an on-premises Exchange server, set up Cloud Voicemail using the steps in [Set up Cloud Voicemail for Exchange Server Mailbox Users](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).</span></span>

## <a name="migration-and-interoperability"></a><span data-ttu-id="de64c-149">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="de64c-149">Migration and interoperability</span></span>

<span data-ttu-id="de64c-150">如果您计划部署 Skype for Business Server 2019 和/或 Exchange Server 2019，则必须仔细规划迁移以确保语音邮件的持续服务。</span><span class="sxs-lookup"><span data-stu-id="de64c-150">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued service for voice messaging.</span></span> <span data-ttu-id="de64c-151">请注意下列事项：</span><span class="sxs-lookup"><span data-stu-id="de64c-151">Keep the following in mind:</span></span>

- <span data-ttu-id="de64c-152">Exchange Server 2019 不再提供 Exchange UM 功能</span><span class="sxs-lookup"><span data-stu-id="de64c-152">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="de64c-153">Skype for Business Server 2019 不再与 Exchange Online UM 集成</span><span class="sxs-lookup"><span data-stu-id="de64c-153">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="de64c-154">下表列出了云语音邮件的版本互操作性和受支持的拓扑，它们将比较用户可能驻留的 Skype for Business Server 版本，并提供其 Exchange 邮箱的可能版本。</span><span class="sxs-lookup"><span data-stu-id="de64c-154">Version interoperability and supported topologies for Cloud Voicemail are listed in the following table, which compares the Skype for Business Server versions the user might be homed on with the possible version providing their Exchange Mailbox.</span></span> <span data-ttu-id="de64c-155">如果要将 Skype for Business 2019 与 Exchange Online 或 Exchange Server 2019 一起使用，则需要使用云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="de64c-155">You need to use Cloud Voicemail if you want to use Skype for Business 2019 with Exchange Online or Exchange Server 2019.</span></span>

| | <span data-ttu-id="de64c-156">Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="de64c-156">Exchange Server 2013</span></span> | <span data-ttu-id="de64c-157">Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="de64c-157">Exchange Server 2016</span></span> | <span data-ttu-id="de64c-158">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="de64c-158">Exchange Server 2019</span></span> | <span data-ttu-id="de64c-159">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="de64c-159">Exchange Online</span></span>   |
|:---    |:--- |:--- |:--- |:---  |
| <span data-ttu-id="de64c-160">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="de64c-160">Skype for Business Server 2019</span></span> | <span data-ttu-id="de64c-161">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="de64c-161">Exchange Server UM</span></span> | <span data-ttu-id="de64c-162">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="de64c-162">Exchange Server UM</span></span> | <span data-ttu-id="de64c-163">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="de64c-163">Cloud Voicemail</span></span> | <span data-ttu-id="de64c-164">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="de64c-164">Cloud Voicemail</span></span> |
| <span data-ttu-id="de64c-165">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="de64c-165">Skype for Business Server 2015</span></span> | <span data-ttu-id="de64c-166">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="de64c-166">Exchange Server UM</span></span> | <span data-ttu-id="de64c-167">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="de64c-167">Exchange Server UM</span></span> | <span data-ttu-id="de64c-168">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="de64c-168">Cloud Voicemail</span></span> | <span data-ttu-id="de64c-169">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="de64c-169">Cloud Voicemail</span></span> |
| <span data-ttu-id="de64c-170">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de64c-170">Lync Server 2013</span></span> <br>  | <span data-ttu-id="de64c-171">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="de64c-171">Exchange Server UM</span></span> | <span data-ttu-id="de64c-172">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="de64c-172">Exchange Server UM</span></span> | <span data-ttu-id="de64c-173">不支持</span><span class="sxs-lookup"><span data-stu-id="de64c-173">Not Supported</span></span> | <span data-ttu-id="de64c-174">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="de64c-174">Cloud Voicemail</span></span> |

<span data-ttu-id="de64c-175">Microsoft 建议采用以下迁移途径：</span><span class="sxs-lookup"><span data-stu-id="de64c-175">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="de64c-176">如果要升级到 Skype for business Server 2019，可以在 Exchange Server 2013 或2016中使用 Exchange UM，但如果使用的是 Exchange Server 2019，则必须升级到云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="de64c-176">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud Voicemail if you are using Exchange Server 2019.</span></span>
- <span data-ttu-id="de64c-177">如果要升级到 Exchange Server 2019，并且使用的是以前版本的 Exchange Server UM for Skype for business Server voice 消息，Microsoft 建议您先升级到 Skype for business Server 2019，然后再升级邮箱。</span><span class="sxs-lookup"><span data-stu-id="de64c-177">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="de64c-178">否则，语音邮件功能将丢失。</span><span class="sxs-lookup"><span data-stu-id="de64c-178">Otherwise, voice messaging capabilities will be lost.</span></span>
- <span data-ttu-id="de64c-179">如果要升级到 Skype for business Server 2019，并且已为使用 Exchange Online UM 的语音邮件配置了 Skype for Business Server 2015，则用户的语音邮件将在其帐户移动到 Skype for business Server 2019 时自动从 Exchange Online UM 迁移到云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="de64c-179">If you are upgrading to Skype for Business Server 2019, and have Skype for Business Server 2015 configured for voicemail with Exchange Online UM, users' voicemail will automatically migrate from Exchange Online UM to Cloud Voicemail when their account is moved to Skype for Business Server 2019.</span></span> 

<span data-ttu-id="de64c-180">有关规划迁移的详细信息，请参阅 [Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="de64c-180">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>
