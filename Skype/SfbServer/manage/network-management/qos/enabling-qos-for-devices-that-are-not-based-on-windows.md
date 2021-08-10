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
description: 了解如何为组织中使用的设备启用 QoS，这些设备使用非 Windows。
ms.openlocfilehash: 81350ae252252a85bd3f88a000d6cd78d85408e43ca56335517de7b50bb6fd49
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590926"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>为不基于Skype for Business Server的设备启用 QoS Windows


安装 Skype for Business Server 时，不会为组织中使用的任何使用非 Windows 操作系统的设备启用服务质量 (Qo) S Windows。 可以通过从 Skype for Business ServerManagement 命令行管理程序中运行以下命令来验证这一点：

**Get-CsMediaConfiguration**

假定你尚未对媒体配置设置进行任何更改，应获取以下类似信息：

标识：全局<br/>
EnableQoS ： False<br/>
EncryptionLevel ：RequireEncryption<br/>
EnableSiren ： False<br/>
MaxVideoRateAllowed ： VGA600K<br/>
EnableG722StereoCodec ： True<br/>
EnableH264Codec ： True<br/>
EnableAdaptiveBandwidthEstimation ：True<br/>

如果 EnableQoS 属性设置为 False (如前面的输出) 则意味着没有为使用非 Windows 操作系统的计算机和设备启用服务质量。

若要在全局范围启用服务质量，请从命令行管理程序Skype for Business Server以下命令：

**Set-CsMediaConfiguration -EnableQoS $True**

上面的命令在全局范围启用 QoS；但是，务必要注意媒体配置设置也可应用于站点范围。 如果需要为站点启用服务质量，则必须在调用 Set-CsMediaConfiguration 时包含配置设置的标识。 例如，此命令为 Redmond 站点启用 QoS：

**Set-CsMediaConfiguration -Identity site：Redmond -EnableQoS $True**


> [!NOTE]
> 您是否需要在站点范围启用 QoS？ 要视情况而定。 分配给站点范围的设置的优先于分配给全局范围的设置。 假设您在全局范围启用了 QoS，但在 Redmond 站点站点的站点 (禁用 QoS) 。 在这种情况下，将禁用 Redmond 站点的服务质量;这是因为网站设置优先。 若要为 Redmond 站点启用 QoS，您必须使用应用于该站点的媒体配置设置进行启用。


如果要同时启用所有媒体配置设置的 QoS， (范围) ，请从 LSkype for Business Server 命令行管理程序中运行以下命令：

**Get-CsMediaConfiguration |Set-CsMediaConfiguration -EnableQoS $True**

可以将 EnableQoS 属性的值设置为 False，为使用非 Windows操作系统的设备禁用 QoS。 例如：

**Set-CsMediaConfiguration -Identity site：Redmond -EnableQoS $False**

这样，您就可以对您的网络的某些部分（例如对 Redmond 站点）实现 QoS，同时对您的网络的其他部分禁用服务质量。

QoS 只能使用 Windows PowerShell。 这些选项在控制面板中Skype for Business Server可用。

> [!NOTE]
> Skype for Business iOS 版本 6.17 及更高版本的客户端现在支持 QoS。  此 QoS 功能仅适用于Skype for Business直接注册到托管网络上内部服务器或 Lync Skype for Business服务器的客户端和 IP 电话设备。 QoS 不适用于通过 Internet 路由的流量。
