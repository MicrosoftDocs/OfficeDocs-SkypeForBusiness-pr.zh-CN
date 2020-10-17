---
title: Lync Server 2013：呼叫寄存的概述
description: Lync Server 2013：呼叫寄存的概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 373a758dcc64dc390255239c0d1fb628308080a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559258"
---
# <a name="overview-of-call-park-in-lync-server-2013"></a>Lync Server 2013 中的呼叫寄存概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

Lync Server 2013 呼叫寄存应用程序允许企业语音用户执行以下任一操作：

  - 将呼叫置于保持状态，然后从同一电话或其他电话检索呼叫。

  - 将呼叫置于保持状态以将其转移到部门或常规区域 (例如，转移到存在公用区域电话) 的销售部门或仓库。

  - 将呼叫置于保持状态，并保持原始应答电话对其他呼叫空闲。

当用户公园呼叫时，Lync Server 会将呼叫转移到一个临时号码（称为 " *轨道*"），其中呼叫将一直保留，直到检索或超时。Lync Server 将轨道发送给寄存呼叫的用户。 若要检索寄存的呼叫，用户可以拨打轨道编号或单击对话窗口中的 "轨道" 链接或按钮。

停用呼叫的用户可以通过外部机制（如即时消息 (IM) 或寻呼系统）通知他人检索呼叫，以将轨道编号传递给其他人。 停用呼叫的用户可以将对话窗口保持打开状态，以便在检索呼叫时接收通知。

由于轨道范围是全局唯一的，因此，如果路由配置正确，则可以从任何 Lync Server 站点或 PBX 电话检索呼叫。 如果没有人在一段可配置的时间内检索呼叫，则该呼叫将环回到寄存该呼叫的人。 如果此人不应答回拨，则会将呼叫转移到一个回退目标，例如，如果配置了，则转移到某个操作员。 可以将呼叫响铃的次数配置为从1到10次转接。 如果没有人应答转移的呼叫，则呼叫将断开连接。 检索或断开呼叫时，将释放轨道。

当您部署呼叫寄存时，需要为停车呼叫保留分机号码的范围。 这些扩展必须是虚拟扩展：没有向其分配用户或电话的扩展。 然后，使用分机号码范围配置呼叫寄存通道表，并指定哪个应用程序服务承载处理每个范围的呼叫寄存应用程序。 每个前端池在对应的后端服务器上都有一个呼叫寄存表，用于管理驻留在池上的呼叫。 轨道范围列表存储在中央管理存储中，用于将轨道式路由到目标池。 在其中部署和配置呼叫寄存应用程序的每个 Lync Server 池都可以有一个或多个轨道范围。 在 Lync Server 部署中，轨道范围必须是全局唯一的。

此外，还可以配置其他呼叫寄存设置，例如在呼叫超时的位置，以及电话上的人员是否在寄存时听到音乐。 您还可以指定要在呼叫处于保留状态时播放的音乐文件。

<div>


> [!NOTE]  
> 在 Lync Server 2013 灾难恢复过程中，不会将呼叫寄存的自定义音乐保留文件作为一部分进行备份，如果上载到池的文件已损坏、损坏或清除，则将丢失。 始终为已为呼叫寄存上载的自定义的保留音乐文件保留一个单独的备份副本。



</div>

呼叫寄存应用程序是企业语音的一个组件。 部署企业语音时，会自动安装并激活呼叫寄存应用程序。 但是，在使用呼叫寄存之前，企业语音管理员必须对其进行配置，并通过语音策略为用户启用呼叫寄存。

</div>

<span> </span>

</div>

</div>

</div>

