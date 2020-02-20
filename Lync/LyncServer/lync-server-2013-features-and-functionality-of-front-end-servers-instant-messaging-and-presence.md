---
title: Lync Server 2013：前端服务器、即时消息和状态的特性和功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 639df8bdcee7531895eaafe9dd8ca5fac3f6fc3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 中前端服务器、即时消息和状态的特性和功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-17_

前端服务器提供大多数 Lync Server 功能。 有两种可用的版本： Lync Server Enterprise Edition 主要针对大型组织和 Lync Server Standard Edition 设计，后者主要针对需要较小硬件 investement 且不支持的小型组织。需要高可用性。 这两个版本都支持所有 Lync Server 工作负载，包括 IM、状态、会议和企业语音。

通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。支持双方和多方之间的 IM 会话。双方 IM 对话中的一方可以随时将第三方参与者加入对话中。发生这种情况时，对话窗口会做出相应改变以支持会议功能。

<div>


> [!IMPORTANT]
> Lync 和 Communicator 客户端参与一次通信时，通常称为对等。 从技术上讲，两个客户端在一次对话中进行通信，中间是即时消息 multipoint 控制单元（IMMCU）。 IMMCU 是前端服务器的组件。 将 IMMCU 置于所需的通信工作流中可允许呼叫详细记录和前端服务器启用的其他功能。 从客户端上的动态源端口到前端服务器端口 TLS/TCP/5061 的通信（假设使用建议的传输层安全性）。 根据设计，仅当 Lync Server 和 IMMCU 处于活动状态且可用时，才可以使用对等通信（以及多方 IM）。



</div>

*状态* 向用户提供网络中其他人的状态信息。 用户的状态所提供的信息有助于其他人决定是否应尝试与该用户联系，以及使用即时消息、电话还是电子邮件。 只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。 此状态显示为 Lync 中的状态图标和其他状态感知应用程序，包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术、Microsoft Word 和 Microsoft Excel 电子表格软件列表. 状态图标表明用户当前是否有空以及是否愿意进行交流。

</div>

<span> </span>

</div>

</div>

</div>

