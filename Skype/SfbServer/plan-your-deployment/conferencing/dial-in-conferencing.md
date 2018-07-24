---
title: 规划电话拨入式会议中 Skype 业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 摘要： 阅读本主题可了解有关规划业务服务器中 Skype 电话拨入式会议。
ms.openlocfilehash: 1b051cc757c0e55fb2f16b790921da962738ade3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973575"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="6a63c-103">规划电话拨入式会议中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="6a63c-103">Plan for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="6a63c-104">**摘要：** 阅读本主题可了解如何规划中 Skype 电话拨入式会议的企业服务器。</span><span class="sxs-lookup"><span data-stu-id="6a63c-104">**Summary:** Read this topic to learn about planning for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="6a63c-105">电话拨入式会议是可选的 Skype 允许与会者加入会议的音频部分，通过从电话加入会议调用中的业务服务器功能。</span><span class="sxs-lookup"><span data-stu-id="6a63c-105">Dial-in conferencing is an optional feature of Skype for Business Server that allows meeting attendees to join the audio portion of a meeting by calling in to the meeting from a phone.</span></span> <span data-ttu-id="6a63c-106">电话拨入式会议是音频会议的子集，需要额外的配置。</span><span class="sxs-lookup"><span data-stu-id="6a63c-106">Dial-in conferencing is a subset of audio conferencing and requires additional configuration.</span></span> <span data-ttu-id="6a63c-107">本主题描述在为组织部署电话拨入式会议之前，需要考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="6a63c-107">This topic describes what you need to think about before deploying dial-in conferencing for your organization.</span></span> 
  
<span data-ttu-id="6a63c-108">特定于电话拨入式会议的电话拨入式会议所需的组件一些和一些企业语音组件。</span><span class="sxs-lookup"><span data-stu-id="6a63c-108">Some of the components required for dial-in conferencing are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="6a63c-109">虽然电话拨入式会议使用的某些组件与企业语音使用的组件相同，但是即使未部署企业语音，也可以部署电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="6a63c-109">Although dial-in conferencing uses some of the same components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span> <span data-ttu-id="6a63c-110">本节介绍电话拨入式会议所需的组件。</span><span class="sxs-lookup"><span data-stu-id="6a63c-110">This section describes the components that are needed for dial-in conferencing.</span></span> <span data-ttu-id="6a63c-111">有关规划完整的企业语音解决方案的详细信息，请参阅[规划企业语音解决方案中的业务服务器 Skype](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="6a63c-111">For more information about planning a complete Enterprise Voice solution, see [Plan your Enterprise Voice solution in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).</span></span>
  
<span data-ttu-id="6a63c-112">电话拨入式会议需要您部署中介服务器来提供与公用电话交换网 (PSTN) 的连接。</span><span class="sxs-lookup"><span data-stu-id="6a63c-112">Dial-in conferencing requires that you provide connectivity to the public switched telephone network (PSTN) by deploying a Mediation Server.</span></span> <span data-ttu-id="6a63c-113">除了部署中介服务器外，还需要考虑以下几点来为组织实现电话拨入式会议：</span><span class="sxs-lookup"><span data-stu-id="6a63c-113">In addition to deploying a Mediation Server, you need to consider the following to allow dial-in conferencing for your organization:</span></span>
  
- <span data-ttu-id="6a63c-114">连接公用电话交换网 (PSTN) 的规划</span><span class="sxs-lookup"><span data-stu-id="6a63c-114">Your plan for connecting to the public switched telephone network (PSTN)</span></span>
    
- <span data-ttu-id="6a63c-115">拨号计划、访问号码以及会议区域的规划</span><span class="sxs-lookup"><span data-stu-id="6a63c-115">Your plan for dial plans, access numbers, and conferencing regions</span></span>
    
- <span data-ttu-id="6a63c-116">创建会议目录的规划</span><span class="sxs-lookup"><span data-stu-id="6a63c-116">Your plan for creating conferencing directories</span></span>
    
- <span data-ttu-id="6a63c-117">允许拨入访问的会议策略</span><span class="sxs-lookup"><span data-stu-id="6a63c-117">Your conferencing policy for allowing dial-in access</span></span>
    
- <span data-ttu-id="6a63c-118">支持企业用户和匿名用户</span><span class="sxs-lookup"><span data-stu-id="6a63c-118">Support for enterprise and anonymous users</span></span>
    
> [!NOTE]
> <span data-ttu-id="6a63c-119">如果您部署电话拨入式会议，您必须在其中部署 Skype Business Server 会议的每个池部署。</span><span class="sxs-lookup"><span data-stu-id="6a63c-119">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Skype for Business Server conferencing.</span></span> <span data-ttu-id="6a63c-120">无需在每个池中分配访问号码（参与者为加入会议而呼叫的号码），但必须在每个池中部署拨入功能。</span><span class="sxs-lookup"><span data-stu-id="6a63c-120">You do not need to assign access numbers--the numbers participants call to join a conference--in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="6a63c-121">当用户从一个池加入 Business Server 会议池中不同 Skype 呼叫访问号码，这一要求支持录制的名称功能。</span><span class="sxs-lookup"><span data-stu-id="6a63c-121">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Skype for Business Server conference in a different pool.</span></span> 
  
## <a name="plan-for-pstn-connectivity"></a><span data-ttu-id="6a63c-122">规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="6a63c-122">Plan for PSTN connectivity</span></span>

<span data-ttu-id="6a63c-123">电话拨入式会议至少需要一台中介服务器和一个公用电话交换网 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="6a63c-123">Dial-in conferencing requires at least one Mediation Server and at least one public switched telephone network (PSTN) gateway.</span></span> 
  
<span data-ttu-id="6a63c-p105">您可以在中央站点或分支站点部署中介服务器。在中央站点，您可以在前端池或 Standard Edition Server 并置中介服务器，或者将其部署在独立服务器或池中。在分支站点，您可以将中介服务器部署在独立服务器中或部署为 Survivable Branch Appliance 的组件。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p105">You can deploy a Mediation Server in a central site or in a branch site. In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool. In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>
  
<span data-ttu-id="6a63c-p106">您可以在中央站点或分支站点部署 PSTN 网关。在分支站点，PSTN 网关可以是独立的，也可以作为 Survivable Branch Appliance 的组件。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p106">You can deploy a PSTN gateway in a central site or in a branch site. In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>
  
<span data-ttu-id="6a63c-129">有关中介服务器和 PSTN 网关要求的详细信息，请参阅[Skype 业务服务器中的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)、[部署中介服务器中的业务服务器 Skype 的拓扑生成器中](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)和[定义拓扑的网关Skype 业务服务器中的生成器](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="6a63c-129">For details about Mediation Server and PSTN gateway requirements, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), [Deploy a Mediation Server in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md), and [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a><span data-ttu-id="6a63c-130">拨号计划、访问号码以及会议区域的规划</span><span class="sxs-lookup"><span data-stu-id="6a63c-130">Plan for dial plans, access numbers, and conferencing regions</span></span>

<span data-ttu-id="6a63c-p107">为了配置电话拨入式会议，要创建拨号计划和电话拨入式会议访问号码。还要指定将电话拨入式会议访问号码与其拨号计划相关联的拨入区域。更具体地说：</span><span class="sxs-lookup"><span data-stu-id="6a63c-p107">To configure dial-in conferencing, you create dial plans and dial-in conferencing access numbers. You also specify the dial-in regions that associate a dial-in conferencing access number with its dial plans. More specifically:</span></span>
  
- <span data-ttu-id="6a63c-134">拨号计划是几组规范化规则，用来指定电话号码的数字和数字模式，并将电话号码转换为呼叫路由所必需的标准 E.164 格式。</span><span class="sxs-lookup"><span data-stu-id="6a63c-134">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number, and translate the phone number into the standard E.164 format required for call routing.</span></span>
    
- <span data-ttu-id="6a63c-135">电话拨入式会议访问号码是参与者为加入会议而呼叫的号码。</span><span class="sxs-lookup"><span data-stu-id="6a63c-135">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>
    
- <span data-ttu-id="6a63c-136">每个电话拨入式会议访问号码必须至少与一个拨号计划关联。</span><span class="sxs-lookup"><span data-stu-id="6a63c-136">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> 
    
- <span data-ttu-id="6a63c-137">每个拨号计划与一个会议区域关联。</span><span class="sxs-lookup"><span data-stu-id="6a63c-137">Every dial plan is associated with a conferencing region.</span></span>
    
<span data-ttu-id="6a63c-p108">创建拨号计划时，要指定适用于该拨号计划的电话拨入式会议区域。创建拨入访问号码时，要选择将访问号码与相应的拨号计划相关联的区域。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p108">When you create a dial plan, you specify the dial-in conferencing region that applies to the dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>
  
<span data-ttu-id="6a63c-p109">还要指定拨号计划的作用域：用户作用域、池作用域或站点作用域。会按照各用户适用的最小作用域为其分配拨号计划。例如，如果适用，则为用户分配用户级别的拨号计划。如果用户级别的拨号计划不适用，则为用户分配池级别的拨号计划。如果池级别的拨号计划不适用，则为用户分配站点级别的拨号计划。如果站点级别的拨号计划不适用，则为用户分配全局拨号计划。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p109">You also specify the scope of the dial plan: user scope, pool scope, or site scope. Every user is assigned the dial plan from the narrowest scope that applies to the user. For example, a user is assigned a user-level dial plan, if one applies. If a user-level dial plan does not apply, the user is assigned a pool-level dial plan. If a pool-level dial plan does not apply, the user is assigned a site-level dial plan. If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span> 
  
<span data-ttu-id="6a63c-p110">配置拨号计划之前，规划命名和使用区域的方式非常重要。对于电话拨入式会议区域，请注意下列事项：</span><span class="sxs-lookup"><span data-stu-id="6a63c-p110">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>
  
- <span data-ttu-id="6a63c-148">区域通常是与某个办公室或一组办公室相关联的地理区域。</span><span class="sxs-lookup"><span data-stu-id="6a63c-148">A region is typically a geographical area that is associated with an office or group of offices.</span></span>
    
- <span data-ttu-id="6a63c-p111">语言与拨入访问号码相关联。如果支持具有多种语言的地理区域，应该决定如何定义区域以便支持多种语言。例如，可以基于地理位置和语言的组合定义多个区域，或者基于地理位置定义一个区域，且每种语言拥有不同的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p111">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>
    
- <span data-ttu-id="6a63c-152">用户安排会议时，默认情况下会议将使用用户的拨号计划所指定的区域。</span><span class="sxs-lookup"><span data-stu-id="6a63c-152">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>
    
- <span data-ttu-id="6a63c-153">默认情况下，区域的所有拨入访问号码都会包含在会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="6a63c-153">By default, all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>
    
- <span data-ttu-id="6a63c-154">是非常重要的名称区域以便它们清楚地识别。</span><span class="sxs-lookup"><span data-stu-id="6a63c-154">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="6a63c-155">用户可以使用的区域的名称，以便其他访问号码都包含在邀请中更改会议的地区。</span><span class="sxs-lookup"><span data-stu-id="6a63c-155">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="6a63c-156">（当用户使用 Outlook 安排会议时，用户使用联机会议外接程序 for Business 的 Skype 更改区域）。</span><span class="sxs-lookup"><span data-stu-id="6a63c-156">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Skype for Business to change the region).</span></span>
    
- <span data-ttu-id="6a63c-157">应该对区域加以设计，以便想要拨入会议的被邀请者可以在会议邀请中看到本地访问号码。</span><span class="sxs-lookup"><span data-stu-id="6a63c-157">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>
    
- <span data-ttu-id="6a63c-158">您可以使用 Skype 业务 Server Management Shell cmdlet 配置的访问号码区域内的出现在电话拨入式会议设置页的顺序 （和，因此，在会议邀请中的显示的顺序）。</span><span class="sxs-lookup"><span data-stu-id="6a63c-158">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Skype for Business Server Management Shell cmdlets.</span></span>
    
- <span data-ttu-id="6a63c-159">任何位置的任何用户均可拨打拨入访问号码来加入会议。</span><span class="sxs-lookup"><span data-stu-id="6a63c-159">Any user from any location can call any dial-in access number to join a conference.</span></span>
    
<span data-ttu-id="6a63c-160">有关创建拨号计划的详细信息，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)和[创建或修改规范化规则中的业务的 Skype](../../deploy/deploy-enterprise-voice/normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="6a63c-160">For more information about creating a dial plan, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span> 
  
## <a name="plan-for-conference-directories"></a><span data-ttu-id="6a63c-161">规划会议目录</span><span class="sxs-lookup"><span data-stu-id="6a63c-161">Plan for conference directories</span></span>

<span data-ttu-id="6a63c-162">会议目录维护参与者加入会议的业务，使用 Skype 时使用的字母数字会议 ID 和电话拨入式会议参与者使用加入会议的仅含数字会议 ID 之间的映射。</span><span class="sxs-lookup"><span data-stu-id="6a63c-162">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="6a63c-163">会议 ID 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="6a63c-163">The format of the conference ID is as follows:</span></span>
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="6a63c-p114">创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。使用此指南，通常可使会议 ID 保持较小数目。但是，一旦会议目录的数目（在池中）超过 9，则会议 ID 号将增大以支持其他会议。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p114">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created. In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a><span data-ttu-id="6a63c-168">允许拨入访问的会议策略的规划</span><span class="sxs-lookup"><span data-stu-id="6a63c-168">Plan for a conferencing policy that allows dial-in access</span></span>

<span data-ttu-id="6a63c-169">配置会议策略时必须启用电话拨入式访问会议。</span><span class="sxs-lookup"><span data-stu-id="6a63c-169">Conferences must be enabled for dial-in access when you configure conferencing policies.</span></span> <span data-ttu-id="6a63c-170">默认情况下，允许拨入访问的会议会在会议邀请中包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="6a63c-170">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>
  
- <span data-ttu-id="6a63c-171">用于标识会议的数字会议 ID</span><span class="sxs-lookup"><span data-stu-id="6a63c-171">A numeric conference ID that identifies the conference</span></span>
    
- <span data-ttu-id="6a63c-172">一个或多个 PSTN 访问号码</span><span class="sxs-lookup"><span data-stu-id="6a63c-172">One or more PSTN access numbers</span></span>
    
- <span data-ttu-id="6a63c-173">指向“电话拨入式会议设置”页的链接，其中包含有其关联语言的访问号码完整列表；创建、重置或解锁个人标识号 (PIN) 的位置；以及其他信息，例如，双音多频 (DTMF) 控制</span><span class="sxs-lookup"><span data-stu-id="6a63c-173">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls</span></span>
    
<span data-ttu-id="6a63c-174">有关会议策略的详细信息，请参阅[配置电话拨入式会议中的业务服务器 Skype](../../deploy/deploy-conferencing/dial-in-conferencing.md)和[Skype 业务服务器中的管理会议策略](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6a63c-174">For more information about conferencing policies, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) and [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>  

## <a name="support-for-enterprise-and-anonymous-users"></a><span data-ttu-id="6a63c-175">支持企业用户和匿名用户</span><span class="sxs-lookup"><span data-stu-id="6a63c-175">Support for enterprise and anonymous users</span></span>

<span data-ttu-id="6a63c-176">电话拨入式会议支持企业用户和匿名用户。</span><span class="sxs-lookup"><span data-stu-id="6a63c-176">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="6a63c-177">企业用户拥有 Active Directory 域服务凭据和 Skype 为其组织内的业务 Server 帐户。</span><span class="sxs-lookup"><span data-stu-id="6a63c-177">Enterprise users have Active Directory Domain Services credentials and Skype for Business Server accounts within their organization.</span></span> <span data-ttu-id="6a63c-178">匿名用户在组织内不具有企业凭据。</span><span class="sxs-lookup"><span data-stu-id="6a63c-178">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="6a63c-179">在电话拨入式会议上下文中，使用 PSTN 连接到会议的联盟的伙伴的组织中的用户视为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="6a63c-179">In the dial-in conferencing context, a user in a federated partner's organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="6a63c-180">对于电话拨入式会议（不同于其他环境），联盟用户都未经过身份验证。</span><span class="sxs-lookup"><span data-stu-id="6a63c-180">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>
  
<span data-ttu-id="6a63c-p117">参加允许拨入访问会议的企业用户或会议主持人拨打一个会议访问号码后，系统会提示他们输入会议 ID。如果主持人尚未参加会议，则用户可以输入其统一通信 (UC) 分机号（或完整电话号码）和 PIN，或者等待主持人准许其参加会议。通过只输入其 PIN，会议组织者就可以以主持人身份参加会议。前端服务器使用完整电话号码或分机号与 PIN 的组合唯一地将企业用户映射到其 Active Directory 凭据。因此，在会议中是按名称对企业用户进行身份验证和标识的。企业用户还可以担任由组织者预定义的会议角色。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p117">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID. If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader. The Meeting organizer can join the meeting as a leader by entering just their PIN. The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials. As a result, enterprise users are authenticated and identified by name in the conference. Enterprise users can also assume a conference role predefined by the organizer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a63c-187">因为已经过身份验证，拨入从办公 IP 电话或从 Skype 业务 Server attendant 的企业用户不会提示其电话号码。</span><span class="sxs-lookup"><span data-stu-id="6a63c-187">Enterprise users who dial in from an office IP phone or from Skype for Business Server Attendant are not prompted for their phone number because they are already authenticated.</span></span> 
  
<span data-ttu-id="6a63c-p118">要参加电话拨入式会议的匿名用户拨打一个会议接入号码后，系统会提示他们输入会议 ID。还会提示未经身份验证的匿名用户记录其名称。记录的名称用于在会议中标识未经身份验证的用户。除非至少一个主持人或经过身份验证的用户已参加会议，否则不允许匿名用户参加会议，且无法向其分配预定义角色。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p118">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a63c-p119">选择不输入其电话号码和 PIN 的企业用户未经过身份验证。系统会提示他们记录其名称，并在会议中将他们视为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p119">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span> 
  
<span data-ttu-id="6a63c-p120">安排会议时，会议组织者可选择关闭或锁定会议来限制访问会议。这种情况下，会请求拨入用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="6a63c-p120">When scheduling a meeting, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked. In this case, dial-in users are requested to authenticate.</span></span> 
  
- <span data-ttu-id="6a63c-196">如果拨入用户身份验证失败或选择不进行身份验证，他们会被转移到会议厅中等待，直到主持人接受或拒绝他们，或者连接超时并断开连接。</span><span class="sxs-lookup"><span data-stu-id="6a63c-196">If dial-in users fail or choose not to authenticate, they are transferred to the lobby where they until a leader accepts or rejects them, or they time out and are disconnected.</span></span>
    
- <span data-ttu-id="6a63c-197">一旦被允许加入会议，电话拨入用户就可以参与会议的音频部分，并可使用电话键盘执行双音多频 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="6a63c-197">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span>
    
- <span data-ttu-id="6a63c-198">电话拨入主持人可以使用 DTMF 命令打开或关闭参与者的取消静音功能、锁定或解锁会议、允许会议厅中的人加入会议、打开或关闭进入和退出通知。</span><span class="sxs-lookup"><span data-stu-id="6a63c-198">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span>
    
- <span data-ttu-id="6a63c-199">主持人还可以使用 DTMF 命令允许会议厅中的每个人加入会议，从而更改会议的权限以允许随后的任何人加入会议。</span><span class="sxs-lookup"><span data-stu-id="6a63c-199">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> 
    
- <span data-ttu-id="6a63c-200">所有电话拨入参与者都可以使用 DTMF 命令收听帮助，收听会议名单，以及使自己静音。</span><span class="sxs-lookup"><span data-stu-id="6a63c-200">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>
    
- <span data-ttu-id="6a63c-201">电话拨入参与者（即，无论他们是否从 PSTN 拨号）在会议期间收听个人通知，例如，是否已将其静音或取消静音，是否记录会议，或者是否有人在会议厅中等待。</span><span class="sxs-lookup"><span data-stu-id="6a63c-201">Dial-in participants (that is, whether or not they dial from the PSTN) hear personal announcements during the conference, such as whether they have been muted or unmuted, whether the meeting is being recorded, or whether someone is waiting in the lobby.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6a63c-202">通过单击链接（而不是电话拨入）参加会议的与会者不会听到个人通知。</span><span class="sxs-lookup"><span data-stu-id="6a63c-202">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span> 
  

