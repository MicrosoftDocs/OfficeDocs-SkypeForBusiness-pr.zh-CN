---
title: 规划 Skype for Business Server 的忙碌选项
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
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: 阅读 Skype for Business Server 中的忙碌选项功能。
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813692"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="510e9-103">规划 Skype for Business Server 的忙碌选项</span><span class="sxs-lookup"><span data-stu-id="510e9-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="510e9-104">阅读 Skype for Business Server 中的忙碌选项功能。</span><span class="sxs-lookup"><span data-stu-id="510e9-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="510e9-105">忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置在用户已接听电话或参加会议或将呼叫置于保留状态时如何处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="510e9-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="510e9-106">可以使用忙音信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="510e9-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="510e9-107">在配对前端池和 Survivable Branch Servers (SBS 服务器上支持忙碌选项策略) 。</span><span class="sxs-lookup"><span data-stu-id="510e9-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="510e9-108">本主题介绍忙碌选项的功能。</span><span class="sxs-lookup"><span data-stu-id="510e9-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="510e9-109">若要了解如何安装和配置忙碌选项，请参阅安装和配置 [Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)的忙碌选项。</span><span class="sxs-lookup"><span data-stu-id="510e9-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="510e9-110">配置选项</span><span class="sxs-lookup"><span data-stu-id="510e9-110">Configuration options</span></span>

<span data-ttu-id="510e9-111">如果为组织启用了忙碌选项，则组织中所有用户（包括企业语音用户和非 企业语音用户）都可以使用以下功能：</span><span class="sxs-lookup"><span data-stu-id="510e9-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="510e9-112">忙碌 - 在用户忙碌时，新传入呼叫将因忙音信号被拒绝。</span><span class="sxs-lookup"><span data-stu-id="510e9-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="510e9-113">Voicemail on Busy - 其中的新传入呼叫将在用户忙碌时转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="510e9-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="510e9-114">忙碌选项功能提供故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="510e9-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="510e9-115">如果出现问题，并且用户故障转移到另一台前端服务器或 Skype for Business Server 中的另一个池，则其忙碌选项设置将保留。</span><span class="sxs-lookup"><span data-stu-id="510e9-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="510e9-116">无论如何配置忙碌选项，呼叫或会议中的用户或呼叫保持的用户不会阻止发起新呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="510e9-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="510e9-117">配置后，忙碌选项设置将作用于用户的 Skype for Business 呼叫设备和客户端。</span><span class="sxs-lookup"><span data-stu-id="510e9-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="510e9-118">根据用户的忙碌选项设置，被拒绝或发送到语音邮件的呼叫不会在用户登录的任何用户的呼叫设备（包括 Macintosh、Windows 桌面、移动客户端或 IP 电话）上响铃。</span><span class="sxs-lookup"><span data-stu-id="510e9-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="510e9-119">用户将在 Skype for Business 客户端和设备上看到未接来电通知，并且也会收到电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="510e9-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="510e9-120">呼叫因忙碌而被拒绝的呼叫的呼叫者将在 Skype for Business 客户端中看到一条通知，指出他们尝试联系的用户正忙于其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="510e9-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="510e9-121">可以使用 Skype for Business PowerShell cmdlet 将忙碌选项功能配置为：</span><span class="sxs-lookup"><span data-stu-id="510e9-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="510e9-122">为企业启用或禁用忙碌选项语音策略。</span><span class="sxs-lookup"><span data-stu-id="510e9-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="510e9-123">为企业中所有用户管理 Busy on Busy 或 Voicemail on Busy。</span><span class="sxs-lookup"><span data-stu-id="510e9-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="510e9-124">为特定前端池中的所有用户管理 Busy on Busy 或 Voicemail on Busy。</span><span class="sxs-lookup"><span data-stu-id="510e9-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="510e9-125">为用户列表管理 Busy on Busy 或 Voicemail on Busy。</span><span class="sxs-lookup"><span data-stu-id="510e9-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="510e9-126">为单个用户管理 Busy on Busy 或 Voicemail on Busy。</span><span class="sxs-lookup"><span data-stu-id="510e9-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="510e9-127">与语音应用程序的互操作性</span><span class="sxs-lookup"><span data-stu-id="510e9-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="510e9-128">忙碌选项提供与 Skype for Business 中的以下语音应用程序的互操作性：</span><span class="sxs-lookup"><span data-stu-id="510e9-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="510e9-129">响应组 (RGS) </span><span class="sxs-lookup"><span data-stu-id="510e9-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="510e9-130">系统将忽略在响应组号码上设置的忙碌选项;允许多个并发呼叫。</span><span class="sxs-lookup"><span data-stu-id="510e9-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="510e9-131">对于忙碌选项设置的代理，响应组中的当前助理路由体验将保持不变。</span><span class="sxs-lookup"><span data-stu-id="510e9-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="510e9-132">来自响应组向作为响应组代理的用户的呼叫不会受忙碌选项设置限制，并且将保持当前的 RGS 体验。</span><span class="sxs-lookup"><span data-stu-id="510e9-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="510e9-133">与代理相关的非 RGS 呼叫将受其忙碌选项设置支持。</span><span class="sxs-lookup"><span data-stu-id="510e9-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="510e9-134">Team Call－ 团队呼叫</span><span class="sxs-lookup"><span data-stu-id="510e9-134">Team Call</span></span>
    
  - <span data-ttu-id="510e9-135">为团队呼叫设置的用户的传入呼叫将设置为忽略"忙碌时忙碌"和"忙时语音邮件"设置。</span><span class="sxs-lookup"><span data-stu-id="510e9-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="510e9-136">对于为用户设置的忙碌选项，当前的团队呼叫体验将保持不变。</span><span class="sxs-lookup"><span data-stu-id="510e9-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="510e9-137">向此类用户进行的非团队呼叫相关呼叫将受其忙碌选项设置支持。</span><span class="sxs-lookup"><span data-stu-id="510e9-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="510e9-138">管理员/管理员委派</span><span class="sxs-lookup"><span data-stu-id="510e9-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="510e9-139">对于设置为"行政/管理员委派"或"管理员"的用户的传入呼叫，其优先级将设置为忽略"忙碌时忙碌"和"忙时语音邮件"设置。</span><span class="sxs-lookup"><span data-stu-id="510e9-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="510e9-140">当前"管理员/管理员委派"体验将保持不变，为管理员或管理员设置忙碌选项。</span><span class="sxs-lookup"><span data-stu-id="510e9-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="510e9-141">非管理员/管理员委派与管理员相关的呼叫将受其忙碌选项设置支持。</span><span class="sxs-lookup"><span data-stu-id="510e9-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="510e9-142">共享线路外观</span><span class="sxs-lookup"><span data-stu-id="510e9-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="510e9-143">将忽略为共享线路外观设置的用户帐户的忙碌选项设置。</span><span class="sxs-lookup"><span data-stu-id="510e9-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="510e9-144">共享线路外观的本机 Busy on Busy 和 Voicemail on Busy 选项将改为可用。</span><span class="sxs-lookup"><span data-stu-id="510e9-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="510e9-145">呼叫收费服务</span><span class="sxs-lookup"><span data-stu-id="510e9-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="510e9-146">允许因超时而未取回且因超时而回响的已呼叫响铃到通过忙碌选项将呼叫接听到该呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="510e9-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="510e9-147">呼叫会议</span><span class="sxs-lookup"><span data-stu-id="510e9-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="510e9-148">电话会议中的用户被视为忙碌，新的传入呼叫将因忙音信号被拒绝或根据用户的忙碌选项设置转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="510e9-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="510e9-149">不会阻止参加会议的用户通过忙碌选项发起新呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="510e9-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="510e9-150">参加会议的用户仍能够接收新的会议邀请，但新的对等呼叫将按照其忙碌选项设置被拒绝。</span><span class="sxs-lookup"><span data-stu-id="510e9-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="510e9-151">同时响铃和呼叫转发</span><span class="sxs-lookup"><span data-stu-id="510e9-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="510e9-152">忙碌时忙碌功能不能用于同时响铃和呼叫转发。</span><span class="sxs-lookup"><span data-stu-id="510e9-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

