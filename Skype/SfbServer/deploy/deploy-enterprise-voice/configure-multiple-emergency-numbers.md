---
title: 在 Skype for Business Server 2015 中配置多个紧急号码
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 4/21/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 阅读本主题，了解如何在 Skype for Business Server 2015 中配置多个紧急号码。
ms.openlocfilehash: 98d9bbef92f5f3894fb288c01e474288f9f7bb4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a><span data-ttu-id="29bb8-103">在 Skype for Business Server 2015 中配置多个紧急号码</span><span class="sxs-lookup"><span data-stu-id="29bb8-103">Configure multiple emergency numbers in Skype for Business 2015</span></span>
 
<span data-ttu-id="29bb8-104">阅读本主题，了解如何在 Skype for Business Server 2015 中配置多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="29bb8-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="29bb8-105">Skype 业务服务器的客户端现在支持多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="29bb8-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="29bb8-106">多个紧急号码是 6 月的 2016 年引入的新功能累积更新。</span><span class="sxs-lookup"><span data-stu-id="29bb8-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="29bb8-107">配置您的环境以支持多个紧急号码之前，请务必阅读[规划业务服务器 2015年的 Skype 在多个紧急号码](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="29bb8-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="29bb8-108">如果您有尚未升级到 11 月 2016年累积更新，请参阅[更新业务服务器 2015年的 Skype](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="29bb8-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="29bb8-109">与 11 月 2016年累积更新，支持紧急号码数增加从 5 到 100。</span><span class="sxs-lookup"><span data-stu-id="29bb8-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 
  
## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="29bb8-110">配置多个紧急号码</span><span class="sxs-lookup"><span data-stu-id="29bb8-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="29bb8-111">要配置多个紧急号码，请使用 New CsEmergencyNumber cmdlet，，然后使用[New CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[一组 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet 指定 EmergencyNumbers 参数。</span><span class="sxs-lookup"><span data-stu-id="29bb8-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="29bb8-112">所有位置策略参数，如 PSTN 使用和所需，位置的完整说明，请参见[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="29bb8-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>
  
<span data-ttu-id="29bb8-113">以下命令通过使用 New-CsEmergency cmdlet，创建了一个包含拨号串 911 的新紧急号码：</span><span class="sxs-lookup"><span data-stu-id="29bb8-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 

```

<span data-ttu-id="29bb8-114">下一个命令通过在 Set-CsLocationPolicy cmdlet 中指定 EmergencyNumbers 参数，将此号码与指定的位置策略关联起来：</span><span class="sxs-lookup"><span data-stu-id="29bb8-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

<span data-ttu-id="29bb8-115">在下一个示例中，创建了一个包含单个拨号掩码 112 的紧急号码：</span><span class="sxs-lookup"><span data-stu-id="29bb8-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

<span data-ttu-id="29bb8-116">下一个命令创建多个拨号屏蔽的紧急号码：</span><span class="sxs-lookup"><span data-stu-id="29bb8-116">The next command creates an emergency number with multiple dial masks:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

<span data-ttu-id="29bb8-117">下一个示例添加了具有多个拨号掩码的多个紧急号码，然后将这些紧急号码与指定位置策略关联起来：</span><span class="sxs-lookup"><span data-stu-id="29bb8-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

<span data-ttu-id="29bb8-118">下一个示例为使用 911 和 450 的医疗保健提供商配置了多个紧急号码： </span><span class="sxs-lookup"><span data-stu-id="29bb8-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="29bb8-119">下一个示例为伦敦市配置了多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="29bb8-119">The next example configures multiple emergency numbers for the city of London:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

<span data-ttu-id="29bb8-120">下一个示例为印度配置了多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="29bb8-120">The next example configures multiple emergency numbers for India:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

<span data-ttu-id="29bb8-121">下一个示例删除了包含拨号串 911 及拨号掩码 112 和 999 的现有条目。</span><span class="sxs-lookup"><span data-stu-id="29bb8-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```


