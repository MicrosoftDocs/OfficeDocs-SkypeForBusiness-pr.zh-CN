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
ms.openlocfilehash: 956fff0e7fc69b1950e35261c02f9f44977510ce
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "37341938"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>在不基于 Windows 的设备的 Skype for Business 服务器中启用 QoS


安装 Skype for Business 服务器时，将不会为你的组织中使用 Windows 之外的操作系统的任何设备启用服务质量（QoS）。 你可以通过从 Skype for Business ServerManagement Shell 中运行以下命令来验证此情况：

    Get-CsMediaConfiguration

如果你未对媒体配置设置进行任何更改，你应返回类似于以下内容的信息：

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

如果 EnableQoS 属性设置为 False （如前面的输出所示），表示没有为使用 Windows 以外的操作系统的计算机和设备启用服务质量。

若要在全局范围内启用服务质量，请从 Skype for Business 服务器管理外壳程序内运行以下命令：

    Set-CsMediaConfiguration -EnableQoS $True

前面的命令在全局范围内启用 QoS;但是，请务必注意，媒体配置设置也可应用于网站范围。 如果需要为网站启用服务质量，则必须在调用 CsMediaConfiguration 时包括配置设置的标识。 例如，此命令为 Redmond 网站启用 QoS：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> 是否需要在网站范围内启用 QoS？ 这取决于。 分配给网站范围的设置优先于分配给全局范围的设置。 假设你已在全局范围内启用了 QoS，但在网站范围（对于 Redmond 网站）禁用了 QoS。 在这种情况下，将为 Redmond 网站禁用服务质量;这是因为网站设置优先。 若要为 Redmond 网站启用 QoS，必须使用应用于该网站的媒体配置设置执行此操作。


如果你希望同时为所有媒体配置设置启用 QoS （无论范围如何），请在 LSkype for Business Server Management Shell 中运行此命令：

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

你可以通过将 EnableQoS 属性的值设置为 False 来禁用使用 Windows 以外操作系统的设备的 QoS。 例如：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

这使你能够在你的网络的某些部分（例如，在雷德蒙的网站上）实现 QoS，同时保留在网络的其他部分禁用的服务质量。

QoS 只能使用 Windows PowerShell 启用和禁用。 这些选项在 "Skype for Business 服务器" 控制面板中不可用。

> [!NOTE]
> 适用于 iOS 版本6.17 和更高版本的 Skype for business 客户端现在支持 QoS。  此 QoS 功能仅适用于直接注册到托管网络上的内部 Skype for business 或 Lync pool Server 的 Skype for business 客户端和 IP 电话设备。 QoS 不适用于通过 Internet 路由的通信。



