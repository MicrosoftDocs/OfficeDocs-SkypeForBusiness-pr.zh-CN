---
title: 云语音部署
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/13/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: 在 Microsoft Teams 中部署云语音功能实践指导
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45528d71dc04b96d77b454d5db402648779c1ac9
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
#<a name="cloud-voice-deployment"></a><span data-ttu-id="8693e-103">云语音部署</span><span class="sxs-lookup"><span data-stu-id="8693e-103">Cloud voice deployment</span></span>

<span data-ttu-id="8693e-104">作为 Office 365 中团队合作和沟通的中心的 Microsoft Teams 现在通过扩展 Teams 会议和通话体验以包含通过公用电话交换网 (PSTN) 连接的外部各方，提供了音频会议和具有通话套餐的电话系统功能，从而满足额外的业务需求。</span><span class="sxs-lookup"><span data-stu-id="8693e-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the Public Switched Telephone Network (PSTN).</span></span>
 
<span data-ttu-id="8693e-105">当以后适用于 Teams 的其他云语音功能发布时，我们将更新此页面。</span><span class="sxs-lookup"><span data-stu-id="8693e-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>


##<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="8693e-106">Microsoft Teams 中的音频会议实践指导</span><span class="sxs-lookup"><span data-stu-id="8693e-106">Practical guidance for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="8693e-107">Office 365 中的音频会议允许参与者从任何电话加入 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="8693e-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="8693e-108">下面是使用 Office 365 中的[音频会议](https://go.microsoft.com/fwlink/?linkid=858992)完成的内容。</span><span class="sxs-lookup"><span data-stu-id="8693e-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

<span data-ttu-id="8693e-109">此实践指导介绍 Office 365 FastTrack 客户旅程框架及其三个阶段（展望、上线和推动价值），帮助你规划、交付和运营音频会议实施以获得成功的业务成果。</span><span class="sxs-lookup"><span data-stu-id="8693e-109">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases, Envision, Onboard, and Drive Value, to help you plan, deliver, and operate an Audio Conferencing implementation towards succesful business outcomes.</span></span>

> [!TIP]
> <span data-ttu-id="8693e-110">在此实践指导中，我们为每个活动和关键讨论提供了示例输出。</span><span class="sxs-lookup"><span data-stu-id="8693e-110">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="8693e-111">本文档中的示例包含在“提示”标注中，它们是可以重用的模板。</span><span class="sxs-lookup"><span data-stu-id="8693e-111">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="8693e-112">对于需要你在规划过程中完成的信息，以“TBA”（待添加）表示。</span><span class="sxs-lookup"><span data-stu-id="8693e-112">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

##<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="8693e-113">Microsoft Teams 中具有通话套餐的电话系统实践指导</span><span class="sxs-lookup"><span data-stu-id="8693e-113">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="8693e-114">电话系统是一项 Office 365 功能，用于管理呼叫路由、策略和用户预配。</span><span class="sxs-lookup"><span data-stu-id="8693e-114">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="8693e-115">其中包括电话呼叫管理系统、呼叫路由和呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="8693e-115">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="8693e-116">Office 365 通话套餐是电话系统功能的附加项，通过 Teams 和 Skype for Business Online 交付。</span><span class="sxs-lookup"><span data-stu-id="8693e-116">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="8693e-117">通话套餐为企业中的人员提供一个主电话号码，让他们可以通过公用电话交换网 (PSTN) 向组织外部拨打电话以及接听来自组织外部的电话。</span><span class="sxs-lookup"><span data-stu-id="8693e-117">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="8693e-118">要了解更多信息，请参阅 [Office 365 中的电话系统提供的功能](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c)和 [Office 365 中的通话套餐是什么？](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span><span class="sxs-lookup"><span data-stu-id="8693e-118">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>

<span data-ttu-id="8693e-119">此实践指导介绍 Office 365 FastTrack 客户旅程框架及其三个阶段（展望、上线和推动价值），帮助你规划、交付和运营成功的具有通话套餐的电话系统实施。</span><span class="sxs-lookup"><span data-stu-id="8693e-119">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases - Envision, Onboard, and Drive Value - to help you plan, deliver, and operate a successful Phone System with Calling Plans implementation.</span></span>

> [!TIP]
> <span data-ttu-id="8693e-120">在此实践指导中，我们为每个活动和关键讨论提供了示例输出。</span><span class="sxs-lookup"><span data-stu-id="8693e-120">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="8693e-121">本文档中的示例包含在“提示”标注中，它们是可以重用的模板。</span><span class="sxs-lookup"><span data-stu-id="8693e-121">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="8693e-122">对于需要你在规划过程中完成的信息，以“TBA”（待添加）表示。</span><span class="sxs-lookup"><span data-stu-id="8693e-122">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>