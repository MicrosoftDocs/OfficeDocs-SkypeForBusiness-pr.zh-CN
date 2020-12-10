---
title: Microsoft 团队中的语音
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 了解有关 Microsoft 团队云语音功能的详细信息以及你将为组织制定的部署决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c392e9a1e2944c573ddfa63da3aa27f56b2380d7
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611694"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="0bd05-103">规划团队语音解决方案</span><span class="sxs-lookup"><span data-stu-id="0bd05-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="0bd05-104">本文将帮助你确定哪种 Microsoft 语音解决方案适合你的组织。</span><span class="sxs-lookup"><span data-stu-id="0bd05-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="0bd05-105">确定后，本文将提供内容的路线图，使你能够实现所选的解决方案。</span><span class="sxs-lookup"><span data-stu-id="0bd05-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span> 

<span data-ttu-id="0bd05-106">您可能希望最简单的解决方案 &mdash; 电话系统具有通话计划。</span><span class="sxs-lookup"><span data-stu-id="0bd05-106">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="0bd05-107">这是 Microsoft 的所有云解决方案，它提供了专用分支 Exchange (PBX) 功能以及对公共交换电话网络 (PSTN) 的调用，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="0bd05-107">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="0bd05-108">通过此解决方案，Microsoft 是你的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="0bd05-108">With this solution, Microsoft is your PSTN carrier.</span></span>

![图1显示了带有呼叫计划的电话系统](media/voice-solutions-simple.png)

<span data-ttu-id="0bd05-110">如果对以下项回答 "是"，则带有呼叫计划的电话系统是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="0bd05-110">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="0bd05-111">您所在的地区有通话计划。</span><span class="sxs-lookup"><span data-stu-id="0bd05-111">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="0bd05-112">您无需保留当前的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="0bd05-112">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="0bd05-113">您想要对 PSTN 使用 Microsoft 托管访问。</span><span class="sxs-lookup"><span data-stu-id="0bd05-113">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="0bd05-114">但是，你的情况可能更复杂。</span><span class="sxs-lookup"><span data-stu-id="0bd05-114">However, your situation might be more complex.</span></span> <span data-ttu-id="0bd05-115">例如，您可能在不支持通话计划的位置有办事处。</span><span class="sxs-lookup"><span data-stu-id="0bd05-115">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="0bd05-116">或者，你可能需要支持复杂的多国部署的组合解决方案，但对不同地理位置的要求不同。</span><span class="sxs-lookup"><span data-stu-id="0bd05-116">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="0bd05-117">Microsoft 支持解决方案组合：</span><span class="sxs-lookup"><span data-stu-id="0bd05-117">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="0bd05-118">带有呼叫计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="0bd05-118">Phone System with Calling Plan</span></span>
- <span data-ttu-id="0bd05-119">带有直接路由的您自己的 PSTN 运营商的电话系统</span><span class="sxs-lookup"><span data-stu-id="0bd05-119">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="0bd05-120">结合使用电话系统和直接路由的通话计划和电话系统结合使用的组合解决方案</span><span class="sxs-lookup"><span data-stu-id="0bd05-120">A combination solution that uses both Phone System with Calling Plan and Phone System with Direct Routing</span></span>

## <a name="what-do-you-need-to-read"></a><span data-ttu-id="0bd05-121">您需要阅读哪些内容？</span><span class="sxs-lookup"><span data-stu-id="0bd05-121">What do you need to read?</span></span>

<span data-ttu-id="0bd05-122">**必填。**</span><span class="sxs-lookup"><span data-stu-id="0bd05-122">**Required for all.**</span></span> <span data-ttu-id="0bd05-123">本文中的部分内容适用于所有组织。</span><span class="sxs-lookup"><span data-stu-id="0bd05-123">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="0bd05-124">例如，每个人都应阅读有关电话系统的信息，并了解连接到公共交换电话网络 (PSTN) 的选项。</span><span class="sxs-lookup"><span data-stu-id="0bd05-124">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="0bd05-125">所有必填</span><span class="sxs-lookup"><span data-stu-id="0bd05-125">Required for all</span></span> | <span data-ttu-id="0bd05-126">说明</span><span class="sxs-lookup"><span data-stu-id="0bd05-126">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="0bd05-127">**电话系统**</span><span class="sxs-lookup"><span data-stu-id="0bd05-127">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="0bd05-128">Microsoft 365 cloud 中与 Microsoft 团队 (PBX) 功能的 microsoft 的技术，用于启用呼叫控制和专用分支 Exchange。</span><span class="sxs-lookup"><span data-stu-id="0bd05-128">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="0bd05-129">**公共交换电话网络 (PSTN) 连接选项**</span><span class="sxs-lookup"><span data-stu-id="0bd05-129">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="0bd05-130">在使用 Microsoft 作为电话运营商，或使用直接路由将您自己的电话运营商连接到 Microsoft 团队之间的选择。</span><span class="sxs-lookup"><span data-stu-id="0bd05-130">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing.</span></span> <span data-ttu-id="0bd05-131">通过结合使用手机系统，PSTN 连接选项使你的用户可以拨打世界各地的电话。</span><span class="sxs-lookup"><span data-stu-id="0bd05-131">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="0bd05-132">**具体取决于你的需求。**</span><span class="sxs-lookup"><span data-stu-id="0bd05-132">**Depending on your requirements.**</span></span> <span data-ttu-id="0bd05-133">本文中的部分内容取决于您的现有部署和要求。</span><span class="sxs-lookup"><span data-stu-id="0bd05-133">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="0bd05-134">例如，仅在不允许进行收费跳过的地理位置直接路由客户的情况下，才需要 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="0bd05-134">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="0bd05-135">考虑你可能需要以下哪些其他配置：</span><span class="sxs-lookup"><span data-stu-id="0bd05-135">Consider which of these additional configurations you might need:</span></span>

![图2显示了其他语音组件，如 Microsoft 的电话号码、拨号计划和呼叫路由等。](media/voice-consider-additional-components.png)

| <span data-ttu-id="0bd05-137">根据您的要求</span><span class="sxs-lookup"><span data-stu-id="0bd05-137">Depending on your requirements</span></span> | <span data-ttu-id="0bd05-138">说明</span><span class="sxs-lookup"><span data-stu-id="0bd05-138">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="0bd05-139">**Microsoft 的电话号码**</span><span class="sxs-lookup"><span data-stu-id="0bd05-139">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="0bd05-140">如何从 Microsoft 获取和管理电话号码，以及如何将现有号码转移到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="0bd05-140">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="0bd05-141">如果需要获取 Microsoft 通话计划的电话号码、转移现有号码、获取服务号码等，请阅读此项。</span><span class="sxs-lookup"><span data-stu-id="0bd05-141">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="0bd05-142">**拨号计划和呼叫路由**</span><span class="sxs-lookup"><span data-stu-id="0bd05-142">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="0bd05-143">如何配置和管理将已拨打的电话号码转换为备用格式的拨号计划 (一般情况下，) 用于呼叫授权和呼叫路由的 E：164格式。</span><span class="sxs-lookup"><span data-stu-id="0bd05-143">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="0bd05-144">如果需要了解拨号计划以及是否需要为你的组织指定拨号计划，请阅读此内容。</span><span class="sxs-lookup"><span data-stu-id="0bd05-144">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="0bd05-145">**紧急电话**</span><span class="sxs-lookup"><span data-stu-id="0bd05-145">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="0bd05-146">如何根据 PSTN 连接选项管理和配置紧急呼叫 &mdash; 。</span><span class="sxs-lookup"><span data-stu-id="0bd05-146">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="0bd05-147">如果您使用的是 Microsoft 通话计划或直接路由，并且需要了解如何管理您的组织的紧急呼叫，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="0bd05-147">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="0bd05-148">**直接路由的基于位置的路由**</span><span class="sxs-lookup"><span data-stu-id="0bd05-148">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="0bd05-149">如何使用 Location-Based 路由 (LBR) 根据地理位置限制 Microsoft 团队用户进行收费跳过。</span><span class="sxs-lookup"><span data-stu-id="0bd05-149">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="0bd05-150">如果你的组织在不允许使用免收费的位置使用直接路由，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="0bd05-150">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="0bd05-151">**云语音功能的网络拓扑**</span><span class="sxs-lookup"><span data-stu-id="0bd05-151">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="0bd05-152">如果你的组织正在部署 Location-Based 路由 (LBR) 用于直接路由或动态紧急呼叫，则必须在 Microsoft 团队中配置用于这些功能的网络设置。</span><span class="sxs-lookup"><span data-stu-id="0bd05-152">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="0bd05-153">如果你要为直接路由实现 LBR，或者如果你要通过呼叫计划或直接路由实施动态紧急呼叫，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="0bd05-153">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="0bd05-154">**迁移现有的语音解决方案**</span><span class="sxs-lookup"><span data-stu-id="0bd05-154">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="0bd05-155">将语音解决方案迁移到团队时需要考虑的内容。</span><span class="sxs-lookup"><span data-stu-id="0bd05-155">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="0bd05-156">如果要从现有语音解决方案迁移到团队，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="0bd05-156">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="0bd05-157">本文重点介绍 Microsoft 团队的语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="0bd05-157">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="0bd05-158">虽然 Skype for business Online 的解决方案仍然可用 (如 [Microsoft 电话解决方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)) 所述，但了解 skype For business online 将于2021年7月31日停用，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="0bd05-158">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="0bd05-159">在该日期之后，Skype for Business Online 服务将无法再访问。</span><span class="sxs-lookup"><span data-stu-id="0bd05-159">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="0bd05-160">此外，你的本地环境之间的 PSTN 连接（ &mdash; 无论是通过 skype For Business 服务器还是云连接器版本 &mdash; 和 Skype For business Online）都将不再受支持。</span><span class="sxs-lookup"><span data-stu-id="0bd05-160">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="0bd05-161">本文介绍团队语音解决方案，以及如何使用直接路由将本地电话网络（如有必要）连接到团队。</span><span class="sxs-lookup"><span data-stu-id="0bd05-161">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing.</span></span>


## <a name="phone-system"></a><span data-ttu-id="0bd05-162">电话系统</span><span class="sxs-lookup"><span data-stu-id="0bd05-162">Phone System</span></span>

<span data-ttu-id="0bd05-163">电话系统是 Microsoft 在 microsoft 365 或 Office 365 云中与 Microsoft 团队 (PBX) 功能的 Microsoft 技术，用于启用呼叫控制和专用分支 Exchange。</span><span class="sxs-lookup"><span data-stu-id="0bd05-163">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="0bd05-164">电话系统与团队或 Skype for business 客户端和认证设备配合使用。</span><span class="sxs-lookup"><span data-stu-id="0bd05-164">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="0bd05-165">电话系统允许你将现有的 PBX 系统替换为从 Microsoft 365 或 Office 365 直接提供的一组功能。</span><span class="sxs-lookup"><span data-stu-id="0bd05-165">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="0bd05-166">您的组织内的用户之间的通话在电话系统内部处理，绝不会转到公共交换电话网络 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="0bd05-166">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="0bd05-167">这适用于位于不同地理区域的组织中的用户之间的通话，可删除这些内部呼叫的长途费用。</span><span class="sxs-lookup"><span data-stu-id="0bd05-167">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="0bd05-168">本文介绍以下电话系统密钥功能和功能，您需要考虑的部署决策：</span><span class="sxs-lookup"><span data-stu-id="0bd05-168">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="0bd05-169">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="0bd05-169">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="0bd05-170">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="0bd05-170">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="0bd05-171">通话标识</span><span class="sxs-lookup"><span data-stu-id="0bd05-171">Calling identity</span></span>](#calling-identity)

![图3显示电话系统包含自动助理和呼叫查询、云语音邮件和呼叫标识](media/phone-system-contains.png)

<span data-ttu-id="0bd05-173">有关所有电话系统功能以及如何设置电话系统的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-173">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="0bd05-174">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="0bd05-174">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="0bd05-175">在组织中设置电话系统</span><span class="sxs-lookup"><span data-stu-id="0bd05-175">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="0bd05-176">介绍如何购买和分配电话系统许可证、管理电话号码以及为免费号码设置通信信用点数。</span><span class="sxs-lookup"><span data-stu-id="0bd05-176">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="0bd05-177">有关管理受支持的设备的信息，请参阅在 Microsoft 团队和[团队市场](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)[中管理设备](devices/device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="0bd05-177">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="0bd05-178">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="0bd05-178">Auto attendants and Call queues</span></span>

<span data-ttu-id="0bd05-179">自动助理允许你设置菜单选项，以根据呼叫方输入路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="0bd05-179">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="0bd05-180">通话队列是呼叫方的等待区域。</span><span class="sxs-lookup"><span data-stu-id="0bd05-180">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="0bd05-181">"自动助理" 和 "呼叫队列" 一起使用，可以轻松地将呼叫者路由到组织中的相应人员或部门。</span><span class="sxs-lookup"><span data-stu-id="0bd05-181">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="0bd05-182">有关自动助理和通话队列的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-182">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="0bd05-183">规划团队自动助理和通话队列</span><span class="sxs-lookup"><span data-stu-id="0bd05-183">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="0bd05-184">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="0bd05-184">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="0bd05-185">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="0bd05-185">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="0bd05-186">Contoso 个案研究：自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="0bd05-186">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="0bd05-187">介绍一个虚构的多国企业（Contoso）如何为其语音解决方案实现自动助理和通话队列。</span><span class="sxs-lookup"><span data-stu-id="0bd05-187">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="0bd05-188">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="0bd05-188">Cloud Voicemail</span></span>

<span data-ttu-id="0bd05-189">云语音邮件（由 Azure 语音邮件服务提供支持）仅支持向 Exchange 邮箱存款语音邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd05-189">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="0bd05-190">它不支持第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="0bd05-190">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="0bd05-191">云语音邮件包括语音邮件脚本，默认情况下为组织中的所有用户启用。</span><span class="sxs-lookup"><span data-stu-id="0bd05-191">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="0bd05-192">您的业务需求可能要求您为整个组织中的特定用户或所有人禁用语音邮件脚本。</span><span class="sxs-lookup"><span data-stu-id="0bd05-192">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="0bd05-193">对于仅供联机使用的用户，为用户分配电话系统许可证后，将自动为其设置和设置云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="0bd05-193">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="0bd05-194">对于具有 Exchange 邮箱的电话系统用户，你将需要执行额外的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="0bd05-194">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="0bd05-195">有关云语音邮件及其配置的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-195">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="0bd05-196">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="0bd05-196">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="0bd05-197">在组织中设置语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="0bd05-197">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="0bd05-198">通话标识</span><span class="sxs-lookup"><span data-stu-id="0bd05-198">Calling identity</span></span>

<span data-ttu-id="0bd05-199">默认情况下，所有出站呼叫使用分配的电话号码作为呼叫标识 (呼叫方 ID) 。</span><span class="sxs-lookup"><span data-stu-id="0bd05-199">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="0bd05-200">呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="0bd05-200">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="0bd05-201">有关配置来电显示或更改或阻止呼叫方 ID 的信息，请参阅 [为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="0bd05-201">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="0bd05-202">公共交换电话网络连接选项</span><span class="sxs-lookup"><span data-stu-id="0bd05-202">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="0bd05-203">电话系统为您的组织提供完整的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="0bd05-203">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="0bd05-204">但是，若要使用户可以在组织外部进行呼叫，您需要将电话系统连接到公共交换电话网络 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="0bd05-204">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="0bd05-205">要将电话系统连接到 PSTN，您可以选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="0bd05-205">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="0bd05-206">[**带有呼叫计划的电话系统**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="0bd05-206">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="0bd05-207">Microsoft 作为 PSTN 运营商提供的所有云解决方案。</span><span class="sxs-lookup"><span data-stu-id="0bd05-207">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="0bd05-208">[**带有您自己的 PSTN 运营商的电话系统**](#phone-system-with-own-pstn-carrier-with-direct-routing) ，使用直接路由将本地环境连接到团队。</span><span class="sxs-lookup"><span data-stu-id="0bd05-208">[**Phone System with your own PSTN carrier**](#phone-system-with-own-pstn-carrier-with-direct-routing) by using Direct Routing to connect your on-premises environment to Teams.</span></span>

<span data-ttu-id="0bd05-209">你还可以选择选项组合，以便为复杂的环境设计解决方案，或者管理多步迁移 (有关稍后) 迁移的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0bd05-209">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="0bd05-210">带有呼叫计划的电话系统</span><span class="sxs-lookup"><span data-stu-id="0bd05-210">Phone System with Calling Plan</span></span> 

<span data-ttu-id="0bd05-211">如本文前面所述，带有呼叫计划的电话系统是适用于团队用户的 Microsoft 的所有云语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="0bd05-211">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="0bd05-212">这是将 Microsoft Phone 系统连接到公共交换电话网络 (PSTN) 的最简单选项，可拨打世界各地的座机和移动电话。</span><span class="sxs-lookup"><span data-stu-id="0bd05-212">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="0bd05-213">通过此选项，Microsoft 为你的组织提供专用分支 Exchange (PBX) 功能，并充当 PSTN 运营商，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="0bd05-213">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![图4显示了带有自动助理、呼叫队列、来电显示等的电话系统，以及 Microsoft 作为 PSTN 运营商](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="0bd05-215">如果对以下项回答 "是"，则带有呼叫计划的电话系统是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="0bd05-215">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="0bd05-216">您所在的地区有通话计划。</span><span class="sxs-lookup"><span data-stu-id="0bd05-216">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="0bd05-217">您无需保留当前的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="0bd05-217">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="0bd05-218">您想要对 PSTN 使用 Microsoft 托管访问。</span><span class="sxs-lookup"><span data-stu-id="0bd05-218">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="0bd05-219">通过此选项：</span><span class="sxs-lookup"><span data-stu-id="0bd05-219">With this option:</span></span> 

- <span data-ttu-id="0bd05-220">您可以通过添加国内或国际呼叫计划的 Microsoft Phone 系统，让您拨打世界各地的电话 (，具体取决于) 许可的服务级别。</span><span class="sxs-lookup"><span data-stu-id="0bd05-220">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="0bd05-221">你不需要部署或维护本地部署， &mdash; 因为通话计划的运行方式不是 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0bd05-221">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="0bd05-222">注意：如有必要，你可以选择通过直接路由与 SBC 支持的第三方 Pbx、模拟设备和其他第三方电话设备的互操作性，将受支持的会话边界控制器连接 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="0bd05-222">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="0bd05-223">此选项需要与 Microsoft 365 或 Office 365 的无中断连接。</span><span class="sxs-lookup"><span data-stu-id="0bd05-223">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="0bd05-224">有关通话计划的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-224">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="0bd05-225">哪种通话套餐适合你？</span><span class="sxs-lookup"><span data-stu-id="0bd05-225">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="0bd05-226">如何购买通话套餐</span><span class="sxs-lookup"><span data-stu-id="0bd05-226">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="0bd05-227">通话套餐的国家和地区可用性</span><span class="sxs-lookup"><span data-stu-id="0bd05-227">Country and region availability for Calling Plan</span></span>](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [<span data-ttu-id="0bd05-228">设置通话计划</span><span class="sxs-lookup"><span data-stu-id="0bd05-228">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="0bd05-229">带有直接路由的 PSTN 运营商的电话系统</span><span class="sxs-lookup"><span data-stu-id="0bd05-229">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="0bd05-230">此选项通过直接路由将 Microsoft Phone 系统连接到电话网络，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="0bd05-230">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![图5显示带有直接路由的电话系统](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="0bd05-232">如果对以下问题回答 "是"，则带有直接路由的电话系统是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="0bd05-232">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="0bd05-233">您希望将团队与电话系统配合使用。</span><span class="sxs-lookup"><span data-stu-id="0bd05-233">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="0bd05-234">您需要保留当前的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="0bd05-234">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="0bd05-235">您想要混合路由，通过通话计划进行一些通话，而有些通过运营商。</span><span class="sxs-lookup"><span data-stu-id="0bd05-235">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="0bd05-236">您需要与第三方的 Pbx 和/或设备互操作，例如，我们的系统开销、模拟设备等。</span><span class="sxs-lookup"><span data-stu-id="0bd05-236">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="0bd05-237">通过此选项：</span><span class="sxs-lookup"><span data-stu-id="0bd05-237">With this option:</span></span>

- <span data-ttu-id="0bd05-238">将您自己支持的 SBC 连接到 Microsoft Phone 系统，而无需额外的本地软件。</span><span class="sxs-lookup"><span data-stu-id="0bd05-238">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="0bd05-239">您可以将任何电话运营商与 Microsoft Phone 系统配合使用。</span><span class="sxs-lookup"><span data-stu-id="0bd05-239">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="0bd05-240">你可以选择配置和管理此选项，或者你的运营商或合作伙伴 (询问你的运营商或合作伙伴是否提供此选项) 。</span><span class="sxs-lookup"><span data-stu-id="0bd05-240">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="0bd05-241">你可以配置电话设备 &mdash; （如第三方 PBX 和模拟设备 &mdash; 和 Microsoft Phone 系统）之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="0bd05-241">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="0bd05-242">此选项需要以下内容：</span><span class="sxs-lookup"><span data-stu-id="0bd05-242">This option requires the following:</span></span>

- <span data-ttu-id="0bd05-243">不中断连接到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0bd05-243">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="0bd05-244">部署和维护受支持的 SBC。</span><span class="sxs-lookup"><span data-stu-id="0bd05-244">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="0bd05-245">与第三方运营商签订的合同。</span><span class="sxs-lookup"><span data-stu-id="0bd05-245">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="0bd05-246"> (，除非已部署为向使用呼叫计划的电话系统上的用户提供与第三方 PBX、模拟设备或其他电话设备的连接的选项。 ) </span><span class="sxs-lookup"><span data-stu-id="0bd05-246">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="0bd05-247">有关直接路由的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-247">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="0bd05-248">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="0bd05-248">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="0bd05-249">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="0bd05-249">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="0bd05-250">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="0bd05-250">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="0bd05-251">管理用于直接路由的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="0bd05-251">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="0bd05-252">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0bd05-252">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="0bd05-253">经认证可用于直接路由的会话边界控制器列表</span><span class="sxs-lookup"><span data-stu-id="0bd05-253">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="0bd05-254">Microsoft 的电话号码</span><span class="sxs-lookup"><span data-stu-id="0bd05-254">Phone numbers from Microsoft</span></span>

<span data-ttu-id="0bd05-255">Microsoft 有两种类型的电话号码可用： *订户* (用户) 号码（可分配给您组织中的用户）和 *服务* 号码（可用作收费电话和免费服务号码）。</span><span class="sxs-lookup"><span data-stu-id="0bd05-255">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="0bd05-256">服务号码的并行呼叫容量比订户号码的数量更高，并且可以分配给服务，例如音频会议、自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="0bd05-256">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="0bd05-257">你将需要确定：</span><span class="sxs-lookup"><span data-stu-id="0bd05-257">You will need to decide:</span></span>

- <span data-ttu-id="0bd05-258">哪些用户位置需要来自 Microsoft 的新电话号码？</span><span class="sxs-lookup"><span data-stu-id="0bd05-258">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="0bd05-259">我需要 (订阅者或服务) 哪些类型的电话号码？</span><span class="sxs-lookup"><span data-stu-id="0bd05-259">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="0bd05-260">如何将现有电话号码移植到团队？</span><span class="sxs-lookup"><span data-stu-id="0bd05-260">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="0bd05-261">有关管理组织中的电话号码的详细信息，包括获取新号码或转移现有号码，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-261">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="0bd05-262">管理组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="0bd05-262">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="0bd05-263">用于呼叫计划的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="0bd05-263">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="0bd05-264">为用户获取电话号码</span><span class="sxs-lookup"><span data-stu-id="0bd05-264">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="0bd05-265">将电话号码转移到 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="0bd05-265">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="0bd05-266">拨号计划和呼叫路由</span><span class="sxs-lookup"><span data-stu-id="0bd05-266">Dial plans and call routing</span></span>

<span data-ttu-id="0bd05-267">拨号计划是一组规范化规则，可将拨出的电话号码转换为备用格式 (一般情况下，) 用于呼叫授权和呼叫路由的 E-164 格式的格式。</span><span class="sxs-lookup"><span data-stu-id="0bd05-267">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="0bd05-268">您需要确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="0bd05-268">You will need to decide the following:</span></span> 

- <span data-ttu-id="0bd05-269">我的组织是否需要自定义拨号计划？</span><span class="sxs-lookup"><span data-stu-id="0bd05-269">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="0bd05-270">哪些用户需要自定义的拨号计划？</span><span class="sxs-lookup"><span data-stu-id="0bd05-270">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="0bd05-271">应将哪些租户拨号计划分配给每个用户？</span><span class="sxs-lookup"><span data-stu-id="0bd05-271">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="0bd05-272">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-272">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="0bd05-273">什么是拨号计划？</span><span class="sxs-lookup"><span data-stu-id="0bd05-273">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="0bd05-274">计划租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="0bd05-274">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="0bd05-275">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="0bd05-275">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="0bd05-276">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="0bd05-276">Emergency calling</span></span>

<span data-ttu-id="0bd05-277">配置紧急呼叫的方式会有所不同，具体取决于 PSTN 连接选项： Microsoft 通话计划或直接路由。</span><span class="sxs-lookup"><span data-stu-id="0bd05-277">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="0bd05-278">Microsoft 通话计划和电话系统直接路由的动态紧急呼叫提供了配置和路由紧急呼叫的功能，并根据团队客户的当前位置通知安全人员。</span><span class="sxs-lookup"><span data-stu-id="0bd05-278">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="0bd05-279">有关紧急呼叫概念和术语以及如何配置动态紧急呼叫的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-279">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="0bd05-280">管理紧急电话</span><span class="sxs-lookup"><span data-stu-id="0bd05-280">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="0bd05-281">规划和配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="0bd05-281">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="0bd05-282">Contoso 案例研究：紧急电话</span><span class="sxs-lookup"><span data-stu-id="0bd05-282">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="0bd05-283">介绍一个虚构的多国企业（Contoso）如何为其组织实现紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="0bd05-283">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="0bd05-284">直接路由的 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="0bd05-284">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="0bd05-285">在某些国家和地区，不能绕过公共交换电话网络 (PSTN) 提供商减少长途通话成本。</span><span class="sxs-lookup"><span data-stu-id="0bd05-285">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="0bd05-286">通过 "Location-Based 路由选择直接路由"，你可以根据其地理位置限制 Microsoft 团队用户的收费跳过。</span><span class="sxs-lookup"><span data-stu-id="0bd05-286">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="0bd05-287">有关如何规划和配置 Location-Based 路由 (LBR) 的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-287">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="0bd05-288">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0bd05-288">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="0bd05-289">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="0bd05-289">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="0bd05-290">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0bd05-290">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="0bd05-291">Contoso 案例研究： Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="0bd05-291">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="0bd05-292">介绍虚构的多国公司（Contoso）如何为其组织实施 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="0bd05-292">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="0bd05-293">语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="0bd05-293">Network topology for voice features</span></span>

<span data-ttu-id="0bd05-294">如果要为直接路由部署动态紧急呼叫或 Location-Based 路由，则必须在 Microsoft 团队中配置用于这些功能的网络设置。</span><span class="sxs-lookup"><span data-stu-id="0bd05-294">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="0bd05-295">若要了解如何配置网络区域、网络站点、网络子网和受信任的 IP 地址的网络设置，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-295">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="0bd05-296">Microsoft 团队中云语音功能的网络设置-概念和术语</span><span class="sxs-lookup"><span data-stu-id="0bd05-296">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="0bd05-297">在 Microsoft 团队中管理云语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="0bd05-297">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="0bd05-298">将现有语音解决方案迁移到团队</span><span class="sxs-lookup"><span data-stu-id="0bd05-298">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="0bd05-299">对于升级到团队的组织，最终目标是将所有用户移到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="0bd05-299">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="0bd05-300">仅当用户处于 TeamsOnly 模式时，才支持将电话系统与团队配合使用。</span><span class="sxs-lookup"><span data-stu-id="0bd05-300">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="0bd05-301">如果需要有关升级到团队的基本信息，请从此处开始：</span><span class="sxs-lookup"><span data-stu-id="0bd05-301">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="0bd05-302">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="0bd05-302">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="0bd05-303">关于升级框架</span><span class="sxs-lookup"><span data-stu-id="0bd05-303">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="0bd05-304">从 Skype for Business 升级到团队-面向 IT 管理员</span><span class="sxs-lookup"><span data-stu-id="0bd05-304">Upgrade from Skype for Business to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-overview.md)

<span data-ttu-id="0bd05-305">迁移语音解决方案时，在移动到 TeamsOnly 模式时有四种可能的通话方案：</span><span class="sxs-lookup"><span data-stu-id="0bd05-305">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="0bd05-306">[**Skype For Business Online 中使用 Microsoft 通话计划的用户**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="0bd05-306">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="0bd05-307">升级后，此用户将继续拥有 Microsoft 通话计划。</span><span class="sxs-lookup"><span data-stu-id="0bd05-307">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="0bd05-308">**[Skype For business Online 中的用户，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)通过 skype for Business 本地或云连接器版本使用本地语音功能**。</span><span class="sxs-lookup"><span data-stu-id="0bd05-308">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="0bd05-309">用户对团队的升级需要与用户迁移以直接路由，以确保 TeamsOnly 用户具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="0bd05-309">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="0bd05-310">**[使用企业语音的 Skype for business Online 中的用户](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，这些用户将移动到联机状态并保持本地 PSTN 连接**。</span><span class="sxs-lookup"><span data-stu-id="0bd05-310">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="0bd05-311">将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并通过将用户迁移到直接路由来协调该用户。</span><span class="sxs-lookup"><span data-stu-id="0bd05-311">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="0bd05-312">**[使用企业语音的 Skype for business Online 中的用户](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，这些用户将移动到联机并使用 Microsoft 通话计划**。</span><span class="sxs-lookup"><span data-stu-id="0bd05-312">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="0bd05-313">将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并使用) 该用户电话号码的端口与 Microsoft 通话计划或 B 进行协调，) 从可用区域分配新的订户号码。</span><span class="sxs-lookup"><span data-stu-id="0bd05-313">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="0bd05-314">有关如何为每种情况实现您的语音迁移的详细信息 &mdash; ，包括有关何时需要设置混合连接的信息以及如何将具有本地语音功能的用户迁移到直接路由， &mdash; 请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-314">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="0bd05-315">升级到团队时的 PSTN 注意事项-适用于 IT 管理员</span><span class="sxs-lookup"><span data-stu-id="0bd05-315">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="0bd05-316">Contoso 语音迁移案例研究</span><span class="sxs-lookup"><span data-stu-id="0bd05-316">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="0bd05-317">案例研究介绍了一个虚构的多国公司（Contoso）如何为其组织实施团队语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="0bd05-317">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="0bd05-318">其中包含以下文章：</span><span class="sxs-lookup"><span data-stu-id="0bd05-318">It contains the following articles:</span></span>

  - [<span data-ttu-id="0bd05-319">团队升级计划</span><span class="sxs-lookup"><span data-stu-id="0bd05-319">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="0bd05-320">电话系统和 PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="0bd05-320">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="0bd05-321">基于位置的路由实现</span><span class="sxs-lookup"><span data-stu-id="0bd05-321">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="0bd05-322">紧急电话</span><span class="sxs-lookup"><span data-stu-id="0bd05-322">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="0bd05-323">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="0bd05-323">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="0bd05-324">音频会议</span><span class="sxs-lookup"><span data-stu-id="0bd05-324">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)












