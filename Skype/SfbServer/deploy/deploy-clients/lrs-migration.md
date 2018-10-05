---
title: 将 Lync 会议室系统设备迁移到 Skype 会议室系统版本 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: 阅读本主题可了解如何迁移 Lync 会议室系统设备使用 Skype 会议室系统 v2 软件。
ms.openlocfilehash: c87081ccd40765b10929a0d2762d834ce6a1b2ab
ms.sourcegitcommit: 2e11749734ff26b18709a1442b2c417f33430144
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "25429450"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="f9a97-103">将 Lync 会议室系统 (LRS) 设备迁移到 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="f9a97-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="f9a97-104">Skype 会议室系统版本 1 (SR v1) 软件 Lync 会议室系统 (LRS) 设备将到达[2018 年 10 月 9，支持的结束](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)。</span><span class="sxs-lookup"><span data-stu-id="f9a97-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software will reach [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="f9a97-105">这意味着所有产品更新或此日期之后的修补程序，也不会都收到 Skype 会议室系统 v1 软件。</span><span class="sxs-lookup"><span data-stu-id="f9a97-105">This means Skype Room Systems v1 software will not get any product updates or fixes after this date.</span></span> <span data-ttu-id="f9a97-106">建议使用 Skype 会议室系统 v1 软件的 Lync 会议室系统设备的客户升级其设备到 Skype 会议室系统版本 2 (SR v2)。</span><span class="sxs-lookup"><span data-stu-id="f9a97-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="f9a97-107">Skype 会议室系统版本 2 (SR v2) 软件与除了 Skype 的 Microsoft 团队适用于会议和呼叫所有 SR v2 支持设备上的业务服务器和联机服务。</span><span class="sxs-lookup"><span data-stu-id="f9a97-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="f9a97-108">您现有设备**可能会**继续工作 Skype 会议室系统 v1 软件支持的结束后，直至此软件命中软件 bug 程序需要 Microsoft 释放修复或可能使用情况下，现有的通信协议 Skype 会议室系统v1 软件更改或不再受支持。</span><span class="sxs-lookup"><span data-stu-id="f9a97-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software suppor until this software hits a software bug that needs Microsoft to release a fix, or may have a case where an existing communication protocol used by Skype Room System v1 software changes or is no longer supported.</span></span> <span data-ttu-id="f9a97-109">此类的一个已知的更改已否决的 TLS 1.0 / 1.1 Microsoft Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="f9a97-109">One such known change is deprecation of TLS 1.0/ 1.1 in Microsoft Office 365.</span></span> <span data-ttu-id="f9a97-110">您可以了解有关[TLS 1.0/1.1 否决准备](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9a97-110">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span>  

## <a name="which-devices-are-affected"></a><span data-ttu-id="f9a97-111">哪些设备会受到影响？</span><span class="sxs-lookup"><span data-stu-id="f9a97-111">Which devices are affected?</span></span>
<span data-ttu-id="f9a97-112">下面是此更改影响的设备的列表：</span><span class="sxs-lookup"><span data-stu-id="f9a97-112">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="f9a97-113">智能会议室系统</span><span class="sxs-lookup"><span data-stu-id="f9a97-113">SMART Room systems</span></span>](https://smartkapp.com/products/smart-room-systems)
- [<span data-ttu-id="f9a97-114">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="f9a97-114">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="f9a97-115">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="f9a97-115">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="f9a97-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="f9a97-116">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="f9a97-117">升级选项</span><span class="sxs-lookup"><span data-stu-id="f9a97-117">Upgrade options</span></span>
<span data-ttu-id="f9a97-118">有多个选项下一代 Skype 会议室系统 (SR v2) 的升级 Lync 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="f9a97-118">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="f9a97-119">Crestron 硬件折旧计划</span><span class="sxs-lookup"><span data-stu-id="f9a97-119">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="f9a97-120">Crestron 将为所有非 Crestron Lync 会议室系统客户[Crestron SR 系统](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)或等效提供升级。</span><span class="sxs-lookup"><span data-stu-id="f9a97-120">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="f9a97-121">此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或<!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。</span><span class="sxs-lookup"><span data-stu-id="f9a97-121">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="f9a97-122">到 RL3 Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="f9a97-122">Crestron RL2 to RL3</span></span>
<span data-ttu-id="f9a97-123">现有 Crestron RL2 （也称为 Crestron RL200） 客户可以获取升级到 RL3 使用当前 RL2 升级程序包的每个设备的最小成本。</span><span class="sxs-lookup"><span data-stu-id="f9a97-123">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="f9a97-124">此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或<!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。</span><span class="sxs-lookup"><span data-stu-id="f9a97-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="f9a97-125">智能会议室系统升级</span><span class="sxs-lookup"><span data-stu-id="f9a97-125">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="f9a97-126">对于智能 LRS 客户，除了 Crestron 硬件折旧计划，Microsoft 和智能还提供解决方案升级到 Skype 会议室系统 v2 工作。</span><span class="sxs-lookup"><span data-stu-id="f9a97-126">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="f9a97-127">将由智能向所有现有智能 LRS 客户提供此升级。</span><span class="sxs-lookup"><span data-stu-id="f9a97-127">This upgrade will be offered by SMART to all existing SMART LRS customers.</span></span> <span data-ttu-id="f9a97-128">将年 10 月 2018年在此页上提供此程序的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9a97-128">More details of this program will be provided on this page in October 2018.</span></span> <span data-ttu-id="f9a97-129">请确保更新后的检查。</span><span class="sxs-lookup"><span data-stu-id="f9a97-129">Please make sure to check back for updates.</span></span>

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a><span data-ttu-id="f9a97-130">怎么办？</span><span class="sxs-lookup"><span data-stu-id="f9a97-130">What should you do?</span></span>
<span data-ttu-id="f9a97-131">我们建议您打算到之前使用上面提到的升级选项的 TLS 1.0/1.1 否决的 Skype 会议室系统 v2 更新 Lync 会议室系统的设备。</span><span class="sxs-lookup"><span data-stu-id="f9a97-131">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="f9a97-132">此外，也可以考虑将新设备认证 SR v2 替换为现有的设备。</span><span class="sxs-lookup"><span data-stu-id="f9a97-132">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="f9a97-133">有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Skype 会议室系统 v2 要求](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="f9a97-133">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="f9a97-134">Skype 会议室系统 v2 中尚不支持触摸和白板功能。</span><span class="sxs-lookup"><span data-stu-id="f9a97-134">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="f9a97-135">触摸和白板支持的 Skype 会议室系统 v2 积压工作中，将被添加到 H1 CY2019。</span><span class="sxs-lookup"><span data-stu-id="f9a97-135">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>
