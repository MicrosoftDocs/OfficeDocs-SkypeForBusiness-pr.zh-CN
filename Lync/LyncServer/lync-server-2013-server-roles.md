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
ms.openlocfilehash: b22115bf137c388fd6cd15103ac882056affa4f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a>Lync Server 2013 中的服务器角色

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-10-07_

运行 Lync 服务器的每台服务器都运行一个或多个*服务器角色*。 服务器角色是由该服务器提供的一组已定义的 Lync Server 功能。 您无需在您的网络中部署所有可用的服务器角色。 只安装包含您想要的功能的服务器角色。

即使你不熟悉 Lync Server 中的服务器角色，规划工具也可以根据你所需的功能为你提供针对你需要部署的服务器的最佳解决方案。 本部分简要概述了服务器角色及其提供的常规功能：

  - Standard Edition Server

  - 前端服务器和后端服务器

  - 边缘服务器

  - 中介服务器

  - 控制器

  - 持久聊天前端服务器

  - 持久聊天应用商店（持久的聊天后端服务器）

  - 持久聊天合规性存储（持久聊天合规性后端服务器）

对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“*池*”。 池中的每台服务器必须运行一个或多个相同的服务器角色。 对于 Lync Server 中的大多数类型的池，必须部署负载平衡器以在池中的各种服务器之间传播流量。 Lync Server 支持域名系统（DNS）负载平衡和硬件负载平衡器。

<div>

## <a name="standard-edition-server"></a>Standard Edition Server

标准版服务器专为小型组织设计，适用于大型组织的试点项目。 它支持 Lync 服务器的许多功能，包括必要的数据库，以在单个服务器上运行。 这使你能够以更低的成本获得 Lync Server 功能，但不提供真正的高可用性解决方案。

标准版服务器使您能够使用即时消息（IM）、状态、会议和企业语音，所有这些都运行在一台服务器上。

对于高可用性解决方案，请使用 Lync Server 企业版。

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a>前端服务器和后端服务器

在 Lync Server 企业版中，前端服务器是核心服务器角色，并且运行许多基本的 Lync 服务器功能。 前端服务器和后端服务器是在任何 Lync Server 企业版部署中唯一需要的服务器角色。

*前端池*是一组前端服务器（配置相同），它们协同工作以为一组常见用户提供服务。 由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。

前端服务器包括以下内容：

  - 用户身份验证和注册

  - 状态信息和联系人卡片交换

  - 通讯簿服务和通讯组列表展开

  - IM 功能，包括多方 IM 会议

  - 网络会议、PSTN 电话拨入式会议和 A/V 会议（如果已部署）

  - 应用程序托管，适用于 Lync Server 附带的两个应用程序（例如，会议助理和响应组应用程序）和第三方应用程序

  - （可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。 此信息提供有关媒体质量（音频和视频）对您的网络进行企业语音通话和 A/V 会议的标准的衡量指标。

  - 用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。

  - （可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。 有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。
    
    在 Lync Server 2010 和早期版本中，监视和存档是独立的服务器角色，而不是前端服务器上的 collocated。

  - （可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。

前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。

此外，部署中的一个前端池还运行*中央管理服务器*，该服务器管理和部署对运行 Lync Server 的所有服务器的基本配置数据。 中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。

后端服务器是运行 Microsoft SQL Server 的数据库服务器，它为前端池提供数据库服务。 后端服务器既可用作池的用户和会议数据的备份存储，又可用作其他数据库（如响应组数据库）的主存储。 你可以使用一台后端服务器，但建议使用 SQL Server 镜像的解决方案进行故障转移。 后端服务器不运行任何 Lync Server 软件。

<div>


> [!IMPORTANT]  
> 我们不建议将 Lync Server 数据库与其他数据库 collocating。 如果您这样做，可能会影响可用性和性能。



</div>

存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。

</div>

<div>

## <a name="edge-server"></a>边缘服务器

边缘服务器使用户能够与组织防火墙外的用户进行通信和协作。 这些外部用户可以包括组织的自己的用户，这些用户当前正在进行异地工作、来自联盟合作伙伴组织的用户以及已被邀请加入在 Lync Server 部署上的会议的外部用户。 边缘服务器还支持与公共 IM 连接服务（包括 Windows Live、AOL、Yahoo\!和 Google 通话）的连接。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo！进行联盟 Messenger，直到服务关闭日期。 AOL 和 Yahoo！的有效期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</P>
> <LI>
> <P>Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>



</div>

部署边缘服务器还支持移动服务，这些服务支持移动设备上的 Lync 功能。 用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。 此外，移动设备支持某些企业语音功能，例如单击加入会议、通过工作、单号码达到、语音邮件和未接来电进行呼叫。 移动功能还支持针对不支持在后台运行的应用程序的移动设备的*推送通知*。 推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。

边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。 你可以配置这些 XMPP 组件以使 Lync Server 2013 用户能够添加来自基于 XMPP 的合作伙伴（如 Google 谈话）的联系人，以便发送即时消息和状态。

有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

</div>

<div>

## <a name="mediation-server"></a>中介服务器

中介服务器是实现企业语音和电话拨入式会议所必需的组件。 中介服务器转换信号，在某些配置中，你的内部 Lync 服务器基础结构和公共交换电话网络（PSTN）网关、IP PBX 或会话初始协议（SIP）干线之间的媒体。 你可以在前端服务器所在的同一台服务器上运行中介服务器 collocated，或将其分到独立的中介服务器池中。

有关详细信息，请参阅规划文档中的[Lync server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)。

</div>

<div>

## <a name="director"></a>控制器

控制器可以对 Lync Server 用户请求进行身份验证，但它们不是家庭用户帐户或提供状态或会议服务。 控制器对于增强支持外部用户访问的部署中的安全性最有用。 控制器可在将请求发送到内部服务器之前对请求进行身份验证。 对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。 有关详细信息，请参阅规划文档中[Lync Server 2013 中的 Director 的方案](lync-server-2013-scenarios-for-the-director.md)。

</div>

<div>

## <a name="persistent-chat-server-roles"></a>持久聊天服务器角色

利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。

运行 Lync Server 标准版的服务器也可以在同一台服务器上运行永久聊天 collocated。 不能将持久聊天前端服务器 collocate 到企业版前端服务器。

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

