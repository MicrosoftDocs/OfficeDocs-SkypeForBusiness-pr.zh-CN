---
title: Lync Server 2013：为不基于 Windows 的设备启用 QoS
description: Lync Server 2013：为不基于 Windows 的设备启用 QoS。
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
ms.openlocfilehash: a09aaea599a28dae9bd2c227439da86e8761b10d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546448"
---
# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>在 Lync Server 2013 中为不基于 Windows 的设备启用 QoS

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

安装 Microsoft Lync Server 2013 时，将不会为您的组织中使用 Windows 以外的操作系统的任何设备启用服务质量 (QoS) 。 您可以通过在 Lync Server 2013 命令行管理程序中运行以下命令来验证这一点：

    Get-CsMediaConfiguration

假设您尚未对媒体配置设置进行任何更改，您应获得如下返回信息：

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

如果将 EnableQoS 属性设置为 False (如前面的输出) 意味着不会为使用 Windows 之外的操作系统的计算机和设备启用服务质量。 默认情况下为 Lync Phone Edition 设备启用了 QoS;但是，可以禁用 Lync Phone Edition 的服务质量。

若要在全局范围内启用服务质量，请在 Lync Server 命令行管理程序中运行以下命令：

    Set-CsMediaConfiguration -EnableQoS $True

上面的命令在全局范围启用 QoS；但是，务必要注意媒体配置设置也可应用于站点范围。如果需要为站点启用服务质量，您必须在调用 Set-CsMediaConfiguration 时包括配置设置的标识。例如，此命令为 Redmond 站点启用 QoS：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> 您是否需要在站点范围启用 QoS？要视情况而定。分配给站点范围的设置的优先于分配给全局范围的设置。假设您在全局范围启用了 QoS 但在站点范围（为 Redmond 站点）禁用了 QoS。在这种情况下，将为 Redmond 站点禁用服务质量；这是因为站点设置的优先级高。要为 Redmond 站点启用 QoS，您必须使用应用于该站点的媒体配置设置执行此操作。



</div>

如果要同时为所有媒体配置设置启用 QoS (而不考虑作用域) 则在 Lync Server 命令行管理程序中运行以下命令：

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

您可以通过将 EnableQoS 属性的值设置为 False 来禁用使用 Windows 操作系统的设备的 QoS。 例如：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

这样，您就可以对您的网络的某些部分（例如对 Redmond 站点）实现 QoS，同时对您的网络的其他部分禁用服务质量。

只能使用 Windows PowerShell 启用和禁用 QoS。这些选项在 Lync Server 控制面板中不可用。

</div>

<span> </span>

</div>

</div>

</div>

