---
title: 规划 Skype for Business Server 2015 中的共享线路外观
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 阅读本主题，了解如何在 Skype for Business Server 2015 2015 年 11 月累积更新中规划共享线路外观 (SLA) 。
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813342"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="8a035-103">规划 Skype for Business Server 2015 中的共享线路外观</span><span class="sxs-lookup"><span data-stu-id="8a035-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8a035-104">阅读本主题，了解如何在 Skype for Business Server 2015 2015 年 11 月累积更新中规划共享线路外观 (SLA) 。</span><span class="sxs-lookup"><span data-stu-id="8a035-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="8a035-105">共享线路外观是 Skype for Business 中的一项功能，用于处理对称为共享号码的特定号码的多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="8a035-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="8a035-106">SLA 可以将任何启用企业语音的 Skype for Business 用户配置为具有多行线路的共享号码，以响应多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="8a035-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="8a035-107">实际上不会在共享号码上收到呼叫，而是将呼叫转发给充当共享号码代理的用户。</span><span class="sxs-lookup"><span data-stu-id="8a035-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="8a035-108">任何一个代理都可以接听呼叫，而其余的代理人会通过电话收到有关接听呼叫的人以及哪条线路因此变得繁忙的通知。</span><span class="sxs-lookup"><span data-stu-id="8a035-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="8a035-109">在 SLA 中，线路数和代理都适用于共享号码。</span><span class="sxs-lookup"><span data-stu-id="8a035-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="8a035-110">此外，还可以为共享号码配置高级选项，例如 BusyOption (当所有线路都繁忙) 和 MissedCallOption (当没有代理接电话) 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="8a035-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="8a035-111">SLA 仅在以下电话设备上受支持 (在计算机、移动电话或其他设备上不支持 Skype for Business) ：</span><span class="sxs-lookup"><span data-stu-id="8a035-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="8a035-112">具有固件更新 5.4.1 的 Polycom VVX300</span><span class="sxs-lookup"><span data-stu-id="8a035-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="8a035-113">具有固件更新 5.4.1 的 Polycom VVX400</span><span class="sxs-lookup"><span data-stu-id="8a035-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="8a035-114">具有固件更新 5.4.1 的 Polycom VVX500</span><span class="sxs-lookup"><span data-stu-id="8a035-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="8a035-115">具有固件更新 5.4.1 的 Polycom VVX600</span><span class="sxs-lookup"><span data-stu-id="8a035-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="8a035-116">SLA 是 Skype for Business Server 中的一项新功能，2015 年 11 月累积更新。</span><span class="sxs-lookup"><span data-stu-id="8a035-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="8a035-117">有关部署 SLA 的信息，请参阅 [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="8a035-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="8a035-118">功能列表</span><span class="sxs-lookup"><span data-stu-id="8a035-118">Feature List</span></span>

<span data-ttu-id="8a035-119">通过设置 SLA 组，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8a035-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="8a035-120">组内的所有代理人都可以应答对同一共享号码的入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="8a035-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="8a035-121">呼叫可以基于 PSTN 或基于 SIP。</span><span class="sxs-lookup"><span data-stu-id="8a035-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="8a035-122">代理人可以保留和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="8a035-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="8a035-123">代理人可以将呼叫转接到 SLA 组外部的号码。</span><span class="sxs-lookup"><span data-stu-id="8a035-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="8a035-124">代理人可以查看共享号码中当前有多少个呼叫，并查看每个呼叫的状态。</span><span class="sxs-lookup"><span data-stu-id="8a035-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="8a035-125">您可以为共享号码配置最大并发呼叫数。</span><span class="sxs-lookup"><span data-stu-id="8a035-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="8a035-126">还可以设置在达到此最大值后处理其他呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="8a035-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="8a035-127">多余呼叫可以通过忙音信号拒绝、转发到备用号码或转发到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="8a035-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="8a035-128">可以配置如何处理未接 (未接来电，) 时间后未接听。</span><span class="sxs-lookup"><span data-stu-id="8a035-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="8a035-129">如果为组标识启用语音邮件，则未接来电将自动转到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="8a035-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="8a035-130">如果没有为组标识启用语音邮件 (共享号码) ，可以选择通过忙音信号拒绝未接来电、转发到备用号码或断开连接。</span><span class="sxs-lookup"><span data-stu-id="8a035-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

