---
title: 在 Skype for Business Server 2015 中规划共享线路外观
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 阅读本主题, 了解如何规划 Skype for Business Server 2015 中的共享行外观 (SLA), 2015 累积更新。
ms.openlocfilehash: 966c9f32a27ba936e880bdb51690bcefed4ffbe4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276445"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="3fbc4-103">在 Skype for Business Server 2015 中规划共享线路外观</span><span class="sxs-lookup"><span data-stu-id="3fbc4-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3fbc4-104">阅读本主题, 了解如何规划 Skype for Business Server 2015 中的共享行外观 (SLA), 2015 累积更新。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="3fbc4-105">共享线路的外观是 Skype for Business 中的一项功能, 用于处理特定号码 (称为共享号码) 的多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="3fbc4-106">SLA 可以将任何企业语音启用的 Skype for business 用户配置为具有多个线路的共享号码, 以响应多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="3fbc4-107">这些呼叫实际上并不是通过共享号码接收的，而是转接给担任共享号码的代理人的用户。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="3fbc4-108">其中任何一个代理人都可以接听呼叫，而其余代理人的电话上将收到一个通知，说明已接听呼叫的代理人和哪条线路非常忙碌。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="3fbc4-109">共享号码的线路数和代理人可以在 SLA 中配置。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="3fbc4-110">此外，也可以为共享号码配置高级选项，例如 BusyOption（所有线路都忙碌时发生的情况）和 MissedCallOption（没有人接听呼叫）。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="3fbc4-111">仅在以下电话设备上支持 SLA (计算机、移动电话或其他设备上的 Skype for business 客户端不支持):</span><span class="sxs-lookup"><span data-stu-id="3fbc4-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="3fbc4-112">具有固件更新 5.4.1 的 Polycom VVX300</span><span class="sxs-lookup"><span data-stu-id="3fbc4-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="3fbc4-113">具有固件更新 5.4.1 的 Polycom VVX400</span><span class="sxs-lookup"><span data-stu-id="3fbc4-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="3fbc4-114">具有固件更新 5.4.1 的 Polycom VVX500</span><span class="sxs-lookup"><span data-stu-id="3fbc4-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="3fbc4-115">具有固件更新 5.4.1 的 Polycom VVX600</span><span class="sxs-lookup"><span data-stu-id="3fbc4-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="3fbc4-116">SLA 是 Skype for Business 服务器中的新功能, 2015 年11月累积更新。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="3fbc4-117">有关部署 SLA 的信息，请参阅[Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="3fbc4-118">功能列表</span><span class="sxs-lookup"><span data-stu-id="3fbc4-118">Feature List</span></span>

<span data-ttu-id="3fbc4-119">设置 SLA 组可以实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="3fbc4-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="3fbc4-p102">组中的所有代理人都可以应答拨打同一共享号码的入站呼叫。呼叫可以是基于 PSTN 的也可以是基于 SIP 的。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="3fbc4-122">代理人可以保持和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="3fbc4-123">代理人可以将呼叫转接到 SLA 组外部的号码。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="3fbc4-124">代理人可以查看共享号码上当前存在的呼叫数，并查看每个呼叫的状态。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="3fbc4-p103">您可以为共享号码配置最大并发呼叫数。还可以设置在达到此最大数之后如何处理其他呼叫。额外呼叫可能会被忙音信号拒绝、转接到备用号码或者转接到语音邮件。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="3fbc4-p104">可以配置如何处理未接来电（在特定时间后未接听的呼叫）。如果为组标识启用语音邮件，未接来电将自动转到语音邮件。如果没有为组标识（共享号码）启用语音邮件，则可以选择通过忙音信号拒绝未接来电、将未接来电转接到备用号码或者断开连接。</span><span class="sxs-lookup"><span data-stu-id="3fbc4-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

