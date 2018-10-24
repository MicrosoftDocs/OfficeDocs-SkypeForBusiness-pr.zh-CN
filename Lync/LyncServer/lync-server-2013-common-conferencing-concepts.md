---
title: Lync Server 2013 中的公用会议概念
TOCTitle: Lync Server 2013 中的公用会议概念
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49888541
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的公用会议概念

 

_**上一次修改主题：** 2012-09-19_

有几个概念对所有类型的会议是通用的。这些概念将在以下章节中进行介绍。

## 策略和带宽管理

通过 Lync Server 2013，管理员能够对用户可组织的会议类型设置策略。这有助于实施组织的策略和控制带宽使用情况。您可以定义各种会议策略，并将其分配给各个用户和用户组。还可以设置用于管理对等对话的策略。有关设置会议策略的详细信息，请参阅操作文档中的[会议策略](lync-server-2013-conferencing-policies.md)。有关宽带管理的详细信息，请参阅[Lync Server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md)和[在 Lync Server 2013 中配置视频带宽](lync-server-2013-configuring-video-bandwidth.md)。

## 存档与合规性功能

如果您的组织必须遵守合规性要求，Lync Server 2013 可以提供所需功能。您可以使用存档功能存档会议中呈现的内容，以及即时消息 (IM) 对话和 IM 会议内容。有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。您可以使用持久聊天服务器的合规性功能存档基于主题的多方持续对话。有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。

## 监控功能

监控服务器功能可以捕获呼叫详细记录 (CDR)，通过这些记录，您可以使用 Lync Server 2013 跟踪哪些用户在与其他哪些用户交谈。有关部署和配置监控的详细信息，请参阅[部署监控](lync-server-2013-deploying-monitoring.md)。

## 允许外部参加会议

通过允许外部用户在受邀时也能参加会议，可大大提高在 Lync Server 2013 会议方面的投资收益。外部用户可能包括：

  - **远程用户**   在防火墙外工作并使用其便携式计算机或其他 Lync Server 2013 设备的组织的内部用户。

  - **联盟用户** 来自合作公司同时也运行 Lync Server 2013 的用户。要使用户轻松与这些用户联系，应与这些公司建立联盟关系。

  - **匿名用户** 用户专门邀请其加入特定会议的任何其他外部用户。公司的会议组织者可以向外部用户发送电子邮件以邀请他们参加会议。该电子邮件包含一个链接，外部用户通过单击该链接即可加入会议。

要实现任意或所有这些方案，需要部署边缘服务器以帮助启用 Lync Server 2013 部署和外部用户之间的安全通信。使用边缘服务器的 Lync Server 2013 解决方案比其他解决方案（如虚拟专用网络 (VPN)）提供的媒体质量更高。有关详细信息，请参阅[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

此外，无论是否部署边缘服务器，用户（即，组织内部或外部）都可以通过标准 PSTN 电话拨入以加入内部音频会议。这是通过部署 Lync Server 2013 电话拨入式会议来实现的。

## 会议类型和客户端版本之间的兼容性

如果打算让 Lync Server 2013 与早期版本的 Office Communications Server 及其客户端进行互操作，则必须注意以下问题：

  - 使用 Lync Server 2013 的用户无法安排 Live Meeting 会议，也无法修改任何此类迁移会议。

  - 使用 Lync Server 2013 的用户除了在其计算机上安装 Lync Server 2013 外还必须安装 Live Meeting 客户端，才能参加驻留在运行 Office Communications Server 2007 R2 的服务器上的Live Meeting 会议。

  - 将 Live Meeting 会议迁移到 Lync Server 2013 时，不会迁移会议内容。如果需要此内容，则必须重新上载。

