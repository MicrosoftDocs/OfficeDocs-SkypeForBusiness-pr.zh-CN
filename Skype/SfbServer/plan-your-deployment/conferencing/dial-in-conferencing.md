---
title: 在 Skype for Business Server 中规划电话拨入式会议
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 摘要：阅读本主题，了解有关在 Skype for Business Server 中规划电话拨入式会议的信息。
ms.openlocfilehash: 31e422a07c34eaf17c09157c2e12ad843dbacb03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814002"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="e3913-103">在 Skype for Business Server 中规划电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="e3913-103">Plan for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="e3913-104">**摘要：** 阅读本主题，了解如何在 Skype for Business Server 中规划电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="e3913-104">**Summary:** Read this topic to learn about planning for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="e3913-105">电话拨入式会议是 Skype for Business Server 的一项可选功能，允许与会者通过电话拨入会议来加入会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="e3913-105">Dial-in conferencing is an optional feature of Skype for Business Server that allows meeting attendees to join the audio portion of a meeting by calling in to the meeting from a phone.</span></span> <span data-ttu-id="e3913-106">电话拨入式会议是音频会议的一部分且需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="e3913-106">Dial-in conferencing is a subset of audio conferencing and requires additional configuration.</span></span> <span data-ttu-id="e3913-107">本主题介绍在为组织部署电话拨入式会议之前需要思考的内容。</span><span class="sxs-lookup"><span data-stu-id="e3913-107">This topic describes what you need to think about before deploying dial-in conferencing for your organization.</span></span> 
  
<span data-ttu-id="e3913-108">电话拨入式会议所需的一些组件特定于电话拨入式会议，有些组件企业语音组件。</span><span class="sxs-lookup"><span data-stu-id="e3913-108">Some of the components required for dial-in conferencing are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="e3913-109">尽管电话拨入式会议使用某些与企业语音相同的组件，但即使未部署电话拨入式会议，企业语音。</span><span class="sxs-lookup"><span data-stu-id="e3913-109">Although dial-in conferencing uses some of the same components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span> <span data-ttu-id="e3913-110">本节介绍电话拨入式会议所需的组件。</span><span class="sxs-lookup"><span data-stu-id="e3913-110">This section describes the components that are needed for dial-in conferencing.</span></span> <span data-ttu-id="e3913-111">有关规划完整解决方案企业语音，请参阅 Plan your 企业语音[solution in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)</span><span class="sxs-lookup"><span data-stu-id="e3913-111">For more information about planning a complete Enterprise Voice solution, see [Plan your Enterprise Voice solution in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).</span></span>
  
<span data-ttu-id="e3913-112">电话拨入式会议要求通过部署中介服务器 (PSTN) 公用电话交换网的连接。</span><span class="sxs-lookup"><span data-stu-id="e3913-112">Dial-in conferencing requires that you provide connectivity to the public switched telephone network (PSTN) by deploying a Mediation Server.</span></span> <span data-ttu-id="e3913-113">除了部署中介服务器之外，还需要考虑以下事项，以允许组织进行电话拨入式会议：</span><span class="sxs-lookup"><span data-stu-id="e3913-113">In addition to deploying a Mediation Server, you need to consider the following to allow dial-in conferencing for your organization:</span></span>
  
- <span data-ttu-id="e3913-114">您用于连接到 PSTN 电话公用电话交换网 (PSTN) </span><span class="sxs-lookup"><span data-stu-id="e3913-114">Your plan for connecting to the public switched telephone network (PSTN)</span></span>
    
- <span data-ttu-id="e3913-115">拨号计划、访问号码和会议区域计划</span><span class="sxs-lookup"><span data-stu-id="e3913-115">Your plan for dial plans, access numbers, and conferencing regions</span></span>
    
- <span data-ttu-id="e3913-116">创建会议目录的计划</span><span class="sxs-lookup"><span data-stu-id="e3913-116">Your plan for creating conferencing directories</span></span>
    
- <span data-ttu-id="e3913-117">允许拨入访问的会议策略</span><span class="sxs-lookup"><span data-stu-id="e3913-117">Your conferencing policy for allowing dial-in access</span></span>
    
- <span data-ttu-id="e3913-118">支持企业用户和匿名用户</span><span class="sxs-lookup"><span data-stu-id="e3913-118">Support for enterprise and anonymous users</span></span>
    
> [!NOTE]
> <span data-ttu-id="e3913-119">如果部署电话拨入式会议，则必须在部署 Skype for Business Server 会议的每一个池中部署电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="e3913-119">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Skype for Business Server conferencing.</span></span> <span data-ttu-id="e3913-120">无需为每个池中分配访问号码（参与者为加入会议而呼叫的号码），但必须在每个池中部署拨入功能。</span><span class="sxs-lookup"><span data-stu-id="e3913-120">You do not need to assign access numbers--the numbers participants call to join a conference--in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="e3913-121">当用户从一个池中呼叫访问号码以加入其他池中的 Skype for Business Server 会议时，此要求支持记录的名称功能。</span><span class="sxs-lookup"><span data-stu-id="e3913-121">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Skype for Business Server conference in a different pool.</span></span> 
  
## <a name="plan-for-pstn-connectivity"></a><span data-ttu-id="e3913-122">规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="e3913-122">Plan for PSTN connectivity</span></span>

<span data-ttu-id="e3913-123">电话拨入式会议至少需要一台中介服务器和至少一个公用电话交换网 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="e3913-123">Dial-in conferencing requires at least one Mediation Server and at least one public switched telephone network (PSTN) gateway.</span></span> 
  
<span data-ttu-id="e3913-124">可以在中央站点或分支站点部署中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e3913-124">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="e3913-125">在中央站点中，可以将中介服务器并排在前端池或 Standard Edition 服务器上，也可以将其部署在独立服务器或池中。</span><span class="sxs-lookup"><span data-stu-id="e3913-125">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="e3913-126">在分支站点中，可以在独立服务器上部署中介服务器，也可以将中介服务器部署为 Survivable Branch Appliance 的组件。</span><span class="sxs-lookup"><span data-stu-id="e3913-126">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>
  
<span data-ttu-id="e3913-127">您可以在中央站点或分支站点部署 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="e3913-127">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="e3913-128">在分支站点中，PSTN 网关可以是独立网关，也可以是 Survivable Branch Appliance 的组件。</span><span class="sxs-lookup"><span data-stu-id="e3913-128">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>
  
<span data-ttu-id="e3913-129">有关中介服务器和 PSTN 网关要求的详细信息，请参阅 [Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)中的中介服务器组件、在 Skype for Business [Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)的拓扑生成器中部署中介服务器，以及定义 Skype for [Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md)中的拓扑生成器中的网关。</span><span class="sxs-lookup"><span data-stu-id="e3913-129">For details about Mediation Server and PSTN gateway requirements, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), [Deploy a Mediation Server in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md), and [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a><span data-ttu-id="e3913-130">规划拨号计划、访问号码和会议区域</span><span class="sxs-lookup"><span data-stu-id="e3913-130">Plan for dial plans, access numbers, and conferencing regions</span></span>

<span data-ttu-id="e3913-131">若要配置电话拨入式会议，请创建拨号计划和电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="e3913-131">To configure dial-in conferencing, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="e3913-132">还可以指定将电话拨入式会议访问号码与拨号计划相关联的拨入区域。</span><span class="sxs-lookup"><span data-stu-id="e3913-132">You also specify the dial-in regions that associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="e3913-133">更具体地说：</span><span class="sxs-lookup"><span data-stu-id="e3913-133">More specifically:</span></span>
  
- <span data-ttu-id="e3913-134">拨号计划是一组规范化规则，用于指定电话号码中的位数和数字模式，将电话号码转换为呼叫路由所需的标准 E.164 格式。</span><span class="sxs-lookup"><span data-stu-id="e3913-134">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number, and translate the phone number into the standard E.164 format required for call routing.</span></span>
    
- <span data-ttu-id="e3913-135">电话拨入式会议访问号码是参与者为加入会议而呼叫的号码。</span><span class="sxs-lookup"><span data-stu-id="e3913-135">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>
    
- <span data-ttu-id="e3913-136">每个电话拨入式会议访问号码必须至少与一个拨号计划关联。</span><span class="sxs-lookup"><span data-stu-id="e3913-136">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> 
    
- <span data-ttu-id="e3913-137">每个拨号计划都与一个会议区域关联。</span><span class="sxs-lookup"><span data-stu-id="e3913-137">Every dial plan is associated with a conferencing region.</span></span>
    
<span data-ttu-id="e3913-138">创建拨号计划时，指定适用于拨号计划的电话拨入式会议区域。</span><span class="sxs-lookup"><span data-stu-id="e3913-138">When you create a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="e3913-139">在创建拨入访问号码时，选择将该访问号码与相应拨号计划关联的区域。</span><span class="sxs-lookup"><span data-stu-id="e3913-139">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>
  
<span data-ttu-id="e3913-140">还可以指定拨号计划的范围：用户作用域、池作用域或站点范围。</span><span class="sxs-lookup"><span data-stu-id="e3913-140">You also specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="e3913-141">会按照各用户适用的最小作用域为其分配拨号计划。</span><span class="sxs-lookup"><span data-stu-id="e3913-141">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="e3913-142">例如，如果适用，则为用户分配用户级别的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="e3913-142">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="e3913-143">如果用户级别的拨号计划不适用，则为用户分配池级别的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="e3913-143">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="e3913-144">如果池级别的拨号计划不适用，则为用户分配站点级别的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="e3913-144">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="e3913-145">如果站点级别的拨号计划不适用，则为用户分配全局拨号计划。</span><span class="sxs-lookup"><span data-stu-id="e3913-145">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span> 
  
<span data-ttu-id="e3913-p110">配置拨号计划之前，规划命名和使用区域的方式非常重要。对于电话拨入式会议区域，请注意下列事项：</span><span class="sxs-lookup"><span data-stu-id="e3913-p110">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>
  
- <span data-ttu-id="e3913-148">区域通常是与某个办公室或一组办公室相关联的地理区域。</span><span class="sxs-lookup"><span data-stu-id="e3913-148">A region is typically a geographical area that is associated with an office or group of offices.</span></span>
    
- <span data-ttu-id="e3913-p111">语言与拨入访问号码相关联。如果支持具有多种语言的地理区域，应该决定如何定义区域以便支持多种语言。例如，可以基于地理位置和语言的组合定义多个区域，或者基于地理位置定义一个区域，且每种语言拥有不同的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="e3913-p111">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>
    
- <span data-ttu-id="e3913-152">用户安排会议时，默认情况下会议将使用用户的拨号计划所指定的区域。</span><span class="sxs-lookup"><span data-stu-id="e3913-152">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>
    
- <span data-ttu-id="e3913-153">默认情况下，区域的所有拨入访问号码都包含在会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="e3913-153">By default, all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>
    
- <span data-ttu-id="e3913-154">命名区域非常重要，以便可以清楚地识别它们。</span><span class="sxs-lookup"><span data-stu-id="e3913-154">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="e3913-155">用户可以使用区域名称更改会议区域，以便邀请中包括不同的访问号码。</span><span class="sxs-lookup"><span data-stu-id="e3913-155">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="e3913-156"> (当用户使用 Outlook 安排会议时，用户使用 Skype for Business 的联机会议外接程序更改区域) 。</span><span class="sxs-lookup"><span data-stu-id="e3913-156">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Skype for Business to change the region).</span></span>
    
- <span data-ttu-id="e3913-157">应该对区域加以设计，以便想要拨入会议的被邀请者可以在会议邀请中看到本地访问号码。</span><span class="sxs-lookup"><span data-stu-id="e3913-157">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>
    
- <span data-ttu-id="e3913-158">可以使用 Skype for Business Server 命令行管理程序 cmdlet 配置区域内访问号码在"电话拨入式会议设置"页上的显示顺序 (以及这些号码在会议邀请) 中的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="e3913-158">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Skype for Business Server Management Shell cmdlets.</span></span>
    
- <span data-ttu-id="e3913-159">任何位置的任何用户均可拨打拨入访问号码来加入会议。</span><span class="sxs-lookup"><span data-stu-id="e3913-159">Any user from any location can call any dial-in access number to join a conference.</span></span>
    
<span data-ttu-id="e3913-160">有关创建拨号计划的信息，请参阅在 [Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) 中创建或修改拨号计划，以及创建或修改 Skype for Business [中的规范化规则](../../deploy/deploy-enterprise-voice/normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="e3913-160">For more information about creating a dial plan, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span> 
  
## <a name="plan-for-conference-directories"></a><span data-ttu-id="e3913-161">规划会议目录</span><span class="sxs-lookup"><span data-stu-id="e3913-161">Plan for conference directories</span></span>

<span data-ttu-id="e3913-162">会议目录维护参与者使用 Skype for Business 加入会议时用于加入会议的字母数字会议 ID 与电话拨入式会议参与者用于加入会议的唯一数字会议 ID 之间的映射。</span><span class="sxs-lookup"><span data-stu-id="e3913-162">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="e3913-163">会议 ID 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="e3913-163">The format of the conference ID is as follows:</span></span>
  

\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\>


<span data-ttu-id="e3913-164">创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。</span><span class="sxs-lookup"><span data-stu-id="e3913-164">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="e3913-165">在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。</span><span class="sxs-lookup"><span data-stu-id="e3913-165">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="e3913-166">使用此指南，会议 ID 通常可以保持较小。</span><span class="sxs-lookup"><span data-stu-id="e3913-166">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="e3913-167">但是，一旦会议目录的数目（在池中）超过 9，则会议 ID 号将增大以支持其他会议。</span><span class="sxs-lookup"><span data-stu-id="e3913-167">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a><span data-ttu-id="e3913-168">规划允许拨入访问的会议策略</span><span class="sxs-lookup"><span data-stu-id="e3913-168">Plan for a conferencing policy that allows dial-in access</span></span>

<span data-ttu-id="e3913-169">配置会议策略时，必须为会议启用拨入访问。</span><span class="sxs-lookup"><span data-stu-id="e3913-169">Conferences must be enabled for dial-in access when you configure conferencing policies.</span></span> <span data-ttu-id="e3913-170">默认情况下，允许拨入访问的会议会在会议邀请中包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="e3913-170">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>
  
- <span data-ttu-id="e3913-171">用于标识会议的数字会议 ID</span><span class="sxs-lookup"><span data-stu-id="e3913-171">A numeric conference ID that identifies the conference</span></span>
    
- <span data-ttu-id="e3913-172">一个或多个 PSTN 访问号码</span><span class="sxs-lookup"><span data-stu-id="e3913-172">One or more PSTN access numbers</span></span>
    
- <span data-ttu-id="e3913-173">指向"电话拨入式会议设置"页的链接，其中包含使用其关联语言的访问号码的完整列表;创建、重置或取消阻止个人标识号 (PIN) ;以及其他信息，例如双音多频 (DTMF) 控件</span><span class="sxs-lookup"><span data-stu-id="e3913-173">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls</span></span>
    
<span data-ttu-id="e3913-174">有关会议策略详细信息，请参阅在 [Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) 中配置电话拨入式会议，以及管理 Skype for Business Server 中的 [会议策略](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e3913-174">For more information about conferencing policies, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) and [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>  

## <a name="support-for-enterprise-and-anonymous-users"></a><span data-ttu-id="e3913-175">支持企业用户和匿名用户</span><span class="sxs-lookup"><span data-stu-id="e3913-175">Support for enterprise and anonymous users</span></span>

<span data-ttu-id="e3913-176">电话拨入式会议支持企业用户和匿名用户。</span><span class="sxs-lookup"><span data-stu-id="e3913-176">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="e3913-177">企业用户在其组织中具有 Active Directory 域服务凭据和 Skype for Business Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="e3913-177">Enterprise users have Active Directory Domain Services credentials and Skype for Business Server accounts within their organization.</span></span> <span data-ttu-id="e3913-178">匿名用户在组织内不具有企业凭据。</span><span class="sxs-lookup"><span data-stu-id="e3913-178">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="e3913-179">在电话拨入式会议上下文中，联盟伙伴组织中使用 PSTN 连接到会议的用户被视为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="e3913-179">In the dial-in conferencing context, a user in a federated partner's organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="e3913-180">对于电话拨入式会议（不同于其他环境），联盟用户都未经过身份验证。</span><span class="sxs-lookup"><span data-stu-id="e3913-180">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>
  
<span data-ttu-id="e3913-181">参加允许拨入访问会议的企业用户或会议主持人拨打一个会议访问号码后，系统会提示他们输入会议 ID。</span><span class="sxs-lookup"><span data-stu-id="e3913-181">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="e3913-182">如果主持人尚未参加会议，则用户可以输入其统一通信 (UC) 分机号（或完整电话号码）和 PIN，或者等待主持人准许其参加会议。</span><span class="sxs-lookup"><span data-stu-id="e3913-182">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="e3913-183">通过只输入其 PIN，会议组织者就可以以主持人身份参加会议。</span><span class="sxs-lookup"><span data-stu-id="e3913-183">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="e3913-184">前端服务器使用完整电话号码或分机号和 PIN 的组合来唯一地将企业用户映射到其 Active Directory 凭据。</span><span class="sxs-lookup"><span data-stu-id="e3913-184">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="e3913-185">因此，在会议中是按名称对企业用户进行身份验证和标识的。</span><span class="sxs-lookup"><span data-stu-id="e3913-185">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="e3913-186">企业用户还可以担任由组织者预定义的会议角色。</span><span class="sxs-lookup"><span data-stu-id="e3913-186">Enterprise users can also assume a conference role predefined by the organizer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3913-187">从 Office IP 电话或 Skype for Business Server Attendant 拨入的企业用户不会提示输入其电话号码，因为他们已经过身份验证。</span><span class="sxs-lookup"><span data-stu-id="e3913-187">Enterprise users who dial in from an office IP phone or from Skype for Business Server Attendant are not prompted for their phone number because they are already authenticated.</span></span> 
  
<span data-ttu-id="e3913-p118">要参加电话拨入式会议的匿名用户拨打一个会议接入号码后，系统会提示他们输入会议 ID。还会提示未经身份验证的匿名用户记录其名称。记录的名称用于在会议中标识未经身份验证的用户。除非至少一个主持人或经过身份验证的用户已参加会议，否则不允许匿名用户参加会议，且无法向其分配预定义角色。</span><span class="sxs-lookup"><span data-stu-id="e3913-p118">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3913-p119">选择不输入其电话号码和 PIN 的企业用户未经过身份验证。系统会提示他们记录其名称，并在会议中将他们视为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="e3913-p119">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span> 
  
<span data-ttu-id="e3913-194">安排会议时，会议组织者可以选择通过关闭或锁定会议来限制对会议的访问。</span><span class="sxs-lookup"><span data-stu-id="e3913-194">When scheduling a meeting, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="e3913-195">在这种情况下，会请求拨入用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e3913-195">In this case, dial-in users are requested to authenticate.</span></span> 
  
- <span data-ttu-id="e3913-196">如果拨入用户失败或选择不进行身份验证，他们将被转移到会议厅，直到领导接受或拒绝他们，或者他们退出并断开连接。</span><span class="sxs-lookup"><span data-stu-id="e3913-196">If dial-in users fail or choose not to authenticate, they are transferred to the lobby where they until a leader accepts or rejects them, or they time out and are disconnected.</span></span>
    
- <span data-ttu-id="e3913-197">在允许他们参加会议后，电话拨入用户可以参与会议的音频部分，并且可以使用电话小键盘练习双音多频 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="e3913-197">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span>
    
- <span data-ttu-id="e3913-198">电话拨入式领导可以练习 DTMF 命令，使参与者能够打开或关闭静音、锁定或解锁会议、允许来自会议厅的人，以及打开或关闭进入和退出通知。</span><span class="sxs-lookup"><span data-stu-id="e3913-198">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span>
    
- <span data-ttu-id="e3913-199">领导者还可使用 DTMF 命令允许会议厅中的每个人参加会议，这将更改会议权限以允许随后加入的任何人。</span><span class="sxs-lookup"><span data-stu-id="e3913-199">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> 
    
- <span data-ttu-id="e3913-200">所有拨入参与者都可以练习 DTMF 命令，以收听帮助、收听会议名单和将自己静音。</span><span class="sxs-lookup"><span data-stu-id="e3913-200">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>
    
- <span data-ttu-id="e3913-201">电话拨入参与者 (即是否从 PSTN) 在会议期间听到个人通知，例如是否已静音或取消静音、是否录制会议，或者是否有人正在会议厅中等待。</span><span class="sxs-lookup"><span data-stu-id="e3913-201">Dial-in participants (that is, whether or not they dial from the PSTN) hear personal announcements during the conference, such as whether they have been muted or unmuted, whether the meeting is being recorded, or whether someone is waiting in the lobby.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3913-202">通过单击链接（而不是电话拨入）参加会议的与会者不会听到个人通知。</span><span class="sxs-lookup"><span data-stu-id="e3913-202">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span> 
  

