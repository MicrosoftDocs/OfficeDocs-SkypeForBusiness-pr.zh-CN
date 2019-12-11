---
title: 设置用于直接路由的 Ringback bot
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 了解如何使用 Ringback 机器人进行直接路由，以防止在建立通话时可能出现的意外 silences。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fcb69ba1bc612fe940054ec982eb7462c6679be
ms.sourcegitcommit: a23f45ab3a2cb7b5c279356edddf61c4030c41bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962499"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="646d4-103">设置用于直接路由的 Ringback bot</span><span class="sxs-lookup"><span data-stu-id="646d4-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="646d4-104">本文介绍了 Ringback 机器人，可用于帮助避免在通话时间较长时可能出现的意外 silences。</span><span class="sxs-lookup"><span data-stu-id="646d4-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="646d4-105">Ringback bot 可在非媒体旁路模式下直接路由使用。</span><span class="sxs-lookup"><span data-stu-id="646d4-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="646d4-106">有时，从公共交换电话网络（PSTN）到团队客户端的入站呼叫的时间可能比预期的要长。</span><span class="sxs-lookup"><span data-stu-id="646d4-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="646d4-107">出现这种情况的原因有多种。</span><span class="sxs-lookup"><span data-stu-id="646d4-107">This can occur for various reasons.</span></span> <span data-ttu-id="646d4-108">发生这种情况时，呼叫者可能听不到任何声音，团队客户不会听到任何信号，并且呼叫可能被某些电信提供商取消。</span><span class="sxs-lookup"><span data-stu-id="646d4-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and the call might be canceled by some telecommunications providers.</span></span>

<span data-ttu-id="646d4-109">Ringback bot 有助于避免在此方案中可能出现的意外 silences。</span><span class="sxs-lookup"><span data-stu-id="646d4-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="646d4-110">对于从 PSTN 到团队客户端的入站呼叫，Ringback bot 会向呼叫者播放独特的音频信号，以指示团队正在建立呼叫的过程。</span><span class="sxs-lookup"><span data-stu-id="646d4-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="646d4-111">Ringback 机器人从团队后端生成早期媒体。</span><span class="sxs-lookup"><span data-stu-id="646d4-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="646d4-112">在某些国家和地区，当媒体开始流动时，您可能需要支付通话费用。</span><span class="sxs-lookup"><span data-stu-id="646d4-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="646d4-113">配置 Ringback bot</span><span class="sxs-lookup"><span data-stu-id="646d4-113">Configure the Ringback bot</span></span>

<span data-ttu-id="646d4-114">将[CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway)和[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet 与**GenerateRingingWhileLocatingUser**参数结合使用，配置 Ringback bot。</span><span class="sxs-lookup"><span data-stu-id="646d4-114">Use the [Set-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) and [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlets together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot.</span></span>

<span data-ttu-id="646d4-115">若要打开 Ringback 机器人，请将**GenerateRingingWhileLocatingUser**参数设置为 " **$True**"。</span><span class="sxs-lookup"><span data-stu-id="646d4-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="646d4-116">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="646d4-116">This is the default value.</span></span> 

<span data-ttu-id="646d4-117">若要关闭 Ringback 机器人，请将**GenerateRingingWhileLocatingUser**参数设置为 " **$False**"。</span><span class="sxs-lookup"><span data-stu-id="646d4-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="646d4-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="646d4-118">Related topics</span></span>

- [<span data-ttu-id="646d4-119">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="646d4-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)