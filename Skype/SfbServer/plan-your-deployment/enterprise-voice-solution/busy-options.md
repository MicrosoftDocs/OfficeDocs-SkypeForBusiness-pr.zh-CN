---
title: 规划适用于 Skype for Business Server 的忙碌选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 阅读有关 Skype for Business 服务器中的 "忙碌选项" 功能的信息。
ms.openlocfilehash: 8e88b4bf3b92c7fea9bcf79822e2711ff3bee7de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277102"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="a013e-103">规划适用于 Skype for Business Server 的忙碌选项</span><span class="sxs-lookup"><span data-stu-id="a013e-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="a013e-104">阅读有关 Skype for Business 服务器中的 "忙碌选项" 功能的信息。</span><span class="sxs-lookup"><span data-stu-id="a013e-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="a013e-105">忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置当用户正在接听电话或参加会议或将呼叫置于等待状态时传入呼叫的处理方式。</span><span class="sxs-lookup"><span data-stu-id="a013e-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="a013e-106">可以通过忙音信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a013e-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="a013e-107">已配对前端池和 Survivable Branch Server (SBS) 上的故障转移和灾难恢复支持忙碌选项策略。</span><span class="sxs-lookup"><span data-stu-id="a013e-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="a013e-108">本主题描述忙碌选项的功能。</span><span class="sxs-lookup"><span data-stu-id="a013e-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="a013e-109">有关如何安装和配置忙碌选项的信息，请参阅[Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="a013e-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="a013e-110">配置选项</span><span class="sxs-lookup"><span data-stu-id="a013e-110">Configuration options</span></span>

<span data-ttu-id="a013e-111">如果已为组织启用忙碌选项，则组织中的所有用户（企业语音用户和非企业语音用户）都可以使用以下功能：</span><span class="sxs-lookup"><span data-stu-id="a013e-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="a013e-112">Busy on Busy - 如果用户忙碌，将通过忙音信号拒绝新的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="a013e-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="a013e-113">Voicemail on Busy - 如果用户忙碌，新的传入呼叫会转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a013e-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="a013e-114">忙碌选项功能可提供故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="a013e-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="a013e-115">如果出现问题, 并且用户故障转移到另一台前端服务器或 Skype for Business Server 中的另一个池, 则将保留其 "忙碌" 选项设置。</span><span class="sxs-lookup"><span data-stu-id="a013e-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="a013e-116">无论其忙碌选项如何配置，都不会阻止通话或会议中的用户或将呼叫置于等待状态的用户发起新呼叫或会议。  </span><span class="sxs-lookup"><span data-stu-id="a013e-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="a013e-117">配置完成后, "忙碌选项" 设置将对所有用户的 Skype for Business 呼叫设备和客户端生效。</span><span class="sxs-lookup"><span data-stu-id="a013e-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="a013e-118">基于用户的忙碌选项设置，被拒绝或发送至语言邮件的呼叫不会在用户已登录的任何呼叫设备（包括 Macintosh、Windows 桌面、移动客户端或 IP 电话）上响铃。</span><span class="sxs-lookup"><span data-stu-id="a013e-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="a013e-119">用户将在其 Skype for Business 客户端和设备上看到错过的通话通知, 这些通知也将通过电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="a013e-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="a013e-120">由于 Busy on Busy 而被拒绝的呼叫的呼叫者将在其 Skype for Business 客户端中看到一个通知，表明他们尝试联系的用户正在通话中。</span><span class="sxs-lookup"><span data-stu-id="a013e-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="a013e-121">你可以使用 Skype for Business PowerShell cmdlet 配置 "忙碌选项" 功能, 以便:</span><span class="sxs-lookup"><span data-stu-id="a013e-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="a013e-122">为企业启用或禁用忙碌选项语言策略。</span><span class="sxs-lookup"><span data-stu-id="a013e-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="a013e-123">为企业中的所有用户管理 Busy on Busy 或 Voicemail on Busy。</span><span class="sxs-lookup"><span data-stu-id="a013e-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="a013e-124">为驻留在特定前端池中的所有用户管理 Busy on Busy 或 Voicemail on Busy。</span><span class="sxs-lookup"><span data-stu-id="a013e-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="a013e-125">为某些用户管理 Busy on Busy 或 Voicemail on Busy。</span><span class="sxs-lookup"><span data-stu-id="a013e-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="a013e-126">为某个用户管理 Busy on Busy 或 Voicemail on Busy。</span><span class="sxs-lookup"><span data-stu-id="a013e-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="a013e-127">与语音应用程序的互操作性</span><span class="sxs-lookup"><span data-stu-id="a013e-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="a013e-128">在 Skype for Business 中, 繁忙选项提供与以下语音应用程序的互操作性:</span><span class="sxs-lookup"><span data-stu-id="a013e-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="a013e-129">响应组 (RGS)</span><span class="sxs-lookup"><span data-stu-id="a013e-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="a013e-130">响应组号码上设置的忙碌选项将被系统忽略；允许多个并发呼叫。</span><span class="sxs-lookup"><span data-stu-id="a013e-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="a013e-131">对于具有忙碌选项设置的代理，响应组中的当前助理路由体验将保持不变。</span><span class="sxs-lookup"><span data-stu-id="a013e-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="a013e-132">忙碌选项设置不会限制从响应组向属于响应组代理的用户发起的呼叫，并且当前的 RGS 体验将保持不变。</span><span class="sxs-lookup"><span data-stu-id="a013e-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="a013e-133">向代理发起的非 RGS 相关呼叫将由其忙碌选项设置处理。</span><span class="sxs-lookup"><span data-stu-id="a013e-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="a013e-134">Team Call－ 团队呼叫</span><span class="sxs-lookup"><span data-stu-id="a013e-134">Team Call</span></span>
    
  - <span data-ttu-id="a013e-135">对设置为团队通话的用户的传入呼叫将优先于 "忽略占线" 和 "繁忙的语音邮件" 设置。</span><span class="sxs-lookup"><span data-stu-id="a013e-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="a013e-136">使用为用户设置的忙碌选项时，当前的团队呼叫体验将保持不变。</span><span class="sxs-lookup"><span data-stu-id="a013e-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="a013e-137">向此类用户发起的非团队呼叫相关呼叫将由其忙碌选项设置处理。</span><span class="sxs-lookup"><span data-stu-id="a013e-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="a013e-138">上级/管理员委派 </span><span class="sxs-lookup"><span data-stu-id="a013e-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="a013e-139">为上司或管理员设置为老板/管理员委派的来电将优先于 "忽略繁忙" 和 "占线" 设置的 "占线"。</span><span class="sxs-lookup"><span data-stu-id="a013e-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="a013e-140">使用为管理员或上级设置的忙碌选项时，当前的上级/管理员委派体验将保持不变。</span><span class="sxs-lookup"><span data-stu-id="a013e-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="a013e-141">向管理员发起的非上级/管理员委派相关呼叫将由其忙碌选项设置处理。</span><span class="sxs-lookup"><span data-stu-id="a013e-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="a013e-142">共享线路外观   </span><span class="sxs-lookup"><span data-stu-id="a013e-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="a013e-143">用户帐户中为共享线路外观设置的忙碌选项将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a013e-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="a013e-144">共享线路外观的本地忙/闲电话将改为接受 "忙碌" 选项。</span><span class="sxs-lookup"><span data-stu-id="a013e-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="a013e-145">呼叫寄存服务 </span><span class="sxs-lookup"><span data-stu-id="a013e-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="a013e-146">允许未检索到且由于超时而回拨的寄存呼叫对通过忙碌选项寄存呼叫的用户响铃。</span><span class="sxs-lookup"><span data-stu-id="a013e-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="a013e-147">电话会议</span><span class="sxs-lookup"><span data-stu-id="a013e-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="a013e-148">电话会议中的用户视为忙碌，并且将根据其忙碌选项设置通过忙音信号拒绝新的传入呼叫，或将新的传入呼叫转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a013e-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="a013e-149">不会阻止会议中的用户通过忙碌选项发起新的呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="a013e-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="a013e-150">会议中的用户仍可以接收到新会议邀请，但会根据其忙碌选项设置拒绝新的对等呼叫。</span><span class="sxs-lookup"><span data-stu-id="a013e-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="a013e-151">同时响铃和呼叫转移</span><span class="sxs-lookup"><span data-stu-id="a013e-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="a013e-152">Busy on Busy 功能设计为不与同时响铃和呼叫转移一起使用。</span><span class="sxs-lookup"><span data-stu-id="a013e-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

