---
title: Lync Server 2013：规划呼叫寄存灾难恢复
TOCTitle: 规划呼叫寄存灾难恢复
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205395(v=OCS.15)
ms:contentKeyID: 49314785
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划呼叫寄存灾难恢复

 

_**上一次修改主题：** 2012-10-30_

本节描述一些用来准备将 呼叫寄存应用程序用于灾难恢复的方法和一些用于灾难恢复过程的注意事项。

## 准备 呼叫寄存灾难恢复

准备和执行灾难恢复过程时牢记以下事项。

  - 执行容量规划时，规划灾难恢复。对于灾难恢复容量，成对池中每个池都应能够处理这两个池中的 呼叫寄存工作负荷。有关 呼叫寄存容量规划的详细信息，请参阅 [Lync Server 2013 中的呼叫寄存容量规划](lync-server-2013-capacity-planning-for-call-park.md)。

  - 灾难恢复期间，作为故障转移过程之一重定向至备份池的用户将使用在备份池中运行的呼叫寄存服务。因此，在灾难恢复期间支持 呼叫寄存需要在主池和备份池中部署并启用 呼叫寄存应用程序。

  - 每个池针对驻留在该池中的用户数必须具有有效范围的用于寄存呼叫的通道号。

  - 始终对已针对 呼叫寄存上载的任何自定义音乐保留一个单独的备份副本。这些文件不会作为 Lync Server 2013 灾难恢复过程之一进行备份，并且将在上载至池的文件毁坏、损坏或清除时丢失。

## 呼叫寄存灾难恢复注意事项

每个池仅可定义一组 呼叫寄存应用程序配置设置和一个自定义的保持音乐音频文件。这些设置包括超时阈值、保持音乐、最大呼叫应答尝试数和超时 URI。要查看这些配置设置，请运行 **Get-CsCpsConfiguration** cmdlet。有关 **Get-CsCpsConfiguration** cmdlet 的详细信息，请参阅 [Get-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCpsConfiguration)。

灾难恢复期间， 呼叫寄存会使用备份池中的 呼叫寄存应用程序，这样主池中的设置不会备份。如果无法恢复主池，且您部署新池来替换主池，则会丢失主池中的设置，且您需要在新池中重新配置 呼叫寄存设置和所有自定义保持音乐音频文件。

如果您部署具有不同完全限定域名 (FQDN) 的新池来替换主池，则需要将与主池关联的所有 呼叫寄存通道范围分配到新池的 FQDN，可使用 Lync Server 控制面板或 **Set-CsCallParkOrbit** cmdlet。有关 **Set-CsCallParkOrbit** cmdlet 的详细信息，请参阅 [Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)。

