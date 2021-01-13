---
title: 为不基于 Windows 的设备启用 QoS
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 了解如何为组织中使用的使用非 Windows 操作系统的设备启用 QoS。
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814172"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="45f44-103">在 Skype for Business Server 中为不基于 Windows 的设备启用 QoS</span><span class="sxs-lookup"><span data-stu-id="45f44-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="45f44-104">安装 Skype for Business Server 时，不会为使用 Windows 操作系统 (组织中使用的任何设备启用 QoS) 服务质量。</span><span class="sxs-lookup"><span data-stu-id="45f44-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="45f44-105">可以通过从 Skype for Business ServerManagement Shell 中运行以下命令来验证这一点：</span><span class="sxs-lookup"><span data-stu-id="45f44-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="45f44-106">假设您尚未对媒体配置设置进行任何更改，应返回类似于以下的信息：</span><span class="sxs-lookup"><span data-stu-id="45f44-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="45f44-107">如果 EnableQoS 属性设置为 False (如前面的输出) 则意味着不会为使用 Windows 操作系统的计算机和设备启用服务质量。</span><span class="sxs-lookup"><span data-stu-id="45f44-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="45f44-108">若要在全局范围启用服务质量，请从 Skype for Business Server 命令行管理程序 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="45f44-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="45f44-109">上面的命令在全局范围启用 QoS；但是，务必要注意媒体配置设置也可应用于站点范围。</span><span class="sxs-lookup"><span data-stu-id="45f44-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="45f44-110">如果需要为站点启用服务质量，则必须在调用 Set-CsMediaConfiguration 时包含配置设置的 Identity。</span><span class="sxs-lookup"><span data-stu-id="45f44-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="45f44-111">例如，此命令为 Redmond 站点启用 QoS：</span><span class="sxs-lookup"><span data-stu-id="45f44-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="45f44-112">您是否需要在站点范围启用 QoS？</span><span class="sxs-lookup"><span data-stu-id="45f44-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="45f44-113">要视情况而定。</span><span class="sxs-lookup"><span data-stu-id="45f44-113">That depends.</span></span> <span data-ttu-id="45f44-114">分配给站点范围的设置的优先于分配给全局范围的设置。</span><span class="sxs-lookup"><span data-stu-id="45f44-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="45f44-115">假设您在全局范围启用了 QoS，但在 Redmond 站点 (站点范围禁用 QoS) 。</span><span class="sxs-lookup"><span data-stu-id="45f44-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="45f44-116">在这种情况下，将禁用 Redmond 站点的服务质量;这是因为网站设置优先。</span><span class="sxs-lookup"><span data-stu-id="45f44-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="45f44-117">若要为 Redmond 站点启用 QoS，您必须使用应用于该站点的媒体配置设置来启用。</span><span class="sxs-lookup"><span data-stu-id="45f44-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="45f44-118">如果要同时为所有媒体配置设置启用 QoS (而不考虑作用域) ，请从 LSkype for Business Server 命令行管理程序中运行此命令：</span><span class="sxs-lookup"><span data-stu-id="45f44-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="45f44-119">可以通过将 EnableQoS 属性的值设置为 False，为使用 Windows 操作系统而非 Windows 的设备禁用 QoS。</span><span class="sxs-lookup"><span data-stu-id="45f44-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="45f44-120">例如：</span><span class="sxs-lookup"><span data-stu-id="45f44-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="45f44-121">这样，您就可以对您的网络的某些部分（例如对 Redmond 站点）实现 QoS，同时对您的网络的其他部分禁用服务质量。</span><span class="sxs-lookup"><span data-stu-id="45f44-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="45f44-122">QoS 只能使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="45f44-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="45f44-123">这些选项在 Skype for Business Server 控制面板中不可用。</span><span class="sxs-lookup"><span data-stu-id="45f44-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="45f44-124">适用于 iOS 版本 6.17 及更高版本的 Skype for Business 客户端现在支持 QoS。</span><span class="sxs-lookup"><span data-stu-id="45f44-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="45f44-125">此 QoS 功能仅适用于直接注册到托管网络上内部 Skype for Business 或 Lync 池服务器的 Skype for Business 客户端和 IP 电话设备。</span><span class="sxs-lookup"><span data-stu-id="45f44-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="45f44-126">QoS 不适用于通过 Internet 路由的流量。</span><span class="sxs-lookup"><span data-stu-id="45f44-126">QoS is not applicable for traffic routed over the Internet.</span></span>



