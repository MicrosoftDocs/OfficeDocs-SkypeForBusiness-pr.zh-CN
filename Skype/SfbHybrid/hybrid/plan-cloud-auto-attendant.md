---
title: 规划云自动助理
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
description: 将云自动助理与 Skype for Business Server 2019 结合使用的概述
ms.openlocfilehash: f0b8018e7a926444e7920ccac31ed3ff4ab5c15f
ms.sourcegitcommit: 477aac9e14fced139ee7dd827942ce35b9769b63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "43510801"
---
# <a name="plan-cloud-auto-attendants"></a><span data-ttu-id="d8c5f-103">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="d8c5f-103">Plan Cloud auto attendants</span></span>

<span data-ttu-id="d8c5f-104">Exchange 统一消息（Exchange Server 2013 或 Exchange Server 2016）使用的自动助理已不再在 Exchange Server 2019 或 Exchange Online 中可用。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-104">The auto attendant used with Exchange Unified Messaging (Exchange Server 2013 or Exchange Server 2016) is no longer available in Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="d8c5f-105">如果实施 Skype for Business Server 2019 与上述任一 Exchange 版本集成，则需要使用与电话系统相关联的联机云语音功能。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-105">If your implementation of Skype for Business Server 2019 integrates with either of these Exchange versions, you'll need to use the online Cloud Voice features associated with Phone System.</span></span> <span data-ttu-id="d8c5f-106">请参阅[Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)，了解有关将 exchange UM 服务托管在 exchange server 2013 和2016上的信息移动到云。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-106">See [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.</span></span>

<span data-ttu-id="d8c5f-107">这本身就意味着，如果您希望使用统一消息功能（如自动助理），您将拥有 Skype for business Server 2019 的混合实施。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-107">This inherently means that you will have a hybrid implementation of Skype for Business Server 2019 if you wish to use Unified Messaging features like auto attendants.</span></span> <span data-ttu-id="d8c5f-108">有关详细信息，请参阅[配置 Skype For Business Server 和 Office 365 之间的混合连接](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-108">See [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md) for details.</span></span>

<span data-ttu-id="d8c5f-109">自动助理是一种云服务，它接受客户呼叫并播放问候语，为他们提供菜单选项，并与使用语音或拨号盘的呼叫者进行交互以将呼叫路由到正确的目标。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-109">An auto attendant is a cloud service that accepts customer calls and plays greetings, provides them with menu options, and interacts with callers using speech or the dial pad to route their calls to the right destination.</span></span> <span data-ttu-id="d8c5f-110">在 Skype for Business Server 2019 系统上为每个自动助理分配一个*资源帐户*（请参阅[配置资源帐户](configure-onprem-ra.md)），该帐户将直接链接到 Microsoft 团队管理中心中的自动助理。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-110">Each auto attendant is assigned a *resource account* (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to an auto attendant in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d8c5f-111">请参阅[什么是云自动助理？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md)有关自动助理的详细信息以及自动助理存在哪些选项和功能的详细信息，请参阅什么是云自动助理。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-111">See [What are Cloud auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) for more detail on what auto attendants are and what options and features exist for auto attendants.</span></span>

> [!NOTE]
> <span data-ttu-id="d8c5f-112">您可以将多个 Microsoft 服务号码、直接传送号码或混合号码分配给自动助理。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-112">You can assign multiple Microsoft service numbers, Direct Routing numbers, or hybrid numbers to an auto attendant.</span></span>

<span data-ttu-id="d8c5f-113">对云自动助理的传入呼叫可以采用多个路径之一，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d8c5f-113">An incoming call to a Cloud auto attendant can take one of several paths, as shown here:</span></span>

![自动助理的关系图](../../SfBServer2019/media/AA-plan-concept.png)

1. <span data-ttu-id="d8c5f-115">通过 Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d8c5f-115">Via Skype for Business Server 2019</span></span>
2. <span data-ttu-id="d8c5f-116">通过[会话边界控制器](/MicrosoftTeams/direct-routing-border-controllers.md)和[直接路由](/MicrosoftTeams/direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="d8c5f-116">Via a [Session Border Controller](/MicrosoftTeams/direct-routing-border-controllers.md) and [Direct Routing](/MicrosoftTeams/direct-routing-plan.md)</span></span>
3. <span data-ttu-id="d8c5f-117">通过在 Office 365 中托管的号码联机。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-117">Via a number homed online in Office 365.</span></span>

<span data-ttu-id="d8c5f-118">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="d8c5f-118">Also see:</span></span>

- [<span data-ttu-id="d8c5f-119">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="d8c5f-119">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)
- [<span data-ttu-id="d8c5f-120">自动接听和路由传入呼叫</span><span class="sxs-lookup"><span data-stu-id="d8c5f-120">Automatically answer and route incoming calls</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a><span data-ttu-id="d8c5f-121">Requirements</span><span class="sxs-lookup"><span data-stu-id="d8c5f-121">Requirements</span></span>

<span data-ttu-id="d8c5f-122">以下要求假定您已在受支持的拓扑中部署了 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-122">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="d8c5f-123">您的要求取决于您的方案：</span><span class="sxs-lookup"><span data-stu-id="d8c5f-123">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="d8c5f-124">如果你已在使用 Exchange UM online 或本地，并且升级到 Skype for Business 2019，你将需要捕获自动助理的结构，并使用云自动助理在云中重新创建它们。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-124">If you are already using Exchange UM online or on-premises and you upgrade to Skype for Business 2019, you will need to capture the structure of your Auto attendants and re-create them in the cloud using Cloud auto attendants.</span></span> <span data-ttu-id="d8c5f-125">有关详细信息，请参阅[将 EXCHANGE UM 自动助理或呼叫队列移动到电话系统](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-125">For more information, see [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).</span></span>

- <span data-ttu-id="d8c5f-126">对于云自动助理的新配置，请按照[Configure resource accounts](configure-onprem-ra.md)中所述的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-126">For a new configuration of Cloud auto attendants, follow the steps outlined in  [Configure resource accounts](configure-onprem-ra.md).</span></span>

<span data-ttu-id="d8c5f-127">除了上述要求之外，还必须将以下要求配置为连接到 Microsoft 云自动助理服务：</span><span class="sxs-lookup"><span data-stu-id="d8c5f-127">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud auto attendant service:</span></span>

- <span data-ttu-id="d8c5f-128">混合连接性。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-128">Hybrid connectivity.</span></span> <span data-ttu-id="d8c5f-129">如果已部署 Skype for Business Server，并且要为本地用户启用云自动助理，则必须确保在本地和联机环境之间设置混合连接。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-129">If you already have Skype for Business Server deployed, and you want to enable Cloud auto attendant for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="d8c5f-130">这有时称为拆分域配置。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-130">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="d8c5f-131">有关详细信息，请参阅[规划 skype For Business server 和 office 365 之间的混合连接](plan-hybrid-connectivity.md)和[配置 Skype for Business server 和 office 365 之间的混合连接](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-131">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="d8c5f-132">如果你要向自动助理分配电话号码，你将需要[Office 365 企业版 E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)许可证。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-132">If you're assigning a phone number to to your auto attendant, you will need an [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) license.</span></span>
- <span data-ttu-id="d8c5f-133">为每个自动助理创建一个联机[资源帐户](/MicrosoftTeams/manage-resource-accounts.md)或本地[资源帐户](configure-onprem-ra.md)，并分配电话号码和许可证。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-133">Create an online [resource account](/MicrosoftTeams/manage-resource-accounts.md) or on-premises [resource account](configure-onprem-ra.md) for each auto attendant, and assign phone numbers and licenses.</span></span> 

## <a name="migration-and-interoperability"></a><span data-ttu-id="d8c5f-134">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="d8c5f-134">Migration and interoperability</span></span>

<span data-ttu-id="d8c5f-135">如果您计划部署 Skype for Business Server 2019 和/或 Exchange Server 2019，则必须仔细规划迁移，以确保自动助理的持续支持。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-135">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued support for auto attendants.</span></span> <span data-ttu-id="d8c5f-136">请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="d8c5f-136">Keep the following in mind:</span></span>

- <span data-ttu-id="d8c5f-137">Exchange Server 2019 不再提供 Exchange UM 功能</span><span class="sxs-lookup"><span data-stu-id="d8c5f-137">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="d8c5f-138">Exchange 统一消息处于退休模式</span><span class="sxs-lookup"><span data-stu-id="d8c5f-138">Exchange Unified Messaging is in retirement mode</span></span>
- <span data-ttu-id="d8c5f-139">Skype for Business Server 2019 不再与 Exchange Online UM 集成</span><span class="sxs-lookup"><span data-stu-id="d8c5f-139">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="d8c5f-140">可以使用 Skype for Business Server 2019、2015和2013配置云自动助理。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-140">Cloud auto attendants can be configured with Skype for Business Server 2019, 2015, and 2013.</span></span>

<span data-ttu-id="d8c5f-141">Microsoft 建议采用以下迁移途径：</span><span class="sxs-lookup"><span data-stu-id="d8c5f-141">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="d8c5f-142">如果要升级到 Skype for business Server 2019，可以在 Exchange Server 2013 或2016中使用 Exchange UM，但如果您使用的是 Exchange Server 2019，则必须升级到云自动助理。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-142">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud auto attendant if you are using Exchange Server 2019.</span></span>

- <span data-ttu-id="d8c5f-143">如果要升级到 Exchange Server 2019，并且使用的是以前版本的 Exchange Server UM for Skype for business Server voice 消息，Microsoft 建议您先升级到 Skype for business Server 2019，然后再升级邮箱。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-143">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="d8c5f-144">否则，语音邮件功能将丢失。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-144">Otherwise, voice messaging capabilities will be lost.</span></span>

<span data-ttu-id="d8c5f-145">有关规划迁移的详细信息，请参阅[Plan For Skype For Business Server 和 Exchange Server 迁移](plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-145">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a><span data-ttu-id="d8c5f-146">迁移以前实施的 Exchange UM 自动助理系统</span><span class="sxs-lookup"><span data-stu-id="d8c5f-146">Migrating a previously implemented Exchange UM auto attendant system</span></span>

<span data-ttu-id="d8c5f-147">目前，我们不支持自动迁移到在 Exchange 2013 或2016中创建的 UM 自动助理系统的云。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-147">Currently we don't support automated migration to the Cloud of a UM auto attendant system created in Exchange 2013 or 2016.</span></span> <span data-ttu-id="d8c5f-148">若要手动重新创建自动助理系统，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8c5f-148">To manually re-create an auto attendant system, you'll need to:</span></span>

1. <span data-ttu-id="d8c5f-149">使用 Exchange 管理 powershell 命令查看旧自动助理系统（包括任何嵌套的自动助理和呼叫队列）的结构。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-149">Use Exchange admin powershell commands to review the structure of the old auto attendant system, including any nested auto attendants and call queues.</span></span>  
2. <span data-ttu-id="d8c5f-150">创建与每个 UM 自动助理节点关联的文本到语音的脚本或记录的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-150">Create copies of text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
3. <span data-ttu-id="d8c5f-151">为每个自动助理节点创建本地终结点，包括为对象分配测试电话号码和许可证。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-151">Create on premise endpoints for each auto attendant node, including assigning a test phone numbers and licenses to the objects.</span></span> <span data-ttu-id="d8c5f-152">请注意，您现在可以分配联机服务（如电话系统）使用的内部部署电话号码许可证。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-152">Note that you now have the ability to assign on-premise phone numbers licenses used by online services like Phone System.</span></span>
4. <span data-ttu-id="d8c5f-153">使用 Skype for Business Online 和电话系统实现新的云自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-153">Implement a new Cloud auto attendant service with Skype for Business Online and Phone System.</span></span> <span data-ttu-id="d8c5f-154">有关实现的详细信息，请参阅[配置资源帐户](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-154">See [Configure resource accounts](configure-onprem-ra.md) for implementation details.</span></span> <span data-ttu-id="d8c5f-155">在执行此操作时，请上载与每个 UM 自动助理节点关联的文本到语音的脚本或记录的邮件。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-155">As you do this, upload the text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
5. <span data-ttu-id="d8c5f-156">测试云自动助理的功能。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-156">Test the functionality of the Cloud auto attendant.</span></span>
6. <span data-ttu-id="d8c5f-157">将分配给旧 Exchange UM 自动助理的电话号码重新分配给新创建的主云自动助理。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-157">Reassign the phone number assigned to the old Exchange UM auto attendant to the newly created main Cloud auto attendant.</span></span>

<span data-ttu-id="d8c5f-158">有关这些步骤的详细信息，请参阅[将 EXCHANGE UM 自动助理或呼叫队列移动到电话系统](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-158">See [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) for details on these steps.</span></span>

## <a name="additional-planning-resources"></a><span data-ttu-id="d8c5f-159">其他规划资源</span><span class="sxs-lookup"><span data-stu-id="d8c5f-159">Additional planning resources</span></span>

<span data-ttu-id="d8c5f-160">标题为 "[小型企业" 的教程示例-设置自动助理](/microsoftteams/tutorial-org-aa)，以收集有关用户需求的信息、规划自动助理和用户的结构（以及可能的呼叫队列）、编写菜单提示以及在团队管理中心实施计划的过程。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-160">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Teams admin center.</span></span> <span data-ttu-id="d8c5f-161">查看教程并使用此处的练习来创建您的计划。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-161">Review the tutorial and use the exercises there to create your plan.</span></span>

<span data-ttu-id="d8c5f-162">如果您具有满足需求的实体结构和指导客户有效的脚本，请继续[配置资源帐户](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-162">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to [Configure resource accounts](configure-onprem-ra.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="d8c5f-163">如[KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)中所述，不鼓励将在服务器2015中创建的 Exchange UM 自动助理移动到运行服务器2019的服务器。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-163">As mentioned in [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), moving Exchange UM auto attendants created in Server 2015 to servers running Server 2019 is discouraged.</span></span> <span data-ttu-id="d8c5f-164">在这种情况下，您必须将其保留在共存模式下运行的 Skype for Business Server 2015 池上。</span><span class="sxs-lookup"><span data-stu-id="d8c5f-164">For the time being, you'd have to keep them on a Skype for Business Server 2015 pool running in coexistance mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8c5f-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8c5f-165">See Also</span></span>

[<span data-ttu-id="d8c5f-166">规划 Skype for Business Server 和 Exchange Server 迁移</span><span class="sxs-lookup"><span data-stu-id="d8c5f-166">Plan for Skype for Business Server and Exchange Server migration</span></span>](plan-um-migration.md)

[<span data-ttu-id="d8c5f-167">配置资源帐户</span><span class="sxs-lookup"><span data-stu-id="d8c5f-167">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="d8c5f-168">允许使用电话用户界面录制自定义提示语</span><span class="sxs-lookup"><span data-stu-id="d8c5f-168">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="d8c5f-169">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="d8c5f-169">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="d8c5f-170">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="d8c5f-170">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

<span data-ttu-id="d8c5f-171">Exchange UM：[自动应答和路由传入呼叫](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span><span class="sxs-lookup"><span data-stu-id="d8c5f-171">Exchange UM: [Automatically answer and route incoming calls](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span></span>

[<span data-ttu-id="d8c5f-172">规划 Skype for Business Server 与 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="d8c5f-172">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="d8c5f-173">配置 Skype for Business Server 和 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="d8c5f-173">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="d8c5f-174">KB4480742：将联系人对象移至 Skype for business Server 2019 后，对订阅者访问或自动助理的呼叫失败，并出现 "500 服务器内部" 错误</span><span class="sxs-lookup"><span data-stu-id="d8c5f-174">KB4480742: Calls to Subscriber Access or auto attendant fail with fast busy and “500 Server Internal" error after moving contact objects to Skype for Business Server 2019</span></span>](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
