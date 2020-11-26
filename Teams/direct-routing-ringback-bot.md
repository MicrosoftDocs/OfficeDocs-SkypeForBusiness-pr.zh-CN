---
title: 设置用于直接路由的 Ringback bot
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 了解如何使用 Ringback 机器人进行直接路由，以防止在建立通话时可能出现的意外 silences。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420952"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="789c1-103">设置用于直接路由的 Ringback bot</span><span class="sxs-lookup"><span data-stu-id="789c1-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="789c1-104">本文介绍了 Ringback 机器人，可用于帮助避免在通话时间较长时可能出现的意外 silences。</span><span class="sxs-lookup"><span data-stu-id="789c1-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="789c1-105">Ringback bot 可在非媒体旁路模式下直接路由使用。</span><span class="sxs-lookup"><span data-stu-id="789c1-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="789c1-106">有时来自公共交换电话网络的入站呼叫 (PSTN) 到团队客户端所需的时间可能比预期的长。</span><span class="sxs-lookup"><span data-stu-id="789c1-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="789c1-107">出现这种情况的原因有多种。</span><span class="sxs-lookup"><span data-stu-id="789c1-107">This can occur for various reasons.</span></span> <span data-ttu-id="789c1-108">发生这种情况时，呼叫者可能听不到任何声音，团队客户不会听到任何声音，并且某些电信提供商可能会取消呼叫。</span><span class="sxs-lookup"><span data-stu-id="789c1-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="789c1-109">Ringback bot 有助于避免在此方案中可能出现的意外 silences。</span><span class="sxs-lookup"><span data-stu-id="789c1-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="789c1-110">对于从 PSTN 到团队客户端的入站呼叫，Ringback bot 会向呼叫者播放独特的音频信号，以指示团队正在建立呼叫的过程。</span><span class="sxs-lookup"><span data-stu-id="789c1-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="789c1-111">Ringback 机器人从团队后端生成早期媒体。</span><span class="sxs-lookup"><span data-stu-id="789c1-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="789c1-112">在某些国家和地区，当媒体开始流动时，您可能需要支付通话费用。</span><span class="sxs-lookup"><span data-stu-id="789c1-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="789c1-113">配置 Ringback bot</span><span class="sxs-lookup"><span data-stu-id="789c1-113">Configure the Ringback bot</span></span>

<span data-ttu-id="789c1-114">使用 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet 修改以前定义的会话边界控制器 (SBC) 配置，或 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet 以创建新的 sbc 配置，以及用于配置 Ringback bot 的 **GenerateRingingWhileLocatingUser** 参数：</span><span class="sxs-lookup"><span data-stu-id="789c1-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="789c1-115">若要打开 Ringback 机器人，请将 **GenerateRingingWhileLocatingUser** 参数设置为 " **$True**"。</span><span class="sxs-lookup"><span data-stu-id="789c1-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="789c1-116">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="789c1-116">This is the default value.</span></span> 

- <span data-ttu-id="789c1-117">若要关闭 Ringback 机器人，请将 **GenerateRingingWhileLocatingUser** 参数设置为 " **$False**"。</span><span class="sxs-lookup"><span data-stu-id="789c1-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="789c1-118">相关主题</span><span class="sxs-lookup"><span data-stu-id="789c1-118">Related topics</span></span>

- [<span data-ttu-id="789c1-119">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="789c1-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
