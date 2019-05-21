---
title: 为不基于 Windows 的设备启用 QoS
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何为组织中使用 Windows 之外的操作系统的设备启用 QoS。
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279408"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="38de2-103">在不基于 Windows 的设备的 Skype for Business 服务器中启用 QoS</span><span class="sxs-lookup"><span data-stu-id="38de2-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="38de2-104">安装 Skype for Business 服务器时, 将不会为你的组织中使用 Windows 之外的操作系统的任何设备启用服务质量 (QoS)。</span><span class="sxs-lookup"><span data-stu-id="38de2-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="38de2-105">你可以通过从 Skype for Business ServerManagement Shell 中运行以下命令来验证此情况:</span><span class="sxs-lookup"><span data-stu-id="38de2-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="38de2-106">如果你未对媒体配置设置进行任何更改, 你应返回类似于以下内容的信息:</span><span class="sxs-lookup"><span data-stu-id="38de2-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="38de2-107">如果 EnableQoS 属性设置为 False (如前面的输出所示), 表示没有为使用 Windows 以外的操作系统的计算机和设备启用服务质量。</span><span class="sxs-lookup"><span data-stu-id="38de2-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="38de2-108">若要在全局范围内启用服务质量, 请从 Skype for Business 服务器管理外壳程序内运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="38de2-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="38de2-109">前面的命令在全局范围内启用 QoS;但是, 请务必注意, 媒体配置设置也可应用于网站范围。</span><span class="sxs-lookup"><span data-stu-id="38de2-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="38de2-110">如果需要为网站启用服务质量, 则必须在调用 CsMediaConfiguration 时包括配置设置的标识。</span><span class="sxs-lookup"><span data-stu-id="38de2-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="38de2-111">例如, 此命令为 Redmond 网站启用 QoS:</span><span class="sxs-lookup"><span data-stu-id="38de2-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="38de2-112">是否需要在网站范围内启用 QoS？</span><span class="sxs-lookup"><span data-stu-id="38de2-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="38de2-113">这取决于。</span><span class="sxs-lookup"><span data-stu-id="38de2-113">That depends.</span></span> <span data-ttu-id="38de2-114">分配给网站范围的设置优先于分配给全局范围的设置。</span><span class="sxs-lookup"><span data-stu-id="38de2-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="38de2-115">假设你已在全局范围内启用了 QoS, 但在网站范围 (对于 Redmond 网站) 禁用了 QoS。</span><span class="sxs-lookup"><span data-stu-id="38de2-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="38de2-116">在这种情况下, 将为 Redmond 网站禁用服务质量;这是因为网站设置优先。</span><span class="sxs-lookup"><span data-stu-id="38de2-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="38de2-117">若要为 Redmond 网站启用 QoS, 必须使用应用于该网站的媒体配置设置执行此操作。</span><span class="sxs-lookup"><span data-stu-id="38de2-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="38de2-118">如果你希望同时为所有媒体配置设置启用 QoS (无论范围如何), 请在 LSkype for Business Server Management Shell 中运行此命令:</span><span class="sxs-lookup"><span data-stu-id="38de2-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="38de2-119">你可以通过将 EnableQoS 属性的值设置为 False 来禁用使用 Windows 以外操作系统的设备的 QoS。</span><span class="sxs-lookup"><span data-stu-id="38de2-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="38de2-120">例如：</span><span class="sxs-lookup"><span data-stu-id="38de2-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="38de2-121">这使你能够在你的网络的某些部分 (例如, 在雷德蒙的网站上) 实现 QoS, 同时保留在网络的其他部分禁用的服务质量。</span><span class="sxs-lookup"><span data-stu-id="38de2-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="38de2-122">QoS 只能使用 Windows PowerShell 启用和禁用。</span><span class="sxs-lookup"><span data-stu-id="38de2-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="38de2-123">这些选项在 "Skype for Business 服务器" 控制面板中不可用。</span><span class="sxs-lookup"><span data-stu-id="38de2-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


