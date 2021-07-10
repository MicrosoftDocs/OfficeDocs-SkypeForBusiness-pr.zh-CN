---
title: PSTN 连接选项
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
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
description: 详细了解如何Teams PSTN (连接) 选项以及您将为组织做出的决策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354512"
---
# <a name="pstn-connectivity-options"></a><span data-ttu-id="21e6f-103">PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="21e6f-103">PSTN connectivity options</span></span>

<span data-ttu-id="21e6f-104">Microsoft 通过 EXCHANGE (为) 提供完整的专用分支和 PBX 电话系统。</span><span class="sxs-lookup"><span data-stu-id="21e6f-104">Microsoft provides complete Private Branch Exchange (PBX) capabilities for your organization through Phone System.</span></span> <span data-ttu-id="21e6f-105">但是，若要让用户在组织外部进行呼叫，你需要将 电话系统 连接到 PSTN (电话) 。</span><span class="sxs-lookup"><span data-stu-id="21e6f-105">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="21e6f-106">本文重点介绍 PSTN 连接选项。</span><span class="sxs-lookup"><span data-stu-id="21e6f-106">This article focuses on PSTN connectivity options.</span></span> <span data-ttu-id="21e6f-107">有关 Microsoft 语音解决方案的详细信息，请参阅规划语音电话系统的详细信息，Teams[解决方案](cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="21e6f-107">For more information about Microsoft voice solutions, incuding details about Phone System features, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>

<span data-ttu-id="21e6f-108">若要电话系统 PSTN，可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="21e6f-108">To connect Phone System to the PSTN, you can choose from the following options:</span></span>

- <span data-ttu-id="21e6f-109">[**调用计划**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="21e6f-109">[**Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="21e6f-110">以 Microsoft 作为 PSTN 运营商的全云解决方案。</span><span class="sxs-lookup"><span data-stu-id="21e6f-110">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="21e6f-111">[**直接路由**](#phone-system-with-direct-routing)，通过连接会话边界控制器和 SBC (，)  (使用自己的 PSTN) 电话系统。</span><span class="sxs-lookup"><span data-stu-id="21e6f-111">[**Direct Routing**](#phone-system-with-direct-routing), which enables you to use your own PSTN carrier by connecting your Session Border Controller(s) (SBC) to Phone System.</span></span>

- <span data-ttu-id="21e6f-112">[**运算符连接，**](#phone-system-with-operator-connect)目前仅在公共预览 **版中提供。**</span><span class="sxs-lookup"><span data-stu-id="21e6f-112">[**Operator Connect**](#phone-system-with-operator-connect), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="21e6f-113">使用运营商连接，如果你的现有运营商是 Microsoft 运营商 连接 计划的参与者，他们可以管理 PSTN 呼叫和会话边界控制器 (SDC) 。</span><span class="sxs-lookup"><span data-stu-id="21e6f-113">With Operator Connect, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage PSTN calling and Session Border Controllers (SBCs).</span></span> 

<span data-ttu-id="21e6f-114">还可以选择一组选项，用于为复杂环境设计解决方案，或管理多步骤迁移。</span><span class="sxs-lookup"><span data-stu-id="21e6f-114">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration.</span></span>

<span data-ttu-id="21e6f-115">请注意，选择的选项会影响某些电话系统的配置方式。</span><span class="sxs-lookup"><span data-stu-id="21e6f-115">Be aware that the option or options you choose affect how some Phone System features are configured.</span></span> <span data-ttu-id="21e6f-116">有关详细信息，请参阅 [本文稍后的配置](#configuration-considerations) 注意事项。</span><span class="sxs-lookup"><span data-stu-id="21e6f-116">For more information, see [Configuration considerations](#configuration-considerations) later in this article.</span></span>


## <a name="phone-system-with-calling-plan"></a><span data-ttu-id="21e6f-117">电话系统套餐</span><span class="sxs-lookup"><span data-stu-id="21e6f-117">Phone System with Calling Plan</span></span> 

<span data-ttu-id="21e6f-118">电话系统套餐"是 Microsoft 为用户提供的所有云中语音Teams解决方案。</span><span class="sxs-lookup"><span data-stu-id="21e6f-118">Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="21e6f-119">这是将客户端连接到 PSTN 电话系统最简单的选项。</span><span class="sxs-lookup"><span data-stu-id="21e6f-119">This is the simplest option that connects Phone System to the PSTN.</span></span> <span data-ttu-id="21e6f-120">使用此选项，Microsoft 将充当 PSTN 运营商，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="21e6f-120">With this option, Microsoft acts as your PSTN carrier, as shown in the following diagram:</span></span>

![图 1 电话系统套餐](media/voice-solutions-simple.png)

<span data-ttu-id="21e6f-122">如果你对以下内容回答"是"，电话系统呼叫计划"是适合你的解决方案：</span><span class="sxs-lookup"><span data-stu-id="21e6f-122">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="21e6f-123">呼叫计划在你的地区可用。</span><span class="sxs-lookup"><span data-stu-id="21e6f-123">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="21e6f-124">无需保留当前 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="21e6f-124">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="21e6f-125">您希望使用 Microsoft 托管的 PSTN 访问权限。</span><span class="sxs-lookup"><span data-stu-id="21e6f-125">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="21e6f-126">使用此选项：</span><span class="sxs-lookup"><span data-stu-id="21e6f-126">With this option:</span></span> 

- <span data-ttu-id="21e6f-127">你可以Microsoft 电话系统添加国内或国际呼叫计划，这些套餐支持拨打世界各地的电话 (具体取决于获得许可的服务) 。</span><span class="sxs-lookup"><span data-stu-id="21e6f-127">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="21e6f-128">不需要部署或维护本地部署，因为调用计划 &mdash; 在Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="21e6f-128">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365.</span></span>

- <span data-ttu-id="21e6f-129">注意：如有必要，可以选择通过直接路由连接受支持的会话边界控制器 (SBC) ，以与 SBC 支持的第三方 PBX、模拟设备和其他第三方电话设备进行互操作性。</span><span class="sxs-lookup"><span data-stu-id="21e6f-129">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="21e6f-130">此选项需要不间断地连接到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="21e6f-130">This option requires uninterrupted connection to Microsoft 365.</span></span>

<span data-ttu-id="21e6f-131">有关呼叫计划详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="21e6f-131">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="21e6f-132">哪种通话套餐适合你？</span><span class="sxs-lookup"><span data-stu-id="21e6f-132">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="21e6f-133">如何购买通话套餐</span><span class="sxs-lookup"><span data-stu-id="21e6f-133">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="21e6f-134">通话套餐的国家和地区可用性</span><span class="sxs-lookup"><span data-stu-id="21e6f-134">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="21e6f-135">设置呼叫计划</span><span class="sxs-lookup"><span data-stu-id="21e6f-135">Set up Calling Plan</span></span>](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a><span data-ttu-id="21e6f-136">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="21e6f-136">Phone System with Direct Routing</span></span>

<span data-ttu-id="21e6f-137">此选项使用电话系统路由将线路连接到电话网络，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="21e6f-137">This option connects Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![图 5 显示电话系统直接路由的路由](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="21e6f-139">如果对以下问题回答"是"，电话系统直接路由是适合的解决方案：</span><span class="sxs-lookup"><span data-stu-id="21e6f-139">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="21e6f-140">想要将 Teams 与 电话系统。</span><span class="sxs-lookup"><span data-stu-id="21e6f-140">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="21e6f-141">你需要保留当前的 PSTN 运营商。</span><span class="sxs-lookup"><span data-stu-id="21e6f-141">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="21e6f-142">您希望混合路由，一些呼叫通过呼叫计划进行，一些呼叫通过运营商进行。</span><span class="sxs-lookup"><span data-stu-id="21e6f-142">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="21e6f-143">需要和第三方 PBX 和/或设备（例如我们的开销寻呼机、模拟设备等）互操作。</span><span class="sxs-lookup"><span data-stu-id="21e6f-143">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="21e6f-144">使用此选项：</span><span class="sxs-lookup"><span data-stu-id="21e6f-144">With this option:</span></span>

- <span data-ttu-id="21e6f-145">将自己的受支持会话边界控制器 (SBC) 连接到 电话系统，而无需其他本地软件。</span><span class="sxs-lookup"><span data-stu-id="21e6f-145">You connect your own supported Session Border Controller (SBC) to Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="21e6f-146">你几乎可以使用任何电话运营商和电话系统。</span><span class="sxs-lookup"><span data-stu-id="21e6f-146">You can use virtually any telephony carrier with Phone System.</span></span>

- <span data-ttu-id="21e6f-147">您可以选择配置和管理此选项，也可以由运营商或合作伙伴组织配置和管理 (询问运营商或合作伙伴是否提供此选项) 。</span><span class="sxs-lookup"><span data-stu-id="21e6f-147">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="21e6f-148">可以在电话设备（例如第三方 PBX）与模拟设备和模拟设备之间配置 &mdash; &mdash; 电话系统。</span><span class="sxs-lookup"><span data-stu-id="21e6f-148">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Phone System.</span></span>

<span data-ttu-id="21e6f-149">此选项需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="21e6f-149">This option requires the following:</span></span>

- <span data-ttu-id="21e6f-150">不间断地连接到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="21e6f-150">Uninterrupted connection to Microsoft 365.</span></span>

- <span data-ttu-id="21e6f-151">部署和维护支持的 SBC。</span><span class="sxs-lookup"><span data-stu-id="21e6f-151">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="21e6f-152">与第三方运营商的合同。</span><span class="sxs-lookup"><span data-stu-id="21e6f-152">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="21e6f-153"> (除非部署为为使用呼叫计划.电话系统的用户提供第三方 PBX、模拟设备或其他电话设备连接的选项) </span><span class="sxs-lookup"><span data-stu-id="21e6f-153">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="21e6f-154">有关直接路由详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="21e6f-154">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="21e6f-155">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="21e6f-155">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="21e6f-156">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="21e6f-156">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="21e6f-157">管理用于直接路由的语音路由策略</span><span class="sxs-lookup"><span data-stu-id="21e6f-157">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="21e6f-158">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="21e6f-158">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="21e6f-159">经认证可用于直接路由的会话边界控制器列表</span><span class="sxs-lookup"><span data-stu-id="21e6f-159">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a><span data-ttu-id="21e6f-160">电话系统运算符连接</span><span class="sxs-lookup"><span data-stu-id="21e6f-160">Phone System with Operator Connect</span></span>

<span data-ttu-id="21e6f-161">使用运营商连接（目前为公共预览版）时，如果你的现有运营商是 Microsoft 运营商 连接 计划的参与者，他们可以管理将 PSTN 呼叫引入 Teams。</span><span class="sxs-lookup"><span data-stu-id="21e6f-161">With Operator Connect, currently in public preview, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="21e6f-162">运营商管理 PSTN 呼叫服务和会话边界控制器 (SDC) ，从而节省硬件购买和管理费用。</span><span class="sxs-lookup"><span data-stu-id="21e6f-162">Your carrier manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

<span data-ttu-id="21e6f-163">如果连接，操作员管理可能是适合组织的解决方案：</span><span class="sxs-lookup"><span data-stu-id="21e6f-163">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="21e6f-164">Microsoft 呼叫计划在你的地理位置不可用。</span><span class="sxs-lookup"><span data-stu-id="21e6f-164">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="21e6f-165">首选运营商是 Microsoft 运营商运营连接参与者。</span><span class="sxs-lookup"><span data-stu-id="21e6f-165">Your preferred carrier is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="21e6f-166">您希望查找新的运营商以在 Teams。</span><span class="sxs-lookup"><span data-stu-id="21e6f-166">You want to find a new carrier to enable calling in Teams.</span></span>

<span data-ttu-id="21e6f-167">有关运营商运营商权益和要求连接，有关参与此计划的运营商列表，请参阅计划运营商[连接。](operator-connect-plan.md)</span><span class="sxs-lookup"><span data-stu-id="21e6f-167">For information on the benefits and requirements of Operator Connect, and for a list of carriers participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span> <span data-ttu-id="21e6f-168">若要了解如何配置运算符连接，请参阅[配置运算符连接。](operator-connect-configure.md)</span><span class="sxs-lookup"><span data-stu-id="21e6f-168">For information on how to configure Operator Connect, see [Configure Operator Connect](operator-connect-configure.md).</span></span>

## <a name="configuration-considerations"></a><span data-ttu-id="21e6f-169">配置注意事项</span><span class="sxs-lookup"><span data-stu-id="21e6f-169">Configuration considerations</span></span>

<span data-ttu-id="21e6f-170">无论电话系统 PSTN 连接选项，大多数服务功能都是相同的。</span><span class="sxs-lookup"><span data-stu-id="21e6f-170">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="21e6f-171">例如，呼叫未回声和转接设置、呼叫转接、保留的自定义音乐、呼叫公园、共享线路和语音应用都可用。</span><span class="sxs-lookup"><span data-stu-id="21e6f-171">For example, call unanswered and forwarding settings, call transfer, custom music on hold, call park, shared line, and voice apps are all available.</span></span> <span data-ttu-id="21e6f-172">有关这些功能的完整电话系统列表，请参阅此处是使用[电话系统。](here-s-what-you-get-with-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="21e6f-172">For a complete list of Phone System features, see [Here's what you get with Phone System](here-s-what-you-get-with-phone-system.md).</span></span>

<span data-ttu-id="21e6f-173">但是，功能存在一些差异，这会影响你配置某些电话系统方式。</span><span class="sxs-lookup"><span data-stu-id="21e6f-173">There are some differences in functionality, however, that affect how you configure certain Phone System features.</span></span> <span data-ttu-id="21e6f-174">例如，直接路由需要额外的步骤来配置呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="21e6f-174">For example, Direct Routing requires additional steps to configure call routing.</span></span> <span data-ttu-id="21e6f-175">另举一例，直接路由提供基于位置的路由 (LBR) ，以便你可以限制某些不允许的地理位置的收费绕过。</span><span class="sxs-lookup"><span data-stu-id="21e6f-175">As another example, Direct Routing provides Location-Based-Routing (LBR)--so that you can restrict toll bypass in certain geographic locations where it is not allowed.</span></span> 


### <a name="phone-number-management"></a><span data-ttu-id="21e6f-176">电话数字管理</span><span class="sxs-lookup"><span data-stu-id="21e6f-176">Phone number management</span></span>

<span data-ttu-id="21e6f-177">Microsoft 提供两种类型的电话号码：订阅者 (用户) 号码（可分配给您的组织中的用户）和服务号码（以收费和免费服务号码提供）。</span><span class="sxs-lookup"><span data-stu-id="21e6f-177">Microsoft has two types of telephone numbers available: subscriber (user) numbers, which can be assigned to users in your organization, and service numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="21e6f-178">服务号码的并发呼叫容量高于订阅者号码，可分配给音频会议、自动助理或呼叫队列等服务。</span><span class="sxs-lookup"><span data-stu-id="21e6f-178">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="21e6f-179">需要确定：</span><span class="sxs-lookup"><span data-stu-id="21e6f-179">You will need to decide:</span></span>

- <span data-ttu-id="21e6f-180">哪些用户位置需要 Microsoft 提供的新电话号码？</span><span class="sxs-lookup"><span data-stu-id="21e6f-180">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="21e6f-181">需要哪种类型的 (或) 电话号码？</span><span class="sxs-lookup"><span data-stu-id="21e6f-181">Which type of telephone number (subscriber or service) do I need?</span></span>
- <span data-ttu-id="21e6f-182">如何将现有电话号码移植到Teams？</span><span class="sxs-lookup"><span data-stu-id="21e6f-182">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="21e6f-183">根据 PSTN 连接选项，你获取和管理电话号码的不同。</span><span class="sxs-lookup"><span data-stu-id="21e6f-183">How you acquire and manage phone numbers differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="21e6f-184">有关管理呼叫计划的电话号码的信息，请参阅 [管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="21e6f-184">For information about managing phone numbers for Calling Plan, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="21e6f-185">有关管理直接路由的电话号码的信息，请参阅配置 [电话号码并启用企业语音和语音邮件](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)。</span><span class="sxs-lookup"><span data-stu-id="21e6f-185">For information about managing phone numbers for Direct Routing, see [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).</span></span>

- <span data-ttu-id="21e6f-186">有关使用接线员管理电话号码连接，[请参阅使用](operator-connect-configure.md#set-up-phone-numbers)接线员连接。</span><span class="sxs-lookup"><span data-stu-id="21e6f-186">For information about managing phone numbers with Operator Connect, see [Set up phone numbers with Operator Connect](operator-connect-configure.md#set-up-phone-numbers).</span></span>


### <a name="call-routing-and-dial-plans"></a><span data-ttu-id="21e6f-187">呼叫路由和拨号计划</span><span class="sxs-lookup"><span data-stu-id="21e6f-187">Call routing and dial plans</span></span>

<span data-ttu-id="21e6f-188">您的呼叫路由配置方式因 PSTN 连接选项的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="21e6f-188">How you configure call routing differs depending on your PSTN connectivity option.</span></span>  

- <span data-ttu-id="21e6f-189">对于呼叫计划，大多数呼叫路由由 Microsoft 呼叫计划基础结构处理。</span><span class="sxs-lookup"><span data-stu-id="21e6f-189">For Calling Plans, most of call routing is handled by the Microsoft Calling Plan infrastructure.</span></span> <span data-ttu-id="21e6f-190">为呼叫授权和呼叫路由配置用户拨号计划，以便进行号码转换。</span><span class="sxs-lookup"><span data-stu-id="21e6f-190">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="21e6f-191">有关详细信息，请参阅[什么是拨号计划？。](what-are-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="21e6f-191">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>

- <span data-ttu-id="21e6f-192">对于直接路由，必须通过指定语音路由并将语音路由策略分配给用户来配置呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="21e6f-192">For Direct Routing, you must configure call routing by specifying the voice routes and assigning voice routing policies to users.</span></span> <span data-ttu-id="21e6f-193">可以在中继级别为号码转换配置拨号计划，以确保与会话边界控制器 (SDC) 。</span><span class="sxs-lookup"><span data-stu-id="21e6f-193">You can configure dial plans for number translation at the trunk level to ensure interoperability with Session Border Controllers (SBCs).</span></span> <span data-ttu-id="21e6f-194">有关详细信息，请参阅配置直接 [路由的语音路由](direct-routing-voice-routing.md)、 [管理语音路由策略](manage-voice-routing-policies.md) 和 [转换电话号码](direct-routing-translate-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="21e6f-194">For more information, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), [Manage voice routing policies](manage-voice-routing-policies.md) and [Translate phone numbers](direct-routing-translate-numbers.md).</span></span> 

- <span data-ttu-id="21e6f-195">对于运营商连接，大多数呼叫路由由运营商管理。</span><span class="sxs-lookup"><span data-stu-id="21e6f-195">For Operator Connect, most of call routing is managed by the carrier.</span></span>  <span data-ttu-id="21e6f-196">为呼叫授权和呼叫路由配置用户拨号计划，以便进行号码转换。</span><span class="sxs-lookup"><span data-stu-id="21e6f-196">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="21e6f-197">有关详细信息，请参阅[什么是拨号计划？。](what-are-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="21e6f-197">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>


### <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="21e6f-198">Location-Based直接路由的路由</span><span class="sxs-lookup"><span data-stu-id="21e6f-198">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="21e6f-199">在某些国家和地区，绕过 PSTN 运营商降低长途呼叫费用非法。</span><span class="sxs-lookup"><span data-stu-id="21e6f-199">In some countries and regions, it's illegal to bypass the PSTN carrier to decrease long-distance calling costs.</span></span> <span data-ttu-id="21e6f-200">Location-Based直接 (LBR) ，可基于用户的地理位置限制Teams用户免收费。</span><span class="sxs-lookup"><span data-stu-id="21e6f-200">Location-Based Routing (LBR) for Direct Routing enables you to restrict toll bypass for Teams users based on their geographic location.</span></span> <span data-ttu-id="21e6f-201">若要详细了解如何计划和配置 LBR，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="21e6f-201">For more information about how to plan and configure LBR, see the following articles:</span></span>

- [<span data-ttu-id="21e6f-202">为直接路由计划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="21e6f-202">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="21e6f-203">为基于位置的路由配置网络设置</span><span class="sxs-lookup"><span data-stu-id="21e6f-203">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="21e6f-204">为直接路由启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="21e6f-204">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="21e6f-205">Contoso 案例研究：Location-Based路由</span><span class="sxs-lookup"><span data-stu-id="21e6f-205">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="21e6f-206">介绍虚拟的多语言公司 Contoso 如何为Location-Based实现路由。</span><span class="sxs-lookup"><span data-stu-id="21e6f-206">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>


### <a name="emergency-calling"></a><span data-ttu-id="21e6f-207">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="21e6f-207">Emergency calling</span></span>

<span data-ttu-id="21e6f-208">根据 PSTN 连接选项，紧急呼叫配置方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="21e6f-208">How you configure emergency calling differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="21e6f-209">对于"呼叫计划"，每个用户会自动启用紧急呼叫，并且需要具有与其分配的电话号码相关联的已注册紧急地址。</span><span class="sxs-lookup"><span data-stu-id="21e6f-209">For Calling Plan, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> <span data-ttu-id="21e6f-210">支持 (客户端服务位置Teams动态) 紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21e6f-210">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>  

- <span data-ttu-id="21e6f-211">对于直接路由，必须使用 Teams 紧急呼叫路由策略 (TeamsEmergencyCallRoutingPolicy) 来定义紧急号码及其关联的路由目标，为用户定义紧急呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="21e6f-211">For Direct Routing, you must define emergency calling policies for users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="21e6f-212">直接路由用户不支持已注册的紧急位置。</span><span class="sxs-lookup"><span data-stu-id="21e6f-212">Registered emergency locations are not supported for Direct Routing users.</span></span> <span data-ttu-id="21e6f-213">对于动态紧急呼叫，需要其他配置才能路由紧急呼叫，并可能需要进行合作伙伴连接。</span><span class="sxs-lookup"><span data-stu-id="21e6f-213">For dynamic emergency calling, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span>

- <span data-ttu-id="21e6f-214">对于接线连接，会自动为每个用户启用紧急呼叫，并且要求具有与其分配的电话号码相关联的已注册紧急地址，但只能由运营商合作伙伴设置。</span><span class="sxs-lookup"><span data-stu-id="21e6f-214">For Operator Connect, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number but can only be set by the carrier partner.</span></span> <span data-ttu-id="21e6f-215">支持 (客户端服务位置Teams动态) 紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21e6f-215">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>

<span data-ttu-id="21e6f-216">有关紧急呼叫的概念和术语以及如何配置紧急呼叫和动态紧急呼叫的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="21e6f-216">For more information about emergency calling concepts and terminology, and how to configure emergency calling and dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="21e6f-217">管理紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="21e6f-217">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="21e6f-218">规划和配置动态紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="21e6f-218">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="21e6f-219">管理紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="21e6f-219">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="21e6f-220">管理直接路由的紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="21e6f-220">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="21e6f-221">Contoso 案例研究：紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="21e6f-221">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="21e6f-222">介绍虚构的多语言公司 Contoso 如何为组织实施紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="21e6f-222">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>


### <a name="network-topology-for-voice-features"></a><span data-ttu-id="21e6f-223">语音功能的网络拓扑</span><span class="sxs-lookup"><span data-stu-id="21e6f-223">Network topology for voice features</span></span>

<span data-ttu-id="21e6f-224">如果要为直接路由部署动态紧急呼叫或Location-Based路由，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="21e6f-224">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="21e6f-225">若要了解如何为网络区域、网络站点、网络子网和受信任的 IP 地址配置网络设置，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="21e6f-225">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="21e6f-226">云语音功能网络设置Microsoft Teams - 概念和术语</span><span class="sxs-lookup"><span data-stu-id="21e6f-226">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="21e6f-227">管理云语音功能的网络拓扑Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="21e6f-227">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)



