---
title: Lync Server 2013：为不基于 Windows 的设备启用 QoS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447c19b96e2189953db81db6ce4f022e4d0f6e6f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="4382a-102">在 Lync Server 2013 中为不基于 Windows 的设备启用 QoS</span><span class="sxs-lookup"><span data-stu-id="4382a-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4382a-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4382a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4382a-104">安装 Microsoft Lync Server 2013 时，将不会为组织中使用 Windows 以外的操作系统的任何设备启用服务质量（QoS）。</span><span class="sxs-lookup"><span data-stu-id="4382a-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="4382a-105">您可以通过在 Lync Server 2013 命令行管理程序中运行以下命令来验证这一点：</span><span class="sxs-lookup"><span data-stu-id="4382a-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="4382a-106">假设您尚未对媒体配置设置进行任何更改，您应获得如下返回信息：</span><span class="sxs-lookup"><span data-stu-id="4382a-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="4382a-107">如果将 EnableQoS 属性设置为 False （如前面的输出中所示），这意味着没有为使用 Windows 之外的操作系统的计算机和设备启用服务质量。</span><span class="sxs-lookup"><span data-stu-id="4382a-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="4382a-108">默认情况下为 Lync Phone Edition 设备启用了 QoS;但是，可以禁用 Lync Phone Edition 的服务质量。</span><span class="sxs-lookup"><span data-stu-id="4382a-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="4382a-109">若要在全局范围内启用服务质量，请在 Lync Server 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4382a-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="4382a-p103">上面的命令在全局范围启用 QoS；但是，务必要注意媒体配置设置也可应用于站点范围。如果需要为站点启用服务质量，您必须在调用 Set-CsMediaConfiguration 时包括配置设置的标识。例如，此命令为 Redmond 站点启用 QoS：</span><span class="sxs-lookup"><span data-stu-id="4382a-p103">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope. If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration. For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="4382a-p104">您是否需要在站点范围启用 QoS？要视情况而定。分配给站点范围的设置的优先于分配给全局范围的设置。假设您在全局范围启用了 QoS 但在站点范围（为 Redmond 站点）禁用了 QoS。在这种情况下，将为 Redmond 站点禁用服务质量；这是因为站点设置的优先级高。要为 Redmond 站点启用 QoS，您必须使用应用于该站点的媒体配置设置执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4382a-p104">Do you need to enable QoS at the site scope? That depends. Settings assigned to the site scope take precedence over settings assigned to the global scope. Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence. To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="4382a-118">如果要同时为所有媒体配置设置启用 QoS （不考虑作用域），请在 Lync Server 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4382a-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="4382a-119">您可以通过将 EnableQoS 属性的值设置为 False 来禁用使用 Windows 操作系统的设备的 QoS。</span><span class="sxs-lookup"><span data-stu-id="4382a-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="4382a-120">例如：</span><span class="sxs-lookup"><span data-stu-id="4382a-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="4382a-121">这样，您就可以对您的网络的某些部分（例如对 Redmond 站点）实现 QoS，同时对您的网络的其他部分禁用服务质量。</span><span class="sxs-lookup"><span data-stu-id="4382a-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="4382a-122">只能使用 Windows PowerShell 启用和禁用 QoS。这些选项在 Lync Server 控制面板中不可用。</span><span class="sxs-lookup"><span data-stu-id="4382a-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

