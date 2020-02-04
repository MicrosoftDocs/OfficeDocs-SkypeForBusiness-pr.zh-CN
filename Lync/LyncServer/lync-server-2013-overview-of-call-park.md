---
title: Lync Server 2013：通话寄存的概述
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
ms.openlocfilehash: c5deeff873b37c0056bf03c598c39e448cba4379
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Lync Server 2013 中的呼叫寄存概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-29_

Lync Server 2013 调用寄存应用程序允许企业语音用户执行以下任一操作：

  - 将呼叫置于保持状态并从同一电话或另一电话取回该呼叫。

  - 将呼叫置于保持状态，以将其转接到某个部门或常规区域（例如，转接到有公用区域电话的销售部门或仓库）。

  - 将呼叫置于保持状态，并保持原始应答电话处于空闲状态，以接听其他呼叫。

当用户公园呼叫时，Lync 服务器将呼叫转移到一个称为 "*轨道*" 的临时号码，在此期间，呼叫将一直保持到被检索或超时。Lync 服务器将轨道发送给停用呼叫的用户。 用户可以通过拨打该通道号或单击“对话”窗口中的通道链接或按钮来取回寄存的呼叫。

寄存呼叫的用户可以使用外部机制（如即时消息 (IM) 或寻呼系统）通知某人取回呼叫，以向其他人通知该通道号。寄存呼叫的用户可以使“对话”窗口保持打开状态，以在取回呼叫时接收通知。

由于轨道范围是全局唯一的，因此，如果路由配置正确，则可以从任何 Lync 服务器站点或 PBX 电话检索呼叫。 如果在可配置的时间内没有人取回呼叫，则呼叫将回拨到寄存它的人。 如果此人不应答回拨电话，呼叫将转接到回退目标，例如接线员（如果这样配置的话）。 可以配置呼叫在转接前的回拨次数（1 到 10 次）。 如果没有人应答转接呼叫，则呼叫将断开连接。 呼叫取回或断开连接后会释放通道。

部署呼叫寄存时，您需要为呼叫寄存保留一定范围的分机号。 这些分机应该是虚拟分机：尚未分配任何用户或电话的分机。 然后根据分机号的范围配置呼叫寄存通道表，并指定承载负责处理每个范围的呼叫寄存应用程序的应用程序服务。 每个前端池在对应的后端服务器上都有一个 "呼叫驻留" 表，用于管理池中停用的呼叫。 轨道范围列表存储在中央管理存储中，用于将 "轨道式" 路由到目标池。 在其中部署和配置呼叫驻留应用程序的每个 Lync 服务器池都可以有一个或多个轨道范围。 在 Lync 服务器部署中，轨道范围必须全局唯一。

您还可以配置其他呼叫寄存设置，例如当呼叫超时时重定向到什么位置以及寄存时打电话的人是否可以听到音乐。您还可以指定呼叫处于保持状态时播放的音乐文件。

<div>


> [!NOTE]  
> Lync Server 2013 灾难恢复过程中不会备份呼叫寄存的自定义的 "保留式音乐" 文件，如果上载到该池中的文件已损坏、损坏或删除，将丢失。 始终保留已为呼叫寄存上载的自定义的保持音乐文件的单独备份副本。



</div>

呼叫寄存应用程序是企业语音的一个组件。 部署企业语音时，将自动安装和激活通话寄存应用程序。 但是，在您可以使用呼叫寄存之前，企业语音管理员必须配置它并通过语音策略为用户启用它。

</div>

<span> </span>

</div>

</div>

</div>

