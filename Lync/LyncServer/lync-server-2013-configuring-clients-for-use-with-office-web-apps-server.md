---
title: Lync Server 2013：配置用于 Office Web Apps 服务器的客户端
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
ms.openlocfilehash: fb4b9b881d0f7d469c924a0ba032071092bddbbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>配置 Lync Server 2013 客户端以与 Office Web Apps 服务器配合使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-25_

如果你希望用户体验 Office Web App 服务器的完整功能，则应将这些用户升级到 Microsoft Lync 2013;只有 Lync 2013 的用户才能像滚动浏览 PowerPoint 幻灯片，而不是在实际的 PowerPoint 演示文稿中执行此操作。 （也就是说，这些用户可以随时查看演示文稿中的任何幻灯片，而无需任何方式干扰实际演示文稿。）未使用 Lync 2013 的用户仍可以加入联机会议和查看 PowerPoint 演示文稿;但是，他们无法单独滚动浏览幻灯片，也不能查看幻灯片切换效果或查看嵌入的视频。

请注意，Lync 2013 的用户将始终可以使用这些功能;即使 PowerPoint 演示者运行的是 Microsoft Lync 2010，也是如此。 如果 PowerPoint 演示文稿由运行 Lync 2010 的用户托管，则 Lync Server 2013 将与 Office Web Apps 服务器协调，以确保 Lync 2013 用户将查看该演示文稿的 Office Web Apps 服务器版本。 对于运行 Lync 2013 以外的客户端的用户，Office Web Apps 服务器不提供 PowerPoint 服务。 相反，这些用户连接到会议服务器服务并以与在 Microsoft Lync Server 2010 中相同的方式查看 PowerPoint 演示文稿。 这还意味着，这些用户将只能访问 Lync Server 2010 提供的更有限的功能。

虽然 Office Web Apps 服务器（而不是升级到 Lync 2013 的用户）不需要任何客户端配置，但建议会议参与者升级到 Internet Explorer 9。 尽管可以使用 Internet Explorer 8 访问会议，但使用该 Web 浏览器有一些限制。 例如，Internet Explorer 8 的用户将无法将 PowerPoint 阶段的大小调整为自定义大小;而是仅限于使用三个预定义的阶段大小之一。 同样，Internet Explorer 8 用户将不能播放媒体文件。

</div>

<span> </span>

</div>

</div>

</div>

