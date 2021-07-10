---
title: 在语音服务中规划Microsoft Teams
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
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 详细了解云Microsoft Teams功能和将为组织做出部署决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95b8f60f9d664432fbb68c48ee61d6f26902eeae
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354378"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="8bd30-103">规划Teams语音解决方案</span><span class="sxs-lookup"><span data-stu-id="8bd30-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="8bd30-104">本文帮助你确定哪个 Microsoft 语音解决方案适合你的组织。</span><span class="sxs-lookup"><span data-stu-id="8bd30-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="8bd30-105">确定后，本文提供内容路线图，实现所选解决方案。</span><span class="sxs-lookup"><span data-stu-id="8bd30-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

<span data-ttu-id="8bd30-106">你可能希望使用呼叫计划 &mdash; 电话系统最简单的解决方案。</span><span class="sxs-lookup"><span data-stu-id="8bd30-106">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="8bd30-107">这是 Microsoft 的全云解决方案，可提供专用分支 Exchange (PBX) 功能，并呼叫公用电话交换网 (PSTN) ，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="8bd30-107">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="8bd30-108">借助此解决方案，Microsoft 是你的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="8bd30-108">With this solution, Microsoft is your PSTN carrier.</span></span>

![图 1 电话系统套餐](media/voice-solutions-simple.png)

<span data-ttu-id="8bd30-110">如果你对以下内容回答"是"，电话系统呼叫计划"是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="8bd30-110">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="8bd30-111">呼叫计划在你的地区可用。</span><span class="sxs-lookup"><span data-stu-id="8bd30-111">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="8bd30-112">无需保留当前 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="8bd30-112">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="8bd30-113">您希望使用 Microsoft 托管的 PSTN 访问权限。</span><span class="sxs-lookup"><span data-stu-id="8bd30-113">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="8bd30-114">但是，情况可能更复杂。</span><span class="sxs-lookup"><span data-stu-id="8bd30-114">However, your situation might be more complex.</span></span> <span data-ttu-id="8bd30-115">例如，你可能在呼叫计划不可用的位置设有办公室。</span><span class="sxs-lookup"><span data-stu-id="8bd30-115">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="8bd30-116">或者，可能需要一个支持复杂、跨区域部署、对不同地理位置有不同的要求的组合解决方案。</span><span class="sxs-lookup"><span data-stu-id="8bd30-116">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="8bd30-117">Microsoft 支持解决方案的组合：</span><span class="sxs-lookup"><span data-stu-id="8bd30-117">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="8bd30-118">电话系统套餐</span><span class="sxs-lookup"><span data-stu-id="8bd30-118">Phone System with Calling Plan</span></span>
- <span data-ttu-id="8bd30-119">电话系统您的 PSTN 运营商运营商连接 (目前仅在公共 **预览版中提供)**</span><span class="sxs-lookup"><span data-stu-id="8bd30-119">Phone System with your own PSTN carrier with Operator Connect (currently available only in **public preview**)</span></span>
- <span data-ttu-id="8bd30-120">电话系统直接路由与自己的 PSTN 运营商联系</span><span class="sxs-lookup"><span data-stu-id="8bd30-120">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="8bd30-121">结合使用解决方案，将 电话系统 与呼叫计划结合使用电话系统接线员连接和/或电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="8bd30-121">A combination solution that uses Phone System with Calling Plan, Phone System with Operator Connect, and/or Phone System with Direct Routing</span></span>


## <a name="what-do-you-need-to-read"></a><span data-ttu-id="8bd30-122">需要阅读哪些信息？</span><span class="sxs-lookup"><span data-stu-id="8bd30-122">What do you need to read?</span></span>

<span data-ttu-id="8bd30-123">**全部必需。**</span><span class="sxs-lookup"><span data-stu-id="8bd30-123">**Required for all.**</span></span> <span data-ttu-id="8bd30-124">本文中的某些部分适用于所有组织。</span><span class="sxs-lookup"><span data-stu-id="8bd30-124">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="8bd30-125">例如，每个人都应该阅读有关电话系统并了解用于连接到 PSTN 公用电话交换网 (的选项) 。</span><span class="sxs-lookup"><span data-stu-id="8bd30-125">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="8bd30-126">全部必需</span><span class="sxs-lookup"><span data-stu-id="8bd30-126">Required for all</span></span> | <span data-ttu-id="8bd30-127">说明</span><span class="sxs-lookup"><span data-stu-id="8bd30-127">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="8bd30-128">**电话系统**</span><span class="sxs-lookup"><span data-stu-id="8bd30-128">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="8bd30-129">Microsoft 在云中启用呼叫控制和专用分支 Exchange (PBX) 功能的技术Microsoft 365云Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="8bd30-129">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="8bd30-130">**PSTN 公用电话交换 (PSTN) 连接选项**</span><span class="sxs-lookup"><span data-stu-id="8bd30-130">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="8bd30-131">可以选择使用 Microsoft 作为电话运营商，还是使用直接路由或接线员Microsoft Teams将你自己的电话运营商连接。</span><span class="sxs-lookup"><span data-stu-id="8bd30-131">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing or Operator Connect.</span></span> <span data-ttu-id="8bd30-132">PSTN 连接电话系统结合使用，使用户能够拨打全球电话。</span><span class="sxs-lookup"><span data-stu-id="8bd30-132">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="8bd30-133">**根据你的要求。**</span><span class="sxs-lookup"><span data-stu-id="8bd30-133">**Depending on your requirements.**</span></span> <span data-ttu-id="8bd30-134">本文和相关文章中的一些部分与现有的部署和要求相关。</span><span class="sxs-lookup"><span data-stu-id="8bd30-134">Some of the sections in this and related articles are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="8bd30-135">例如，Location-Based直接路由客户在不允许收费绕过的地理位置进行直接路由。</span><span class="sxs-lookup"><span data-stu-id="8bd30-135">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="8bd30-136">请考虑可能需要以下附加配置中的哪一种：</span><span class="sxs-lookup"><span data-stu-id="8bd30-136">Consider which of these additional configurations you might need:</span></span>

![图 2 显示了其他语音组件，电话 Microsoft 的电话号码、拨号计划和呼叫路由等。](media/voice-consider-additional-components.png)

| <span data-ttu-id="8bd30-138">根据要求</span><span class="sxs-lookup"><span data-stu-id="8bd30-138">Depending on your requirements</span></span> | <span data-ttu-id="8bd30-139">说明</span><span class="sxs-lookup"><span data-stu-id="8bd30-139">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="8bd30-140">**电话数字管理**</span><span class="sxs-lookup"><span data-stu-id="8bd30-140">**Phone number management**</span></span>](pstn-connectivity.md#phone-number-management) | <span data-ttu-id="8bd30-141">如何获取和管理电话号码因 PSTN 连接选项不同而不同。</span><span class="sxs-lookup"><span data-stu-id="8bd30-141">How to get and manage phone numbers differs depending on your PSTN connectivity option.</span></span> <span data-ttu-id="8bd30-142">如果需要获取电话号码、转移现有号码、获取服务号码等，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="8bd30-142">Read this section if you need to obtain phone numbers, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="8bd30-143">**呼叫路由和拨号计划**</span><span class="sxs-lookup"><span data-stu-id="8bd30-143">**Call routing and dial plans**</span></span>](pstn-connectivity.md#call-routing-and-dial-plans) | <span data-ttu-id="8bd30-144">如何配置和管理将拨号电话号码转换为备用格式的拨号计划 (通常为 E.164 格式) 进行呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="8bd30-144">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="8bd30-145">如果需要了解什么是拨号计划以及是否需要为组织指定拨号计划，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="8bd30-145">Read this section if you need to understand what dial plans are and whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="8bd30-146">**紧急呼叫**</span><span class="sxs-lookup"><span data-stu-id="8bd30-146">**Emergency calling**</span></span>](pstn-connectivity.md#emergency-calling) | <span data-ttu-id="8bd30-147">如何管理和配置紧急呼叫因 PSTN 连接选项的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="8bd30-147">How to manage and configure emergency calling differs depending on your PSTN connectivity option.</span></span> <span data-ttu-id="8bd30-148">如果需要了解如何为组织管理紧急呼叫，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="8bd30-148">Read this section if you need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="8bd30-149">**用于直接路由的基于位置的路由**</span><span class="sxs-lookup"><span data-stu-id="8bd30-149">**Location-Based Routing for Direct Routing**</span></span>](pstn-connectivity.md#location-based-routing-for-direct-routing) |<span data-ttu-id="8bd30-150">如何使用 LBR Location-Based路由 (，) 基于用户的地理位置Microsoft Teams免收费。</span><span class="sxs-lookup"><span data-stu-id="8bd30-150">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="8bd30-151">如果组织在不允许绕过收费站的位置使用直接路由，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="8bd30-151">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="8bd30-152">**云语音功能的网络拓扑**</span><span class="sxs-lookup"><span data-stu-id="8bd30-152">**Network topology for cloud voice features**</span></span>](pstn-connectivity.md#network-topology-for-voice-features) | <span data-ttu-id="8bd30-153">如果组织为直接路由Location-Based LBR (部署) 路由或动态紧急呼叫，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="8bd30-153">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="8bd30-154">如果要为直接路由实现 LBR，或者使用呼叫计划或直接路由实现动态紧急呼叫，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="8bd30-154">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="8bd30-155">**迁移现有语音解决方案**</span><span class="sxs-lookup"><span data-stu-id="8bd30-155">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="8bd30-156">将语音解决方案迁移到云时需考虑Teams。</span><span class="sxs-lookup"><span data-stu-id="8bd30-156">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="8bd30-157">如果要从现有语音解决方案迁移到现有语音解决方案，请阅读此Teams。</span><span class="sxs-lookup"><span data-stu-id="8bd30-157">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 

> [!Important]
> <span data-ttu-id="8bd30-158">本文重点介绍语音解决方案与Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="8bd30-158">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="8bd30-159">虽然具有 Skype for Business Online 的解决方案仍然可用，但必须了解 Skype for Business Online 将于 2021 年 7 月 31 日停用。</span><span class="sxs-lookup"><span data-stu-id="8bd30-159">While solutions with Skype for Business Online are still available, it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="8bd30-160">该日期之后，Skype for Business不再可访问联机服务。</span><span class="sxs-lookup"><span data-stu-id="8bd30-160">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="8bd30-161">此外，将不再支持本地环境之间的 PSTN 连接 &mdash; Skype for Business Server云连接器版本和 Skype for Business Online &mdash; 连接。</span><span class="sxs-lookup"><span data-stu-id="8bd30-161">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="8bd30-162">本文介绍Teams语音解决方案，以及如何在必要时使用直接路由或接线员Teams连接本地电话连接。</span><span class="sxs-lookup"><span data-stu-id="8bd30-162">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing or Operator Connect.</span></span>


## <a name="phone-system"></a><span data-ttu-id="8bd30-163">电话系统</span><span class="sxs-lookup"><span data-stu-id="8bd30-163">Phone System</span></span>

<span data-ttu-id="8bd30-164">电话系统是 Microsoft 的技术，用于通过 Microsoft Teams 在 Microsoft 365 云中启用呼叫控制和专用分支 Exchange (PB) X Microsoft 365功能。</span><span class="sxs-lookup"><span data-stu-id="8bd30-164">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="8bd30-165">电话系统适用于Teams或Skype for Business客户端和认证设备。</span><span class="sxs-lookup"><span data-stu-id="8bd30-165">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="8bd30-166">电话系统将现有 PBX 系统替换为一组直接从 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8bd30-166">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365.</span></span> 

<span data-ttu-id="8bd30-167">您的组织中的用户之间的呼叫在内部处理电话系统，永远不会转到 PSTN (电话) 。</span><span class="sxs-lookup"><span data-stu-id="8bd30-167">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="8bd30-168">这适用于组织中位于不同地理区域的用户之间的呼叫，消除了这些内部呼叫的远程成本。</span><span class="sxs-lookup"><span data-stu-id="8bd30-168">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="8bd30-169">本文介绍以下电话系统特性和功能，以及需要考虑的部署决策：</span><span class="sxs-lookup"><span data-stu-id="8bd30-169">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="8bd30-170">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="8bd30-170">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="8bd30-171">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="8bd30-171">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="8bd30-172">调用标识</span><span class="sxs-lookup"><span data-stu-id="8bd30-172">Calling identity</span></span>](#calling-identity)

![图 3 电话系统包含自动助理和呼叫查询、云语音邮件和呼叫标识](media/phone-system-contains.png)

<span data-ttu-id="8bd30-174">有关所有电话系统功能以及如何设置电话系统，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8bd30-174">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="8bd30-175">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="8bd30-175">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="8bd30-176">在组织中设置电话系统</span><span class="sxs-lookup"><span data-stu-id="8bd30-176">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="8bd30-177">介绍如何购买和分配电话系统、管理电话号码以及设置免费号码的通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="8bd30-177">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="8bd30-178">有关管理受支持设备的信息，请参阅[在](devices/device-management.md)Microsoft Teams 和 Teams[中管理设备](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="8bd30-178">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="8bd30-179">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="8bd30-179">Auto attendants and Call queues</span></span>

<span data-ttu-id="8bd30-180">自动助理允许您设置菜单选项，以便根据呼叫者输入路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="8bd30-180">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="8bd30-181">呼叫队列正在等待呼叫者的区域。</span><span class="sxs-lookup"><span data-stu-id="8bd30-181">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="8bd30-182">自动助理和呼叫队列一起使用可以轻松地将呼叫者路由到组织中相应的人员或部门。</span><span class="sxs-lookup"><span data-stu-id="8bd30-182">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="8bd30-183">有关自动助理和呼叫队列的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8bd30-183">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="8bd30-184">规划Teams助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="8bd30-184">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="8bd30-185">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="8bd30-185">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="8bd30-186">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="8bd30-186">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="8bd30-187">Contoso 案例研究：自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="8bd30-187">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="8bd30-188">介绍虚构的多语言公司 Contoso 如何为语音解决方案实现自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="8bd30-188">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="8bd30-189">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="8bd30-189">Cloud Voicemail</span></span>

<span data-ttu-id="8bd30-190">云语音邮件由 Azure 语音邮件服务支持将语音邮件Exchange邮箱。</span><span class="sxs-lookup"><span data-stu-id="8bd30-190">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="8bd30-191">它不支持第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="8bd30-191">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="8bd30-192">云语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。</span><span class="sxs-lookup"><span data-stu-id="8bd30-192">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="8bd30-193">你的业务需求可能要求你为特定用户或整个组织所有人禁用语音邮件转录。</span><span class="sxs-lookup"><span data-stu-id="8bd30-193">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="8bd30-194">对于仅联机用户云语音邮件，系统会自动为用户设置和预配用户许可证电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="8bd30-194">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="8bd30-195">对于电话系统邮箱Exchange，需要执行额外的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="8bd30-195">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="8bd30-196">有关应用程序及其云语音邮件，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8bd30-196">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="8bd30-197">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="8bd30-197">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="8bd30-198">在组织中设置语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="8bd30-198">Set voicemail policies in your organization</span></span>](manage-voicemail-policies.md)


### <a name="calling-identity"></a><span data-ttu-id="8bd30-199">调用标识</span><span class="sxs-lookup"><span data-stu-id="8bd30-199">Calling identity</span></span>

<span data-ttu-id="8bd30-200">默认情况下，所有出站呼叫使用分配的电话号码作为呼叫标识 (呼叫者 ID) 。</span><span class="sxs-lookup"><span data-stu-id="8bd30-200">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="8bd30-201">呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="8bd30-201">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="8bd30-202">有关配置来电显示或更改或阻止来电显示的信息，请参阅 [为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="8bd30-202">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="8bd30-203">公用电话交换网络连接选项</span><span class="sxs-lookup"><span data-stu-id="8bd30-203">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="8bd30-204">电话系统为组织提供完整的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="8bd30-204">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="8bd30-205">但是，若要让用户在组织外部进行呼叫，你需要将 电话系统 连接到 PSTN (电话) 。</span><span class="sxs-lookup"><span data-stu-id="8bd30-205">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="8bd30-206">若要电话系统 PSTN，可以选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="8bd30-206">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="8bd30-207">[**电话系统套餐 。**](pstn-connectivity.md#phone-system-with-calling-plan)</span><span class="sxs-lookup"><span data-stu-id="8bd30-207">[**Phone System with Calling Plan**](pstn-connectivity.md#phone-system-with-calling-plan).</span></span> <span data-ttu-id="8bd30-208">以 Microsoft 作为 PSTN 运营商的全云解决方案。</span><span class="sxs-lookup"><span data-stu-id="8bd30-208">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="8bd30-209">[**电话系统直接**](pstn-connectivity.md#phone-system-with-direct-routing)路由将本地环境连接到本地环境，与自己的 PSTN 运营商Teams。</span><span class="sxs-lookup"><span data-stu-id="8bd30-209">[**Phone System with your own PSTN carrier by using Direct Routing**](pstn-connectivity.md#phone-system-with-direct-routing) to connect your on-premises environment to Teams.</span></span>

- <span data-ttu-id="8bd30-210">电话系统运营商或运营商与自己的 [**PSTN 运营商连接，**](operator-connect-plan.md)目前仅在公共预览 **版中提供。**</span><span class="sxs-lookup"><span data-stu-id="8bd30-210">[**Phone System with your own PSTN carrier by using Operator Connect**](operator-connect-plan.md), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="8bd30-211">使用接线连接，如果现有运营商是 Microsoft 接线员连接参与者，他们可管理将 PSTN 呼叫引入 Teams。</span><span class="sxs-lookup"><span data-stu-id="8bd30-211">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="8bd30-212">有关操作员服务权益和要求连接，有关参与此计划的操作员的列表，请参阅计划操作员[连接。](operator-connect-plan.md)</span><span class="sxs-lookup"><span data-stu-id="8bd30-212">For information on the benefits and requirements of Operator Connect, and for a list of operators participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span>

<span data-ttu-id="8bd30-213">还可以选择一组选项，用于为复杂环境设计解决方案，或管理多步骤迁移 (以后迁移) 。</span><span class="sxs-lookup"><span data-stu-id="8bd30-213">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

<span data-ttu-id="8bd30-214">无论电话系统 PSTN 连接选项，大多数服务功能都是相同的。</span><span class="sxs-lookup"><span data-stu-id="8bd30-214">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="8bd30-215">但是，在功能上存在一些差异，这会影响配置某些电话系统，例如呼叫路由和紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="8bd30-215">There are some differences in functionality, however, that affect how you configure certain Phone System features, such as call routing and emergency calling.</span></span> <span data-ttu-id="8bd30-216">有关 PSTN 连接选项和这些配置注意事项的详细信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="8bd30-216">For more information about PSTN connectivity options and these configuration considerations, see [PSTN connectivity options](pstn-connectivity.md).</span></span>


## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="8bd30-217">将现有语音解决方案迁移到Teams</span><span class="sxs-lookup"><span data-stu-id="8bd30-217">Migrate your existing voice solution to Teams</span></span>

> [!NOTE]
> <span data-ttu-id="8bd30-218">有关规划 Teams 语音解决方案作为从 Skype for Business Server 升级到 Teams 的总体计划的一部分的指导，请参阅从 Skype for Business 本地升级到 Teams 的[PSTN 注意事项](upgrade-to-teams-on-prem-pstn-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="8bd30-218">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="8bd30-219">对于要升级到 Teams，最终目标是将所有用户移动到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="8bd30-219">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="8bd30-220">仅在电话系统 TeamsOnly Teams，才支持将 Teams 与应用一起使用。</span><span class="sxs-lookup"><span data-stu-id="8bd30-220">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="8bd30-221">如果需要有关升级到 Teams 的基本信息，请从此处开始：</span><span class="sxs-lookup"><span data-stu-id="8bd30-221">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="8bd30-222">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="8bd30-222">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="8bd30-223">关于升级框架</span><span class="sxs-lookup"><span data-stu-id="8bd30-223">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="8bd30-224">适用于 IT 管理员的升级策略</span><span class="sxs-lookup"><span data-stu-id="8bd30-224">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md)

<span data-ttu-id="8bd30-225">迁移语音解决方案时，迁移到 TeamsOnly 模式时，有四种可能的呼叫方案：</span><span class="sxs-lookup"><span data-stu-id="8bd30-225">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="8bd30-226">[**具有 Microsoft 呼叫Skype for Business的 Skype for Business Online 中的用户**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="8bd30-226">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="8bd30-227">升级后，此用户将继续拥有 Microsoft 呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="8bd30-227">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="8bd30-228">**[Skype for Business Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 中的用户，通过本地或云连接器Skype for Business本地语音功能。</span><span class="sxs-lookup"><span data-stu-id="8bd30-228">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="8bd30-229">用户升级到 Teams需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="8bd30-229">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="8bd30-230">**[在本地使用 Skype for Business 的用户企业语音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)该用户将移动到联机并保持本地 PSTN 连接**。</span><span class="sxs-lookup"><span data-stu-id="8bd30-230">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="8bd30-231">将该用户迁移到 Teams需要将用户的本地 Skype for Business 帐户移动到云，并协调该移动，同时将用户迁移到直接路由。</span><span class="sxs-lookup"><span data-stu-id="8bd30-231">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="8bd30-232">**[在本地使用 Skype for Business 的用户企业语音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)该用户将移动到联机，使用 Microsoft 呼叫计划**。</span><span class="sxs-lookup"><span data-stu-id="8bd30-232">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="8bd30-233">将该用户迁移到 Teams 需要将用户的本地 Skype for Business 帐户移动到云，并将该帐户与 A) 用户电话号码的端口转移到 Microsoft 呼叫计划或 B) 从可用区域分配新的订阅者号码协调。</span><span class="sxs-lookup"><span data-stu-id="8bd30-233">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="8bd30-234">若要详细了解如何针对每种方案实现语音迁移，包括有关何时需要设置混合连接以及如何将具有本地语音功能的用户迁移到直接路由的信息， &mdash; &mdash; 请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="8bd30-234">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="8bd30-235">升级到网络时 PSTN Teams注意事项 - 适用于 IT 管理员</span><span class="sxs-lookup"><span data-stu-id="8bd30-235">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="8bd30-236">Contoso 语音迁移案例研究</span><span class="sxs-lookup"><span data-stu-id="8bd30-236">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="8bd30-237">案例研究介绍了虚构的多语言公司 Contoso 如何为Teams实现语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="8bd30-237">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="8bd30-238">它包含以下文章：</span><span class="sxs-lookup"><span data-stu-id="8bd30-238">It contains the following articles:</span></span>

  - [<span data-ttu-id="8bd30-239">Teams升级计划</span><span class="sxs-lookup"><span data-stu-id="8bd30-239">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="8bd30-240">电话系统和 PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="8bd30-240">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="8bd30-241">基于位置的路由实现</span><span class="sxs-lookup"><span data-stu-id="8bd30-241">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="8bd30-242">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="8bd30-242">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="8bd30-243">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="8bd30-243">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="8bd30-244">音频会议</span><span class="sxs-lookup"><span data-stu-id="8bd30-244">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)
