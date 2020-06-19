---
title: 团队语音 Contoso 个案研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785955"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="4a1b6-103">Contoso 案例研究：团队语音迁移概述</span><span class="sxs-lookup"><span data-stu-id="4a1b6-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="4a1b6-104">本文将介绍一个案例研究，介绍如何为其组织实施团队语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="4a1b6-105">Contoso 已部署 Microsoft 365 企业版并解决了主要的设计决策和实现详细信息：网络、标识、Windows 10 企业版、Office 365 专业增强版、移动设备管理、信息保护、安全性、从 Skype for Business 升级到团队、电话系统和音频会议。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="4a1b6-106">本文重点介绍 Contoso 如何将他们的本地用户迁移到团队进行统一通信、协作和语音。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="4a1b6-107">有关 Contoso 如何使用 Microsoft 的云服务加速其数字转换的背景信息，请参阅从[Contoso 案例研究概述](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)开始的所有核心文章。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="4a1b6-108">在核心文章中，你将找到有关以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="4a1b6-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="4a1b6-109">Contoso 的 IT 基础结构需求</span><span class="sxs-lookup"><span data-stu-id="4a1b6-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="4a1b6-110">网络</span><span class="sxs-lookup"><span data-stu-id="4a1b6-110">Networking</span></span>
- <span data-ttu-id="4a1b6-111">Identity </span><span class="sxs-lookup"><span data-stu-id="4a1b6-111">Identity</span></span>
- <span data-ttu-id="4a1b6-112">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="4a1b6-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="4a1b6-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="4a1b6-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="4a1b6-114">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="4a1b6-114">Mobile device management</span></span>
- <span data-ttu-id="4a1b6-115">信息保护</span><span class="sxs-lookup"><span data-stu-id="4a1b6-115">Information protection</span></span>
- <span data-ttu-id="4a1b6-116">Microsoft 365 企业版安全摘要</span><span class="sxs-lookup"><span data-stu-id="4a1b6-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="4a1b6-117">首要项目的团队</span><span class="sxs-lookup"><span data-stu-id="4a1b6-117">Team for a top-secret project</span></span>
- <span data-ttu-id="4a1b6-118">高机密数字资产的 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="4a1b6-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="4a1b6-119">有关规划升级的详细信息，您将希望从[Microsoft 团队升级](upgrade-start-here.md)入门开始。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="4a1b6-120">Contoso 企业团队的目标</span><span class="sxs-lookup"><span data-stu-id="4a1b6-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="4a1b6-121">要将他们的本地用户迁移到团队进行统一通信、协作和语音，Contoso 确定以下业务目标：</span><span class="sxs-lookup"><span data-stu-id="4a1b6-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="4a1b6-122">团队支持</span><span class="sxs-lookup"><span data-stu-id="4a1b6-122">Teams enablement</span></span> 

  <span data-ttu-id="4a1b6-123">Contoso 的统一通信和协作团队使用正确的策略管理和启用安全的内部和外部协作。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="4a1b6-124">Skype for Business 到 Teams 的升级</span><span class="sxs-lookup"><span data-stu-id="4a1b6-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="4a1b6-125">Skype for business 已在 Contoso 中广泛部署。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="4a1b6-126">由于需要移出旧式系统，Contoso 决定将其 Skype for Business 用户升级到团队。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="4a1b6-127">有关详细信息，请参阅[Contoso 个案研究：团队升级计划](voice-case-study-migration-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="4a1b6-128">电话系统</span><span class="sxs-lookup"><span data-stu-id="4a1b6-128">Phone System</span></span>  

  <span data-ttu-id="4a1b6-129">企业语音版 Skype for Business 在 Contoso 中广泛部署。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="4a1b6-130">如果需要将下一跃点的旧系统迁移到其中介服务器的下一跃点，Contoso 将其 Skype for Business 企业语音用户迁移到电话系统。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="4a1b6-131">Contoso 站点使用的是 Microsoft 通话计划、电话系统直接路由或两者的组合。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="4a1b6-132">有关详细信息，请参阅[Contoso 个案研究：电话系统](voice-case-study-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="4a1b6-133">基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="4a1b6-133">Location-Based Routing</span></span> 

  <span data-ttu-id="4a1b6-134">在电话管控国家/地区的 office 位置，Contoso 需要在其手机系统部署中重新创建 Skype for Business 中提供的基于位置的路线。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="4a1b6-135">有关详细信息，请参阅[Contoso 个案研究：基于位置的路由](voice-case-study-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="4a1b6-136">紧急呼叫</span><span class="sxs-lookup"><span data-stu-id="4a1b6-136">Emergency Calling</span></span> 

  <span data-ttu-id="4a1b6-137">在直接路由实施的位置，Contoso 利用经认可的第三方设置紧急电话。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="4a1b6-138">有关详细信息，请参阅[Contoso 个案研究：紧急电话](voice-case-study-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="4a1b6-139">音频会议</span><span class="sxs-lookup"><span data-stu-id="4a1b6-139">Audio Conferencing</span></span> 

  <span data-ttu-id="4a1b6-140">Contoso 将其 SIP 主干上托管的音频会议服务号码设置为其 PSTN 提供商。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="4a1b6-141">有关详细信息，请参阅[Contoso 个案研究：音频会议](voice-case-study-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="4a1b6-142">本地媒体优化</span><span class="sxs-lookup"><span data-stu-id="4a1b6-142">Local Media Optimization</span></span> 

  <span data-ttu-id="4a1b6-143">Contoso 利用本地媒体优化功能，这些位置中的位置与远程站点使用的 Microsoft Phone 系统之间有一个直接路由主干。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="4a1b6-144">有关详细信息，请参阅[规划本地媒体优化](direct-routing-media-optimization.md)和[配置本地媒体优化](direct-routing-media-optimization-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="4a1b6-145">自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="4a1b6-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="4a1b6-146">由于 Covid-19，Contoso 希望在员工在远程工作的同时提供接待员支持。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="4a1b6-147">Contoso 使用 "自动助理" 和 "呼叫队列" 来管理传入呼叫的接待员电话号码。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="4a1b6-148">有关详细信息，请参阅[Contoso 个案研究：自动助理和呼叫队列](voice-case-study-call-queues.md)。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


