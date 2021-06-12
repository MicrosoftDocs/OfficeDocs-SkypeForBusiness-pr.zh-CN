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
ms.openlocfilehash: 391b8e2f30aa5e64fcb4b9e418af49341c2b9042
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901929"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="6d1aa-103">规划Teams语音解决方案</span><span class="sxs-lookup"><span data-stu-id="6d1aa-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="6d1aa-104">本文帮助你确定哪个 Microsoft 语音解决方案适合你的组织。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="6d1aa-105">确定后，本文提供内容路线图，实现所选解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

> [!NOTE]
> <span data-ttu-id="6d1aa-106">有关规划 Teams 语音解决方案作为从 Skype for Business Server 升级到 Teams 的总体计划的一部分的指导，请参阅从 Skype for Business 本地升级到 Teams 的[PSTN 注意事项](upgrade-to-teams-on-prem-pstn-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-106">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="6d1aa-107">你可能希望使用呼叫计划 &mdash; 电话系统最简单的解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-107">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="6d1aa-108">这是 Microsoft 的全云解决方案，可提供专用分支 Exchange (PBX) 功能，并呼叫公用电话交换网 (PSTN) ，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-108">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="6d1aa-109">借助此解决方案，Microsoft 是你的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-109">With this solution, Microsoft is your PSTN carrier.</span></span>

![图 1 电话系统套餐](media/voice-solutions-simple.png)

<span data-ttu-id="6d1aa-111">如果你对以下内容回答"是"，电话系统呼叫计划"是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-111">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="6d1aa-112">呼叫计划在你的地区可用。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-112">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="6d1aa-113">无需保留当前 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-113">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="6d1aa-114">您希望使用 Microsoft 托管的 PSTN 访问权限。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-114">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="6d1aa-115">但是，情况可能更复杂。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-115">However, your situation might be more complex.</span></span> <span data-ttu-id="6d1aa-116">例如，你可能在呼叫计划不可用的位置设有办公室。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-116">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="6d1aa-117">或者，可能需要一个支持复杂、跨区域部署、对不同地理位置有不同的要求的组合解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-117">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="6d1aa-118">Microsoft 支持解决方案的组合：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-118">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="6d1aa-119">电话系统套餐</span><span class="sxs-lookup"><span data-stu-id="6d1aa-119">Phone System with Calling Plan</span></span>
- <span data-ttu-id="6d1aa-120">电话系统您的 PSTN 运营商运营商连接 (目前仅在公共 **预览版中提供)**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-120">Phone System with your own PSTN carrier with Operator Connect (currently available only in **public preview**)</span></span>
- <span data-ttu-id="6d1aa-121">电话系统直接路由与自己的 PSTN 运营商联系</span><span class="sxs-lookup"><span data-stu-id="6d1aa-121">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="6d1aa-122">结合使用解决方案，将 电话系统 与呼叫计划结合使用电话系统接线员连接和/或电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-122">A combination solution that uses Phone System with Calling Plan, Phone System with Operator Connect, and/or Phone System with Direct Routing</span></span>


## <a name="what-do-you-need-to-read"></a><span data-ttu-id="6d1aa-123">需要阅读哪些信息？</span><span class="sxs-lookup"><span data-stu-id="6d1aa-123">What do you need to read?</span></span>

<span data-ttu-id="6d1aa-124">**全部必需。**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-124">**Required for all.**</span></span> <span data-ttu-id="6d1aa-125">本文中的某些部分适用于所有组织。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-125">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="6d1aa-126">例如，每个人都应该阅读有关电话系统并了解用于连接到 PSTN 公用电话交换网 (的选项) 。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-126">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="6d1aa-127">全部必需</span><span class="sxs-lookup"><span data-stu-id="6d1aa-127">Required for all</span></span> | <span data-ttu-id="6d1aa-128">说明</span><span class="sxs-lookup"><span data-stu-id="6d1aa-128">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="6d1aa-129">**电话系统**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-129">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="6d1aa-130">Microsoft 在云中启用呼叫控制和专用分支 Exchange (PBX) 功能的技术Microsoft 365云Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-130">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="6d1aa-131">**PSTN 公用电话交换 (PSTN) 连接选项**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-131">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="6d1aa-132">可以选择使用 Microsoft 作为电话运营商，还是使用直接路由或接线员Microsoft Teams将你自己的电话运营商连接。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-132">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing or Operator Connect.</span></span> <span data-ttu-id="6d1aa-133">PSTN 连接电话系统结合使用，使用户能够拨打全球电话。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-133">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="6d1aa-134">**根据你的要求。**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-134">**Depending on your requirements.**</span></span> <span data-ttu-id="6d1aa-135">本文中的某些部分与现有的部署和要求相关。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-135">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="6d1aa-136">例如，Location-Based直接路由客户在不允许收费绕过的地理位置进行直接路由。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-136">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="6d1aa-137">请考虑可能需要以下附加配置中的哪一种：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-137">Consider which of these additional configurations you might need:</span></span>

![图 2 显示了其他语音组件，电话 Microsoft 的电话号码、拨号计划和呼叫路由等。](media/voice-consider-additional-components.png)

| <span data-ttu-id="6d1aa-139">根据要求</span><span class="sxs-lookup"><span data-stu-id="6d1aa-139">Depending on your requirements</span></span> | <span data-ttu-id="6d1aa-140">说明</span><span class="sxs-lookup"><span data-stu-id="6d1aa-140">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="6d1aa-141">**电话 Microsoft 提供的电话号码**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-141">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="6d1aa-142">如何从 Microsoft 获取和管理电话号码，以及如何将现有号码转移到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-142">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="6d1aa-143">如果需要获取 Microsoft 呼叫计划的电话号码、转移现有号码、获取服务号码等，请阅读此内容。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-143">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="6d1aa-144">**拨号计划和呼叫路由**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-144">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="6d1aa-145">如何配置和管理将拨号电话号码转换为备用格式的拨号计划 (通常为 E.164 格式) 进行呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-145">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="6d1aa-146">如果需要了解什么是拨号计划以及是否需要为组织指定拨号计划，请阅读此说明。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-146">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="6d1aa-147">**紧急呼叫**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-147">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="6d1aa-148">如何管理和配置紧急呼叫 &mdash; ，具体取决于 PSTN 连接选项。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-148">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="6d1aa-149">如果使用 Microsoft 呼叫计划或直接路由，并且需要了解如何为组织管理紧急呼叫，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-149">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="6d1aa-150">**用于直接路由的基于位置的路由**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-150">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="6d1aa-151">如何使用 LBR Location-Based路由 (，) 基于用户的地理位置Microsoft Teams免收费。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-151">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="6d1aa-152">如果组织在不允许绕过收费站的位置使用直接路由，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-152">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="6d1aa-153">**云语音功能的网络拓扑**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-153">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="6d1aa-154">如果组织为直接路由Location-Based LBR (部署) 路由或动态紧急呼叫，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-154">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="6d1aa-155">如果要为直接路由实现 LBR，或者使用呼叫计划或直接路由实现动态紧急呼叫，请阅读本部分。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-155">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="6d1aa-156">**迁移现有语音解决方案**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-156">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="6d1aa-157">将语音解决方案迁移到云时需考虑Teams。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-157">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="6d1aa-158">如果要从现有语音解决方案迁移到现有语音解决方案，请阅读此Teams。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-158">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="6d1aa-159">本文重点介绍语音解决方案与Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-159">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="6d1aa-160">虽然 Skype for Business Online 解决方案 ([Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions)电话解决方案) 中所述，但必须了解 Skype for Business Online 将于 2021 年 7 月 31 日停用。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-160">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="6d1aa-161">该日期之后，Skype for Business不再可访问联机服务。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-161">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="6d1aa-162">此外，将不再支持本地环境之间的 PSTN 连接 &mdash; Skype for Business Server云连接器版本和 Skype for Business Online &mdash; 连接。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-162">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="6d1aa-163">本文介绍Teams语音解决方案，以及如何在必要时使用直接路由或接线员Teams连接本地电话连接。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-163">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing or Operator Connect.</span></span>


## <a name="phone-system"></a><span data-ttu-id="6d1aa-164">电话系统</span><span class="sxs-lookup"><span data-stu-id="6d1aa-164">Phone System</span></span>

<span data-ttu-id="6d1aa-165">电话系统是 Microsoft 在 Microsoft 365 或 Office 365 云中启用呼叫控制和专用分支 Exchange (PBX) 功能的技术，Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-165">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="6d1aa-166">电话系统适用于Teams或Skype for Business客户端和认证设备。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-166">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="6d1aa-167">电话系统将现有 PBX 系统替换为一组直接从 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-167">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="6d1aa-168">您的组织中的用户之间的呼叫在内部处理电话系统，永远不会转到 PSTN (电话) 。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-168">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="6d1aa-169">这适用于组织中位于不同地理区域的用户之间的呼叫，消除了这些内部呼叫的远程成本。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-169">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="6d1aa-170">本文介绍以下电话系统特性和功能，以及需要考虑的部署决策：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-170">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="6d1aa-171">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="6d1aa-171">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="6d1aa-172">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="6d1aa-172">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="6d1aa-173">调用标识</span><span class="sxs-lookup"><span data-stu-id="6d1aa-173">Calling identity</span></span>](#calling-identity)

![图 3 电话系统包含自动助理和呼叫查询、云语音邮件和呼叫标识](media/phone-system-contains.png)

<span data-ttu-id="6d1aa-175">有关所有电话系统功能以及如何设置电话系统，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-175">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-176">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="6d1aa-176">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="6d1aa-177">在组织中设置电话系统</span><span class="sxs-lookup"><span data-stu-id="6d1aa-177">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="6d1aa-178">介绍如何购买和分配电话系统、管理电话号码以及设置免费号码的通信信用额度。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-178">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="6d1aa-179">有关管理受支持设备的信息，请参阅[在](devices/device-management.md)Microsoft Teams 和 Teams[中管理设备](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-179">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="6d1aa-180">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="6d1aa-180">Auto attendants and Call queues</span></span>

<span data-ttu-id="6d1aa-181">自动助理允许您设置菜单选项，以便根据呼叫者输入路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-181">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="6d1aa-182">呼叫队列正在等待呼叫者的区域。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-182">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="6d1aa-183">自动助理和呼叫队列一起使用可以轻松地将呼叫者路由到组织中相应的人员或部门。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-183">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="6d1aa-184">有关自动助理和呼叫队列的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-184">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-185">规划Teams助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="6d1aa-185">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="6d1aa-186">设置自动助理</span><span class="sxs-lookup"><span data-stu-id="6d1aa-186">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="6d1aa-187">创建呼叫队列</span><span class="sxs-lookup"><span data-stu-id="6d1aa-187">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="6d1aa-188">Contoso 案例研究：自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="6d1aa-188">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="6d1aa-189">介绍虚构的多语言公司 Contoso 如何为语音解决方案实现自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-189">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="6d1aa-190">云语音邮件</span><span class="sxs-lookup"><span data-stu-id="6d1aa-190">Cloud Voicemail</span></span>

<span data-ttu-id="6d1aa-191">云语音邮件由 Azure 语音邮件服务支持将语音邮件Exchange邮箱。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-191">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="6d1aa-192">它不支持第三方电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-192">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="6d1aa-193">云语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-193">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="6d1aa-194">你的业务需求可能要求你为特定用户或整个组织所有人禁用语音邮件转录。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-194">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="6d1aa-195">对于仅联机用户云语音邮件，系统会自动为用户设置和预配用户许可证电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-195">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="6d1aa-196">对于电话系统邮箱Exchange，需要执行额外的配置步骤。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-196">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="6d1aa-197">有关应用程序及其云语音邮件，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-197">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-198">设置云语音邮件</span><span class="sxs-lookup"><span data-stu-id="6d1aa-198">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="6d1aa-199">在组织中设置语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="6d1aa-199">Set voicemail policies in your organization</span></span>](manage-voicemail-policies.md)


### <a name="calling-identity"></a><span data-ttu-id="6d1aa-200">调用标识</span><span class="sxs-lookup"><span data-stu-id="6d1aa-200">Calling identity</span></span>

<span data-ttu-id="6d1aa-201">默认情况下，所有出站呼叫使用分配的电话号码作为呼叫标识 (呼叫者 ID) 。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-201">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="6d1aa-202">呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-202">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="6d1aa-203">有关配置来电显示或更改或阻止来电显示的信息，请参阅 [为用户设置来电显示](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-203">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="6d1aa-204">公用电话交换网络连接选项</span><span class="sxs-lookup"><span data-stu-id="6d1aa-204">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="6d1aa-205">电话系统为组织提供完整的 PBX 功能。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-205">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="6d1aa-206">但是，若要让用户在组织外部进行呼叫，你需要将 电话系统 连接到 PSTN (电话) 。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-206">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="6d1aa-207">若要电话系统 PSTN，可以选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-207">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="6d1aa-208">[**电话系统套餐 。**](#phone-system-with-calling-plan)</span><span class="sxs-lookup"><span data-stu-id="6d1aa-208">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="6d1aa-209">以 Microsoft 作为 PSTN 运营商的全云解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-209">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="6d1aa-210">[**电话系统直接**](#phone-system-with-own-pstn-carrier-with-direct-routing)路由将本地环境连接到本地环境，与自己的 PSTN 运营商Teams。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-210">[**Phone System with your own PSTN carrier by using Direct Routing**](#phone-system-with-own-pstn-carrier-with-direct-routing) to connect your on-premises environment to Teams.</span></span>

- <span data-ttu-id="6d1aa-211">电话系统运营商或运营商与自己的 [**PSTN 运营商连接，**](operator-connect-plan.md)目前仅在公共预览 **版中提供。**</span><span class="sxs-lookup"><span data-stu-id="6d1aa-211">[**Phone System with your own PSTN carrier by using Operator Connect**](operator-connect-plan.md), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="6d1aa-212">使用接线连接，如果现有运营商是 Microsoft 接线员连接参与者，他们可管理将 PSTN 呼叫引入 Teams。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-212">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="6d1aa-213">有关操作员服务权益和要求连接，有关参与此计划的操作员的列表，请参阅计划操作员[连接。](operator-connect-plan.md)</span><span class="sxs-lookup"><span data-stu-id="6d1aa-213">For information on the benefits and requirements of Operator Connect, and for a list of operators participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span>

<span data-ttu-id="6d1aa-214">还可以选择一组选项，用于为复杂环境设计解决方案，或管理多步骤迁移 (以后迁移) 。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-214">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="6d1aa-215">电话系统套餐</span><span class="sxs-lookup"><span data-stu-id="6d1aa-215">Phone System with Calling Plan</span></span> 

<span data-ttu-id="6d1aa-216">如本文前面所述，电话系统套餐是 Microsoft 为用户提供的所有云语音Teams解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-216">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="6d1aa-217">这是将 Microsoft 电话 系统连接到公用电话交换网 (PSTN) 以启用对世界各地的座机和移动电话的呼叫的最简单选项。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-217">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="6d1aa-218">使用此选项，Microsoft 为组织Exchange (PBX) 专用分支，并充当 PSTN 运营商，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-218">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![图 4 电话系统自动助理、呼叫队列、呼叫者 ID 等，以及 Microsoft 作为 PSTN 运营商](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="6d1aa-220">如果你对以下内容回答"是"，电话系统呼叫计划"是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-220">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="6d1aa-221">呼叫计划在你的地区可用。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-221">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="6d1aa-222">无需保留当前 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-222">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="6d1aa-223">您希望使用 Microsoft 托管的 PSTN 访问权限。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-223">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="6d1aa-224">使用此选项：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-224">With this option:</span></span> 

- <span data-ttu-id="6d1aa-225">你可以Microsoft 电话系统添加国内或国际呼叫计划，这些套餐支持拨打世界各地的电话 (具体取决于获得许可的服务) 。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-225">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="6d1aa-226">不需要部署或维护本地部署，因为呼叫计划在 Microsoft 365 &mdash; 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-226">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="6d1aa-227">注意：如有必要，可以选择通过直接路由连接受支持的会话边界控制器 (SBC) ，以与 SBC 支持的第三方 PBX、模拟设备和其他第三方电话设备进行互操作性。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-227">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="6d1aa-228">此选项需要不间断地连接到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-228">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="6d1aa-229">有关呼叫计划详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-229">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-230">哪种通话套餐适合你？</span><span class="sxs-lookup"><span data-stu-id="6d1aa-230">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="6d1aa-231">如何购买通话套餐</span><span class="sxs-lookup"><span data-stu-id="6d1aa-231">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="6d1aa-232">通话套餐的国家和地区可用性</span><span class="sxs-lookup"><span data-stu-id="6d1aa-232">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="6d1aa-233">设置呼叫计划</span><span class="sxs-lookup"><span data-stu-id="6d1aa-233">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="6d1aa-234">电话系统具有直接路由的 PSTN 运营商</span><span class="sxs-lookup"><span data-stu-id="6d1aa-234">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="6d1aa-235">此选项使用Microsoft 电话路由将系统连接到电话网络，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-235">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![图 5 显示电话系统直接路由的路由](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="6d1aa-237">如果对以下问题回答"是"，电话系统直接路由是适合的解决方案：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-237">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="6d1aa-238">想要将 Teams 与 电话系统。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-238">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="6d1aa-239">你需要保留当前的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-239">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="6d1aa-240">您希望混合路由，一些呼叫通过呼叫计划进行，一些呼叫通过运营商进行。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-240">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="6d1aa-241">需要和第三方 PBX 和/或设备（例如我们的开销寻呼机、模拟设备等）互操作。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-241">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="6d1aa-242">使用此选项：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-242">With this option:</span></span>

- <span data-ttu-id="6d1aa-243">将自己支持的 SBC 连接到 Microsoft 电话 System，而无需其他本地软件。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-243">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="6d1aa-244">几乎可以将任何电话运营商与 Microsoft 电话系统一起使用。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-244">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="6d1aa-245">您可以选择配置和管理此选项，也可以由运营商或合作伙伴组织配置和管理 (询问运营商或合作伙伴是否提供此选项) 。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-245">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="6d1aa-246">可以在电话设备（例如第三方 PBX 和模拟设备）与 Microsoft 电话 &mdash; &mdash; 系统之间配置互操作性。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-246">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="6d1aa-247">此选项需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-247">This option requires the following:</span></span>

- <span data-ttu-id="6d1aa-248">不间断地连接到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-248">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="6d1aa-249">部署和维护支持的 SBC。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-249">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="6d1aa-250">与第三方运营商的合同。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-250">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="6d1aa-251"> (除非部署为为使用呼叫计划.电话系统的用户提供第三方 PBX、模拟设备或其他电话设备连接的选项) </span><span class="sxs-lookup"><span data-stu-id="6d1aa-251">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="6d1aa-252">有关直接路由详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-252">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-253">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-253">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="6d1aa-254">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-254">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="6d1aa-255">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-255">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="6d1aa-256">管理用于直接路由的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="6d1aa-256">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="6d1aa-257">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-257">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="6d1aa-258">经认证可用于直接路由的会话边界控制器列表</span><span class="sxs-lookup"><span data-stu-id="6d1aa-258">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="6d1aa-259">电话 Microsoft 提供的电话号码</span><span class="sxs-lookup"><span data-stu-id="6d1aa-259">Phone numbers from Microsoft</span></span>

<span data-ttu-id="6d1aa-260">Microsoft 提供两种类型的电话号码：订阅者 (用户) 号码（可分配给您的组织中的用户）和服务号码（以收费和免费服务号码提供）。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-260">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="6d1aa-261">服务号码的并发呼叫容量高于订阅者号码，可分配给音频会议、自动助理或呼叫队列等服务。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-261">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="6d1aa-262">需要确定：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-262">You will need to decide:</span></span>

- <span data-ttu-id="6d1aa-263">哪些用户位置需要 Microsoft 提供的新电话号码？</span><span class="sxs-lookup"><span data-stu-id="6d1aa-263">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="6d1aa-264">需要哪种类型的 (或) 电话号码？</span><span class="sxs-lookup"><span data-stu-id="6d1aa-264">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="6d1aa-265">如何将现有电话号码移植到Teams？</span><span class="sxs-lookup"><span data-stu-id="6d1aa-265">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="6d1aa-266">有关管理组织中电话号码（包括获取新号码或转移退出号码）的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-266">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-267">管理组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="6d1aa-267">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="6d1aa-268">用于呼叫计划的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="6d1aa-268">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="6d1aa-269">为用户获取电话号码</span><span class="sxs-lookup"><span data-stu-id="6d1aa-269">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="6d1aa-270">将电话号码转移到Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d1aa-270">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="6d1aa-271">拨号计划和呼叫路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-271">Dial plans and call routing</span></span>

<span data-ttu-id="6d1aa-272">拨号计划是一组规范化规则，将拨入的电话号码转换为备用格式 (通常为 E.164 格式) 进行呼叫授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-272">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="6d1aa-273">需要确定以下事项：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-273">You will need to decide the following:</span></span> 

- <span data-ttu-id="6d1aa-274">我的组织是否需要自定义拨号计划？</span><span class="sxs-lookup"><span data-stu-id="6d1aa-274">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="6d1aa-275">哪些用户需要自定义拨号计划？</span><span class="sxs-lookup"><span data-stu-id="6d1aa-275">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="6d1aa-276">应该向每个用户分配哪个租户拨号计划？</span><span class="sxs-lookup"><span data-stu-id="6d1aa-276">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="6d1aa-277">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-277">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="6d1aa-278">什么是拨号计划？</span><span class="sxs-lookup"><span data-stu-id="6d1aa-278">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="6d1aa-279">规划租户拨号计划</span><span class="sxs-lookup"><span data-stu-id="6d1aa-279">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="6d1aa-280">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="6d1aa-280">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="6d1aa-281">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="6d1aa-281">Emergency calling</span></span>

<span data-ttu-id="6d1aa-282">如何配置紧急呼叫取决于 PSTN 连接选项：Microsoft 呼叫计划或直接路由。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-282">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="6d1aa-283">Microsoft 呼叫计划和直接路由电话系统动态紧急呼叫提供配置和路由紧急呼叫以及根据客户端的当前位置通知安全Teams的功能。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-283">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="6d1aa-284">有关紧急呼叫概念和术语以及如何配置动态紧急呼叫的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-284">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-285">管理紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="6d1aa-285">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="6d1aa-286">规划和配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="6d1aa-286">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="6d1aa-287">Contoso 案例研究：紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="6d1aa-287">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="6d1aa-288">介绍虚构的多语言公司 Contoso 如何为组织实施紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-288">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="6d1aa-289">Location-Based直接路由的路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-289">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="6d1aa-290">在某些国家和地区，绕过 PSTN 公用电话交换网 (PSTN) 降低远程呼叫成本非法。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-290">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="6d1aa-291">Location-Based直接路由的路由允许根据用户Microsoft Teams限制免收费。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-291">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="6d1aa-292">若要详细了解如何计划和配置 Location-Based LBR (路由) ，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-292">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-293">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-293">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="6d1aa-294">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="6d1aa-294">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="6d1aa-295">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-295">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="6d1aa-296">Contoso 案例研究：Location-Based路由</span><span class="sxs-lookup"><span data-stu-id="6d1aa-296">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="6d1aa-297">介绍虚拟的多语言公司 Contoso 如何为Location-Based实现路由。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-297">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="6d1aa-298">语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="6d1aa-298">Network topology for voice features</span></span>

<span data-ttu-id="6d1aa-299">如果要为直接路由部署动态紧急呼叫或Location-Based路由，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-299">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="6d1aa-300">若要了解如何为网络区域、网络站点、网络子网和受信任的 IP 地址配置网络设置，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-300">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-301">云语音功能网络设置Microsoft Teams - 概念和术语</span><span class="sxs-lookup"><span data-stu-id="6d1aa-301">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="6d1aa-302">管理云语音功能的网络拓扑Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d1aa-302">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="6d1aa-303">将现有语音解决方案迁移到Teams</span><span class="sxs-lookup"><span data-stu-id="6d1aa-303">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="6d1aa-304">对于要升级到 Teams，最终目标是将所有用户移动到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-304">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="6d1aa-305">仅在电话系统 TeamsOnly Teams，才支持将 Teams 与应用一起使用。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-305">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="6d1aa-306">如果需要有关升级到 Teams 的基本信息，请从此处开始：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-306">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="6d1aa-307">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="6d1aa-307">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="6d1aa-308">关于升级框架</span><span class="sxs-lookup"><span data-stu-id="6d1aa-308">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="6d1aa-309">适用于 IT 管理员的升级策略</span><span class="sxs-lookup"><span data-stu-id="6d1aa-309">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md)

<span data-ttu-id="6d1aa-310">迁移语音解决方案时，迁移到 TeamsOnly 模式时，有四种可能的呼叫方案：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-310">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="6d1aa-311">[**具有 Microsoft 呼叫Skype for Business的 Skype for Business Online 中的用户**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-311">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="6d1aa-312">升级后，此用户将继续拥有 Microsoft 呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-312">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="6d1aa-313">**[Skype for Business Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 中的用户，通过本地或云连接器Skype for Business本地语音功能。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-313">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="6d1aa-314">用户升级到 Teams需要与将用户迁移到直接路由进行协调，以确保 TeamsOnly 用户具有 PSTN 功能。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-314">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="6d1aa-315">**[在本地使用 Skype for Business 的用户企业语音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)该用户将移动到联机并保持本地 PSTN 连接**。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-315">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="6d1aa-316">将该用户迁移到 Teams需要将用户的本地 Skype for Business 帐户移动到云，并协调该移动，同时将用户迁移到直接路由。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-316">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="6d1aa-317">**[在本地使用 Skype for Business 的用户企业语音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)该用户将移动到联机，使用 Microsoft 呼叫计划**。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-317">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="6d1aa-318">将该用户迁移到 Teams 需要将用户的本地 Skype for Business 帐户移动到云，并将该帐户与 A) 用户电话号码的端口转移到 Microsoft 呼叫计划或 B) 从可用区域分配新的订阅者号码协调。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-318">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="6d1aa-319">若要详细了解如何针对每种方案实现语音迁移，包括有关何时需要设置混合连接以及如何将具有本地语音功能的用户迁移到直接路由的信息， &mdash; &mdash; 请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-319">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="6d1aa-320">升级到网络时 PSTN Teams注意事项 - 适用于 IT 管理员</span><span class="sxs-lookup"><span data-stu-id="6d1aa-320">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="6d1aa-321">Contoso 语音迁移案例研究</span><span class="sxs-lookup"><span data-stu-id="6d1aa-321">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="6d1aa-322">案例研究介绍了虚构的多语言公司 Contoso 如何为Teams实现语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d1aa-322">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="6d1aa-323">它包含以下文章：</span><span class="sxs-lookup"><span data-stu-id="6d1aa-323">It contains the following articles:</span></span>

  - [<span data-ttu-id="6d1aa-324">Teams升级计划</span><span class="sxs-lookup"><span data-stu-id="6d1aa-324">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="6d1aa-325">电话系统和 PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="6d1aa-325">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="6d1aa-326">基于位置的路由实现</span><span class="sxs-lookup"><span data-stu-id="6d1aa-326">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="6d1aa-327">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="6d1aa-327">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="6d1aa-328">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="6d1aa-328">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="6d1aa-329">音频会议</span><span class="sxs-lookup"><span data-stu-id="6d1aa-329">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)
