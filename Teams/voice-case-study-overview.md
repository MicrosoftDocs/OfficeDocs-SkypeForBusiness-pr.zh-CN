---
title: Teams 语音 Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 针对多语言公司的 Teams 语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097488"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="0db85-103">Contoso 案例研究：Teams 语音迁移概述</span><span class="sxs-lookup"><span data-stu-id="0db85-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="0db85-104">本文介绍一个案例研究，该案例研究介绍了虚构的多语言公司 Contoso 如何为组织实现 Teams 语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="0db85-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="0db85-105">Contoso 部署了 Microsoft 365 企业版，并针对以下事项解决了主要设计决策和实施细节：网络、标识、Windows 10 企业版、Office 365 专业增强版、移动设备管理、信息保护、安全性、从 Skype for Business 升级到 Teams、电话系统和音频会议。</span><span class="sxs-lookup"><span data-stu-id="0db85-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="0db85-106">本文重点介绍 Contoso 如何将其本地用户迁移到 Teams，实现统一的通信、协作和语音。</span><span class="sxs-lookup"><span data-stu-id="0db85-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="0db85-107">有关 Contoso 如何使用 Microsoft 云服务加速数字化转型的背景信息，请参阅从 [Contoso](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)案例研究概述 开始的所有核心文章。</span><span class="sxs-lookup"><span data-stu-id="0db85-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="0db85-108">在核心文章中，可找到以下信息：</span><span class="sxs-lookup"><span data-stu-id="0db85-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="0db85-109">Contoso 的 IT 基础结构需求</span><span class="sxs-lookup"><span data-stu-id="0db85-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="0db85-110">网络</span><span class="sxs-lookup"><span data-stu-id="0db85-110">Networking</span></span>
- <span data-ttu-id="0db85-111">Identity </span><span class="sxs-lookup"><span data-stu-id="0db85-111">Identity</span></span>
- <span data-ttu-id="0db85-112">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="0db85-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="0db85-113">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="0db85-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="0db85-114">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="0db85-114">Mobile device management</span></span>
- <span data-ttu-id="0db85-115">信息保护</span><span class="sxs-lookup"><span data-stu-id="0db85-115">Information protection</span></span>
- <span data-ttu-id="0db85-116">Microsoft 365 企业安全性摘要</span><span class="sxs-lookup"><span data-stu-id="0db85-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="0db85-117">顶级机密项目的团队</span><span class="sxs-lookup"><span data-stu-id="0db85-117">Team for a top-secret project</span></span>
- <span data-ttu-id="0db85-118">用于高度机密数字资产的 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="0db85-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="0db85-119">有关规划升级的信息，需要从 Microsoft Teams 升级入门 [开始](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="0db85-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="0db85-120">Teams 的 Contoso 业务目标</span><span class="sxs-lookup"><span data-stu-id="0db85-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="0db85-121">为了将其本地用户迁移到 Teams，实现统一的通信、协作和语音，Contoso 决定实现以下业务目标：</span><span class="sxs-lookup"><span data-stu-id="0db85-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="0db85-122">Teams 启用</span><span class="sxs-lookup"><span data-stu-id="0db85-122">Teams enablement</span></span> 

  <span data-ttu-id="0db85-123">Contoso 的统一通信和协作团队为 Teams 启用了正确的策略，用于治理和实现安全的内部和外部协作。</span><span class="sxs-lookup"><span data-stu-id="0db85-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="0db85-124">Skype for Business 到 Teams 的升级</span><span class="sxs-lookup"><span data-stu-id="0db85-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="0db85-125">Skype for Business 已广泛部署在 Contoso 中。</span><span class="sxs-lookup"><span data-stu-id="0db85-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="0db85-126">由于需要关闭旧系统，Contoso 决定将其 Skype for Business 用户升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="0db85-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="0db85-127">有关详细信息，请参阅 [Contoso 案例研究：Teams 升级计划](voice-case-study-migration-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="0db85-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="0db85-128">电话系统</span><span class="sxs-lookup"><span data-stu-id="0db85-128">Phone System</span></span>  

  <span data-ttu-id="0db85-129">具有企业语音的 Skype for Business 已广泛部署在 Contoso 中。</span><span class="sxs-lookup"><span data-stu-id="0db85-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="0db85-130">由于需要将旧系统（作为中介服务器的下一跃点）移走，Contoso 将其 Skype for Business 企业语音用户迁移到了电话系统。</span><span class="sxs-lookup"><span data-stu-id="0db85-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="0db85-131">Contoso 站点使用 Microsoft 呼叫计划、电话系统直接路由或两者的组合。</span><span class="sxs-lookup"><span data-stu-id="0db85-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="0db85-132">有关详细信息，请参阅 [Contoso 案例研究：电话系统](voice-case-study-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="0db85-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="0db85-133">基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="0db85-133">Location-Based Routing</span></span> 

  <span data-ttu-id="0db85-134">由于办公地点位于电话管制的国家/地区，Contoso 需要重新创建 Skype for Business Location-Based电话系统部署中的网络路由。</span><span class="sxs-lookup"><span data-stu-id="0db85-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="0db85-135">有关详细信息，请参阅 [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="0db85-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="0db85-136">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="0db85-136">Emergency Calling</span></span> 

  <span data-ttu-id="0db85-137">实施直接路由时，Contoso 与批准的第三方建立紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="0db85-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="0db85-138">有关详细信息，请参阅 [Contoso 案例研究：紧急呼叫](voice-case-study-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="0db85-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="0db85-139">音频会议</span><span class="sxs-lookup"><span data-stu-id="0db85-139">Audio Conferencing</span></span> 

  <span data-ttu-id="0db85-140">Contoso 设置在 PSTN 提供商的 SIP 中继上托管的音频会议服务号码。</span><span class="sxs-lookup"><span data-stu-id="0db85-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="0db85-141">有关详细信息，请参阅 [Contoso 案例研究：音频会议](voice-case-study-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="0db85-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="0db85-142">本地媒体优化</span><span class="sxs-lookup"><span data-stu-id="0db85-142">Local Media Optimization</span></span> 

  <span data-ttu-id="0db85-143">Contoso 在有一个直接路由中继到远程站点利用的 Microsoft Phone System 的位置利用了本地媒体优化。</span><span class="sxs-lookup"><span data-stu-id="0db85-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="0db85-144">有关详细信息，请参阅[规划本地媒体优化和](direct-routing-media-optimization.md)[配置本地媒体优化](direct-routing-media-optimization-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="0db85-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="0db85-145">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="0db85-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="0db85-146">由于 Covid-19，Contoso 想要在员工远程工作的同时提供接待员支持。</span><span class="sxs-lookup"><span data-stu-id="0db85-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="0db85-147">Contoso 使用自动助理和呼叫队列来管理接收者电话号码的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="0db85-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="0db85-148">有关详细信息，请参阅 [Contoso 案例研究：自动助理和呼叫队列](voice-case-study-call-queues.md)。</span><span class="sxs-lookup"><span data-stu-id="0db85-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>