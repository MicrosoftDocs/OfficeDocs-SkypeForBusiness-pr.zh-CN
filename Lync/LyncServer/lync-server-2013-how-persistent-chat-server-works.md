---
title: Lync Server 2013：持久聊天服务器的工作方式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c582ad9e21e111745dc55fd2d43feada761e58d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Lync Server 2013 中持久聊天服务器的工作原理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-21_

Lync Server 2013、持久聊天服务器使您能够参与在一段时间内保持的基于主题的多个会话。 持久聊天服务器可帮助您的组织执行以下操作：

  - 改善分散在不同地理位置的跨部门团队间的通信

  - 扩大信息的知晓和参与范围

  - 改善组织扩大后的通信

  - 减少信息过载

  - 提高信息感知能力

  - 扩大重要知识和信息的传播范围

您可以将持久聊天服务器部署为 Lync Server 2013 的可选角色。 持久聊天服务在专用池上运行，持久聊天服务器池依赖于 Lync Server 池来将邮件路由到它。 客户端使用 eXtensible Chat Communication Over SIP (XCCOS)。 将 Lync Server 前端服务器配置为将流量路由到持久聊天服务器池。

<div>

## <a name="high-level-architecture"></a>高级体系结构

下面的关系图提供持久聊天服务器体系结构和服务的高级别角度。

**持久聊天服务器高级体系结构**

![持久聊天服务器体系结构。](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "持久聊天服务器体系结构。")

**持久聊天服务器高级服务**

![持久聊天服务器组件。](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "持久聊天服务器组件。")

在持久聊天服务器前端服务器上运行两个服务：

  - 持久聊天（通道）

  - 合规性

<div>

## <a name="persistent-chat-channel-service"></a>持久聊天（通道）服务

持久聊天（频道）服务是负责持久聊天服务器的核心服务。 此服务提供了以下功能：

  - 接受传入消息

  - 在持久聊天室中注册和列出在线参与者

  - 向其他通道订阅者重新传输消息

  - 实现通道管理、聊天室邀请、搜索和新内容通知的逻辑

持久聊天（通道）服务使用持久聊天存储来存储和访问聊天室内容以及其他系统元数据（授权规则等）。 此服务将上传到聊天室中的文件存储在持久聊天文件存储区中。

</div>

<div>

## <a name="compliance-service"></a>合规性服务

合规性服务是持久聊天服务器的可选组件，负责将聊天内容和事件存档到持久聊天合规性存储。 如果您的组织具有要求存档持久聊天活动的法规，则可以部署可选的持久聊天合规性服务。 合规性服务安装在持久聊天池中的每台持久聊天服务器上。 配置后，持久聊天服务器合规性记录用户活动，如加入和离开聊天室，以及投递和阅读邮件。 合规性服务存储需要存档在持久聊天合规性文件存储中的文件。

</div>

<div>

## <a name="persistent-chat-web-services"></a>持久聊天 Web 服务

在 Lync Server 前端服务器上，运行的两个服务依赖于 Internet 信息服务（IIS），并作为 web 组件实现：

  - **用于文件上载/下载的持久聊天 Web 服务**负责在聊天室中发布和检索文件。

  - **聊天室管理的持久聊天 Web 服务**负责为用户提供管理其聊天室和创建新聊天室的功能。

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>如何开始使用持久聊天服务器？

持久聊天服务器是 Lync Server 2013 基础结构中的可选服务器角色。 如果安装持久聊天服务器角色，则由管理员通过策略启用的任何用户都可以与 Lync 2013 客户端一起使用持久聊天。

有关如何部署持久聊天服务器并使用户能够利用策略功能的详细信息，请参阅[在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)。

有关如何在持久聊天服务器部署上配置设置的详细信息，请参阅[在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)和[管理 Lync Server 2013 的持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md)。

有关如何根据策略启用用户以在 Lync 2013 客户端中利用持久聊天功能的详细信息，请参阅[在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)和[管理 Lync Server 2013、持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md)。

如果已部署持久聊天合规性，请参阅[管理 Lync server 2013 和持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md)，了解有关如何配置合规性设置的详细信息。

</div>

<div>

## <a name="persistent-chat-call-flows"></a>持久聊天呼叫流

持久聊天客户端通过使用 XCCOS 与持久聊天服务进行通信。 以下顺序说明了登录过程以及典型的聊天室订阅和消息发布方案。

<div>

## <a name="sign-in"></a>登录

下面的调用流程图和步骤介绍了登录过程。

**持久聊天客户端登录呼叫流**

![持久聊天服务器呼叫流图表。](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "持久聊天服务器呼叫流图表。")

1.  持久聊天客户端先发送 SIP 订阅，以从服务器检索带内设置文档。 本文档指明是否为用户启用或禁用持久聊天以及持久聊天服务器池的 SIP Uri 列表。

2.  持久聊天客户端将 SIP 邀请邮件发送到在上一步中获取的持久聊天服务器的 SIP URI。 邀请序列后跟 200 OK 和 ACK，持久聊天客户端现在已使用持久聊天服务器终结点打开了 SIP 会话。 因此，持久聊天客户端通过发送 SIP 信息消息（其中包含聊天消息或命令请求服务器执行操作）与持久聊天服务器进行通信。 所有这些消息都使用“200 - 确定”或“503 - 服务不可用”（即，在服务器负载过重的情况下）确认。 如果客户端收到 503 响应，则会重试消息。 （此示例不包含503响应。）如果服务器接受消息或命令并发送 200 "确定"，则它会以单独的 SIP 信息消息的形式向客户端提供响应。 此响应包括对发出的命令的引用。

3.  持久聊天客户端发送包含 XCCOS **getserverinfo**命令的 SIP 信息消息。 持久聊天服务器使用新的 SIP 信息消息进行答复，其中包含有关持久聊天服务配置的信息。

4.  持久聊天客户端发送包含 XCCOS **getassociations**命令的 SIP 信息消息。 持久聊天服务器使用新的 SIP 信息消息进行答复，其中包含用户所属的聊天室的列表。 持久聊天客户端将重复命令，以检索用户是其管理员的聊天室的列表。

5.  持久聊天客户端从 "状态" 文档中获取关注的聊天室列表，其中每个聊天室都由一个 "roomSetting" 类别表示。 所有已关注的聊天室都通过一个包含 XCCOS **bjoin** 命令（包含聊天室 URI 列表）的 SIP INFO 消息联接。 由于已关注的聊天室的列表保存在服务器上，因此任何计算机上的任何客户端都具有相同的指定用户 URI 的已关注聊天室列表。 持久聊天客户端还会在本地计算机注册表中保留打开的会议室（如果用户已启用此选项）的列表，并通过发送包含每个打开的聊天室的 XCCOS **join**命令的 SIP 信息消息，在登录时加入这些会议室。 由于此列表保留在注册表中，因此在不同计算机上运行的两台持久聊天客户端上可能会有所不同。

6.  对于每个加入的会议室，持久聊天客户端发送包含 XCCOS **bccontext**命令的 SIP 信息消息。 持久聊天服务器使用新的 SIP 信息消息进行答复，其中包含聊天室中最新的聊天消息。

7.  持久聊天客户端发送包含 XCCOS **getinv** （即获取邀请）命令的 SIP 信息消息，以请求客户端尚未看到的任何新的聊天室邀请。 在单独的 SIP 信息消息中，持久聊天服务器返回这些聊天室的列表。

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>订阅聊天室和发布消息

下面的调用流程图和步骤介绍了典型的会议室订阅和邮件发布方案。

**持久聊天客户端会议室订阅和邮件发布呼叫流**

![会议室订阅和邮件发布方案。](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "会议室订阅和邮件发布方案。")

1.  在持久聊天客户端中，User1 单击 "**加入聊天室**"，单击 "**搜索**"，然后输入一些搜索条件。 持久聊天客户端发送包含 XCCOS **chansrch** （聊天室搜索）命令的 SIP 信息消息以及搜索条件。 持久聊天服务器查询后端数据库，并在新的 SIP 信息消息中进行答复，其中包含满足搜索条件的可用聊天室的列表。

2.  User1 选择他/她要加入的聊天室，然后单击“关注此聊天室”****。 持久聊天客户端向持久聊天服务器发送包含 XCCOS **join**命令的 SIP 信息消息和用户选择的聊天室的聊天室 ID。 持久聊天服务器使用包含预配数据的 SIP 信息消息进行答复。

3.  持久聊天客户端向持久聊天服务器发送包含 XCCOS **bccontext** （backchat 上下文）命令的 SIP 信息消息。 持久聊天服务器检索聊天历史记录，并在单独的 SIP 信息消息中将其返回到持久聊天客户端。 此时，用户进入聊天室并准备好参与。

4.  User1 输入新消息，然后单击“发送”****。 持久聊天客户端将邮件发送到 SIP INFO XCCOS **grpchat**命令中的聊天室。 持久聊天服务器将此新邮件的副本存储在持久聊天后端数据库中。

5.  持久聊天服务器将 SIP 信息 XCCOS **grpchat**邮件的单独副本发送给使用商，他们已经进入聊天室。

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>持久聊天合规性呼叫流

持久聊天服务器使用消息队列（也称为 MSMQ）和其他合规性数据库（mgccomp）来处理合规性数据。 作为合规性事件处理方式的示例，以下事件顺序说明了如何处理消息发布事件。

1.  用户向聊天室发布消息。

2.  持久聊天服务器将与事件相关的信息放在专用 "消息队列" 队列中。

3.  持久聊天合规性服务器从队列中读取此事件，并将其放入 mgccomp 数据库以供以后处理。

4.  持久聊天合规性服务器会定期处理数据库中的一组事件，并将其发送到持久聊天合规性适配器以进行处理。

5.  如果适配器成功处理数据，则持久聊天合规性服务器将从 mgccomp 数据库中删除事件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

