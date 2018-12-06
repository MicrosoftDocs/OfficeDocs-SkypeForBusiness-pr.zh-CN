---
title: 为不基于 Windows 的设备启用 QoS
TOCTitle: 为不基于 Windows 的设备启用 QoS
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204750(v=OCS.15)
ms:contentKeyID: 49312298
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为不基于 Windows 的设备启用 QoS

 

_**上一次修改主题：** 2012-11-01_

在您安装 Microsoft Lync Server 2013 时，不会为贵组织中使用除 Windows 之外的操作系统的任何设备启用服务质量 (QoS)。可通过从 Lync Server 2013 命令行管理程序中运行以下命令来验证这一点：

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

如果 EnableQoS 属性设置为 False（如前面的输出所示），则意味着没有为使用除 Windows 外的操作系统的计算机和设备启用服务质量。默认情况下为 Lync Phone Edition 设备启用 QoS；但是，可以为 Lync Phone Edition 禁用服务质量。

若要在全局范围启用服务质量，请从 Lync Server 命令行管理程序中运行以下命令：

    Set-CsMediaConfiguration -EnableQoS $True

上面的命令在全局范围启用 QoS；但是，务必要注意媒体配置设置也可应用于站点范围。如果需要为站点启用服务质量，您必须在调用 Set-CsMediaConfiguration 时包括配置设置的标识。例如，此命令为 Redmond 站点启用 QoS：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

> [!NOTE]  
> 您是否需要在站点范围启用 QoS？要视情况而定。分配给站点范围的设置的优先于分配给全局范围的设置。假设您在全局范围启用了 QoS 但在站点范围（为 Redmond 站点）禁用了 QoS。在这种情况下，将为 Redmond 站点禁用服务质量；这是因为站点设置的优先级高。要为 Redmond 站点启用 QoS，您必须使用应用于该站点的媒体配置设置执行此操作。



如果您要同时为所有媒体配置设置（不管范围为何）启用 QoS，请从 Lync Server 命令行管理程序中运行此命令：

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

可以为使用除 Windows 之外的操作系统的设备禁用 QoS，方法是将 EnableQoS 属性的值设置为 False。例如：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

这样，您就可以对您的网络的某些部分（例如对 Redmond 站点）实现 QoS，同时对您的网络的其他部分禁用服务质量。

只能使用 Lync Server 命令行管理程序启用和禁用 QoS。这些选项在 Lync Server 控制面板中不可用。

