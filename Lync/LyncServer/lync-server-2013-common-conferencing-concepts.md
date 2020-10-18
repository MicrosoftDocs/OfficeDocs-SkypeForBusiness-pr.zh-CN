---
title: Lync Server 2013：常见会议概念
description: Lync Server 2013：常见的会议概念。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2eeea52070c65a8a037eb44e75ceb2d937b91a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577008"
---
# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Lync Server 2013 中的常见会议概念

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-19_

有几个概念对所有类型的会议是通用的。这些概念将在以下章节中进行介绍。

<div>

## <a name="policies-and-bandwidth-management"></a>策略和带宽管理

Lync Server 2013 使管理员能够为用户可组织的会议类型设置策略。 这有助于实施组织的策略和控制带宽使用情况。 您可以定义各种会议策略，并将其分配给各个用户和用户组。 还可以设置用于管理对等对话的策略。 有关设置会议策略的详细信息，请参阅操作文档中的 [Lync Server 2013 中的会议策略](lync-server-2013-conferencing-policies.md) 。 有关带宽管理的详细信息，请参阅 [Lync server 2013 中的呼叫允许控制概述](lync-server-2013-overview-of-call-admission-control.md) 和 [在 lync Server 2013 中配置视频带宽](lync-server-2013-configuring-video-bandwidth.md)。

</div>

<div>

## <a name="archiving-and-compliance-features"></a>存档与合规性功能

如果您的组织必须遵循合规性管理法规，Lync Server 2013 提供了您可以使用的功能。 您可以使用存档功能存档会议中呈现的内容，以及即时消息 (IM) 对话和 IM 会议内容。 有关详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md) 。 您可以使用持久聊天服务器的合规性功能存档基于主题的多方持续对话。 有关详细信息，请参阅规划文档中的在 [Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md) 。

</div>

<div>

## <a name="monitoring-feature"></a>监控功能

监视服务器功能可以 (Cdr) 中捕获呼叫详细信息记录，您可以使用它来跟踪哪些用户与使用 Lync Server 2013 的其他用户通信。 有关部署和配置监控的详细信息，请参阅 [在 Lync Server 2013 中部署监控](lync-server-2013-deploying-monitoring.md)。

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>允许外部参加会议

您可以通过让外部用户也在受邀时加入会议，从而大大提高您的投资在 Lync Server 2013 会议中的优势。 外部用户可能包括：

  - **远程用户**    在防火墙外工作并使用其便携式计算机或其他 Lync Server 2013 设备时，您的组织自己的用户。

  - **联合用户**    与其他人合作的公司用户也运行 Lync Server 2013。 若要使您的用户能够轻松地与这些用户联系，您可以创建与这些公司的联盟关系。

  - **匿名用户**    您的用户专门邀请其加入特定会议的任何其他外部用户。 公司中的会议组织者可以向外部用户发送会议的电子邮件邀请。 该电子邮件包含外部用户可单击以加入会议的链接。

若要启用任何或所有这些方案，需要部署边缘服务器以帮助启用 Lync Server 2013 部署和外部用户之间的安全通信。 使用边缘服务器的 Lync Server 2013 解决方案比其他解决方案（如虚拟专用网络 (VPN) ）提供了更高的质量的媒体。 有关详细信息，请参阅 [在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。

此外，无论是否部署边缘服务器，用户（即，组织内部或外部）都可以通过标准 PSTN 电话拨入以加入内部音频会议。 这是通过部署 Lync Server 2013 电话拨入式会议来实现的。

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>会议类型和客户端版本之间的兼容性

如果您将 Lync Server 2013 与 Office 通信服务器及其客户端的早期版本进行互操作，则必须注意以下问题：

  - 使用 Lync Server 2013 的用户无法安排 Live Meeting 会议，也无法修改此类型的任何已迁移的会议。

  - 使用 Lync Server 2013 的用户需要参加运行 Office 通信服务器 2007 R2 的服务器上的 Live Meeting 会议的用户必须在其计算机上安装 Live 会议客户端 (除了 Lync Server 2013) 之外，还可以参加这些会议。

  - 当 Live Meeting 会议迁移到 Lync Server 2013 时，会议内容不会迁移。 如果需要此内容，则必须重新上载。

</div>

</div>

<span> </span>

</div>

</div>

</div>

