---
title: 为直接路由设置环回机器人
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 了解如何使用环回机器人进行直接路由，以防止建立呼叫时可能会发生意外的静音。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098418"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="afd89-103">为直接路由设置环回机器人</span><span class="sxs-lookup"><span data-stu-id="afd89-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="afd89-104">本文介绍环回机器人，可用于帮助避免在建立调用需要较长时间时可能会发生意外的静音。</span><span class="sxs-lookup"><span data-stu-id="afd89-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="afd89-105">环回机器人可用于非媒体旁路模式下的直接路由。</span><span class="sxs-lookup"><span data-stu-id="afd89-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="afd89-106">有时，从公共电话交换网 (PSTN) 到 Teams 客户端的入站呼叫的建立时间可能超过预期。</span><span class="sxs-lookup"><span data-stu-id="afd89-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="afd89-107">发生这种情况的原因有多种。</span><span class="sxs-lookup"><span data-stu-id="afd89-107">This can occur for various reasons.</span></span> <span data-ttu-id="afd89-108">发生这种情况时，呼叫者可能不会听到任何内容，Teams 客户端不会响铃，并且某些电信提供商可能会取消呼叫。</span><span class="sxs-lookup"><span data-stu-id="afd89-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="afd89-109">环回机器人可帮助避免此方案中可能会发生意外的静音。</span><span class="sxs-lookup"><span data-stu-id="afd89-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="afd89-110">对于从 PSTN 到 Teams 客户端的入站呼叫，环回机器人向呼叫者播放独特的音频信号，以指示 Teams 正在建立呼叫。</span><span class="sxs-lookup"><span data-stu-id="afd89-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="afd89-111">环回机器人从 Teams 后端生成早期媒体。</span><span class="sxs-lookup"><span data-stu-id="afd89-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="afd89-112">在某些国家和地区，当媒体开始流动时，可能会为呼叫付费。</span><span class="sxs-lookup"><span data-stu-id="afd89-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="afd89-113">配置环回机器人</span><span class="sxs-lookup"><span data-stu-id="afd89-113">Configure the Ringback bot</span></span>

<span data-ttu-id="afd89-114">使用 [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet 修改以前定义的会话边界控制器 (SBC) 配置，或使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet 创建新的 SBC 配置，以及 **GenerateRingingWhileLocatingUser** 参数来配置环回机器人：</span><span class="sxs-lookup"><span data-stu-id="afd89-114">Use the [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="afd89-115">若要打开环回机器人，将 **GenerateRingingWhileLocatingUser** 参数设置为 **$True。**</span><span class="sxs-lookup"><span data-stu-id="afd89-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="afd89-116">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="afd89-116">This is the default value.</span></span> 

- <span data-ttu-id="afd89-117">若要关闭环回机器人，将 **GenerateRingingWhileLocatingUser** 参数设置为 **$False。**</span><span class="sxs-lookup"><span data-stu-id="afd89-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="afd89-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="afd89-118">Related topics</span></span>

- [<span data-ttu-id="afd89-119">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="afd89-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)