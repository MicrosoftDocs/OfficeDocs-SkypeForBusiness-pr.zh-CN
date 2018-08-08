---
title: Skype for Business 中配置多个紧急号码
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 阅读本主题可了解如何在 Skype for Business Server 中配置多个紧急号码。
ms.openlocfilehash: 01dc72e2d165ff3c4076aa4180768ca941607b93
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985421"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="95881-103">Skype for Business 中配置多个紧急号码</span><span class="sxs-lookup"><span data-stu-id="95881-103">Configure multiple emergency numbers in Skype for Business</span></span>
 
<span data-ttu-id="95881-104">阅读本主题可了解如何在 Skype for Business Server 中配置多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="95881-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="95881-105">Skype 业务服务器现在支持的客户端的多个紧急号码。</span><span class="sxs-lookup"><span data-stu-id="95881-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="95881-106">多个紧急号码是年 6 月 2016年中引入的新功能累积更新。</span><span class="sxs-lookup"><span data-stu-id="95881-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="95881-107">在配置您的环境以支持多个紧急号码之前，请务必阅读[Plan for Business Server 的 Skype 中的多个紧急号码](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="95881-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="95881-108">如果您具有尚未升级到年 11 月 2016年累积更新，请参阅[业务服务器 2015年的 Skype 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)。</span><span class="sxs-lookup"><span data-stu-id="95881-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="95881-109">与年 11 月 2016年累积更新，支持紧急号码数增大从 5 至 100。</span><span class="sxs-lookup"><span data-stu-id="95881-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 
  
## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="95881-110">配置多个紧急号码</span><span class="sxs-lookup"><span data-stu-id="95881-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="95881-111">若要配置多个紧急号码，请使用新建 CsEmergencyNumber cmdlet，然后 EmergencyNumbers 参数指定使用[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)和[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95881-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="95881-112">有关所有位置策略参数，如 PSTN 用法和所需的位置的完整说明，请参阅[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="95881-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>
  
<span data-ttu-id="95881-113">以下命令通过使用 New-CsEmergency cmdlet，创建了一个包含拨号串 911 的新紧急号码：</span><span class="sxs-lookup"><span data-stu-id="95881-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="95881-114">下一个命令通过在 Set-CsLocationPolicy cmdlet 中指定 EmergencyNumbers 参数，将此号码与指定的位置策略关联起来：</span><span class="sxs-lookup"><span data-stu-id="95881-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

<span data-ttu-id="95881-115">在下一个示例中，创建了一个包含单个拨号掩码 112 的紧急号码：</span><span class="sxs-lookup"><span data-stu-id="95881-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

<span data-ttu-id="95881-116">下面的命令创建多个拨号掩码紧急号码：</span><span class="sxs-lookup"><span data-stu-id="95881-116">The next command creates an emergency number with multiple dial masks:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

<span data-ttu-id="95881-117">下一个示例添加了具有多个拨号掩码的多个紧急号码，然后将这些紧急号码与指定位置策略关联起来：</span><span class="sxs-lookup"><span data-stu-id="95881-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

<span data-ttu-id="95881-118">下一个示例为使用 911 和 450 的医疗保健提供商配置了多个紧急号码： </span><span class="sxs-lookup"><span data-stu-id="95881-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="95881-119">下一个示例为伦敦市配置了多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="95881-119">The next example configures multiple emergency numbers for the city of London:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

<span data-ttu-id="95881-120">下一个示例为印度配置了多个紧急号码：</span><span class="sxs-lookup"><span data-stu-id="95881-120">The next example configures multiple emergency numbers for India:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

<span data-ttu-id="95881-121">下一个示例删除了包含拨号串 911 及拨号掩码 112 和 999 的现有条目。</span><span class="sxs-lookup"><span data-stu-id="95881-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```


