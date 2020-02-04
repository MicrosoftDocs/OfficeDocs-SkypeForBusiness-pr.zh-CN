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
ms.openlocfilehash: d7574169c5a8c9cb660a81b384711a4937056b37
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>在 Lync Server 2013 中为不基于 Windows 的设备启用 QoS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

安装 Microsoft Lync Server 2013 时，将不会为你的组织中使用 Windows 之外的操作系统的任何设备启用服务质量（QoS）。 你可以通过从 Lync Server 2013 命令行管理程序中运行以下命令来验证此情况：

    Get-CsMediaConfiguration

如果你未对媒体配置设置进行任何更改，你应返回类似以下内容的信息：

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

如果 EnableQoS 属性设置为 False （如前面的输出所示），表示没有为使用 Windows 以外的操作系统的计算机和设备启用服务质量。 默认情况下，Lync Phone Edition 设备启用 QoS;但是，可以禁用 Lync Phone Edition 的服务质量。

若要在全局范围内启用服务质量，请从 Lync Server 命令行管理程序中运行以下命令：

    Set-CsMediaConfiguration -EnableQoS $True

前面的命令在全局范围内启用 QoS;但是，请务必注意，媒体配置设置也可应用于网站范围。 如果需要为网站启用服务质量，则必须在调用 CsMediaConfiguration 时包括配置设置的标识。 例如，此命令为 Redmond 网站启用 QoS：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> 是否需要在网站范围内启用 QoS？ 这取决于。 分配给网站范围的设置优先于分配给全局范围的设置。 假设您已在全局范围内启用了 QoS，但在网站范围内禁用了该服务（对于雷德蒙的网站）。在这种情况下，将为 Redmond 网站禁用服务质量;这是因为网站设置优先。 若要为 Redmond 网站启用 QoS，您必须使用应用于该网站的媒体配置设置执行此操作。



</div>

如果你希望同时为所有媒体配置设置启用 QoS （无论范围如何），请在 Lync Server Management Shell 中运行以下命令：

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

你可以通过将 EnableQoS 属性的值设置为 False 来禁用使用 Windows 以外操作系统的设备的 QoS。 例如：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

这使你能够在你的网络的某些部分（例如，在雷德蒙的网站上）实现 QoS，同时保留在网络的其他部分禁用的服务质量。

QoS 只能使用 Windows PowerShell 启用和禁用这些选项在 Lync Server 控制面板中不可用。

</div>

<span> </span>

</div>

</div>

</div>

