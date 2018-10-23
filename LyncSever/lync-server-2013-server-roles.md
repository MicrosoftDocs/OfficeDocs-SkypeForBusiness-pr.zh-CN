---
title: Lync Server 2013 服务器角色
TOCTitle: 服务器角色
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398536(v=OCS.15)
ms:contentKeyID: 49313211
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的服务器角色

 

_**上一次修改主题：** 2013-10-07_

运行 Lync Server 的每台服务器可运行一个或多个“服务器角色”。服务器角色是由该服务器提供的一组已定义的 Lync Server 功能。无需在网络中部署所有可用服务器角色。只安装包含您想要的功能的服务器角色。

即使不熟悉 Lync Server 中的服务器角色， 规划工具也可基于您想要的功能引导您为需要部署的服务器找到最佳解决方案。本节简要概述了服务器角色及其提供的常规功能：

  - Standard Edition Server

  - 前端服务器和后端服务器

  - 边缘服务器

  - 中介服务器

  - 控制器

  - 持久聊天前端服务器

  - 持久聊天存储（持久聊天后端服务器）

  - 持久聊天合规性存储（持久聊天合规性后端服务器）

对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“池”。池中的每台服务器必须运行一个或多个相同的服务器角色。对于 Lync Server 中大多数类型的池，必须部署负载平衡器以分散池中各服务器之间的流量。Lync Server 支持域名系统 (DNS) 负载平衡和硬件负载平衡器。

## Standard Edition Server

Standard Edition Server 是为小型组织以及大型组织的试验项目而设计的。它使 Lync Server 的许多功能（包括所需数据库）可在一台服务器上运行。这样可使 Lync Server 功能的成本更低，但不提供实际的高可用性解决方案。

通过 Standard Edition Server，您可以使即时消息 (IM)、状态、会议和 企业语音等全部在一台服务器上运行。

要获取高可用性解决方案，请使用 Lync Server Enterprise Edition。

## 前端服务器和后端服务器

在 Lync Server Enterprise Edition 中，前端服务器是核心服务器角色，可运行许多 Lync Server 基本功能。前端服务器和后端服务器是任何 Lync Server Enterprise Edition 部署中需要的唯一的服务器角色。

“前端池”是一组配置相同的前端服务器，其协同工作为公用组用户提供服务。由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。

前端服务器包括以下功能：

  - 用户身份验证和注册

  - 状态信息和联系人卡片交换

  - 通讯簿服务和通讯组列表扩展

  - IM 功能，包括多方 IM 会议

  - Web 会议、PSTN 电话拨入式会议和 A/V 会议（如果部署）

  - 用于 Lync Server 附带的应用程序（例如会议助理和 响应组应用程序）以及第三方应用程序的应用程序托管

  - （可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。这些信息可提供 企业语音呼叫和 A/V 会议中遍历网络的媒体（音频和视频）质量的指标。

  - 用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。

  - （可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。
    
    在 Lync Server 2010 及早期版本中，监控和存档是两个不同的服务器角色，且未并置在前端服务器上。

  - （可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。

前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。

此外，部署中的一个前端池还运行 *中央管理服务器* ，该服务器管理基本配置数据并将其部署到所有运行 Lync Server 的服务器。 中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。

后端服务器是运行 Microsoft SQL Server 的数据库服务器，旨在为前端池提供数据库服务。后端服务器既可用作池的用户和会议数据的备份存储，又可用作其他数据库（如响应组数据库）的主存储。您可以只有一台后端服务器，但建议将一个使用 SQL Server 镜像的解决方案用于故障转移。后端服务器不运行任何 Lync Server 软件。

> [!IMPORTANT]
> 建议不要将 Lync Server 数据库与其他数据库并置。如果您这样做，可能会影响可用性和性能。


存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。

## 边缘服务器

通过使用边缘服务器，您的用户可与组织防火墙外的用户通信和协作。这些外部用户可包括当前在组织外工作的组织内部用户、来自联盟伙伴组织的用户和已受邀加入 Lync Server 部署承载的会议的外部用户。边缘服务器还对公共 IM 连接服务（包括 Windows Live、AOL、Yahoo\! 和 Google Talk）启用连接。

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
> <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
> </ul>


部署边缘服务器还将启用移动服务，此服务支持移动设备上的 Lync 功能。用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。移动功能还支持针对不支持在后台运行的应用程序的移动设备的*推送通知*。推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。

边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。您可以配置这些 XMPP 组件以使您的 Lync Server 2013 用户能够添加来自基于 XMPP 的合作伙伴（如 Google Talk）的联系人以获得即时消息和状态。

有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

## 中介服务器

中介服务器是实现 企业语音和电话拨入式会议的必需组件。中介服务器用于在内部 Lync Server 基础结构和公用电话交换网 (PSTN) 网关、IP-PBX 或会话初始协议 (SIP) 中继之间转换信号和媒体（在某些配置中）。您可以运行在前端服务器所在的服务器上并置的中介服务器，也可以运行分隔到单独的中介服务器池中的中介服务器。

有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)。

## 控制器

控制器可对 Lync Server 用户请求进行身份验证，但它们不驻留用户帐户，也不提供状态或会议服务。控制器对于增强支持外部用户访问的部署中的安全性最有用。控制器可在将请求发送到内部服务器之前对请求进行身份验证。对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的控制器方案](lync-server-2013-scenarios-for-the-director.md)。

## 持久聊天服务器角色

利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。

运行 Lync Server标准版 的服务器还可运行在同一服务器上并置的持久聊天。您无法将持久聊天前端服务器与 企业版前端服务器并置。

有关详细信息，请参阅 [在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

## 另请参阅

#### 概念

[Lync Server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)  

#### 其他资源

[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)  
[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 中的控制器方案](lync-server-2013-scenarios-for-the-director.md)  
[在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)

