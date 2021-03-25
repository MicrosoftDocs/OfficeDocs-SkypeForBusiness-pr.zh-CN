---
title: 在 Skype for Business 中配置多个紧急号码
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 阅读本主题，了解如何在 Skype for Business Server 中配置多个紧急号码。
ms.openlocfilehash: dc05e94e88b371bb9ee22568eff567e758311233
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111888"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="11331-103">在 Skype for Business 中配置多个紧急号码</span><span class="sxs-lookup"><span data-stu-id="11331-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="11331-104">阅读本主题，了解如何在 Skype for Business Server 中配置多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="11331-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="11331-105">Skype for Business Server 现在支持客户端的多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="11331-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="11331-106">多个紧急号码是 2016 年 6 月累积更新中引入的新功能。</span><span class="sxs-lookup"><span data-stu-id="11331-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="11331-107">在将环境配置为支持多个紧急号码之前，请务必阅读在 Skype for Business Server 中规划多个 [紧急号码](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="11331-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="11331-108">如果你尚未升级到 2016 年 11 月累积更新，请参阅[Updates to Skype for Business Server 2015。](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="11331-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="11331-109">随着 2016 年 11 月累积更新，支持紧急号码的数量从 5 增加至 100。</span><span class="sxs-lookup"><span data-stu-id="11331-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="11331-110">配置多个紧急号码</span><span class="sxs-lookup"><span data-stu-id="11331-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="11331-111">若要配置多个紧急号码，请使用 New-CsEmergencyNumber cmdlet，然后使用 [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 和 [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet 指定 EmergencyNumbers 参数。</span><span class="sxs-lookup"><span data-stu-id="11331-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="11331-112">有关所有位置策略参数（如 PSTN 用法和所需位置）的完整说明，请参阅 [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="11331-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="11331-113">以下命令使用 cmdlet 创建一个拨号字符串为 911 的新New-CsEmergency号码：</span><span class="sxs-lookup"><span data-stu-id="11331-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="11331-114">下一个命令通过指定 Set-CsLocationPolicy cmdlet 中的 EmergencyNumbers 参数，将号码与指定位置策略关联：</span><span class="sxs-lookup"><span data-stu-id="11331-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="11331-115">下一个示例使用单个拨号掩码 112 创建紧急号码：</span><span class="sxs-lookup"><span data-stu-id="11331-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="11331-116">下一个命令将创建具有多个拨号掩码的紧急号码：</span><span class="sxs-lookup"><span data-stu-id="11331-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="11331-117">下一个示例添加多个具有多个拨号掩码的紧急号码，然后将紧急号码与指定的位置策略关联：</span><span class="sxs-lookup"><span data-stu-id="11331-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="11331-118">下一个示例为同时使用 911 和 450 的医疗保健提供商配置多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="11331-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="11331-119">下一个示例为伦敦市配置多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="11331-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="11331-120">下一个示例为印度配置多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="11331-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="11331-121">下一个示例删除 Dial 字符串为 911 且 Dial 掩码为 112 和 999 的现有条目：</span><span class="sxs-lookup"><span data-stu-id="11331-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```