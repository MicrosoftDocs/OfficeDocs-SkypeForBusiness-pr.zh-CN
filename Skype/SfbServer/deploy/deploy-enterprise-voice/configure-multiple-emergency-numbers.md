---
title: 在 Skype for Business 中配置多个紧急号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027793"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="26151-103">在 Skype for Business 中配置多个紧急号码</span><span class="sxs-lookup"><span data-stu-id="26151-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="26151-104">阅读本主题，了解如何在 Skype for Business Server 中配置多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="26151-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="26151-105">Skype for Business Server 现在支持客户端的多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="26151-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="26151-106">"多个紧急号码" 是6月2016累积更新中引入的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="26151-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="26151-107">在将环境配置为支持多个紧急号码之前，请务必阅读[Plan For Skype For Business Server 中的多个紧急号码](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="26151-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="26151-108">如果尚未升级到2016年11月累积更新，请参阅[更新到 Skype For Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="26151-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="26151-109">在11月2016累积更新中，支持紧急号码的数量从5增加到100。</span><span class="sxs-lookup"><span data-stu-id="26151-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="26151-110">配置多个紧急号码</span><span class="sxs-lookup"><span data-stu-id="26151-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="26151-111">若要配置多个紧急号码，请使用 New-csemergencynumber cmdlet，然后将 EmergencyNumbers 参数指定为[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="26151-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="26151-112">有关所有位置策略参数的完整说明（如 PSTN 用法和所需的位置），请参阅[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="26151-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="26151-113">以下命令使用 CsEmergency cmdlet 创建带有拨号字符串911的新的紧急号码：</span><span class="sxs-lookup"><span data-stu-id="26151-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="26151-114">下一个命令通过在 New-cslocationpolicy cmdlet 中指定 EmergencyNumbers 参数，将该号码与指定的位置策略相关联：</span><span class="sxs-lookup"><span data-stu-id="26151-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="26151-115">在下一个示例中，使用单个拨号掩码（112）创建一个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="26151-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="26151-116">下一个命令将创建带有多个拨号掩码的紧急号码：</span><span class="sxs-lookup"><span data-stu-id="26151-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="26151-117">下一个示例添加多个带多个拨号掩码的紧急号码，然后将紧急号码与指定的位置策略相关联：</span><span class="sxs-lookup"><span data-stu-id="26151-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="26151-118">下一个示例为使用911和450的卫生保健提供商配置了多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="26151-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="26151-119">下一个示例为伦敦的城市配置了多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="26151-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="26151-120">下一个示例为印度配置了多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="26151-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="26151-121">下一个示例将删除带有拨号字符串911和拨号掩码112和999的现有条目：</span><span class="sxs-lookup"><span data-stu-id="26151-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
