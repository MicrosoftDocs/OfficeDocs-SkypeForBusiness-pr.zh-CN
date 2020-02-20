---
title: Lync Server 2013 服务器角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2166d6fb3f7f5c8c159c150cd9a0eff07e8fe0de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Lync Server 2013 中的服务器角色

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

运行 Lync Server 的每台服务器都运行一个或多个*服务器角色*。 服务器角色是由该服务器提供的一组已定义的 Lync Server 功能。 无需在网络中部署所有可用服务器角色。 只安装包含您想要的功能的服务器角色。

即使您不熟悉 Lync Server 中的服务器角色，规划工具也可以根据您所需的功能，为您提供针对您需要部署的服务器的最佳解决方案。 本节简要概述了服务器角色及其提供的常规功能：

  - Standard Edition Server

  - 前端服务器和后端服务器

  - 边缘服务器

  - 中介服务器

  - 控制器

  - 持久聊天前端服务器

  - 持久聊天存储（持久聊天后端服务器）

  - 持久聊天合规性存储（持久聊天合规性后端服务器）

对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“池”**。 池中的每台服务器必须运行一个或多个相同的服务器角色。 对于 Lync Server 中的大多数类型的池，您必须部署负载平衡器，以在池中的各个服务器之间传播流量。 Lync Server 支持域名系统（DNS）负载平衡和硬件负载平衡器。

<div>

## <a name="standard-edition-server"></a>Standard Edition Server

Standard Edition Server 是为小型组织以及大型组织的试验项目而设计的。 它启用了 Lync Server 的许多功能，包括所需的数据库，以在单台服务器上运行。 这使您能够以更低的成本实现 Lync Server 功能，但不提供真正的高可用性解决方案。

通过 Standard Edition server，可以使用即时消息（IM）、状态、会议和企业语音，所有运行在一台服务器上。

对于高可用性解决方案，请使用 Lync Server Enterprise Edition。

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>前端服务器和后端服务器

在 Lync Server Enterprise Edition 中，前端服务器是核心服务器角色，并运行许多基本的 Lync Server 功能。 前端服务器和后端服务器是在任何 Lync Server Enterprise Edition 部署中唯一需要的服务器角色。

“前端池”** 是一组配置相同的前端服务器，其协同工作为公用组用户提供服务。由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。

前端服务器包括以下功能：

  - 用户身份验证和注册

  - 状态信息和联系人卡片交换

  - 通讯簿服务和通讯组列表扩展

  - IM 功能，包括多方 IM 会议

  - Web 会议、PSTN 电话拨入式会议和 A/V 会议（如果部署）

  - 应用程序托管，适用于 Lync Server 附带的应用程序（例如，会议助理和响应组应用程序）和第三方应用程序

  - （可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。 此信息提供有关为企业语音呼叫和 A/V 会议遍历网络的媒体质量（音频和视频）的指标。

  - 用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。

  - （可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。 有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。
    
    在 Lync Server 2010 和早期版本中，监视和存档是独立的服务器角色，而不是前端服务器上的并置。

  - （可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。

前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。

此外，部署中的一个前端池还运行*中央管理服务器*，该服务器管理基本配置数据并将其部署到运行 Lync Server 的所有服务器。 中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。

后端服务器是运行 Microsoft SQL Server 的数据库服务器，可为前端池提供数据库服务。 后端服务器既可用作池的用户和会议数据的备份存储，又可用作其他数据库（如响应组数据库）的主存储。 可以拥有一台后端服务器，但建议使用 SQL Server 镜像的解决方案进行故障转移。 后端服务器不运行任何 Lync Server 软件。

<div>


> [!IMPORTANT]  
> 我们不建议将并置 Lync Server 数据库与其他数据库一起使用。 如果您这样做，可能会影响可用性和性能。



</div>

存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。

</div>

<div>

## <a name="edge-server"></a>边缘服务器

边缘服务器使您的用户能够与组织的防火墙之外的用户进行通信和协作。 这些外部用户可以包括当前在异地工作的组织自己的用户、来自联盟合作伙伴组织的用户以及已被邀请加入托管在 Lync Server 部署中的会议的外部用户。 边缘服务器还支持与公共 IM 连接服务（包括 Windows Live、AOL、Yahoo\!和 Google 谈话）的连接。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
> <LI>
> <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>



</div>

部署边缘服务器还将启用移动服务，此服务支持移动设备上的 Lync 功能。 用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。 此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。 移动功能还支持针对不支持在后台运行的应用程序的移动设备的*推送通知*。 推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。

边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。 您可以配置这些 XMPP 组件以使 Lync Server 2013 用户能够添加来自基于 XMPP 的合作伙伴（如 Google 谈话）的联系人，以实现即时消息和状态。

有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

</div>

<div>

## <a name="mediation-server"></a>中介服务器

中介服务器是实施企业语音和电话拨入式会议所必需的组件。 中介服务器转换信号，在某些配置中，在内部 Lync Server 基础结构和公共交换电话网络（PSTN）网关、ip-pbx 或会话初始协议（SIP）中继之间的媒体。 您可以运行在前端服务器所在的服务器上并置的中介服务器，也可以运行分隔到单独的中介服务器池中的中介服务器。

有关详细信息，请参阅规划文档中的 "[在 Lync server 2013 中中介服务器组件](lync-server-2013-mediation-server-component.md)"。

</div>

<div>

## <a name="director"></a>控制器

控制器可以对 Lync Server 用户请求进行身份验证，但他们不会在家用户帐户或提供状态或会议服务。 控制器对于增强支持外部用户访问的部署中的安全性最有用。 控制器可在将请求发送到内部服务器之前对请求进行身份验证。 对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。 有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 Director 方案](lync-server-2013-scenarios-for-the-director.md)。

</div>

<div>

## <a name="persistent-chat-server-roles"></a>持久聊天服务器角色

利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。

运行 Lync Server Standard Edition 的服务器也可以在同一台服务器上运行持久聊天并置。 您不能并置持久聊天前端服务器与 Enterprise Edition 前端服务器。

有关详细信息，请参阅[在 Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)  


[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)  
[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 中的控制器方案](lync-server-2013-scenarios-for-the-director.md)  
[在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

