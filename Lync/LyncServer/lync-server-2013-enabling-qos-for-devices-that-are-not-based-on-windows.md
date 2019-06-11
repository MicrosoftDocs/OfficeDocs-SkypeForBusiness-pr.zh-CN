---
title: 'Lync Server 2013: 为不基于 Windows 的设备启用 QoS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="2a8e2-102">在 Lync Server 2013 中为不基于 Windows 的设备启用 QoS</span><span class="sxs-lookup"><span data-stu-id="2a8e2-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a8e2-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2a8e2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2a8e2-104">安装 Microsoft Lync Server 2013 时, 将不会为你的组织中使用 Windows 之外的操作系统的任何设备启用服务质量 (QoS)。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="2a8e2-105">你可以通过从 Lync Server 2013 命令行管理程序中运行以下命令来验证此情况:</span><span class="sxs-lookup"><span data-stu-id="2a8e2-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="2a8e2-106">如果你未对媒体配置设置进行任何更改, 你应返回类似以下内容的信息:</span><span class="sxs-lookup"><span data-stu-id="2a8e2-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="2a8e2-107">如果 EnableQoS 属性设置为 False (如前面的输出所示), 表示没有为使用 Windows 以外的操作系统的计算机和设备启用服务质量。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="2a8e2-108">默认情况下, Lync Phone Edition 设备启用 QoS;但是, 可以禁用 Lync Phone Edition 的服务质量。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="2a8e2-109">若要在全局范围内启用服务质量, 请从 Lync Server 命令行管理程序中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="2a8e2-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="2a8e2-110">前面的命令在全局范围内启用 QoS;但是, 请务必注意, 媒体配置设置也可应用于网站范围。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-110">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="2a8e2-111">如果需要为网站启用服务质量, 则必须在调用 CsMediaConfiguration 时包括配置设置的标识。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-111">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="2a8e2-112">例如, 此命令为 Redmond 网站启用 QoS:</span><span class="sxs-lookup"><span data-stu-id="2a8e2-112">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="2a8e2-113">是否需要在网站范围内启用 QoS？</span><span class="sxs-lookup"><span data-stu-id="2a8e2-113">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="2a8e2-114">这取决于。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-114">That depends.</span></span> <span data-ttu-id="2a8e2-115">分配给网站范围的设置优先于分配给全局范围的设置。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-115">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="2a8e2-116">假设您已在全局范围内启用了 QoS, 但在网站范围内禁用了该服务 (对于雷德蒙的网站)。在这种情况下, 将为 Redmond 网站禁用服务质量;这是因为网站设置优先。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-116">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="2a8e2-117">若要为 Redmond 网站启用 QoS, 您必须使用应用于该网站的媒体配置设置执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-117">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="2a8e2-118">如果你希望同时为所有媒体配置设置启用 QoS (无论范围如何), 请在 Lync Server Management Shell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="2a8e2-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="2a8e2-119">你可以通过将 EnableQoS 属性的值设置为 False 来禁用使用 Windows 以外操作系统的设备的 QoS。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="2a8e2-120">例如：</span><span class="sxs-lookup"><span data-stu-id="2a8e2-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="2a8e2-121">这使你能够在你的网络的某些部分 (例如, 在雷德蒙的网站上) 实现 QoS, 同时保留在网络的其他部分禁用的服务质量。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="2a8e2-122">QoS 只能使用 Windows PowerShell 启用和禁用这些选项在 Lync Server 控制面板中不可用。</span><span class="sxs-lookup"><span data-stu-id="2a8e2-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

