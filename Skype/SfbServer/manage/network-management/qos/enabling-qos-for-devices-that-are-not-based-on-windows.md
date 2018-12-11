---
title: 未基于 Windows 的设备启用 QoS
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
ms.openlocfilehash: 0dc870080b3cfcd5f73eaf6e45aee841b9c8b488
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222770"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>未基于 Windows 的设备的企业服务器启用 QoS Skype 中


在安装 Skype 业务服务器时，将未启用任何使用非 Windows 操作系统的设备在组织中使用的服务质量 (QoS)。 您可以为业务 ServerManagement 命令行管理程序中运行以下命令从 Skype 中的进行验证：

    Get-CsMediaConfiguration

假定您不具有对媒体配置设置进行任何更改，您应获得信息类似如下：

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

如果 EnableQoS 属性设置为 False （如所示的上述输出） 的计算机和使用非 Windows 操作系统的设备意味着，未启用服务质量。

若要在全局范围内的服务质量，请运行 Business Server 命令行管理程序从 Skype 中的以下命令：

    Set-CsMediaConfiguration -EnableQoS $True

上述命令启用 QoS 在全局范围;但是，务必要注意的媒体配置设置也可以应用到站点范围。 如果您需要为网站启用服务质量，您必须在调用设置 CsMediaConfiguration 时包括的配置设置的标识。 例如，此命令为 Redmond 站点启用 QoS:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> 您是否需要启用 QoS 站点范围？ 这取决于。 分配给网站范围的设置优先于分配给全局作用域的设置。 假设您有 QoS 在全局范围启用，但禁用在站点范围 （对于 Redmond 站点）。 在这种情况下，为 Redmond 站点; 将禁用的服务质量这是因为站点设置优先。 若要为 Redmond 站点启用 QoS，必须要使用的媒体配置设置应用到该网站这样做。


如果您想要同时为 （不管范围） 所有媒体配置设置启用 QoS 中, 运行此命令从 LSkype for Business Server 命令行管理程序：

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

您可以禁用 QoS EnableQoS 属性的值设置为 False 使用非 Windows 操作系统的设备。 例如：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

这使您能够在您的网络 （例如，在 Redmond 站点） 的某些部分实现 QoS 同时保持其他部分的网络上禁用的服务质量。

仅可以启用或禁用使用 Windows PowerShell QoS。 这些选项不可用的业务 Server Control Panel Skype 中。


