---
title: 在 Microsoft Teams 中规划语音解决方案
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
description: 了解有关 Microsoft Teams 云语音功能以及你将为组织做出部署决策的信息。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 213950b808d781e8566e1ffae6f6075bb7b3371b
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686448"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="deed6-103">规划 Teams 语音解决方案</span><span class="sxs-lookup"><span data-stu-id="deed6-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="deed6-104">本文帮助你确定哪个 Microsoft 语音解决方案适合你的组织。</span><span class="sxs-lookup"><span data-stu-id="deed6-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="deed6-105">确定后，本文提供了一个路线图用于实现所选解决方案的内容。</span><span class="sxs-lookup"><span data-stu-id="deed6-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

> [!NOTE]
> <span data-ttu-id="deed6-106">有关规划 Teams 语音解决方案作为从 Skype for Business Server 升级到 Teams 总体计划的一部分的指导，请参阅从本地 Skype for Business 升级到 Teams 的 [PSTN 注意事项](upgrade-to-Teams-on-prem-pstn-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="deed6-106">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-Teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="deed6-107">你可能希望使用具有呼叫计划 &mdash; 的最简单解决方案电话系统。</span><span class="sxs-lookup"><span data-stu-id="deed6-107">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="deed6-108">这是 Microsoft 的全云解决方案，可提供 Private Branch Exchange (PBX) 功能，并呼叫公用电话交换网 (PSTN) ，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="deed6-108">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="deed6-109">借助此解决方案，Microsoft 是你的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="deed6-109">With this solution, Microsoft is your PSTN carrier.</span></span>

![图 1 显示具有通话套餐的电话系统](media/voice-solutions-simple.png)

<span data-ttu-id="deed6-111">如果你对以下内容回答"是"，则"电话系统与通话套餐"是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="deed6-111">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="deed6-112">呼叫计划在你的地区可用。</span><span class="sxs-lookup"><span data-stu-id="deed6-112">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="deed6-113">无需保留当前 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="deed6-113">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="deed6-114">您希望使用 Microsoft 托管的 PSTN 访问权限。</span><span class="sxs-lookup"><span data-stu-id="deed6-114">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="deed6-115">但是，情况可能更复杂。</span><span class="sxs-lookup"><span data-stu-id="deed6-115">However, your situation might be more complex.</span></span> <span data-ttu-id="deed6-116">例如，你可能在呼叫计划不可用的位置设有办公室。</span><span class="sxs-lookup"><span data-stu-id="deed6-116">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="deed6-117">或者，可能需要一个支持复杂、跨区域部署的组合解决方案，对不同的地理位置有不同的要求。</span><span class="sxs-lookup"><span data-stu-id="deed6-117">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="deed6-118">Microsoft 支持组合解决方案：</span><span class="sxs-lookup"><span data-stu-id="deed6-118">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="deed6-119">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="deed6-119">Phone System with Calling Plan</span></span>
- <span data-ttu-id="deed6-120">具有自己的 PSTN 运营商的电话系统与直接路由</span><span class="sxs-lookup"><span data-stu-id="deed6-120">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="deed6-121">将电话系统与通话计划结合使用和电话系统与直接路由的组合解决方案</span><span class="sxs-lookup"><span data-stu-id="deed6-121">A combination solution that uses both Phone System with Calling Plan and Phone System with Direct Routing</span></span>

## <a name="what-do-you-need-to-read"></a><span data-ttu-id="deed6-122">需要阅读哪些信息？</span><span class="sxs-lookup"><span data-stu-id="deed6-122">What do you need to read?</span></span>

<span data-ttu-id="deed6-123">**全部必需。**</span><span class="sxs-lookup"><span data-stu-id="deed6-123">**Required for all.**</span></span> <span data-ttu-id="deed6-124">本文中的某些部分适用于所有组织。</span><span class="sxs-lookup"><span data-stu-id="deed6-124">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="deed6-125">例如，每个人都应阅读有关电话系统的信息，并了解用于连接到 PSTN 公用电话交换 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="deed6-125">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="deed6-126">全部必需</span><span class="sxs-lookup"><span data-stu-id="deed6-126">Required for all</span></span> | <span data-ttu-id="deed6-127">说明</span><span class="sxs-lookup"><span data-stu-id="deed6-127">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="deed6-128">**电话系统**</span><span class="sxs-lookup"><span data-stu-id="deed6-128">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="deed6-129">Microsoft 的技术，用于通过 Microsoft Teams 在 Microsoft 365 云 (PBX) 实现呼叫控制和专用交换机交换功能。</span><span class="sxs-lookup"><span data-stu-id="deed6-129">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="deed6-130">**公用电话交换网 (PSTN) 连接选项**</span><span class="sxs-lookup"><span data-stu-id="deed6-130">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="deed6-131">可以选择使用 Microsoft 作为电话运营商，还是使用直接路由将你自己的电话运营商连接到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="deed6-131">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing.</span></span> <span data-ttu-id="deed6-132">PSTN 连接选项与电话系统相结合，可让用户进行全球电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="deed6-132">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="deed6-133">**取决于你的要求。**</span><span class="sxs-lookup"><span data-stu-id="deed6-133">**Depending on your requirements.**</span></span> <span data-ttu-id="deed6-134">本文中的某些部分与现有的部署和要求相关。</span><span class="sxs-lookup"><span data-stu-id="deed6-134">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="deed6-135">例如，Location-Based不允许通行费绕过的地理位置中的直接路由客户需要直接路由。</span><span class="sxs-lookup"><span data-stu-id="deed6-135">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="deed6-136">请考虑可能需要以下哪些附加配置：</span><span class="sxs-lookup"><span data-stu-id="deed6-136">Consider which of these additional configurations you might need:</span></span>

![图 2 显示了其他语音组件，例如来自 Microsoft 的电话号码、拨号计划和呼叫路由等。](media/voice-consider-additional-components.png)

| <span data-ttu-id="deed6-138">根据要求</span><span class="sxs-lookup"><span data-stu-id="deed6-138">Depending on your requirements</span></span> | <span data-ttu-id="deed6-139">说明</span><span class="sxs-lookup"><span data-stu-id="deed6-139">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="deed6-140">**Microsoft 提供的电话号码**</span><span class="sxs-lookup"><span data-stu-id="deed6-140">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="deed6-141">如何从 Microsoft 获取和管理电话号码，以及如何将现有号码转移到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="deed6-141">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="deed6-142">如果需要获取 Microsoft 呼叫计划的电话号码、转移现有号码、获取服务号码等，请阅读此内容。</span><span class="sxs-lookup"><span data-stu-id="deed6-142">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="deed6-143">**拨号计划和呼叫路由**</span><span class="sxs-lookup"><span data-stu-id="deed6-143">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="deed6-144">如何配置和管理将拨号电话号码转换为备用格式的拨号计划 (通常为 E.164 格式) 呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="deed6-144">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="deed6-145">如果你需要了解什么是拨号计划以及是否需要为组织指定拨号计划，请阅读此说明。</span><span class="sxs-lookup"><span data-stu-id="deed6-145">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="deed6-146">**紧急呼叫**</span><span class="sxs-lookup"><span data-stu-id="deed6-146">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="deed6-147">如何管理和配置紧急呼叫 &mdash; ，具体取决于 PSTN 连接选项。</span><span class="sxs-lookup"><span data-stu-id="deed6-147">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="deed6-148">如果使用 Microsoft 呼叫计划或直接路由，并且需要了解如何为组织管理紧急呼叫，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="deed6-148">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="deed6-149">**用于直接路由的基于位置的路由**</span><span class="sxs-lookup"><span data-stu-id="deed6-149">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="deed6-150">如何使用 LBR Location-Based路由 (，) 根据地理位置限制 Microsoft Teams 用户的通行费绕过。</span><span class="sxs-lookup"><span data-stu-id="deed6-150">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="deed6-151">如果组织在不允许通行费绕过的位置使用直接路由，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="deed6-151">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="deed6-152">**云语音功能的网络拓扑**</span><span class="sxs-lookup"><span data-stu-id="deed6-152">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="deed6-153">如果组织为直接Location-Based或 (呼叫) LBR 路由服务，则必须配置网络设置，以在 Microsoft Teams 中与这些功能一同使用。</span><span class="sxs-lookup"><span data-stu-id="deed6-153">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="deed6-154">如果要为直接路由实现 LBR，或者使用呼叫计划或直接路由实现动态紧急呼叫，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="deed6-154">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="deed6-155">**迁移现有语音解决方案**</span><span class="sxs-lookup"><span data-stu-id="deed6-155">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="deed6-156">将语音解决方案迁移到 Teams 时需考虑的问题。</span><span class="sxs-lookup"><span data-stu-id="deed6-156">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="deed6-157">如果要从现有语音解决方案迁移到 Teams，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="deed6-157">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="deed6-158">本文重点介绍 Microsoft Teams 的语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="deed6-158">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="deed6-159">虽然 Skype for Business Online 解决方案 ([如 Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) 电话解决方案) 中所述，但必须了解 Skype for Business Online 将于 2021 年 7 月 31 日停用。</span><span class="sxs-lookup"><span data-stu-id="deed6-159">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="deed6-160">在此日期之后，Skype for Business Online 服务将无法再访问。</span><span class="sxs-lookup"><span data-stu-id="deed6-160">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="deed6-161">此外，将不再支持本地环境（无论是通过 Skype for Business Server 还是 Cloud Connector Edition 和 Skype for Business Online）建立 PSTN &mdash; &mdash; 连接。</span><span class="sxs-lookup"><span data-stu-id="deed6-161">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="deed6-162">本文介绍 Teams 语音解决方案，以及如何在必要时使用直接路由将本地电话网络连接到 Teams。</span><span class="sxs-lookup"><span data-stu-id="deed6-162">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing.</span></span>


## <a name="phone-system"></a><span data-ttu-id="deed6-163">电话系统</span><span class="sxs-lookup"><span data-stu-id="deed6-163">Phone System</span></span>

<span data-ttu-id="deed6-164">电话系统是 Microsoft 的技术，用于通过 Microsoft Teams 在 Microsoft 365 或 Office 365 云中启用呼叫控制和专用交换机 (PBX) 功能。</span><span class="sxs-lookup"><span data-stu-id="deed6-164">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="deed6-165">电话系统适用于 Teams 或 Skype for Business 客户端和经过认证的设备。</span><span class="sxs-lookup"><span data-stu-id="deed6-165">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="deed6-166">使用电话系统，可以使用直接从 Microsoft 365 或 Office 365 提供的一组功能替换现有 PBX 系统。</span><span class="sxs-lookup"><span data-stu-id="deed6-166">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="deed6-167">组织中用户之间的呼叫在电话系统内部处理，永远不会转到 PSTN (公用电话) 。</span><span class="sxs-lookup"><span data-stu-id="deed6-167">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="deed6-168">这适用于组织中位于不同地理区域的用户之间的呼叫，消除了这些内部呼叫的远程成本。</span><span class="sxs-lookup"><span data-stu-id="deed6-168">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="deed6-169">本文介绍以下电话系统关键特性和功能，以及需要考虑的部署决策：</span><span class="sxs-lookup"><span data-stu-id="deed6-169">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="deed6-170">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="deed6-170">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="deed6-171">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="deed6-171">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="deed6-172">调用标识</span><span class="sxs-lookup"><span data-stu-id="deed6-172">Calling identity</span></span>](#calling-identity)

![图 3 显示电话系统包含自动助理和呼叫查询、云语音邮件和呼叫标识](media/phone-system-contains.png)

<span data-ttu-id="deed6-174">有关所有电话系统功能以及如何设置电话系统的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-174">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="deed6-175">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="deed6-175">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="deed6-176">在组织中设置电话系统</span><span class="sxs-lookup"><span data-stu-id="deed6-176">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="deed6-177">介绍如何购买和分配电话系统许可证、管理电话号码以及设置免费号码的通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="deed6-177">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="deed6-178">有关管理受支持设备的信息，请参阅"在[Microsoft Teams](devices/device-management.md)和 Teams 市场中管理[设备"。](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="deed6-178">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="deed6-179">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="deed6-179">Auto attendants and Call queues</span></span>

<span data-ttu-id="deed6-180">自动助理允许您设置菜单选项，以便根据呼叫者输入路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="deed6-180">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="deed6-181">呼叫队列正在等待呼叫者的区域。</span><span class="sxs-lookup"><span data-stu-id="deed6-181">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="deed6-182">自动助理和呼叫队列一起使用可以轻松地将呼叫者路由到组织中相应的人员或部门。</span><span class="sxs-lookup"><span data-stu-id="deed6-182">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="deed6-183">有关自动助理和呼叫队列的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-183">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="deed6-184">规划 Teams 自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="deed6-184">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="deed6-185">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="deed6-185">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="deed6-186">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="deed6-186">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="deed6-187">Contoso 案例研究：自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="deed6-187">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="deed6-188">介绍虚构的多语言公司 Contoso 如何为语音解决方案实现自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="deed6-188">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="deed6-189">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="deed6-189">Cloud Voicemail</span></span>

<span data-ttu-id="deed6-190">云语音邮件（由 Azure 语音邮件服务提供）仅支持将语音邮件置于 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="deed6-190">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="deed6-191">它不支持第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="deed6-191">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="deed6-192">云语音邮件包括语音邮件听录，默认情况下为贵组织的所有用户启用。</span><span class="sxs-lookup"><span data-stu-id="deed6-192">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="deed6-193">你的业务需求可能要求你为特定用户或整个组织所有人禁用语音邮件转录。</span><span class="sxs-lookup"><span data-stu-id="deed6-193">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="deed6-194">对于仅联机用户，为用户分配电话系统许可证后，会自动设置和预配云语音邮件。</span><span class="sxs-lookup"><span data-stu-id="deed6-194">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="deed6-195">对于具有 Exchange 邮箱的电话系统用户，需要执行额外的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="deed6-195">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="deed6-196">有关云语音邮件及其配置的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-196">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="deed6-197">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="deed6-197">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="deed6-198">在组织中设置语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="deed6-198">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="deed6-199">调用标识</span><span class="sxs-lookup"><span data-stu-id="deed6-199">Calling identity</span></span>

<span data-ttu-id="deed6-200">默认情况下，所有出站呼叫使用分配的电话号码作为呼叫 (呼叫方 ID) 。</span><span class="sxs-lookup"><span data-stu-id="deed6-200">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="deed6-201">呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="deed6-201">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="deed6-202">有关配置呼叫者 ID 或更改或阻止呼叫者 ID 的信息，请参阅"为[用户设置呼叫方 ID"。](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="deed6-202">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="deed6-203">公用电话交换网络连接选项</span><span class="sxs-lookup"><span data-stu-id="deed6-203">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="deed6-204">电话系统为组织提供完整的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="deed6-204">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="deed6-205">但是，若要让用户在组织外部进行呼叫，你需要将电话系统连接到 PSTN (公用电话) 。</span><span class="sxs-lookup"><span data-stu-id="deed6-205">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="deed6-206">若要将电话系统连接到 PSTN，可以选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="deed6-206">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="deed6-207">[**具有通话套餐的电话系统**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="deed6-207">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="deed6-208">使用 Microsoft 作为 PSTN 运营商的全云解决方案。</span><span class="sxs-lookup"><span data-stu-id="deed6-208">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="deed6-209">[**使用直接路由将本地**](#phone-system-with-own-pstn-carrier-with-direct-routing) 环境连接到 Teams，使用自己的 PSTN 运营商的电话系统。</span><span class="sxs-lookup"><span data-stu-id="deed6-209">[**Phone System with your own PSTN carrier**](#phone-system-with-own-pstn-carrier-with-direct-routing) by using Direct Routing to connect your on-premises environment to Teams.</span></span>

<span data-ttu-id="deed6-210">还可以选择选项组合，这样，就可以为复杂环境设计解决方案，或者管理多步骤迁移 (以后进行迁移) 。</span><span class="sxs-lookup"><span data-stu-id="deed6-210">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="deed6-211">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="deed6-211">Phone System with Calling Plan</span></span> 

<span data-ttu-id="deed6-212">如本文前面所述，具有通话计划的电话系统是 Microsoft 为 Teams 用户提供的全云语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="deed6-212">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="deed6-213">这是将 Microsoft Phone System 连接到公用电话交换网 (PSTN) 以启用对世界各地的座机和移动电话的呼叫的最简单选项。</span><span class="sxs-lookup"><span data-stu-id="deed6-213">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="deed6-214">通过此选项，Microsoft (PBX) 功能，并充当 PSTN 运营商，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="deed6-214">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![图 4 显示电话系统与自动助理、呼叫队列、呼叫者 ID 等，以及 Microsoft 作为 PSTN 运营商](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="deed6-216">如果你对以下内容回答"是"，则"电话系统与通话套餐"是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="deed6-216">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="deed6-217">呼叫计划在你的地区可用。</span><span class="sxs-lookup"><span data-stu-id="deed6-217">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="deed6-218">无需保留当前 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="deed6-218">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="deed6-219">您希望使用 Microsoft 托管的 PSTN 访问权限。</span><span class="sxs-lookup"><span data-stu-id="deed6-219">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="deed6-220">使用此选项：</span><span class="sxs-lookup"><span data-stu-id="deed6-220">With this option:</span></span> 

- <span data-ttu-id="deed6-221">通过添加的国内或国际呼叫计划，你可以获取 Microsoft Phone 系统 (根据获得许可的服务级别拨打世界各地的) 。</span><span class="sxs-lookup"><span data-stu-id="deed6-221">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="deed6-222">由于呼叫计划在 &mdash; Microsoft 365 或 Office 365 外运行，因此不需要部署或维护本地部署。</span><span class="sxs-lookup"><span data-stu-id="deed6-222">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="deed6-223">注意：如有必要，可以选择通过直接路由连接受支持的会话边界控制器 (SBC) ，以与 SBC 支持的第三方 PBX、模拟设备和其他第三方电话设备进行互操作性。</span><span class="sxs-lookup"><span data-stu-id="deed6-223">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="deed6-224">此选项需要不间断地连接到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="deed6-224">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="deed6-225">有关呼叫计划详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-225">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="deed6-226">哪种通话套餐适合你？</span><span class="sxs-lookup"><span data-stu-id="deed6-226">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="deed6-227">如何购买通话套餐</span><span class="sxs-lookup"><span data-stu-id="deed6-227">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="deed6-228">通话套餐的国家和地区可用性</span><span class="sxs-lookup"><span data-stu-id="deed6-228">Country and region availability for Calling Plan</span></span>](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [<span data-ttu-id="deed6-229">设置呼叫计划</span><span class="sxs-lookup"><span data-stu-id="deed6-229">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="deed6-230">使用直接路由的具有自己的 PSTN 运营商的电话系统</span><span class="sxs-lookup"><span data-stu-id="deed6-230">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="deed6-231">此选项使用直接路由将 Microsoft Phone 系统连接到电话网络，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="deed6-231">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![图 5 显示具有直接路由的电话系统](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="deed6-233">如果对以下问题回答"是"，则使用直接路由的电话系统是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="deed6-233">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="deed6-234">你想要将 Teams 与手机系统一同使用。</span><span class="sxs-lookup"><span data-stu-id="deed6-234">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="deed6-235">你需要保留当前的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="deed6-235">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="deed6-236">您希望混合路由，一些呼叫通过呼叫计划进行，一些呼叫通过运营商进行。</span><span class="sxs-lookup"><span data-stu-id="deed6-236">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="deed6-237">你需要与第三方 PBX 和/或设备（例如我们的开销分页器、模拟设备等）互操作。</span><span class="sxs-lookup"><span data-stu-id="deed6-237">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="deed6-238">使用此选项：</span><span class="sxs-lookup"><span data-stu-id="deed6-238">With this option:</span></span>

- <span data-ttu-id="deed6-239">将自己支持的 SBC 连接到 Microsoft Phone System，而无需其他本地软件。</span><span class="sxs-lookup"><span data-stu-id="deed6-239">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="deed6-240">几乎可以将任何电话运营商与 Microsoft Phone System 一同使用。</span><span class="sxs-lookup"><span data-stu-id="deed6-240">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="deed6-241">你可以选择配置和管理此选项，也可以由运营商或合作伙伴配置和管理 (询问你的运营商或合作伙伴是否提供此选项) 。</span><span class="sxs-lookup"><span data-stu-id="deed6-241">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="deed6-242">可以在电话设备（例如第三方 PBX 和模拟设备和 Microsoft Phone 系统）之间配置 &mdash; &mdash; 互操作性。</span><span class="sxs-lookup"><span data-stu-id="deed6-242">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="deed6-243">此选项需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="deed6-243">This option requires the following:</span></span>

- <span data-ttu-id="deed6-244">不间断连接到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="deed6-244">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="deed6-245">部署和维护支持的 SBC。</span><span class="sxs-lookup"><span data-stu-id="deed6-245">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="deed6-246">与第三方运营商签署合同。</span><span class="sxs-lookup"><span data-stu-id="deed6-246">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="deed6-247"> (，除非部署为为使用呼叫计划的电话系统上的用户提供第三方 PBX、模拟设备或其他电话设备连接的选项) </span><span class="sxs-lookup"><span data-stu-id="deed6-247">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="deed6-248">有关直接路由详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-248">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="deed6-249">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="deed6-249">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="deed6-250">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="deed6-250">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="deed6-251">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="deed6-251">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="deed6-252">管理用于直接路由的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="deed6-252">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="deed6-253">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="deed6-253">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="deed6-254">经认证可用于直接路由的会话边界控制器列表</span><span class="sxs-lookup"><span data-stu-id="deed6-254">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="deed6-255">Microsoft 提供的电话号码</span><span class="sxs-lookup"><span data-stu-id="deed6-255">Phone numbers from Microsoft</span></span>

<span data-ttu-id="deed6-256">Microsoft 提供两种类型的电话号码：订阅者 (用户) 号码（可分配给您的组织中的用户）和服务号码（以收费和免费服务号码提供）。</span><span class="sxs-lookup"><span data-stu-id="deed6-256">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="deed6-257">服务号码的并发呼叫容量高于订阅者号码，可分配给音频会议、自动助理或呼叫队列等服务。</span><span class="sxs-lookup"><span data-stu-id="deed6-257">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="deed6-258">需要确定：</span><span class="sxs-lookup"><span data-stu-id="deed6-258">You will need to decide:</span></span>

- <span data-ttu-id="deed6-259">哪些用户位置需要 Microsoft 提供的新电话号码？</span><span class="sxs-lookup"><span data-stu-id="deed6-259">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="deed6-260">我需要哪种类型的 (或) 电话号码？</span><span class="sxs-lookup"><span data-stu-id="deed6-260">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="deed6-261">如何将现有电话号码移植到 Teams？</span><span class="sxs-lookup"><span data-stu-id="deed6-261">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="deed6-262">有关管理组织中电话号码（包括获取新号码或转移退出号码）的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-262">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="deed6-263">管理组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="deed6-263">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="deed6-264">用于呼叫计划的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="deed6-264">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="deed6-265">为用户获取电话号码</span><span class="sxs-lookup"><span data-stu-id="deed6-265">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="deed6-266">将电话号码转移到 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="deed6-266">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="deed6-267">拨号计划和呼叫路由</span><span class="sxs-lookup"><span data-stu-id="deed6-267">Dial plans and call routing</span></span>

<span data-ttu-id="deed6-268">拨号计划是一组规范化规则，用于将拨打的电话号码转换为备用格式 (通常为 E.164 格式) 呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="deed6-268">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="deed6-269">需要确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="deed6-269">You will need to decide the following:</span></span> 

- <span data-ttu-id="deed6-270">我的组织是否需要自定义拨号计划？</span><span class="sxs-lookup"><span data-stu-id="deed6-270">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="deed6-271">哪些用户需要自定义拨号计划？</span><span class="sxs-lookup"><span data-stu-id="deed6-271">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="deed6-272">应该将哪个租户拨号计划分配给每个用户？</span><span class="sxs-lookup"><span data-stu-id="deed6-272">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="deed6-273">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-273">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="deed6-274">什么是拨号计划？</span><span class="sxs-lookup"><span data-stu-id="deed6-274">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="deed6-275">规划租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="deed6-275">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="deed6-276">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="deed6-276">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="deed6-277">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="deed6-277">Emergency calling</span></span>

<span data-ttu-id="deed6-278">你的紧急呼叫配置方式因 PSTN 连接选项（Microsoft 呼叫计划或直接路由）不同。</span><span class="sxs-lookup"><span data-stu-id="deed6-278">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="deed6-279">Microsoft 呼叫计划和电话系统直接路由的动态紧急呼叫提供配置和路由紧急呼叫以及根据 Teams 客户端的当前位置通知安全人员的功能。</span><span class="sxs-lookup"><span data-stu-id="deed6-279">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="deed6-280">有关紧急呼叫概念和术语以及如何配置动态紧急呼叫的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-280">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="deed6-281">管理紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="deed6-281">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="deed6-282">规划和配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="deed6-282">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="deed6-283">Contoso 案例研究：紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="deed6-283">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="deed6-284">介绍虚构的多语言公司 Contoso 如何为组织实施紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="deed6-284">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="deed6-285">Location-Based直接路由的路由</span><span class="sxs-lookup"><span data-stu-id="deed6-285">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="deed6-286">在某些国家和地区，绕过公用电话交换网和 PSTN (PSTN) 降低远程呼叫成本非法。</span><span class="sxs-lookup"><span data-stu-id="deed6-286">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="deed6-287">Location-Based路由允许根据 Microsoft Teams 用户的地理位置限制免验证收费。</span><span class="sxs-lookup"><span data-stu-id="deed6-287">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="deed6-288">若要详细了解如何为 LBR Location-Based和配置 (路由) ，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-288">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="deed6-289">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="deed6-289">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="deed6-290">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="deed6-290">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="deed6-291">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="deed6-291">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="deed6-292">Contoso 案例研究：Location-Based路由</span><span class="sxs-lookup"><span data-stu-id="deed6-292">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="deed6-293">介绍虚拟的多语言公司 Contoso 如何为Location-Based实现虚拟路由。</span><span class="sxs-lookup"><span data-stu-id="deed6-293">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="deed6-294">语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="deed6-294">Network topology for voice features</span></span>

<span data-ttu-id="deed6-295">如果要为直接路由部署动态紧急呼叫或Location-Based路由，则必须配置网络设置，以在 Microsoft Teams 中与这些功能一同使用。</span><span class="sxs-lookup"><span data-stu-id="deed6-295">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="deed6-296">若要了解如何为网络区域、网络站点、网络子网和受信任的 IP 地址配置网络设置，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-296">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="deed6-297">Microsoft Teams 中云语音功能的网络设置 - 概念和术语</span><span class="sxs-lookup"><span data-stu-id="deed6-297">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="deed6-298">在 Microsoft Teams 中管理云语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="deed6-298">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="deed6-299">将现有语音解决方案迁移到 Teams</span><span class="sxs-lookup"><span data-stu-id="deed6-299">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="deed6-300">对于要升级到 Teams 的组织，最终目标是将所有用户移动到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="deed6-300">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="deed6-301">仅在用户位于 TeamsOnly 模式下时，才支持将电话系统与 Teams 一同使用。</span><span class="sxs-lookup"><span data-stu-id="deed6-301">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="deed6-302">如果需要有关升级到 Teams 的基本信息，请从此处开始：</span><span class="sxs-lookup"><span data-stu-id="deed6-302">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="deed6-303">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="deed6-303">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="deed6-304">关于升级框架</span><span class="sxs-lookup"><span data-stu-id="deed6-304">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="deed6-305">从 Skype for Business 升级到 Teams - 适用于 IT 管理员</span><span class="sxs-lookup"><span data-stu-id="deed6-305">Upgrade from Skype for Business to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-overview.md)

<span data-ttu-id="deed6-306">迁移语音解决方案时，在迁移到 TeamsOnly 模式时，有四种可能的通话方案：</span><span class="sxs-lookup"><span data-stu-id="deed6-306">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="deed6-307">[**Skype for Business Online 中的用户，具有 Microsoft 呼叫计划**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="deed6-307">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="deed6-308">升级后，此用户将继续拥有 Microsoft 呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="deed6-308">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="deed6-309">**[Skype for Business Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 中的用户，通过本地 Skype for Business 或 Cloud Connector Edition 提供本地语音功能。</span><span class="sxs-lookup"><span data-stu-id="deed6-309">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="deed6-310">用户升级到 Teams 需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="deed6-310">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="deed6-311">**[本地 Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** 中具有 企业语音 的用户，该用户将移动到联机并保留本地 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="deed6-311">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="deed6-312">将该用户迁移到 Teams 需要将用户本地 Skype for Business 帐户移动到云，并协调该移动，同时将用户迁移到直接路由。</span><span class="sxs-lookup"><span data-stu-id="deed6-312">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="deed6-313">**[本地 Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** 中具有 企业语音 的用户，该用户将移动到在线，使用 Microsoft 呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="deed6-313">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="deed6-314">将该用户迁移到 Teams 需要将用户本地 Skype for Business 帐户移动到云，并将该移动与 A 协调) 将该用户的电话号码的端口转移到 Microsoft 呼叫计划，或者 B) 从可用区域分配新的订阅者号码。</span><span class="sxs-lookup"><span data-stu-id="deed6-314">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="deed6-315">若要详细了解如何针对每种方案实现语音迁移，包括有关何时需要设置混合连接以及如何将具有本地语音功能的用户迁移到直接路由的信息，请参阅 &mdash; &mdash; 以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-315">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="deed6-316">升级到 Teams 时 PSTN 注意事项 - 适用于 IT 管理员</span><span class="sxs-lookup"><span data-stu-id="deed6-316">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="deed6-317">Contoso 语音迁移案例研究</span><span class="sxs-lookup"><span data-stu-id="deed6-317">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="deed6-318">案例研究介绍虚构的多语言公司 Contoso 如何为组织实现 Teams 语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="deed6-318">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="deed6-319">它包含以下文章：</span><span class="sxs-lookup"><span data-stu-id="deed6-319">It contains the following articles:</span></span>

  - [<span data-ttu-id="deed6-320">Teams 升级计划</span><span class="sxs-lookup"><span data-stu-id="deed6-320">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="deed6-321">电话系统和 PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="deed6-321">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="deed6-322">基于位置的路由实现</span><span class="sxs-lookup"><span data-stu-id="deed6-322">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="deed6-323">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="deed6-323">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="deed6-324">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="deed6-324">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="deed6-325">音频会议</span><span class="sxs-lookup"><span data-stu-id="deed6-325">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)












