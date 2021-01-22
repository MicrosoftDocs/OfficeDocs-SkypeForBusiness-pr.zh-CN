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
description: 将云自动助理与 Skype for Business Server 2019 一同使用概述
ms.openlocfilehash: 50cd9bb8b20e44d750dab68ec6fecb30bd02e203
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918688"
---
# <a name="plan-cloud-auto-attendants"></a><span data-ttu-id="6f0b4-103">规划云自动助理</span><span class="sxs-lookup"><span data-stu-id="6f0b4-103">Plan Cloud auto attendants</span></span>

<span data-ttu-id="6f0b4-104">与 Exchange 统一消息 (Exchange Server 2013 或 Exchange Server 2016) 一起使用的自动助理在 Exchange Server 2019 或 Exchange Online 中不再可用。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-104">The auto attendant used with Exchange Unified Messaging (Exchange Server 2013 or Exchange Server 2016) is no longer available in Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="6f0b4-105">如果你的 Skype for Business Server 2019 实现与这些 Exchange 版本之一集成，你将需要使用与电话系统关联的联机云语音功能。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-105">If your implementation of Skype for Business Server 2019 integrates with either of these Exchange versions, you'll need to use the online Cloud Voice features associated with Phone System.</span></span> <span data-ttu-id="6f0b4-106">请参阅 [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.</span><span class="sxs-lookup"><span data-stu-id="6f0b4-106">See [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.</span></span>

<span data-ttu-id="6f0b4-107">这本质上意味着如果你想要使用统一消息功能（如自动助理），你将拥有 Skype for Business Server 2019 的混合实现。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-107">This inherently means that you will have a hybrid implementation of Skype for Business Server 2019 if you wish to use Unified Messaging features like auto attendants.</span></span> <span data-ttu-id="6f0b4-108">有关详细信息 [，请参阅配置 Skype for Business Server 与 Microsoft 365 或 Office 365](configure-hybrid-connectivity.md) 之间的混合连接。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-108">See [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md) for details.</span></span>

<span data-ttu-id="6f0b4-109">自动助理是一种云服务，它接受客户呼叫并播放问候语，为用户提供菜单选项，并且使用语音或拨号盘与呼叫者交互，以将呼叫路由到正确的目标。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-109">An auto attendant is a cloud service that accepts customer calls and plays greetings, provides them with menu options, and interacts with callers using speech or the dial pad to route their calls to the right destination.</span></span> <span data-ttu-id="6f0b4-110">每个自动助理分配有一个资源 *帐户 (请参阅* 在 Skype for Business Server 2019 系统上配置资源帐户 [) ，](configure-onprem-ra.md) 这些帐户将直接链接到 Microsoft Teams 管理中心中的自动助理。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-110">Each auto attendant is assigned a *resource account* (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to an auto attendant in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6f0b4-111">请参阅 [什么是云自动助理？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 有关什么是自动助理以及自动助理存在的选项和功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-111">See [What are Cloud auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) for more detail on what auto attendants are and what options and features exist for auto attendants.</span></span>

> [!NOTE]
> <span data-ttu-id="6f0b4-112">可以将多个 Microsoft 服务号码、直接路由号码或混合号码分配给自动助理。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-112">You can assign multiple Microsoft service numbers, Direct Routing numbers, or hybrid numbers to an auto attendant.</span></span>

<span data-ttu-id="6f0b4-113">对云自动助理的传入呼叫可以采用以下几种路径之一，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f0b4-113">An incoming call to a Cloud auto attendant can take one of several paths, as shown here:</span></span>

![自动助理关系图](../../SfBServer2019/media/AA-plan-concept.png)

1. <span data-ttu-id="6f0b4-115">通过 Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="6f0b4-115">Via Skype for Business Server 2019</span></span>
2. <span data-ttu-id="6f0b4-116">通过会话[边界控制器和](/MicrosoftTeams/direct-routing-border-controllers.md)[直接路由](/MicrosoftTeams/direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="6f0b4-116">Via a [Session Border Controller](/MicrosoftTeams/direct-routing-border-controllers.md) and [Direct Routing](/MicrosoftTeams/direct-routing-plan.md)</span></span>
3. <span data-ttu-id="6f0b4-117">通过 Microsoft 365 或 Office 365 中在线存储的号码。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-117">Via a number homed online in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="6f0b4-118">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="6f0b4-118">Also see:</span></span>

- [<span data-ttu-id="6f0b4-119">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="6f0b4-119">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)
- [<span data-ttu-id="6f0b4-120">自动接听和路由传入呼叫</span><span class="sxs-lookup"><span data-stu-id="6f0b4-120">Automatically answer and route incoming calls</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a><span data-ttu-id="6f0b4-121">要求</span><span class="sxs-lookup"><span data-stu-id="6f0b4-121">Requirements</span></span>

<span data-ttu-id="6f0b4-122">以下要求假定你已在支持的拓扑中部署了 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-122">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="6f0b4-123">你的要求取决于你的方案：</span><span class="sxs-lookup"><span data-stu-id="6f0b4-123">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="6f0b4-124">如果你已在联机或本地使用 Exchange UM 并升级到 Skype for Business 2019，则需要捕获自动助理的结构，然后使用云自动助理在云中重新创建它们。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-124">If you are already using Exchange UM online or on-premises and you upgrade to Skype for Business 2019, you will need to capture the structure of your Auto attendants and re-create them in the cloud using Cloud auto attendants.</span></span> <span data-ttu-id="6f0b4-125">有关详细信息，请参阅将 [Exchange UM 自动助理或呼叫队列移动到电话系统](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-125">For more information, see [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).</span></span>

- <span data-ttu-id="6f0b4-126">有关云自动助理的新配置，请按照配置资源帐户中  [概述的步骤操作](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-126">For a new configuration of Cloud auto attendants, follow the steps outlined in  [Configure resource accounts](configure-onprem-ra.md).</span></span>

<span data-ttu-id="6f0b4-127">除了上述要求外，还必须将以下要求配置为连接到 Microsoft 云自动助理服务：</span><span class="sxs-lookup"><span data-stu-id="6f0b4-127">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud auto attendant service:</span></span>

- <span data-ttu-id="6f0b4-128">混合连接。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-128">Hybrid connectivity.</span></span> <span data-ttu-id="6f0b4-129">如果你已部署 Skype for Business Server，并且想要为本地用户启用云自动助理，则必须确保在本地环境和联机环境之间设置了混合连接。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-129">If you already have Skype for Business Server deployed, and you want to enable Cloud auto attendant for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="6f0b4-130">这有时称为拆分域配置。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-130">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="6f0b4-131">有关详细信息，请参阅[Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="6f0b4-131">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="6f0b4-132">如果将电话号码分配给自动助理，则需要 [Office 365 企业版 E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) 许可证。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-132">If you're assigning a phone number to to your auto attendant, you will need an [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) license.</span></span>
- <span data-ttu-id="6f0b4-133">为每个自动[助理创建](/MicrosoftTeams/manage-resource-accounts.md)联机资源帐户或本地[](configure-onprem-ra.md)资源帐户，并分配电话号码和许可证。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-133">Create an online [resource account](/MicrosoftTeams/manage-resource-accounts.md) or on-premises [resource account](configure-onprem-ra.md) for each auto attendant, and assign phone numbers and licenses.</span></span> 

## <a name="migration-and-interoperability"></a><span data-ttu-id="6f0b4-134">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="6f0b4-134">Migration and interoperability</span></span>

<span data-ttu-id="6f0b4-135">如果计划部署 Skype for Business Server 2019 和/或 Exchange Server 2019，则必须仔细规划迁移以确保自动助理的持续支持。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-135">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued support for auto attendants.</span></span> <span data-ttu-id="6f0b4-136">请注意下列事项：</span><span class="sxs-lookup"><span data-stu-id="6f0b4-136">Keep the following in mind:</span></span>

- <span data-ttu-id="6f0b4-137">Exchange Server 2019 不再提供 Exchange UM 功能</span><span class="sxs-lookup"><span data-stu-id="6f0b4-137">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="6f0b4-138">Exchange 统一消息已停用模式</span><span class="sxs-lookup"><span data-stu-id="6f0b4-138">Exchange Unified Messaging is in retirement mode</span></span>
- <span data-ttu-id="6f0b4-139">Skype for Business Server 2019 不再与 Exchange Online UM 集成</span><span class="sxs-lookup"><span data-stu-id="6f0b4-139">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="6f0b4-140">云自动助理可以使用 Skype for Business Server 2019、2015 和 2013 进行配置。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-140">Cloud auto attendants can be configured with Skype for Business Server 2019, 2015, and 2013.</span></span>

<span data-ttu-id="6f0b4-141">Microsoft 建议以下迁移路径：</span><span class="sxs-lookup"><span data-stu-id="6f0b4-141">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="6f0b4-142">如果要升级到 Skype for Business Server 2019，可以在 Exchange Server 2013 或 2016 中使用 Exchange UM，但如果使用的是 Exchange Server 2019，则必须升级到云自动助理。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-142">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud auto attendant if you are using Exchange Server 2019.</span></span>

- <span data-ttu-id="6f0b4-143">如果要升级到 Exchange Server 2019，并且使用的是早期版本的 Exchange Server UM for Skype for Business Server 语音邮件，Microsoft 建议在邮箱升级之前升级到 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-143">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="6f0b4-144">否则，语音邮件功能将丢失。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-144">Otherwise, voice messaging capabilities will be lost.</span></span>

<span data-ttu-id="6f0b4-145">有关规划迁移的信息，请参阅 Plan [for Skype for Business Server and Exchange Server migration.](plan-um-migration.md)</span><span class="sxs-lookup"><span data-stu-id="6f0b4-145">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a><span data-ttu-id="6f0b4-146">迁移以前实现的 Exchange UM 自动助理系统</span><span class="sxs-lookup"><span data-stu-id="6f0b4-146">Migrating a previously implemented Exchange UM auto attendant system</span></span>

<span data-ttu-id="6f0b4-147">目前，我们不支持自动迁移到在 Exchange 2013 或 2016 中创建的 UM 自动助理系统的云。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-147">Currently we don't support automated migration to the Cloud of a UM auto attendant system created in Exchange 2013 or 2016.</span></span> <span data-ttu-id="6f0b4-148">若要手动重新创建自动助理系统，需要：</span><span class="sxs-lookup"><span data-stu-id="6f0b4-148">To manually re-create an auto attendant system, you'll need to:</span></span>

1. <span data-ttu-id="6f0b4-149">使用 Exchange 管理员 PowerShell 命令查看旧自动助理系统的结构，包括任何嵌套的自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-149">Use Exchange admin PowerShell commands to review the structure of the old auto attendant system, including any nested auto attendants and call queues.</span></span>  
2. <span data-ttu-id="6f0b4-150">创建与每个 UM 自动助理节点关联的文本到语音脚本或录制的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-150">Create copies of text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
3. <span data-ttu-id="6f0b4-151">为每个自动助理节点创建本地终结点，包括为对象分配测试电话号码和许可证。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-151">Create on premise endpoints for each auto attendant node, including assigning a test phone numbers and licenses to the objects.</span></span> <span data-ttu-id="6f0b4-152">请注意，你现在能够分配电话系统等联机服务使用本地电话号码许可证。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-152">Note that you now have the ability to assign on-premise phone numbers licenses used by online services like Phone System.</span></span>
4. <span data-ttu-id="6f0b4-153">使用 Microsoft Teams 和电话系统实施新的云自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-153">Implement a new Cloud auto attendant service with Microsoft Teams and Phone System.</span></span> <span data-ttu-id="6f0b4-154">有关 [实现的详细信息，](configure-onprem-ra.md) 请参阅配置资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-154">See [Configure resource accounts](configure-onprem-ra.md) for implementation details.</span></span> <span data-ttu-id="6f0b4-155">在这样做时，请上载与每个 UM 自动助理节点关联的文本到语音传输脚本或录制的邮件。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-155">As you do this, upload the text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
5. <span data-ttu-id="6f0b4-156">测试云自动助理的功能。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-156">Test the functionality of the Cloud auto attendant.</span></span>
6. <span data-ttu-id="6f0b4-157">将分配给旧 Exchange UM 自动助理的电话号码重新分配给新建的主云自动助理。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-157">Reassign the phone number assigned to the old Exchange UM auto attendant to the newly created main Cloud auto attendant.</span></span>

<span data-ttu-id="6f0b4-158">有关这些步骤的详细信息，请参阅"将 [Exchange UM 自动助理或呼叫队列移动到电话](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) 系统"。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-158">See [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) for details on these steps.</span></span>

<span data-ttu-id="6f0b4-159">当你拥有一个满足你需求的稳固结构和一个可有效地指导客户的脚本时，请继续 [配置资源帐户](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-159">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to [Configure resource accounts](configure-onprem-ra.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="6f0b4-160">如 [KB4480742 所述](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)，建议不要将服务器 2015 中创建的 Exchange UM 自动助理移动到运行 Server 2019 的服务器。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-160">As mentioned in [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), moving Exchange UM auto attendants created in Server 2015 to servers running Server 2019 is discouraged.</span></span> <span data-ttu-id="6f0b4-161">目前，你必须在 Skype for Business Server 2015 池中保持它们以共存模式运行。</span><span class="sxs-lookup"><span data-stu-id="6f0b4-161">For the time being, you'd have to keep them on a Skype for Business Server 2015 pool running in coexistance mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f0b4-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f0b4-162">See Also</span></span>

[<span data-ttu-id="6f0b4-163">Skype for Business Server 和 Exchange Server 迁移规划</span><span class="sxs-lookup"><span data-stu-id="6f0b4-163">Plan for Skype for Business Server and Exchange Server migration</span></span>](plan-um-migration.md)

[<span data-ttu-id="6f0b4-164">配置资源帐户</span><span class="sxs-lookup"><span data-stu-id="6f0b4-164">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="6f0b4-165">允许使用电话用户界面录制自定义提示语</span><span class="sxs-lookup"><span data-stu-id="6f0b4-165">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="6f0b4-166">什么是云自动助理？</span><span class="sxs-lookup"><span data-stu-id="6f0b4-166">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="6f0b4-167">设置云自动助理</span><span class="sxs-lookup"><span data-stu-id="6f0b4-167">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

<span data-ttu-id="6f0b4-168">Exchange [UM：自动应答和路由传入呼叫](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span><span class="sxs-lookup"><span data-stu-id="6f0b4-168">Exchange UM: [Automatically answer and route incoming calls](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span></span>

[<span data-ttu-id="6f0b4-169">规划 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="6f0b4-169">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="6f0b4-170">配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="6f0b4-170">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="6f0b4-171">KB4480742：将联系人对象移动到 Skype for Business Server 2019 后，订阅者访问或自动助理的呼叫失败，同时出现快速忙碌和"500 服务器内部"错误</span><span class="sxs-lookup"><span data-stu-id="6f0b4-171">KB4480742: Calls to Subscriber Access or auto attendant fail with fast busy and “500 Server Internal" error after moving contact objects to Skype for Business Server 2019</span></span>](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
