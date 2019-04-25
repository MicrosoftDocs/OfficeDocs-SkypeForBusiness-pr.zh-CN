---
title: 为不基于 Windows 的设备启用 QoS
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何为组织中使用的使用非 Windows 操作系统的设备启用 QoS。
ms.openlocfilehash: b1f3dae2d2b499b334995d7754282c56872ce111
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232711"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="1cb8e-103">未基于 Windows 的设备的企业服务器启用 QoS Skype 中</span><span class="sxs-lookup"><span data-stu-id="1cb8e-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="1cb8e-104">在安装 Skype 业务服务器时，将未启用任何使用非 Windows 操作系统的设备在组织中使用的服务质量 (QoS)。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="1cb8e-105">您可以为业务 ServerManagement 命令行管理程序中运行以下命令从 Skype 中的进行验证：</span><span class="sxs-lookup"><span data-stu-id="1cb8e-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="1cb8e-106">假定您不具有对媒体配置设置进行任何更改，您应获得信息类似如下：</span><span class="sxs-lookup"><span data-stu-id="1cb8e-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="1cb8e-107">如果 EnableQoS 属性设置为 False （如所示的上述输出） 的计算机和使用非 Windows 操作系统的设备意味着，未启用服务质量。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="1cb8e-108">若要在全局范围内的服务质量，请运行 Business Server 命令行管理程序从 Skype 中的以下命令：</span><span class="sxs-lookup"><span data-stu-id="1cb8e-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="1cb8e-109">上述命令启用 QoS 在全局范围;但是，务必要注意的媒体配置设置也可以应用到站点范围。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="1cb8e-110">如果您需要为网站启用服务质量，您必须在调用设置 CsMediaConfiguration 时包括的配置设置的标识。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="1cb8e-111">例如，此命令为 Redmond 站点启用 QoS:</span><span class="sxs-lookup"><span data-stu-id="1cb8e-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="1cb8e-112">您是否需要启用 QoS 站点范围？</span><span class="sxs-lookup"><span data-stu-id="1cb8e-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="1cb8e-113">这取决于。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-113">That depends.</span></span> <span data-ttu-id="1cb8e-114">分配给网站范围的设置优先于分配给全局作用域的设置。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="1cb8e-115">假设您有 QoS 在全局范围启用，但禁用在站点范围 （对于 Redmond 站点）。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="1cb8e-116">在这种情况下，为 Redmond 站点; 将禁用的服务质量这是因为站点设置优先。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="1cb8e-117">若要为 Redmond 站点启用 QoS，必须要使用的媒体配置设置应用到该网站这样做。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="1cb8e-118">如果您想要同时为 （不管范围） 所有媒体配置设置启用 QoS 中, 运行此命令从 LSkype for Business Server 命令行管理程序：</span><span class="sxs-lookup"><span data-stu-id="1cb8e-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="1cb8e-119">您可以禁用 QoS EnableQoS 属性的值设置为 False 使用非 Windows 操作系统的设备。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="1cb8e-120">例如：</span><span class="sxs-lookup"><span data-stu-id="1cb8e-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="1cb8e-121">这使您能够在您的网络 （例如，在 Redmond 站点） 的某些部分实现 QoS 同时保持其他部分的网络上禁用的服务质量。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="1cb8e-122">仅可以启用或禁用使用 Windows PowerShell QoS。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="1cb8e-123">这些选项不可用的业务 Server Control Panel Skype 中。</span><span class="sxs-lookup"><span data-stu-id="1cb8e-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


