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
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>在 Skype for Business Server 中为不基于 Windows 的设备启用 QoS


安装 Skype for Business Server 时，不会为使用 Windows 操作系统 (组织中使用的任何设备启用 QoS) 服务质量。 可以通过从 Skype for Business ServerManagement Shell 中运行以下命令来验证这一点：

    Get-CsMediaConfiguration

假设您尚未对媒体配置设置进行任何更改，应返回类似于以下的信息：

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

如果 EnableQoS 属性设置为 False (如前面的输出) 则意味着不会为使用 Windows 操作系统的计算机和设备启用服务质量。

若要在全局范围启用服务质量，请从 Skype for Business Server 命令行管理程序 中运行以下命令：

    Set-CsMediaConfiguration -EnableQoS $True

上面的命令在全局范围启用 QoS；但是，务必要注意媒体配置设置也可应用于站点范围。 如果需要为站点启用服务质量，则必须在调用 Set-CsMediaConfiguration 时包含配置设置的 Identity。 例如，此命令为 Redmond 站点启用 QoS：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> 您是否需要在站点范围启用 QoS？ 要视情况而定。 分配给站点范围的设置的优先于分配给全局范围的设置。 假设您在全局范围启用了 QoS，但在 Redmond 站点 (站点范围禁用 QoS) 。 在这种情况下，将禁用 Redmond 站点的服务质量;这是因为网站设置优先。 若要为 Redmond 站点启用 QoS，您必须使用应用于该站点的媒体配置设置来启用。


如果要同时为所有媒体配置设置启用 QoS (而不考虑作用域) ，请从 LSkype for Business Server 命令行管理程序中运行此命令：

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

可以通过将 EnableQoS 属性的值设置为 False，为使用 Windows 操作系统而非 Windows 的设备禁用 QoS。 例如：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

这样，您就可以对您的网络的某些部分（例如对 Redmond 站点）实现 QoS，同时对您的网络的其他部分禁用服务质量。

QoS 只能使用 Windows PowerShell。 这些选项在 Skype for Business Server 控制面板中不可用。

> [!NOTE]
> 适用于 iOS 版本 6.17 及更高版本的 Skype for Business 客户端现在支持 QoS。  此 QoS 功能仅适用于直接注册到托管网络上内部 Skype for Business 或 Lync 池服务器的 Skype for Business 客户端和 IP 电话设备。 QoS 不适用于通过 Internet 路由的流量。



