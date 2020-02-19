---
title: Lync Server 2013：规划呼叫寄存灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca9eb8b87d4485fe1cb02aa8663b362d921a4fff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中规划呼叫寄存灾难恢复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-30_

本节介绍一些为灾难恢复准备呼叫寄存应用程序以及灾难恢复过程的一些注意事项的方法。

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>为呼叫寄存灾难恢复做准备

准备和执行灾难恢复过程时牢记以下事项。

  - 执行容量规划时，规划灾难恢复。 对于灾难恢复容量，配对池中的每个池都应能够处理两个池中的呼叫寄存服务的工作负荷。 有关呼叫寄存容量规划的详细信息，请参阅[Lync Server 2013 中的呼叫寄存的容量规划](lync-server-2013-capacity-planning-for-call-park.md)。

  - 灾难恢复期间，作为故障转移过程之一重定向至备份池的用户将使用在备份池中运行的呼叫寄存服务。 因此，在灾难恢复过程中对呼叫寄存的支持要求在主池和备份池中部署和启用呼叫寄存应用程序。

  - 每个池针对驻留在该池中的用户数必须具有有效范围的用于寄存呼叫的通道号。

  - 始终保留已为呼叫寄存上载的任何自定义音乐保留的单独备份副本。 这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份，如果上载到池的文件已损坏、损坏或清除，则这些文件将丢失。

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>呼叫寄存灾难恢复注意事项

您可以为每个池仅定义一组呼叫寄存应用程序配置设置和一个自定义的音乐保留音频文件。 这些设置包括超时阈值、保持音乐、最大呼叫应答尝试数和超时 URI。 要查看这些配置设置，请运行 **Get-CsCpsConfiguration** cmdlet。 有关**CsCpsConfiguration** cmdlet 的详细信息，请参阅[CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)。

在灾难恢复过程中，呼叫寄存将使用备份池中的呼叫寄存应用程序，因此不会备份主池中的设置。 如果无法恢复主池并部署新池以替换主池，则将丢失主池的设置，并且需要在新池中重新配置呼叫寄存设置和任何自定义的音乐保留音频文件。

如果使用其他完全限定的域名（FQDN）部署新池以替换主池，则需要将与主池关联的所有呼叫寄存轨道范围重新分配给新池的 FQDN。 若要将轨道范围重新分配给新池，可以使用 Lync Server 控制面板或**CsCallParkOrbit** cmdlet。 有关**CsCallParkOrbit** cmdlet 的详细信息，请参阅[CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

