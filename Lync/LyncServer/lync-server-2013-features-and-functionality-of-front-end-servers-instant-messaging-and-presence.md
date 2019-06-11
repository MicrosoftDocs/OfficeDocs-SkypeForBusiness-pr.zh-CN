---
title: Lync Server 2013：前端服务器、即时消息和状态的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739825eed3c8a3ba8239849e0c17c449180a2d95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 中前端服务器、即时消息和状态的功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-17_

前端服务器提供大多数 Lync 服务器功能。 有两个可用版本: Lync Server 企业版 (主要针对较大组织和 Lync Server 标准版设计), 它主要用于需要较小硬件 investement 的小型组织需要高可用性。 这两个版本都支持所有 Lync Server 工作负荷, 包括即时消息、状态、会议和企业语音。

通过即时消息 (IM)，用户可以在其计算机上使用基于文本的消息进行实时通信。 支持双方和多方之间的 IM 会话。 双方 IM 对话中的一方可以随时将第三方参与者加入对话中。 发生这种情况时，对话窗口会做出相应改变以支持会议功能。

<div>


> [!IMPORTANT]
> Lync 和 Communicator 客户参与一次通信时, 通常称为对等。 从技术上讲, 两个客户在一次对话中进行通信, 中间有即时消息 multipoint control 单元 (IMMCU)。 IMMCU 是前端服务器的组件。 将 IMMCU 放入所需的通信工作流中, 可使呼叫详细记录和前端服务器启用的其他功能。 通信来自客户端上的动态源端口到前端服务器端口 TLS/TCP/5061 (假设使用了推荐的传输层安全性)。 根据设计, 仅当 Lync Server 和 IMMCU 处于活动状态且可用时, 才能使用对等通信 (以及多方 IM)。



</div>

"*状态*" 向用户提供有关网络上其他人的状态的信息。 用户的状态所提供的信息有助于其他人决定是否应尝试与该用户联系，以及使用即时消息、电话还是电子邮件。 只要有可能，状态就会敦促进行即时通信；但状态也提供关于用户是否在开会或外出的信息，表明这种情况下不能进行即时通信。 此状态显示为 Lync 和其他状态感知应用程序中的 "状态" 图标, 包括 Microsoft Outlook 消息和协作客户端、Microsoft SharePoint 技术、Microsoft Word 和 Microsoft Excel 电子表格软件业. 状态图标表明用户当前是否有空以及是否愿意进行交流。

</div>

<span> </span>

</div>

</div>

</div>

