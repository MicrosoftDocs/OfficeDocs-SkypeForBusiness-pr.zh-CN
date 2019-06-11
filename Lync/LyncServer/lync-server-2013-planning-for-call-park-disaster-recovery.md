---
title: Lync Server 2013：规划呼叫寄存灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7da940f55574e1c6d50aeb06c0c80710bdbaad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中规划呼叫寄存灾难恢复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-30_

本部分介绍了一些方法, 用于准备用于灾难恢复的呼叫寄存应用程序以及灾难恢复过程的一些注意事项。

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>准备呼叫寄存灾难恢复

在准备和执行灾难恢复过程时, 请牢记以下事项。

  - 在执行容量规划时规划灾难恢复。 对于灾难恢复容量, 配对池中的每个池都应该能够处理两个池中的呼叫寄存服务的工作负荷。 有关呼叫寄存容量规划的详细信息, 请参阅[Lync Server 2013 中的呼叫寄存的容量规划](lync-server-2013-capacity-planning-for-call-park.md)。

  - 在灾难恢复期间, 已被重定向到备份池的用户将使用在备份池中运行的呼叫驻留服务。 因此, 在灾难恢复期间对呼叫寄存的支持需要在主池和备份池中部署和启用呼叫驻留应用程序。

  - 对于驻留在该池中的用户, 每个池必须具有有效的轨道编号范围, 以便用于停车通话。

  - 始终保留已为呼叫寄存上载的任何自定义音乐的单独备份副本。 这些文件不会作为 Lync Server 2013 灾难恢复过程的一部分进行备份, 如果上载到该池的文件已损坏、损坏或删除, 将丢失这些文件。

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>呼叫寄存灾难恢复注意事项

每个池中只能定义一组通话寄存应用程序配置设置和一个自定义的音乐保留音频文件。 这些设置包括超时阈值、暂停的音乐、最大的呼叫装货尝试和超时 URI。 若要查看这些配置设置, 请运行**CsCpsConfiguration** cmdlet。 有关**CsCpsConfiguration** cmdlet 的详细信息, 请参阅[CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)。

在灾难恢复期间, 呼叫寄存使用备份池中的 "呼叫驻留" 应用程序, 因此不会备份主池中的设置。 如果无法恢复主池, 并且你部署新池以替换主池, 则会丢失主池中的设置, 你需要在新池中重新配置呼叫寄存设置和任何自定义的音乐保留音频文件。

如果你部署具有不同完全限定的域名 (FQDN) 的新池来替换主池, 你需要将与主池相关联的所有呼叫寄存轨道范围重新分配给新池的 FQDN。 若要将轨道范围重新分配给新池, 你可以使用 Lync Server 控制面板或**CsCallParkOrbit** cmdlet。 有关**CsCallParkOrbit** cmdlet 的详细信息, 请参阅[set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

