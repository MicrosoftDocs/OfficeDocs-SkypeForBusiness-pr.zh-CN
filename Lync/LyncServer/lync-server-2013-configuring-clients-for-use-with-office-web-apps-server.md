---
title: Lync Server 2013：配置客户端以用于 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf46a16d38e37dd8faac39a438053dcc7b8c103
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537059"
---
# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>配置用于 Office Web Apps Server 的 Lync Server 2013 客户端

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-25_

如果您希望用户体验 Office Web App Server 的全部功能，则应将这些用户升级到 Microsoft Lync 2013;只有 Lync 2013 的用户才能通过独立于实际 PowerPoint 演示文稿的 PowerPoint 幻灯片进行滚动来执行此操作。  (也就是说，这些用户可以随时查看演示文稿中的任何幻灯片，而无需干预实际演示文稿。 ) 未使用 Lync 2013 的用户仍可以加入联机会议并查看 PowerPoint 演示文稿。但是，它们不能独立滚动幻灯片，也不能查看幻灯片切换或查看嵌入的视频。

请注意，Lync 2013 的用户将始终可以使用这些功能。即使 PowerPoint 演示者运行的是 Microsoft Lync 2010，也是如此。 如果 PowerPoint 演示文稿由运行 Lync 2010 的用户托管，则 Lync Server 2013 将与 Office Web Apps Server 进行协调，以确保 Lync 2013 用户将查看该演示文稿的 Office Web Apps Server 版本。 Office Web Apps Server 不会为运行 Lync 2013 之外的客户端的用户提供 PowerPoint 服务。 相反，这些用户连接到会议服务器服务并以与在 Microsoft Lync Server 2010 中相同的方式查看 PowerPoint 演示文稿。 这也意味着这些用户将只能访问 Lync Server 2010 提供的更有限的功能。

尽管 Office Web Apps Server (不需要客户端配置，而不是将用户升级到 Lync 2013) ，但建议会议与会者升级到 Internet Explorer 9。 尽管可使用 Internet Explorer 8 访问会议，但对使用 Web 浏览器有一些限制。 例如，Internet Explorer 8 的用户无法将 PowerPoint 阶段的大小重新调整为自定义大小；而是将其限制为使用三个预定义阶段大小之一。 Internet Explorer 8 用户将很有可能无法播放媒体文件。

</div>

<span> </span>

</div>

</div>

</div>

